---
title: "Glossing pipeline"
author: "Niko Partanen"
date: "23 Sep 2014"
---

## Background

We have been discussing in our team several times that we would need additional glosses into our ELAN files. In yesterday's meeting it was decided that we try to implement Giellatekno's FST tools to our data. The goal is to have a command line pipeline which runs all needed XML transformations and FST. We have gathered here all the notes that are relevant for our work and for the thinking process that lead us to the point we are now.

There have been several advanced pipelines to manage interaction between ELAN and FLEX. However, this seems to be double-edged blade as FLEX also has lots of its own problems one has to deal with. For later data analysis we would like to have all annotations in our ELAN XML files. At the moment ELAN files contain two metadata items, which are the file name that corresponds with the session name. Each tier is also assigned with participant ID, which in turn matches with the data we have in our metadata database about individual participants.

The main advantage of doing glossing with FST technology is that a large amount of data can be processed fast.

There are several steps:

- Exporting word tokens from ELAN
- Running FST into words
- Bringing glosses to ELAN

All the examples here assume that you are running terminal from the highest level, in this case you should sit in the directory "data". In our case the folder "lang" would be actually a local GitHub repository, so the whole team can work with the files simultaneously.

    |-data
     -saxon9he.jar
    |lang
    -eaf2gloss.xsl
      |-dial1
        -story1.eaf
        -story2.eaf
      |-dial2
        -story3.eaf
        -story4.eaf
      |-dial3
        -story5.eaf
        -story6.eaf

We are using Saxon to transform our XSLT. Usually we develope the stylesheets in oXygen, but once we want to have the work at command line we have found Saxon Java application to be a good alternative. Well, it's the same Saxon more or less that's baked into oXygen as well. From "data" folder it is possible to run a command:

    java -jar saxon9he.jar izma/kpv_lit/kpv_lit.eaf izma/eaf2xml.xsl -o:test1

    java -jar saxon9he.jar izma/kpv_lit/kpv_lit19570000lytkin.eaf izma/eaf2gloss.xsl | hfst-lookup ~niko/GT/main/langs/kpv/src/analyser-gt-norm.hfst > izma_kpv_lit/kpv_lit19570000lytkin_test.txt > test2.txt
    
    java -jar saxon9he.jar izma/kpv_lit/kpv_lit19570000lytkin.eaf izma/eaf2gloss.xsl -o:list
    cat list | hfst-lookup ~niko/GT/main/langs/kpv/src/analyser-gt-norm.hfst > test3.txt


## Tools

### FST

Basically the FST requires the following file structures, as an example

     |-main
     |-hfst3
     |-forrest

The main folder contains relevant GiellaTekno infrastructure and hfst3 contains the newest transducers. It is important to keep updating these regularly as the files evolve. This means that we also have to compile the analysator itself from the source code each time we want to use improved version from it.

Many things also rely on Macports, so running:

    sudo port selfupdate
    sudo port upgrade outdated

Which updates them.

This has to be done time to time in hfst3-folder to update the HFST3 infrastructure:

    svn up
    ./autogen.sh

    ./configure --without-foma --with-unicode-handler=glib --enable-all-tools \
            CXXFLAGS=" -stdlib=libstdc++" LDFLAGS=" -stdlib=libstdc++"
    make clean
    ./scripts/generate-cc-files.sh
    make
    sudo make install


    ./configure --without-foma --with-unicode-handler=glib --enable-all-tools \
            CXXFLAGS=" -stdlib=libstdc++" LDFLAGS=" -stdlib=libstdc++"

Good to notice that I get errors:


    configure: WARNING: hfst-train-tagger and hfst-tag are not enabled; you will not be able to train and use taggers; enable using --enable-tagger
    configure: WARNING: hfst-calculate is not enabled; you will not be able to compile SFST-PL scripts; enable using --enable-calculate
    configure: WARNING: hfst-xfst is not enabled; you will not be able to compile XFST scripts; enable using --enable-xfst

This has to be remembered in the next step. So to get the actual Komi HFST work we need this:

    svn up
    cd langs/kpv/
    ./autogen.sh -l
    ./configure --with-hfst --enable-spellers
    make
    sudo make install

So at first we update the whole main folder. After that we move into folder that contains Komi files. There is a lot there, but it makes sense after looking to src folder. There are, as an example, dictionaries in XML format and list of affixes in another format. All this is used to build a morphological analysator, which is done with the other commands.