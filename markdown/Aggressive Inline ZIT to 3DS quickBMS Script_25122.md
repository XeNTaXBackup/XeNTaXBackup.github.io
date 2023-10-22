## Post #1
- Username: Jamaicano
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Dec 06, 2015 11:52 pm
- Post datetime: 2022-03-06T22:20:09+00:00
- Post Title: Aggressive Inline ZIT to 3DS quickBMS Script

Hi my good friends of Hacking!
This week i tried obtain Agressive Inline SKATERS models;

I found a script quickBMS  for extract .ZIT (skaters) files to .3DS, the (skaters) folder founded in XBOX classic game version. 
This working perfect and extract to 3DS and i import to blender export again and open in 3DS max.
Now is the problem. When i apply the textures this is wrong. The model don't have the UV coords correctly   . 
In my idea when we extract ZIT to 3DS this lost UV's. The correct is export the models .ZIT in a .OBJ format for preserve the UV's coords ??

Wat i do for correct it? Have a method to correct this?
[agressiveskater.jpg](https://xentaxbackup.github.io/file/21893_agressiveskater.jpg)
## Post #2
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2022-03-07T00:36:56+00:00
- Post Title: Aggressive Inline ZIT to 3DS quickBMS Script

Probably the script you are using doesn't support UVs, you will need another script to extract with the uvs
Post some example .ZIT files so we can analyze them
## Post #3
- Username: Jamaicano
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Dec 06, 2015 11:52 pm
- Post datetime: 2022-03-07T05:19:43+00:00
- Post Title: Aggressive Inline ZIT to 3DS quickBMS Script

> Reply from reh ↑Mon Mar 07, 2022 8:36 am at Mon Mar 07, 2022 8:36 am
>
> 
Probably the script you are using doesn't support UVs, you will need another script to extract with the uvs
Post some example .ZIT files so we can analyze them

Thanks for helping friend. I put all skaters .ZIT files on mega for download.

The AGRUB folder is unique with textures.

https://mega.nz/file/1DZSlByK#k3fW5xYkt ... g38Oe-figw

Not is possible modify the BMS script to add UV's coords for extract correct the characters models? I don't know about scripting make. My speciality is Riggind and Modelling in 3DSMAX!
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-03-07T08:01:46+00:00
- Post Title: Aggressive Inline ZIT to 3DS quickBMS Script

> Reply from Jamaicano ↑Mon Mar 07, 2022 1:19 pm at Mon Mar 07, 2022 1:19 pm
>
> Not is possible modify the BMS script to add UV's coords for extract correct the characters models?You missed to add a link to said script.
## Post #5
- Username: Jamaicano
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Dec 06, 2015 11:52 pm
- Post datetime: 2022-03-07T13:12:13+00:00
- Post Title: Aggressive Inline ZIT to 3DS quickBMS Script

> Reply from shakotay2 ↑Mon Mar 07, 2022 4:01 pm at Mon Mar 07, 2022 4:01 pm
>
> 
Jamaicano wrote: ↑Mon Mar 07, 2022 1:19 pmNot is possible modify the BMS script to add UV's coords for extract correct the characters models?You missed to add a link to said script.

Hi friend. Thanks a lot for response. I put Script BMS in mega.
Download it here: https://mega.nz/file/taA0mZ4Y#uSibvOcgq ... sR0forpYDs
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-03-07T16:30:03+00:00
- Post Title: Aggressive Inline ZIT to 3DS quickBMS Script

I see, those nonsense variables, tigertiger, dragondragon  
.



Pirate_point_cloud.png (156.09 KiB) Viewed 147 times


(Trying to rebuild it using hex2obj.)

Well, with hex2obj it is rotated by 90 degrees. Used the face indices provided by the bms script, btw, too lazy to check them.
May care for uvs, when I have more time.
## Post #7
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2022-03-08T05:59:04+00:00
- Post Title: Aggressive Inline ZIT to 3DS quickBMS Script

I believe it would be possible to edit the bms script to support UVs but I don't know how to do that and I would also have to ask the script's author for permission. It looks like there are some DXT3 textures at the beginning of the files.
If you search for TGVU you will find the UVs and before the UVs there are the normal ones, search for TGVN to find them.



GOR.ZIT.png (47.43 KiB) Viewed 135 times
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-03-08T09:19:45+00:00
- Post Title: Aggressive Inline ZIT to 3DS quickBMS Script

> Reply from reh ↑Tue Mar 08, 2022 1:59 pm at Tue Mar 08, 2022 1:59 pm
>
> 
I believe it would be possible to edit the bms script to support UVsWhy would you do that when you solved it with hex2obj?  

Indeed  there's code in the bms script to handle uvs:
Math uvbase += tigertigertigerface ;

but I had no nerves to deal again with nonsense variables to find out what goes wrong with uvs there.

Plus, quickbms is great when it comes to archives, (de)compression, textures and what not.

But I'd never use it for extracting 3D models. Just my 2 cents.
Better try my Make_obj project (using C) or a Noesis script for such.

btw, you should have mentioned TGFM to find start of face indices
TGVU, TGFM: iirc you were using py code for searching patterns in MUA files, didn't you?
## Post #9
- Username: Jamaicano
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Dec 06, 2015 11:52 pm
- Post datetime: 2022-03-08T14:15:41+00:00
- Post Title: Aggressive Inline ZIT to 3DS quickBMS Script

> Reply from reh ↑Tue Mar 08, 2022 1:59 pm at Tue Mar 08, 2022 1:59 pm
>
> 
I believe it would be possible to edit the bms script to support UVs but I don't know how to do that and I would also have to ask the script's author for permission. It looks like there are some DXT3 textures at the beginning of the files.
If you search for TGVU you will find the UVs and before the UVs there are the normal ones, search for TGVN to find them.
GOR.ZIT.png

Can you tell me the method you used to correct the UV'S using hex2obj?
I don't understand hex code language and another code language . I only work with modeling...
## Post #10
- Username: Jamaicano
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Dec 06, 2015 11:52 pm
- Post datetime: 2022-03-08T14:16:36+00:00
- Post Title: Aggressive Inline ZIT to 3DS quickBMS Script

> Reply from shakotay2 ↑Tue Mar 08, 2022 5:19 pm at Tue Mar 08, 2022 5:19 pm
>
> 
reh wrote: ↑Tue Mar 08, 2022 1:59 pm
I believe it would be possible to edit the bms script to support UVs Why would you do that when you solved it with hex2obj?  

Indeed  there's code in the bms script to handle uvs:
Math uvbase += tigertigertigerface ;

but I had no nerves to deal again with nonsense variables to find out what goes wrong with uvs there.

Plus, quickbms is great when it comes to archives, (de)compression, textures and what not.

But I'd never use it for extracting 3D models. Just my 2 cents.
Better try my Make_obj project (using C) or a Noesis script for such.

btw, you should have mentioned TGFM to find start of face indices
TGVU, TGFM: iirc you were using py code for searching patterns in MUA files, didn't you?

Thanks to try help me solving this problem dear
## Post #11
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-08T14:45:44+00:00
- Post Title: Aggressive Inline ZIT to 3DS quickBMS Script

> Reply from Jamaicano ↑Mon Mar 07, 2022 6:20 am at Mon Mar 07, 2022 6:20 am
>
> 
The correct is export the models .ZIT in a .OBJ format for preserve the UV's coords ??

[fmt_zit.zip](https://xentaxbackup.github.io/file/21904_fmt_zit.zip)
## Post #12
- Username: Jamaicano
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Dec 06, 2015 11:52 pm
- Post datetime: 2022-03-08T15:16:54+00:00
- Post Title: Aggressive Inline ZIT to 3DS quickBMS Script

> Reply from Durik256 ↑Tue Mar 08, 2022 10:45 pm at Tue Mar 08, 2022 10:45 pm
>
> 
 

Jamaicano wrote: ↑Mon Mar 07, 2022 6:20 am
The correct is export the models .ZIT in a .OBJ format for preserve the UV's coords ??

You do a magic!!! How you make it friend? This is a NOESIS script?
## Post #13
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2022-03-09T01:51:50+00:00
- Post Title: Aggressive Inline ZIT to 3DS quickBMS Script

> Reply from Jamaicano ↑Tue Mar 08, 2022 11:16 pm at Tue Mar 08, 2022 11:16 pm
>
> 
 This is a NOESIS script?
Hello Jamaicano, yep, download noesis from here: [https://richwhitehouse.com/index.php?co ... sv4464.zip](https://richwhitehouse.com/index.php?content=inc_projects.php&filemirror=noesisv4464.zip)
and paste the script into the ../plugins/python/  folder.
## Post #14
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2022-03-14T02:03:23+00:00
- Post Title: Aggressive Inline ZIT to 3DS quickBMS Script

> Reply from shakotay2 ↑Tue Mar 08, 2022 5:19 pm at Tue Mar 08, 2022 5:19 pm
>
> 
Why would you do that when you solved it with hex2obj?
Just answer the question he asked.

> Reply from shakotay2 ↑Tue Mar 08, 2022 5:19 pm at Tue Mar 08, 2022 5:19 pm
>
> 
btw, you should have mentioned TGFM to find start of face indices TGVU, TGFM:
Really forgot to mention.

> Reply from shakotay2 ↑Tue Mar 08, 2022 5:19 pm at Tue Mar 08, 2022 5:19 pm
>
> 
iirc you were using py code for searching patterns in MUA files, didn't you?
Yes, I would rely on that code to get some results, luckily Durik256 has already solved it.
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-03-14T10:28:04+00:00
- Post Title: Aggressive Inline ZIT to 3DS quickBMS Script

> Reply from reh ↑Mon Mar 14, 2022 10:03 am at Mon Mar 14, 2022 10:03 am
>
> 
shakotay2 wrote: ↑Tue Mar 08, 2022 5:19 pm
Why would you do that when you solved it with hex2obj? 

Just answer the question he asked.No. I will never answer any question about "TigerTiger" bms scripts. Feel free to answer yourself.
## Post #16
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2022-03-14T15:13:25+00:00
- Post Title: Re: Aggressive Inline ZIT to 3DS quickBMS Script

> Reply from shakotay2 ↑Mon Mar 14, 2022 6:28 pm at Mon Mar 14, 2022 6:28 pm
>
> 
No. I will never answer any question about "TigerTiger" bms scripts. Feel free to answer yourself.
Sorry, I think I expressed myself badly. I didn't want you to answer that question, I was just answering the question the Jamaicano asked.
English is not my native language.
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-03-14T18:07:32+00:00
- Post Title: Re: Aggressive Inline ZIT to 3DS quickBMS Script

yeah, I see.  

Nethertheless, again, I think it really does make no sense to patch that TigerTiger bms script to handle uvs
if you already understood the ZIT format using hex2obj.

For me it wood make more sense to create a Noesis script then.
