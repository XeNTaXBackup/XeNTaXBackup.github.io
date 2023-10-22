## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-07-03T21:11:42+00:00
- Post Title: Ratchet & Clank: A Crack in Time Animation Tool

A tool for previewing/exporting animations from the PS3 game Ratchet & Clank Future: A Crack in Time. Some animations may not work atm. Root motion is there, but it is applied on a separate bone that is not part of the skinned bones. The root skinned bone should be parented to this root motion bone, so that the model moves properly. This is how it's done by the game, not something I choose to do.

Some example animations





How to use

0) Get the game files
1) Extract the level psarc you want
2) Drag and drop the assetlookup file on Insomniac Engine AllExtractor: [https://lukascone.wordpress.com/2017/12 ... extractor/](https://lukascone.wordpress.com/2017/12/03/insomniac-engine-allextractor/)
3) Animated models are extracted to moby folder. Load the model (irb) in Noesis using the included script
4) Export it to NUX
5) Load NUX in RCCITViewer
6) Load the matching animation file in animsets folder. Read below for finding the correct animation file
7) Export the animation to NUX
8 ) You can load the exported file in Noesis and convert it to any format you want

Note: Animations usually work fine with default translation factor. However, some models, like Qwark, need a higher factor. If the model looks weird/broken increase the factor.

Download :  [https://www.mediafire.com/file/g1fazyx2 ... 1.rar/file](https://www.mediafire.com/file/g1fazyx2sud0tpk/RCCITViewer_U1.rar/file)

Finding the correct animation file

I have included a program called RCCITAnimList. Drag and drop the animsets folder on it. It will create a text file listing all the animations contained in each file. You can understand which file to load based on the animation names.

Credits

- Ghostblade - Noesis script for irb models [viewtopic.php?p=98553#p98553](https://forum.xentax.com/viewtopic.php?p=98553#p98553)
- PredatorCZ - Insomniac Engine AllExtractor
## Post #2
- Username: DarthphoeniX
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Nov 06, 2015 11:10 pm
- Post datetime: 2021-07-04T21:43:46+00:00
- Post Title: Ratchet & Clank: A Crack in Time Animation Tool

thanks! how can it be extracted the level psarc?
## Post #3
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-07-05T06:57:57+00:00
- Post Title: Ratchet & Clank: A Crack in Time Animation Tool

> Reply from DarthphoeniX ↑Mon Jul 05, 2021 5:43 am at Mon Jul 05, 2021 5:43 am
>
> 
thanks! how can it be extracted the level psarc?

I have used "PS3 Game Extractor" which should work with no problem. Maybe you can also try Noesis or bms scripts for psarc.
## Post #4
- Username: DarthphoeniX
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Nov 06, 2015 11:10 pm
- Post datetime: 2021-07-05T17:34:30+00:00
- Post Title: Ratchet & Clank: A Crack in Time Animation Tool

Thanks! works fine!
## Post #5
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2021-07-07T15:27:25+00:00
- Post Title: Ratchet & Clank: A Crack in Time Animation Tool

The tool also work for R&C next installment "Into the Nexus"! While the previous 2 games seems to use different files management.



Tried with a few models and anims and they seems to work fine. I'm unsure if all animations are "extracted"
Ex: the animlist.txt present itself like this

> 3790508132
>
> 	winged_demon_master
>
> 	IGHW
>
> 	IGHW
>
> 	winged_demon_fly_turn_left_90
>
> 	IGHW
>
> 	IGHW
>
> 	winged_demon_fly_turn_left_180
>
> 	IGHW
>
> 	IGHW
>
> 	winged_demon_swim_forward
>
> 	IGHW
>
> 	IGHW
>
> 	winged_demon_swim_tread_water
>
> 	IGHW
>
> 	IGHW
>
> 	winged_demon_water_death
>
> 	IGHW
>
> 	IGHW
>
> 	winged_demon_fly_hover_hit_react_med
>
> 	IGHW
>
> 	IGHW
>
> ...

The program also visualize them like that ^ 1 animation then 2 IGHW with T-pose.

[Samples](https://www.mediafire.com/file/eh5t5e0033k4va1/Into+the+Nexus.7z/file)
## Post #6
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-07-07T15:45:49+00:00
- Post Title: Ratchet & Clank: A Crack in Time Animation Tool

> Reply from Allanoon ↑Wed Jul 07, 2021 11:27 pm at Wed Jul 07, 2021 11:27 pm
>
> 
The tool also work for R&C next installment "Into the Nexus"!

I was also looking into it  Into the nexus and full frontal assault have a single minor change with animation offsets. I will release an update supporting both of them soon.

I don't really wanna download All 4 One. If you have samples let me know.

> Reply from Allanoon ↑Wed Jul 07, 2021 11:27 pm at Wed Jul 07, 2021 11:27 pm
>
> 
While the previous 2 games seems to use different files management.
I have actually started out with tools of destruction which also has very similar animation format to CiT with small changes. However, I have dropped it since file extraction wasn't as good as later games. If I ever find the time to make a somewhat working extractor for first 2 games, I will add support for them also.
## Post #7
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2021-07-07T18:27:07+00:00
- Post Title: Ratchet & Clank: A Crack in Time Animation Tool

> Reply from akderebur ↑Wed Jul 07, 2021 11:45 pm at Wed Jul 07, 2021 11:45 pm
>
> 
Allanoon wrote: ↑Wed Jul 07, 2021 11:27 pm
The tool also work for R&C next installment "Into the Nexus"! 


I was also looking into it  Into the nexus and full frontal assault have a single minor change with animation offsets. I will release an update supporting both of them soon.

I don't really wanna download All 4 One. If you have samples let me know.
[Here you go](https://www.mediafire.com/file/ua8r3ejz5b1p06s/R&CAll4One.7z/file)  
It's similar to the other 2~

> I have actually started out with tools of destruction which also has very similar animation format to CiT with small changes. However, I have dropped it since file extraction wasn't as good as later games. If I ever find the time to make a somewhat working extractor for first 2 games, I will add support for them also.

I guess things rarely go has expected, at least we have... the better looking ones?
## Post #8
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-07-09T21:10:36+00:00
- Post Title: Ratchet & Clank: A Crack in Time Animation Tool

UPDATE: Into the Nexus, Full Frontal Assault, All 4 One*

ItN and FFA seem to work fine. A4O should technically work too since the format is the same. However, the model weights seemed problematic. So, I haven't tested the animations a lot.

Full Frontal Assault



Into the Nexus



> Reply from Allanoon ↑Thu Jul 08, 2021 2:27 am at Thu Jul 08, 2021 2:27 am
>
> 
I guess things rarely go has expected, at least we have... the better looking ones?
Yep, that is also my reasoning  Currently available stuff should be somewhat enough. I imagine some animations are recycled between these games anyway.
