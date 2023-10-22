## Post #1
- Username: jamiros
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Feb 15, 2016 5:18 am
- Post datetime: 2016-02-15T07:57:50+00:00
- Post Title: Disney Infinity 2.0 HUD texture replacement

I would like to ask smart people here about some help.

I need to replace the radar textures with same textures but totally transparent, so in fact the radar will stay in game but will be absolutely invisible. I tried to replace those ".tbody" files with empty (incl. alpha-channel) DDS file created in Photoshop with Nvidia Tools plug-in, however in this case after replace even only 1 texture the rest of interface is missed or I got the game freeze...
I'm just graphic designer and not familiar with all this game-dev specific file types, etc, and not sure that I'm moving the right way, so any help or idea where to dig will be greatly appreciated!


[radar.zip](https://xentaxbackup.github.io/file/10493_radar.zip)
## Post #2
- Username: jamiros
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Feb 15, 2016 5:18 am
- Post datetime: 2016-03-14T18:15:34+00:00
- Post Title: Disney Infinity 2.0 HUD texture replacement

Any ideas?

Or if there is any difficulties with textures replacment in this game, then I'll probably need a person who will help me to get ride this HUD completely, and I'm ready to pay for that help.
## Post #3
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2016-03-14T18:44:29+00:00
- Post Title: Disney Infinity 2.0 HUD texture replacement

From what I see they are stndards DDS with headers. GFX is SWF file editable in Flash application. You must only change magic GFX to FWS.
And at textures change extension .tbody to .dds. Edit them a rename back to .tbody.

Yeah and forgot about paying for this. It's nothing hard... I can do that for you if you not understand.
## Post #4
- Username: jamiros
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Feb 15, 2016 5:18 am
- Post datetime: 2016-03-14T19:40:26+00:00
- Post Title: Disney Infinity 2.0 HUD texture replacement

Thank you very much for your reply!
I'm not sure I understand this part 
> You must only change magic GFX to FWS. - I'm not sure what the ".FWS" extention is,  but the rest is pretty clear to me, and I tried already to rename the "radar.gfx" to "radar.swf" and then open that file in Flash, however nothing really happened on timeline and preview window, and Flash library was still empty. (Also tried to import that radar.swf instead of opening, but got this message: "One or more files were not imported because there were problems reading them").
If you can help me with it, that would be really awesome, because I've spent already two days trying to solve this problem with no result and I'm still would like to pay for it (at least for couple of beer) as thanks for your time, expertise and good will to help.
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-03-14T19:44:46+00:00
- Post Title: Disney Infinity 2.0 HUD texture replacement

You might not need to mess with anything but the textures. after you rename them from tbody to dds you should be able to open it in Photoshop and paint the alpha channel black and save as dxt5 with no mip maps then copy the 128 byte header from the original over the edited one and rename back to tbody and you should be good.
## Post #6
- Username: jamiros
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Feb 15, 2016 5:18 am
- Post datetime: 2016-03-14T20:08:00+00:00
- Post Title: Disney Infinity 2.0 HUD texture replacement

Ok, I'm going to try it right now, thank you!

And sorry for a couple of lame questions (please see attach. screenshot)
1) should I paint black completely only the alpha channel and leave the rest of channels as is?
2) about 128 byte header, I have to use this part, right?

Thanks again!
[1-2.png](https://xentaxbackup.github.io/file/10590_1-2.png)
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-03-14T20:17:17+00:00
- Post Title: Disney Infinity 2.0 HUD texture replacement

Your number 1 image looks ok, but you have too many bytes selected in the number 2 image, the hexadecimal length will be 80, which is the first 8 rows of bytes.
## Post #8
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2016-03-14T21:15:17+00:00
- Post Title: Disney Infinity 2.0 HUD texture replacement

> Reply from jamiros
>
> Thank you very much for your reply!
I'm not sure I understand this part You must only change magic GFX to FWS. - I'm not sure what the ".FWS" extention is,  but the rest is pretty clear to me, and I tried already to rename the "radar.gfx" to "radar.swf" and then open that file in Flash, however nothing really happened on timeline and preview window, and Flash library was still empty. (Also tried to import that radar.swf instead of opening, but got this message: "One or more files were not imported because there were problems reading them").
If you can help me with it, that would be really awesome, because I've spent already two days trying to solve this problem with no result and I'm still would like to pay for it (at least for couple of beer) as thanks for your time, expertise and good will to help.

Open GFX file in hex and change GFX header "magic" to FWS and save as SWF. There can be even compressed SWF, header is CFX so change it to CWS.

EDiT: This game has crc check of files, when you replace original zip with modiffied, game after launch re-download new one. Even if you change only one byte in original.
## Post #9
- Username: jamiros
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Feb 15, 2016 5:18 am
- Post datetime: 2016-03-15T07:17:26+00:00
- Post Title: Disney Infinity 2.0 HUD texture replacement

> EDiT: This game has crc check of files, when you replace original zip with modiffied, game after launch re-download new one. Even if you change only one byte in original
Yeah thanks I noticed that, so I put "read only" on zip-file I currently work with. Btw, is that possible to turn off that crc-check somehow?

Ok, I successfully renamed the header with FWS and open it with Flash, and there I just found some red squares in it and then deleted them.
After that I replaced the original file with updated one (also changed back the GFX header, etc). but when I open game now - almost all interface is missed (radar, character's avatar, etc) which is not bad actually,  but in same time the rest of interface doesn't work at all either, nothing happens when press ESC button or when trying to change weapons, etc... just nothing, but I still can play with a character though, jump, run, etc.

I also tried just modify the textures by AceWell's method (thank you again , however, got the same result as described few lines before - even if only one texture is modified, all radar is missed completely along with few other parts of HUD, and nothing else works... OMG this problem turns into a huge quest for me... :-\
