---
title: "Recording through audio interfaces"
---

Some weeks ago I watched a documentary film made by Tim Laman and Ed Scholes. It was about the birds of paradise. The topic was of course interesting, though of course not very directly related to what I work with. Or so I thought. After sawing the way they shot video I realized that there is something to dive more into. Many things in their setup reminded the tools we use: similar recorders, similar DSLR cameras, but the need to shoot birds from distance creates also many differences. Maybe some of the approaches they have tested could give something for us too? Perhaps linguists have something to learn from the ornithologists.

It is evident that we linguists are not the only scientists working with audio and video, yet I think there is not very much methodological exchange across the discipline boundaries. Though I think the hardware side we use is increasingly similar, and maybe even in software there are some parallel trends? However, now I take a small look into the software.

Our common set-up is more or less as described below:

I wrote earlier about the possibility of using R-26 recorder as an audio interface at computer. In this post I summarise in more detail where that ended up. Little bit about my own background -- I've been carrying out linguistic fieldwork regularly in last five years, usually using Roland recorders, mainly R-09. I've been cutting the files in Audacity whenever that has been necessary, after which I've been annotating them in ELAN. I've developed quite effective and nice workflow with these tools, but I have usually had only one audio track for each recording session. This may consist of several files, if, as an example, the batteries were changed in the middle of the session, but there is always only one layer of audio track for any given point in time during the session.

This is different now when we have started to have multiple recorders and high quality video. The video camera we use records already in itself six channel surround sound. This adds a new post production phase between recording and annotating files. I think this will have a large impact into technical infrastructure we need to master in order to work effectively with our data. I try to cover regularly different things which I've ended up to learn more about. Many of these will be dead ends, though some probably find their way into our future workflow.

This exploration to new tools was strongly stimulated by the documentary made by Tim Laman and Ed Scholes. Their set-up included cameras hanging high in the trees, and apparently one of them was most of the time controlling things from the ground. I think they had more traditional set-up for audio, but it got me thinking that the way biologists record at the field is not necessarily so far away from what the linguists do.

## Problems with the current set-up

I think the way we record our sessions now is good and advanced. However, I think there are some problems too. First of all, I think we have a problem when we set everything up and turn recording on, after which we have a large amount of technical tools running with their fast emptying batteries. We can hope everything runs as expected, but there is always a small feeling that we are not in charge of every detail. Maybe this is just me, but I guess there vmust be ways to monitor better and more automatically that the system is running.

## Non-portable recording

When we take a look into non-portable recorders we must ask what does it mean that a system is portable or that it is not? Is it about the size or weight? I guess the independency from external electricity sources is something that defines portability in many cases. However, the line is slippery here. All portable devices can be charged while they are used, and I think many times when we have the possibility we connect them into external electricity anyway just to make it more reliable.

Apparently the idea in normal non-portable recording is that instead of having a recorder you have an audio interface which is between your computer and devices like microphones. It is not recording anything itself, but it takes care of the audio signal and gives access to level controls. These interfaces look like one below, that is called [EIE pro](http://www.akaipro.com/product/eiepro) from AKAI.

![Eie PRO audio Interface](/medias/images/eie_pro.png)
My caption...{:.figcaption}

## Audio interfaces and DAWs

It seems that audio interface tools require a particular set of programs to do the actual recording. These are called Digital Audio Workstations, DAW. There are many alternatives and they tend to be **very** expensive. As an example, Pro Tools seems to cost easily 500 euros, and alternatives are not much better. I Would assume that free programs like Audacity work well too, but there seems to be some real difference in high quality professional tools and free software available at the moment. Of The fact is that as linguists we are audio professionals and in some sense we must use the current industry standard. Our recordings can be of no less quality than that at other fields where recording is a normal procedure.

After taking a look to the different programs I found one called Cockos Reaper. It seems to newer than many more established alternatives, but it seems to be used in more professional setting. And I like a lot their philosophy in which it is possible to download fully functional version for evaluation. I'm not sure, but it seems a bit it maybe works even after the 60 days trial has ended. We will see. However, the full version was well below 100 euros which makes it even realistic to buy if it seems to be useful.

## Audio interface in fieldwork

I think it could be an improvement if the multi-channel recording flow could be monitored from computer instead of each device being monitored independently from their own small screens. If all incoming audio could be summarised and visualised into my MacBook screen it could be much easier to see what is actually being recorded and what are the levels. I think that with this kind of setup it could also be possible to change the output that goes to your headphones from one mic to another. This way we would have absolute control over what we are recording. However, there are few requirements I see.

- USB-powered or independent
- Small enough
- Enough XLR inputs
- Does it record both to the recorder and computer at the same time?

The last two points are actually quite crucial. The number of XLR inputs limits how many microphones we can have in. Then I think it would be ideal to have data automatically both at the computer and at the SD-card. This way SD-card would never needed to be touched, but it would always contain backups from everything.

One possibility would be to have a cable like this from recorder in a good location to the laptop aside from the actual scene. The cable can be bought from [Amazon](http://www.amazon.com/Tether-Tools-Mini-B-Plated-High-Visibility/dp/B00827MK3S/ref=pd_bxgy_p_text_y), an an example. It costs 36 dollars, but only 10 if you don't want it in fancy orange colour.

![test](/medias/images/USB-5pin.jpg)
<center>Tether Tools Pro 15' USB 2.0 A Male to Mini-B 5 Pin Gold Plated Cable</center>

With a cable like this we could control our recording from 4,5 metres away.  For many situations that's probably long enough. Naturally laptop cannot just be anywhere, as its location should not influence any other decisions in whole set-up. Luckily there are [places from where](http://www.tabelz.com/sp135m-macbook-pro-air-mac-laptop-stand.html) it is possible to buy laptop stands for tripods.



![test2](/medias/images/laptop-platform.jpg)
<center>Tabelz laptop stand, fits into a normal tripod</center>

Naturally for field situations we may need more battery life than MacBook normally has. Just out of curiosity I'll be taking look into the world of solar panels, as they are developing pretty fast right now. However, to actually integrate laptop into our fieldwork procedure we don't really need so much more for electricity than a good and long extension cord.

## Testing the set-up

## Recording into Reaper

## Impressions and comments

## Next steps

This maybe goes too far, but it would be interesting to know whether someone has been using tethered video cameras in fieldwork. Tethered means that the camera is being monitored and controlled from distance, as an example, with a cable or wirelessly from a laptop.

## References

Picture source: "Astrapia splendidissima 1895" by John Gerrard Keulemans - Novitates Zoologicae, vol. 2. Licensed under Public domain via [Wikimedia Commons](http://commons.wikimedia.org/wiki/File:Astrapia_splendidissima_1895.jpg)
