## Post #1
- Username: ramyosama
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 04, 2022 8:38 am
- Post datetime: 2022-11-04T00:56:49+00:00
- Post Title: Hollow Knight android Localization

Hi guys, I am new in the field of localization.  I want to ask a question: How can I find the subtitle file for Hollow Knight on Android?

The game is powered by Unity 5 engine 
The translation file is inside resources.assets, but the problem is that the file format in the apk is resources.resource, similar to the first file, but I can never open !

My question now is:
1:How can I decrypt resources.resource
2:How can I decrypt data.unity3d
3:What tools should be used ?

Finally, I will post some screenshots
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-11-04T21:34:51+00:00
- Post Title: Hollow Knight android Localization

> 1:How can I decrypt resources.resource
>
> 2:How can I decrypt data.unity3d
>
> 3:What tools should be used ?

Answer to all 3 questions is here [http://wiki.xentax.com/index.php/List_of_Unity_Tools](http://wiki.xentax.com/index.php/List_of_Unity_Tools)
Just download some tools from this list and try to extract/import data.


You can find more detailed articled below:
[http://wiki.xentax.com/index.php/Unity_Assets](http://wiki.xentax.com/index.php/Unity_Assets)
[http://wiki.xentax.com/index.php/Unity_Unity3d_UnityFS](http://wiki.xentax.com/index.php/Unity_Unity3d_UnityFS)
[https://grajpopolsku.pl/forum/viewtopic.php?f=75&t=2295](https://grajpopolsku.pl/forum/viewtopic.php?f=75&t=2295)


Edit: I almost forgot about this one 
[https://ikskoks.pl/searching-text-strin ... commander/](https://ikskoks.pl/searching-text-strings-using-total-commander/)
## Post #3
- Username: ramyosama
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 04, 2022 8:38 am
- Post datetime: 2022-11-04T23:47:45+00:00
- Post Title: Hollow Knight android Localization

I thank my brother for this wonderful help, it will really help me ❤

  But, excuse my ignorance, I have some questions. When I searched a little, I found that there is a script that decodes files with the extension (.resource), which is
 (dump_fsbs.bms)

Is this really the tool that will decrypt or is there another tool ?

One last question. If I did not bother you, I did not find any explanation of how to decompile the file (data.unity3d) ?

If you can just give me some hints I will be very thankful to you
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-11-05T01:45:10+00:00
- Post Title: Hollow Knight android Localization

> Is this really the tool that will decrypt or is there another tool ?
dump_fsbs.bms is a script for dumping audio data (FSB files) from Unity assets.
For more general use, you would need some assets extractor like UnityEx.

> I did not find any explanation of how to decompile the file (data.unity3d) ?
unity3d is a UnityFS file which is asset format introduced in more recent games.
You don't need to decompile, you only need to extract/import data from it.
You could also use UnityEx or any other tool listed on the wiki which is capable of exporting and importing data.


Please also read the articles I've linked earlier. Everything is explained there...
