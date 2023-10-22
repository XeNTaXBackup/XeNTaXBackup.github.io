## Post #1
- Username: Ginsor
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Nov 23, 2017 5:46 pm
- Post datetime: 2017-11-23T11:01:03+00:00
- Post Title: Texture Analysis

Hi guys,

id like to ask for some help/advice.
I managed to extract a game archiv (without any correct filenames or file extension [everything is just a .bin file]). Now i am - file by file - trying to find out what it is. I think i found a texture file with texturefinder 2.1 but somehow it seem that its not shown correctly. 

Any advice what i am doing wrong to show that texture in a proper way? I tried all options from texturefinder.

Thanks for you help!

[game file](https://mega.nz/#!ZDAURByS!5hWyL3ZNK13aAOx_TETV1qaM-Xox4CyT4A2LJRLFvMc)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-11-23T12:38:10+00:00
- Post Title: Texture Analysis

daemon1's "Raw texture cooker" can convert it as 512x512 BC7 (bc7_unorm)   
you can open and convert the attached dxt10 dds further in Noesis


[019C-2.zip](https://xentaxbackup.github.io/file/13582_019C-2.zip)
## Post #3
- Username: Ginsor
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Nov 23, 2017 5:46 pm
- Post datetime: 2017-11-23T14:55:01+00:00
- Post Title: Texture Analysis

> Reply from AceWell
>
> daemon1's "Raw texture cooker" can convert it as 512x512 BC7 (bc7_unorm)   
you can open and convert the attached dxt10 dds further in Noesis

awesome! great, thanks for your quick help! can open your file in noesis perfectly 

one more thing tho: where can i find that "raw texture cooker" or what do you mean by that? haha
when i google it, i dont find anything lol
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-11-23T15:13:22+00:00
- Post Title: Texture Analysis

you can find his program here   
[viewtopic.php?f=18&t=16461](http://forum.xentax.com/viewtopic.php?f=18&t=16461)
## Post #5
- Username: Ginsor
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Nov 23, 2017 5:46 pm
- Post datetime: 2017-11-23T15:20:35+00:00
- Post Title: Texture Analysis

> Reply from AceWell
>
> you can find his program here   
viewtopic.php?f=18&t=16461

haha...i should better search here, than on google! thanks a lot

how did you manage to find out it is BC7 and 512x512? The preview doesnt seem to work if i click on those settings (converting works tho)

edit: nevermind..preview works now haha. thanks again
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-11-23T15:51:37+00:00
- Post Title: Texture Analysis

> Reply from Ginsor
>
> how did you manage to find out it is BC7 and 512x512?
the sample was headerless, so trial and error is only way my friend
