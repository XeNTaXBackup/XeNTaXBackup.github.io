## Post #1
- Username: ekardon
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jun 27, 2015 10:32 am
- Post datetime: 2016-07-24T11:16:35+00:00
- Post Title: How to open/edit the files that extracted with quickBMS?

Hi,
I am trying to extract some files from unity based android game. It had the split assets files, and I have managed to merge and extract them with QuickBMS. All the file extension I got as follows:

*.1, *.-1, *.-2, *.-3, *.4, *.-4, *.-5, *.-6, *.-7, *.-8, *.-9, *.-10, *.-11, *.-12, *.-13, *.-14, *.-15, *.-16, *.-17, *.-18, *.-19, *.-20, *.23, *.33,, *.43, *.49, *.82, *.89, *.111, *.137, *.198, *.200, *.bin, *.fsb, *.ani, *.mat, *.script, *.shader, *.tex

Well, I am not familiar with these extensions. I was expecting to see some *.ogg or *.ttf files. Seems like I am out of luck here. It would be really nice if somebody would tell, what types are these extensions are, and how to open/edit etc.

Thanks
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-24T12:08:38+00:00
- Post Title: How to open/edit the files that extracted with quickBMS?

i know *.43 are models and *.tex are the textures and *.fsb are usually audio files and *.ani are likely animation files, i never really looked into most of the others.  

there is a Noesis script on this page by finale00 to open .43 models
[http://himeworks.com/noesis-plugins/](http://himeworks.com/noesis-plugins/)

the textures could be any number of texture formats, its easier to just have these converted on extraction by one of the many Unity tools floating around.
[http://zenhax.com/viewtopic.php?f=9&t=12](http://zenhax.com/viewtopic.php?f=9&t=12)
[https://7daystodie.com/forums/showthrea ... -Extractor](https://7daystodie.com/forums/showthread.php?22675-Unity-Assets-Bundle-Extractor)
[http://www.zoneofgames.ru/forum/index.p ... opic=36240](http://www.zoneofgames.ru/forum/index.php?showtopic=36240)

for the fsb files you probably need an extractor of some sort, but audio is not my area, maybe try these?
[https://github.com/gdawg/fsbext](https://github.com/gdawg/fsbext)
[http://zenhax.com/viewtopic.php?f=17&t=1901](http://zenhax.com/viewtopic.php?f=17&t=1901)
[http://aezay.dk/aezay/fsbextractor/](http://aezay.dk/aezay/fsbextractor/)
## Post #3
- Username: ekardon
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jun 27, 2015 10:32 am
- Post datetime: 2016-07-24T21:07:43+00:00
- Post Title: How to open/edit the files that extracted with quickBMS?

Wow, thanks man  

I was able to check some of the tools that you suggested. So, here is the results;

I have tried all of these 3, but none got job done. Only first one gives some file playable *.wav files, but those are just random noises. I was unable to extract the main track. Second one didn't even open and third one was giving me error when try to open a file. 

> Reply from AceWell
>
> for the fsb files you probably need an extractor of some sort, but audio is not my area, maybe try these?
https://github.com/gdawg/fsbext
http://zenhax.com/viewtopic.php?f=17&t=1901
http://aezay.dk/aezay/fsbextractor/
I was able get more tools thanks to first link. I am not really interested in textures, so I have tried Grim's Unity Asset Editor and Unity Studio to look inside of asset bundles. Now, I am able to see all content inside of the maindata and assets. I was able to extract text and font files, that made me really happy, idk why 

> Reply from AceWell
>
> the textures could be any number of texture formats, its easier to just have these converted on extraction by one of the many Unity tools floating around.
http://zenhax.com/viewtopic.php?f=9&t=12
https://7daystodie.com/forums/showthrea ... -Extractor
http://www.zoneofgames.ru/forum/index.p ... opic=36240
I haven't checked out the *.43 tool yet. I'll look when I have the time.

I have one more question now, as I said above I was able to get text files, but how can I edit and import it back? 

Thanks
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-25T14:30:31+00:00
- Post Title: How to open/edit the files that extracted with quickBMS?

modding is not my area but i believe this tool is designed to inject modified files back into the resource files
[https://7daystodie.com/forums/showthrea ... -Extractor](https://7daystodie.com/forums/showthread.php?22675-Unity-Assets-Bundle-Extractor)
