## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-15T23:47:11+00:00
- Post Title: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

UPDATE

I was able to finish my tool, thanks to AceWell figuring out the encryption key. Now it can load the skeleton too. Also it seems to work fine with Onmyoji and Crusaders of Light too, at least for the mobile versions.

Here is a preview of the program.



Load your file/folder from the "File" menu. Select the model from the list. Export it as OBJ or IQE (skinned). 
How to open/convert IQE: [viewtopic.php?p=138153#p138153](http://forum.xentax.com/viewtopic.php?p=138153#p138153)

For getting the textures read the posts below.

Viewer/b] http://www.mediafire.com/file/m6d90s8j6 ... A_Upd3.rar

F7C File Extractor/b] http://www.mediafire.com/file/z0pyyy6kn ... ractor.rar

Example exported model:
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-04-16T02:20:54+00:00
- Post Title: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from akderebur
>
> I have absolutely no idea for the textures. I put some random files that aren't related to model/skeleton in the "other" folder. They might be the textures but I am not sure.
yeah they're textures, but they have some light encryption i think, at least in the 128 byte header. 
unfortunately encryption is not my area outside of simple xoring so i don't know any more to say.
## Post #3
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-16T08:08:48+00:00
- Post Title: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from AceWell
>
> 
they have some light encryption i think, at least in the 128 byte header.
I see, that actually makes sense. I wasn't able to find anything useful in the character headers, so that would explain it.

Thanks for taking a look, at least I know which files to focus on now. Encryption isn't my forte either, but I will give it a try.

Edit : 

I guess I won't go much further with the encryption. It might be easier trying to get the textures manually, without the header info. I tried using the TextureFinder, but wasn't fully successful.

It looks like something if I select block compression, but couldn't get the texture properly. Any idea what the image/pixel format might be?
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-04-16T14:11:36+00:00
- Post Title: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

being from a mobile game is a good chance they're using some type of mobile compression,
you can open the raw data in PVRTextool and test various formats. 

edit
now i see this byte pattern in the encrypted headers and it is looking like xor based on the results  

```
8A 8B 8C 8D 8E 8F 90 91 92 93 94 95 96 97 98 99 
9A 9B 9C 9D 9E 9F A0 A1 A2 A3 A4 A5 A6 A7 A8 A9
AA AB AC AD AE AF B0 B1 B2 B3 B4 B5 B6 B7 B8 B9 
BA BB BC BD BE BF C0 C1 C2 C3 C4 C5 C6 C7 C8 C9 
CA CB CC CD CE CF D0 D1 D2 D3 D4 D5 D6 D7 D8 D9 
DA DB DC DD DE DF E0 E1 E2 E3 E4 E5 E6 E7 E8 E9 
EA EB EC ED EE EF F0 F1 F2 F3 F4 F5 F6 F7 F8 F9
```


using that key reveals a ktx format header and first 4 rows of image data

```
00 00 00 00 01 00 00 00 00 00 00 00 78 92 00 00
08 19 00 00 00 04 00 00 00 04 00 00 00 00 00 00
00 00 00 00 01 00 00 00 01 00 00 00 00 00 00 00
00 00 10 00 FF 00 00 00 00 00 00 00 0D 57 B7 62
EE 00 EE 00 FF 00 00 00 00 00 00 00 0D 57 B7 62
EE EE EE EE FF 00 00 00 00 00 00 00 0D 57 B7 62
EE EE EE EE FF 00 00 00 00 00 00 00 0D 57 B7 62
```


bms script to fix the samples

```

get SIZE asize
get NAME basename
string NAME + .ktx
math SIZE - 0x80
filexor "\x7A\x7B\x7C\x7D\x7E\x7F\x80\x81\x82\x83\x84\x85\x86\x87\x88\x89\x8A\x8B\x8C\x8D\x8E\x8F\x90\x91\x92\x93\x94\x95\x96\x97\x98\x99\x9A\x9B\x9C\x9D\x9E\x9F\xA0\xA1\xA2\xA3\xA4\xA5\xA6\xA7\xA8\xA9\xAA\xAB\xAC\xAD\xAE\xAF\xB0\xB1\xB2\xB3\xB4\xB5\xB6\xB7\xB8\xB9\xBA\xBB\xBC\xBD\xBE\xBF\xC0\xC1\xC2\xC3\xC4\xC5\xC6\xC7\xC8\xC9\xCA\xCB\xCC\xCD\xCE\xCF\xD0\xD1\xD2\xD3\xD4\xD5\xD6\xD7\xD8\xD9\xDA\xDB\xDC\xDD\xDE\xDF\xE0\xE1\xE2\xE3\xE4\xE5\xE6\xE7\xE8\xE9\xEA\xEB\xEC\xED\xEE\xEF\xF0\xF1\xF2\xF3\xF4\xF5\xF6\xF7\xF8\xF9"
log NAME 0x0 0x80
append
filexor ""
log NAME 0x80 SIZE
```


00000372.ktx opened and converted to png with "Mali Texture Compression Tool"  



00000372.png (101.85 KiB) Viewed 3441 times


the original size is actually 1024x1024 i just scaled it down to fit under the max attachment size.
## Post #5
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-16T14:45:09+00:00
- Post Title: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Incredible! Thank you very much. I just need to get the skeleton now.
## Post #6
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-18T00:05:06+00:00
- Post Title: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

I am done with the tool, and updated my original post. Thank you again AceWell, that encryption key was really necessary for getting the skeleton.

I hope double post is okay in this situation. I wanted to bump, since it is an update
## Post #7
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2018-04-20T12:43:24+00:00
- Post Title: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Thanks. I was able to get the models with no problems.

I'm kinda wondering where are the textures? Which NPK are they located?
And... are they in a different format or they are in .dat as well?
## Post #8
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-21T13:24:45+00:00
- Post Title: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from lolwatt
>
> 
I'm kinda wondering where are the textures? Which NPK are they located?
And... are they in a different format or they are in .dat as well?
They are also inside the character.npk. From what I see they also have the extension ".dat". Still lot of the files seem to have that extension, so it is best to check them inside a hex editor.

My tool scans the files and finds the ones related to models, then it decrypts the header if necessary. It has no support for textures, so you would need to use AceWell's script for them. They will be proper ktx files after that and you can open them with Mali Texture Compression Tool.

Since there are no file names, I imagine it would be hell trying to find which texture file is the one matching the model. I don't know if there is any other way than doing it manually.
## Post #9
- Username: goliathus18
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Aug 12, 2015 9:49 pm
- Post datetime: 2018-05-17T22:56:51+00:00
- Post Title: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

hi, how do you use this for onmyoji? i really want to extract the model files. thanks a lot. kudos to youuu :>
## Post #10
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-18T09:26:34+00:00
- Post Title: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from goliathus18
>
> how do you use this for onmyoji?
Download the game apk. Find the npk file that has the models. Unpack it into a folder with this quickbms script : [http://aluigi.altervista.org/bms/nxpk.bms](http://aluigi.altervista.org/bms/nxpk.bms)

Then using my tool click File->Open Folder. Select the folder where the files are exported. The tool should find the ones that has model data automatically, and add them to the list.

Edit:

Also only one of the Onmyoji games works (I guess there are two). Probably it was the old one that I tested with. The new one seems to have encryption for the npk archives.
## Post #11
- Username: goliathus18
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Aug 12, 2015 9:49 pm
- Post datetime: 2018-05-19T03:20:17+00:00
- Post Title: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

thank you for the quick reply. hmm. there are 2 onmyoji games. there is onmyoji which is a gacha type game, and onmyoji arena. so you are saying this works with the onmyoji gacha type. then I will try. thank you very much again.
## Post #12
- Username: goliathus18
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Aug 12, 2015 9:49 pm
- Post datetime: 2018-05-21T13:05:23+00:00
- Post Title: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

your program definitely works, thank you soooo much. but I have a slight problem though. I think it's with the unpacking of .dat files, some of the files get extracted but doesn't show the model in your viewer or I can't export it to obj. why is that?
## Post #13
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-21T13:15:28+00:00
- Post Title: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from goliathus18
>
> I think it's with the unpacking of .dat files, some of the files get extracted but doesn't show the model in your viewer or I can't export it to obj. why is that?
It is possible that those dat files aren't model files. They might be textures, or something else. After all there are other stuff than models that make up a game
## Post #14
- Username: goliathus18
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Aug 12, 2015 9:49 pm
- Post datetime: 2018-05-21T13:25:12+00:00
- Post Title: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Oh I see. but I have scraped all the .dat files and I had seen and converted a handful of models. some but not all. I think I made a mistake on the way. I will just redo it to see if it still happens. Thanks for the fast reply. Cheers!
## Post #15
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-05-23T07:49:39+00:00
- Post Title: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

unfortunately IQE doesn't support more than one UV channel
## Post #16
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2018-05-23T11:22:18+00:00
- Post Title: Re: Rebellious Million Arthur Tool + Research

Thanks for your work. 
So are you interested in these two games?

Forever 7th Capital
[http://f7.163.com](http://f7.163.com)

Onmoji Arena
[https://moba.163.com](https://moba.163.com)

I prefer Forever 7th Capital, but few informations about it.
## Post #17
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-23T12:10:57+00:00
- Post Title: Re: Rebellious Million Arthur Tool + Research

The problem is the NPK archive with those games. They are encrypted. If you can somehow unpack the NPKs, I think the tool will work as it is, or maybe with a slight modification.

I was also interested in Forever 7th Capital and asked for help here : [https://zenhax.com/viewtopic.php?t=7740](https://zenhax.com/viewtopic.php?t=7740) . Not much I can do though, since it is encrypted.
## Post #18
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2018-05-24T14:36:03+00:00
- Post Title: Re: Rebellious Million Arthur Tool + Research

Hi, just want to say this tool is awesome! However, is there any chance for Rules Of Survival from NetEase? I've tried to unpack npk and got all files but just a few meshes of characters are able to be extracted.
Hope you can take a look on those files 

Link: [https://www.drive.google.com/open?id=1l ... 05M4NOnQ4C](https://www.drive.google.com/open?id=1lIDJ9hZ9OObX27lC0V3ZRP05M4NOnQ4C)
## Post #19
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-24T15:56:05+00:00
- Post Title: Re: Rebellious Million Arthur Tool + Research

> Reply from onelove1210
>
> However, is there any chance for Rules Of Survival from NetEase? I've tried to unpack npk and got all files but just a few meshes of characters are able to be extracted.
That is my bad. I am mostly interested in character models, so forgot to do the changes required to load the non-skinned meshes  . I updated the tool, you can download it from the first post. It should be able to load the non-skinned meshes now and possibly more character models.

@goliathus18 I think this will also solve your problem with some files not getting loaded.

So RoS seems fine in general. From the weapon samples you uploaded.



Some character models I tried earlier.
## Post #20
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2018-05-25T04:52:55+00:00
- Post Title: Re: Rebellious Million Arthur Tool + Research

> Reply from akderebur
>
> 
I updated the tool, you can download it from the first post. It should be able to load the non-skinned meshes now and possibly more character models.

So RoS seems fine in general. From the weapon samples you uploaded.

Thank you so much for spending time doing my request!  That's kind of you.
P/s: This tool should be renamed to NE Model Viewer Tool instead of one specific game
## Post #21
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2018-06-11T08:44:06+00:00
- Post Title: Re: Rebellious Million Arthur Tool + Research

Awesome
Thank for your tool
Now the only thing I still waiting for is a script to extract NPK files from Onmyoji Arena.
## Post #22
- Username: goliathus18
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Aug 12, 2015 9:49 pm
- Post datetime: 2018-06-11T13:04:27+00:00
- Post Title: Re: Rebellious Million Arthur Tool + Research

thank you very much for making time for our requests, we can't thank you enough. I will try this asap.
## Post #23
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2018-06-14T13:46:21+00:00
- Post Title: Re: Rebellious Million Arthur Tool + Research

How do we get textures from RoS files?
BMS script to get ktx seem not working with this game
## Post #24
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-06-14T16:06:14+00:00
- Post Title: Re: Rebellious Million Arthur Tool + Research

> Reply from ngovandang
>
> 
BMS script to get ktx seem not working with this game
That script xor's the header with a key. It works for RMA, but it will probably mess up RoS files. RoS files don't seem to have any encryption.

I don't know if it uses ktx or some other format. I haven't checked the textures. If you suspect a file to be a texture, post a sample here and someone might take look.
## Post #25
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2018-06-20T09:33:38+00:00
- Post Title: Re: Rebellious Million Arthur Tool + Research

> Reply from AceWell
>
> .
Really hope someone could extract NPK files from Onmyoji Arena
[http://www.mediafire.com/file/g94dv1jtev0f1yd/hero2.npk](http://www.mediafire.com/file/g94dv1jtev0f1yd/hero2.npk)
## Post #26
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-07-06T02:26:10+00:00
- Post Title: Re: Rebellious Million Arthur Tool + Research

I was able to extract the model files from Forever 7th Capital. Not the best method, but it seems to be working fine so far. No textures atm though.



I will release it after some more tests. This might end up working for the new Onmyoji game too. Also I am changing the title, since the viewer seems to be working for significant amount of other games.
## Post #27
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2018-07-06T02:48:35+00:00
- Post Title: Re: Rebellious Million Arthur Tool + Research

> Reply from akderebur
>
> I was able to extract the model files from Forever 7th Capital. Not the best method, but it seems to be working fine so far. No textures atm though.

I will release it after some more tests. This might end up working for the new Onmyoji game too. Also I am changing the title, since the viewer seems to be working for significant amount of other games.

Cool    what is your method to extract the model files? Seem like there is no solution for NPK archive   but what you've done is amazing
## Post #28
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-07-06T03:01:46+00:00
- Post Title: Re: Rebellious Million Arthur Tool + Research

> Reply from onelove1210
>
> Seem like there is no solution for NPK archive
I am extracting them from the NPK. The ToC is encrypted but the rest of the NPK is actually not, and it is just compressed with lz4.

I made a program that finds the model related chunks and decompresses the lz4 blocks. Kinda like aluigi's offzip for lz4. You usually end up with unnecessary data at the end of the files, and that is why I said it isn't the best method. Still the viewer loads them fine.
## Post #29
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2018-07-06T03:12:07+00:00
- Post Title: Re: Rebellious Million Arthur Tool + Research

> Reply from akderebur
>
> 
I am extracting them from the NPK. The ToC is encrypted but the rest of the NPK is actually not, and it is just compressed with lz4.

I made a program that finds the model related chunks and decompresses the lz4 blocks. Kinda like aluigi's offzip for lz4. You usually end up with unnecessary data at the end of the files, and that is why I said it isn't the best method. Still the viewer loads them fine.

Amazing! Thank you so much
## Post #30
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2018-07-11T19:01:15+00:00
- Post Title: Re: Rebellious Million Arthur Tool + Research

> Reply from akderebur
>
> 
I will release it after some more tests. This might end up working for the new Onmyoji game too. Also I am changing the title, since the viewer seems to be working for significant amount of other games.
 yes. Onmyoji Arena please. Too much beautiful characters there
## Post #31
- Username: eaglekuz
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Feb 25, 2012 6:15 pm
- Post datetime: 2018-07-12T13:03:35+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

thank you so much!
I hope one day we can rip from Onmyoji Arena too... Models in this game has good quality with their normal maps.
## Post #32
- Username: eaglekuz
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Feb 25, 2012 6:15 pm
- Post datetime: 2018-07-13T03:33:44+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from akderebur
>
> ngovandang wrote:
BMS script to get ktx seem not working with this game
That script xor's the header with a key. It works for RMA, but it will probably mess up RoS files. RoS files don't seem to have any encryption.

I don't know if it uses ktx or some other format. I haven't checked the textures. If you suspect a file to be a texture, post a sample here and someone might take look.
this is one of Onmyoji's texture files that i couldn't convert using that script, can you take a look?
[https://drive.google.com/open?id=1gjRBo ... 7RNGS7jecu](https://drive.google.com/open?id=1gjRBo2Z-60AWPjKv6MAguV7RNGS7jecu)
## Post #33
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2018-07-13T07:37:31+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from eaglekuz
>
> 
this is one of Onmyoji's texture files that i couldn't convert using that script, can you take a look?

There is no encryption. Just open it normally without the script.
## Post #34
- Username: eaglekuz
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Feb 25, 2012 6:15 pm
- Post datetime: 2018-07-13T07:55:39+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from onelove1210
>
> 
There is no encryption. Just open it normally without the script.

what program can i use to open that?
## Post #35
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-07-13T09:35:42+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from eaglekuz
>
> 
what program can i use to open that?
Mali Texture Compression Tool or PVRTexTool
## Post #36
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2018-07-14T23:53:50+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from onelove1210
>
> eaglekuz wrote:
this is one of Onmyoji's texture files that i couldn't convert using that script, can you take a look?


There is no encryption. Just open it normally without the script.

Are you porting Onmyoji Arena models?
## Post #37
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2018-07-15T15:51:43+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from ngovandang
>
> 

Are you porting Onmyoji Arena models?

What do you mean "porting"? The texture above is from Onmyoji, not Onmyoji Arena
## Post #38
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2018-07-19T12:52:47+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from onelove1210
>
> 

What do you mean "porting"? The texture above is from Onmyoji, not Onmyoji Arena
Sorry, I mean Extracting.
Are you extracting Onmyoji Arena models?
## Post #39
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2018-07-19T15:38:46+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from ngovandang
>
> 
Sorry, I mean Extracting.
Are you extracting Onmyoji Arena models?

I'm trying to. However, there is no clue. Hope akadebur finish his own work and then release the tool asap.
## Post #40
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-07-21T00:05:19+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from onelove1210
>
> Hope akadebur finish his own work and then release the tool asap.
I am more or less done with it. Just too busy/lazy to finalize it and upload  It will be a seperate tool for unpacking model and texture files from the NPK archive. I just made slight changes to the viewer

However, from what I have seen it is only useful for Forever 7th Capital. Onmyoji arena is encrypted, and other games just extract fine with the quickbms script. So this will most likely be an update for a single game.
## Post #41
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-08-02T17:28:03+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

I updated the first post.

What's new
- Posted model/texture extractor for Forever 7th Capital NPK files
- Viewer now reads the correct data for meshes that have multiple uv channels
- Fixed bone transformations for some models

Issues
- For some models bone transformations are still wrong. Depending on the model it might be more noticeable or not. This is because of the coordinate system differences between OpenGL and the one Netease uses. I will see what I can do about this in a future update.
## Post #42
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2018-08-03T08:40:57+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

how to extract dat from nxpk? the bms script return memory error on onmyoji npk
## Post #43
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-08-03T09:55:21+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from wansf
>
> how to extract dat from nxpk? the bms script return memory error on onmyoji npk
The bms script should work with the classic Onmyoji, unless they changed something. If you are trying to unpack Onmyoji Arena, it won't work.
## Post #44
- Username: lisomn
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 07, 2018 9:20 pm
- Post datetime: 2018-08-03T10:40:25+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

thanks. I don't know how to feel about you, thank you very much, thank you for sharing.
## Post #45
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2018-08-03T13:33:15+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from akderebur
>
> wansf wrote:how to extract dat from nxpk? the bms script return memory error on onmyoji npk
The bms script should work with the classic Onmyoji, unless they changed something. If you are trying to unpack Onmyoji Arena, it won't work.
thx man
i finally got those dats but there are like 20000+ files inside one npk , my pc is dying LOL
## Post #46
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2018-08-10T11:37:15+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

help me please,  where is the  (1020x1020) textures of forever 7th capital located? i only have lowres.npk that contains 512x512 textures
## Post #47
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-08-10T12:37:16+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from tone
>
> where is the  (1020x1020) textures of forever 7th capital located?
"model.npk"
## Post #48
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2018-08-10T14:23:35+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from akderebur
>
> tone wrote:where is the  (1020x1020) textures of forever 7th capital located?
"model.npk"

thank you very much . 


i have a question regarding difference between versions.
in my korean version, this character below was censored  and she now wears a trouser
does the chinese version got censored too?
[https://candoru.ru/wp-content/uploads/2017/11/3-3.jpg](https://candoru.ru/wp-content/uploads/2017/11/3-3.jpg)
## Post #49
- Username: lxxxk
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jul 02, 2014 1:33 pm
- Post datetime: 2018-11-06T08:45:35+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

thank you，help me  [https://n.163.com/](https://n.163.com/) Netease Games DAT model.

Script[https://zenhax.com/viewtopic.php?f=9&t= ... ainst+cold](https://zenhax.com/viewtopic.php?f=9&t=7235&hilit=against+cold)

DAT 

 test.rar
(61.04 KiB) Downloaded 42 times
## Post #50
- Username: usabdt
- Rank: advanced
- Number of posts: 47
- Joined date: Fri Sep 21, 2018 4:28 am
- Post datetime: 2018-12-04T05:14:09+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from akderebur
>
> UPDATE

I was able to finish my tool, thanks to AceWell figuring out the encryption key. Now it can load the skeleton too. Also it seems to work fine with Onmyoji and Crusaders of Light too, at least for the mobile versions.

Here is a preview of the program.



Load your file/folder from the "File" menu. Select the model from the list. Export it as OBJ or IQE (skinned). 
How to open/convert IQE: viewtopic.php?p=138153#p138153

For getting the textures read the posts below.

Viewer/b] http://www.mediafire.com/file/m6d90s8j6 ... A_Upd3.rar

F7C File Extractor/b] http://www.mediafire.com/file/z0pyyy6kn ... ractor.rar

Example exported model:


Hi akderebur , Let me ask the software has the updated version? I need to extract game http://n.163.com/download/
## Post #51
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-12-04T10:05:26+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from usabdt
>
> I need to extract game http://n.163.com/download/
That game uses a different model format. It would require a whole new program. I have no plans to work on that game atm.
## Post #52
- Username: Shinteo
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Apr 06, 2016 11:26 am
- Post datetime: 2019-01-06T18:15:03+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Hi. I used your program for a game
[http://toarumajutsunoindex.wikia.com/wi ... obile_MMO)](http://toarumajutsunoindex.wikia.com/wiki/Toaru_Majutsu_no_Index_%28Mobile_MMO%29)

It also uses .dat files. I can get the model from it, using your program, but am unable to find the textures. 

I'll leave one of the npk files I found in the game data here, in case someone is able to help find where the texture file is hiding. Because after extracting, there is a whole bunch of files that I have no idea the purpose of, so in order to ensure that nothing is left out that could help with the search, I'll just leave the whole file here.

[https://www.mediafire.com/file/avdhoe34 ... s.npk/file](https://www.mediafire.com/file/avdhoe34amsdw4y/res.npk/file)
## Post #53
- Username: sfc123
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Nov 10, 2014 2:25 am
- Post datetime: 2019-01-08T05:33:27+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

well done~~;
thx~~
## Post #54
- Username: kotaxzz1
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 21, 2015 1:44 am
- Post datetime: 2019-02-02T07:27:36+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

EDIT : My bad.

for texture i just need find the header with notepad++ and move it to texture folder for work with that script .ktx
## Post #55
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-02-02T10:28:49+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from kotaxzz1
>
> export with nothing when try to extract model or texture from Million Arthur.
Can you preview the model and only have problem with exporting? Better post a small sample because I can't help much without seeing what you are trying to load.

The tool doesn't export textures.
## Post #56
- Username: kotaxzz1
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 21, 2015 1:44 am
- Post datetime: 2019-02-02T14:01:03+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from akderebur
>
> kotaxzz1 wrote:export with nothing when try to extract model or texture from Million Arthur.
Can you preview the model and only have problem with exporting? Better post a small sample because I can't help much without seeing what you are trying to load.

The tool doesn't export textures.
sorry for that, it just my bad , your tool work correctly.
## Post #57
- Username: kessa,,a
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 01, 2019 8:04 pm
- Post datetime: 2019-02-02T17:36:58+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from akderebur
>
> usabdt wrote:I need to extract game http://n.163.com/download/
That game uses a different model format. It would require a whole new program. I have no plans to work on that game atm.
[viewtopic.php?f=16&t=19299](http://forum.xentax.com/viewtopic.php?f=16&t=19299)
There was someone writing the script for this game, but it was not complete, could you help renovate it ??There was someone writing the script for this game, but it was not complete, could you help renovate it ??
## Post #58
- Username: kessa,,a
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 01, 2019 8:04 pm
- Post datetime: 2019-02-02T17:37:46+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from lxxxk
>
> thank you，help me  https://n.163.com/ Netease Games DAT model.

Scripthttps://zenhax.com/viewtopic.php?f=9&t= ... ainst+cold

DAT test.rar
[viewtopic.php?f=16&t=19299](http://forum.xentax.com/viewtopic.php?f=16&t=19299)
## Post #59
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-02-02T19:31:07+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from kessa,,a
>
> could you help renovate it ??
Sorry, I am not interested in that game.
## Post #60
- Username: dhnRiz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 03, 2019 3:23 pm
- Post datetime: 2019-02-03T07:28:24+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from kotaxzz1
>
> EDIT : My bad.

for texture i just need find the header with notepad++ and move it to texture folder for work with that script .ktx

how do you do that, i can't find the texture file anywhere, is it included on the .dat file?
## Post #61
- Username: ssit
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 04, 2019 4:00 am
- Post datetime: 2019-02-03T20:04:26+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Hi, new in here and are the other resources like talking scripts in those .npk in F7C?
## Post #62
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-02-03T20:20:12+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from ssit
>
> are the other resources like talking scripts in those .npk in F7C?
They should be in one of the npk archives. F7CExtractor in the first post will only extract models and textures though.
## Post #63
- Username: ssit
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 04, 2019 4:00 am
- Post datetime: 2019-02-03T21:40:10+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Having no idea of the encryption.
where should it be started with?
Can't identify those names, but guess cinematic or scene would be close
## Post #64
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-02-09T05:24:22+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

i was playing around with aluigi's nxpk bms script to make it extract and 
decrypt "Rebellious Million Arthur" npk files for fun and give a meaningful
extension with focus to the texture files (pvr, dds, png, ktx).  


 RebelliousMillionArthur_nxpk.zip
(881 Bytes) Downloaded 197 times
## Post #65
- Username: iyar7x
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 28, 2017 2:14 pm
- Post datetime: 2019-03-06T04:17:28+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

hi guys, few month ago netease released new game called Cyber Hunter.
as far as i know, its still use npk file like netease other games.
i tried open the char model using aluigi nxpk.bms + quickBMS but no luck. with RMA viewer also didn't work.
can some one help me? i didn't mean to make cheat or some thing, just want to try make a custom skin/model.
thanks.
here the file link :
[http://www.mediafire.com/file/kmbxm8kfp ... l.zip/file](http://www.mediafire.com/file/kmbxm8kfpnbsj4k/femalemodel.zip/file)
## Post #66
- Username: MoonlightFox
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Sep 17, 2018 4:08 pm
- Post datetime: 2019-04-06T09:17:25+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Anyone have a new download link for the Viewer in first post? The MediaFire link gives a strange error whenever I try to download it. Tried in two different browsers but it keeps failing to download. The F7CExtractor downloaded fine though.

Thank you for taking the time to make these tools!
## Post #67
- Username: lishaoran00
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 05, 2017 10:11 am
- Post datetime: 2019-04-06T19:59:27+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Hi, I have a problem with the RMAViewer when I try to save a model to IQE I get a dialog box with the following error:

Unhandled exception has occurred in a component in your application.  If you click continue, the application will ignore this error and attempt to continue. 
The given key was not present in the dictionary

```
just-in-time (JIT) debugging instead of this dialog box.

************** Exception Text **************
System.Collections.Generic.KeyNotFoundException: The given key was not present in the dictionary
   at System.ThrowHelper.ThrowKeyNotFoundException()
   at System.Collections.Generic.Dictionary`2.get_Item(TKey key)
   at  . . (String )
   at  . . (Boolean )
   at System.Windows.Forms.Control.OnClick(EventArgs e)
   at System.Windows.Forms.Button.OnClick(EventArgs e)
   at System.Windows.Forms.Button.OnMouseUp(MouseEventArgs mevent)
   at System.Windows.Forms.Control.WmMouseUp(Message& m, MouseButtons button, Int32 clicks)
   at System.Windows.Forms.Control.WndProc(Message& m)
   at System.Windows.Forms.ButtonBase.WndProc(Message& m)
   at System.Windows.Forms.Button.WndProc(Message& m)
   at System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)


************** Loaded Assemblies**************
mscorlib
    Assembly Version: 4.0.0.0
    Win32 Version: 4.7.3324.0 built by: NET472REL1LAST_C
    CodeBase: file:///C:/Windows/Microsoft.NET/Framework64/v4.0.30319/mscorlib.dll
----------------------------------------
RMAViewer
    Assembly Version: 1.0.0.0
    Win32 Version: 1.0.0.0
    CodeBase: file:///C:/Users/Nick/Documents/Nick/3D%20Models/F7C%20Models/Resources/RMA_Upd3/RMAViewer.exe
----------------------------------------
System.Windows.Forms
    Assembly Version: 4.0.0.0
    Win32 Version: 4.7.3324.0 built by: NET472REL1LAST_C
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Windows.Forms/v4.0_4.0.0.0__b77a5c561934e089/System.Windows.Forms.dll
----------------------------------------
System
    Assembly Version: 4.0.0.0
    Win32 Version: 4.7.3353.0 built by: NET472REL1LAST_B
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System/v4.0_4.0.0.0__b77a5c561934e089/System.dll
----------------------------------------
System.Drawing
    Assembly Version: 4.0.0.0
    Win32 Version: 4.7.3190.0 built by: NET472REL1LAST_C
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Drawing/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Drawing.dll
----------------------------------------
System.Configuration
    Assembly Version: 4.0.0.0
    Win32 Version: 4.7.3324.0 built by: NET472REL1LAST_C
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Configuration/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Configuration.dll
----------------------------------------
System.Core
    Assembly Version: 4.0.0.0
    Win32 Version: 4.7.3324.0 built by: NET472REL1LAST_C
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Core/v4.0_4.0.0.0__b77a5c561934e089/System.Core.dll
----------------------------------------
System.Xml
    Assembly Version: 4.0.0.0
    Win32 Version: 4.7.3190.0 built by: NET472REL1LAST_C
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Xml/v4.0_4.0.0.0__b77a5c561934e089/System.Xml.dll
----------------------------------------
OpenTK
    Assembly Version: 1.1.0.0
    Win32 Version: 1.1.1664.6217
    CodeBase: file:///C:/Users/Nick/Documents/Nick/3D%20Models/F7C%20Models/Resources/RMA_Upd3/OpenTK.DLL
----------------------------------------
mscorlib.resources
    Assembly Version: 4.0.0.0
    Win32 Version: 4.7.3190.0 built by: NET472REL1LAST_C
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/mscorlib.resources/v4.0_4.0.0.0_es_b77a5c561934e089/mscorlib.resources.dll
----------------------------------------
System.Windows.Forms.resources
    Assembly Version: 4.0.0.0
    Win32 Version: 4.7.3190.0 built by: NET472REL1LAST_C
    CodeBase: file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Windows.Forms.resources/v4.0_4.0.0.0_es_b77a5c561934e089/System.Windows.Forms.resources.dll
----------------------------------------

************** JIT Debugging **************
To enable just-in-time (JIT) debugging, the .config file for this
application or computer (machine.config) must have the
jitDebugging value set in the system.windows.forms section.
The application must also be compiled with debugging
enabled.

For example:
<configuration>
    <system.windows.forms jitDebugging="true" />
</configuration>

When JIT debugging is enabled, any unhandled exception
will be sent to the JIT debugger registered on the computer
rather than be handled by this dialog box.

```


the problem is not with all the models for now only with some and it does not give error when saved in OBJ

This is one of the models with which I had problems:
[https://www.mediafire.com/file/1msj67i0 ... 3.dat/file](https://www.mediafire.com/file/1msj67i07cx7b36/0063.dat/file)

Sorry for my English
## Post #68
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-04-06T22:41:32+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from lishaoran00 ↑Sun Apr 07, 2019 3:59 am at Sun Apr 07, 2019 3:59 am
>
> 
when I try to save a model to IQE I get a dialog box with the following error
Another user also reported this problem. It probably just needs a quick fix. I will update the viewer, when I have the time.
## Post #69
- Username: lishaoran00
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 05, 2017 10:11 am
- Post datetime: 2019-04-06T23:54:23+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from akderebur ↑Sun Apr 07, 2019 6:41 am at Sun Apr 07, 2019 6:41 am
>
> 
lishaoran00 wrote: ↑Sun Apr 07, 2019 3:59 am
when I try to save a model to IQE I get a dialog box with the following error

Another user also reported this problem. It probably just needs a quick fix. I will update the viewer, when I have the time.

thanks for answering   I'll wait until the update   .
## Post #70
- Username: Jinseiisla2
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 09, 2019 5:30 am
- Post datetime: 2019-04-23T02:29:21+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

So i am ripping from the Non Human Academy game and i got the models but i dont have the textures. I dont know where the textures are located or how to get them when i locate. I did see a bunch of KTX files but i cant open them.
## Post #71
- Username: lenovotxwd
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu May 23, 2019 8:37 pm
- Post datetime: 2019-05-23T12:50:39+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from akderebur ↑Fri Jul 06, 2018 10:26 am at Fri Jul 06, 2018 10:26 am
>
> 
I was able to extract the model files from Forever 7th Capital. Not the best method, but it seems to be working fine so far. No textures atm though.



I will release it after some more tests. This might end up working for the new Onmyoji game too. Also I am changing the title, since the viewer seems to be working for significant amount of other games.

There are two ways to get  Onmyoji  Anera model.
1. Analyize the update data.(Maybe)
It is a online game. It need updata.
We can analyize the data from downloading data by net package.
Then find the difference before and after in game files.
Process like: net data -> difference before and after in game files
Find the data transfrom to infer the encryption process.
I suggest you can try this way if you would.

2.Analyize the so lib to find how it work.
The game is program. We can analyize binary to find how it read epkx file.
I will try this way when not busy.
## Post #72
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-05-23T12:59:51+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from lenovotxwd ↑Thu May 23, 2019 8:50 pm at Thu May 23, 2019 8:50 pm
>
> 
2.Analyize the so lib to find how it work.
The game is program. We can analyize binary to find how it read epkx file.
I will try this way when not busy.
This would make more sense. Of course the encryption can be found and I don't think it will be really hard but I basically have no interest for this game. That is why I didn't bother.

Still it might help with other Netease games so give it a shot
## Post #73
- Username: huitbgoiouythy
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Nov 16, 2018 12:43 am
- Post datetime: 2019-05-28T11:04:35+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Hello thank you for your tools, do you plan to make the tools compatible for Marvel Super War (available on neoggwpp) ?
## Post #74
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-05-28T14:57:35+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from huitbgoiouythy ↑Tue May 28, 2019 7:04 pm at Tue May 28, 2019 7:04 pm
>
> 
do you plan to make the tools compatible for Marvel Super War ?
I will do an update for the Netease tool soon. That game might work too.
## Post #75
- Username: waru1001
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Oct 25, 2014 11:43 am
- Post datetime: 2019-06-02T15:32:33+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Hi,

not sure if I can ask about sound files here, but this is from Eternal City.

First, I use FSB Extracter to extract sounds from res/sound



But I cannot play it and not sure why...



Example File: [https://drive.google.com/open?id=1n5G7V ... say9mIY7ld](https://drive.google.com/open?id=1n5G7V-j7_S2ACWfKZLtZM8say9mIY7ld)
## Post #76
- Username: godskin
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Nov 05, 2015 9:45 pm
- Post datetime: 2019-06-02T15:44:16+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from waru1001 ↑Sun Jun 02, 2019 11:32 pm at Sun Jun 02, 2019 11:32 pm
>
> 
Hi,

not sure if I can ask about sound files here, but this is from Eternal City.

First, I use FSB Extracter to extract sounds from res/sound



But I cannot play it and not sure why...



Example File: https://drive.google.com/open?id=1n5G7V ... say9mIY7ld

Stop stupid  used GOM player or Etc player for support .ogg file
very stupid not use googgle
## Post #77
- Username: waru1001
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Oct 25, 2014 11:43 am
- Post datetime: 2019-06-03T15:36:20+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from godskin ↑Sun Jun 02, 2019 11:44 pm at Sun Jun 02, 2019 11:44 pm
>
> 

Stop stupid  used GOM player or Etc player for support .ogg file
very stupid not use googgle

Hey godskin.

I will not blame you for being a rude here.

I already try Window's Groove Music, GOM Player, VLC, MPC Player, Foobar 2000 none of them can play the file.

Do you have any player able to play the file attached?
## Post #78
- Username: lenovotxwd
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu May 23, 2019 8:37 pm
- Post datetime: 2019-06-07T02:44:58+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from akderebur ↑Thu May 23, 2019 8:59 pm at Thu May 23, 2019 8:59 pm
>
> 
lenovotxwd wrote: ↑Thu May 23, 2019 8:50 pm
2.Analyize the so lib to find how it work.
The game is program. We can analyize binary to find how it read epkx file.
I will try this way when not busy.

This would make more sense. Of course the encryption can be found and I don't think it will be really hard but I basically have no interest for this game. That is why I didn't bother.

Still it might help with other Netease games so give it a shot
Could you release your code of viewer or format spec?
I wanna try to convert it to gltf format in python.
## Post #79
- Username: fdtggf
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Feb 07, 2016 3:12 am
- Post datetime: 2019-06-11T15:18:04+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

akderebur,can you update the F7CExtractor? hero.npk and hero_skin.npk can't extract textures
## Post #80
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-06-11T16:29:50+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from fdtggf ↑Tue Jun 11, 2019 11:18 pm at Tue Jun 11, 2019 11:18 pm
>
> 
hero.npk and hero_skin.npk can't extract textures
I don't have the latest files. Maybe they encrypted the archives now.
## Post #81
- Username: fdtggf
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Feb 07, 2016 3:12 am
- Post datetime: 2019-06-12T19:48:20+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from akderebur ↑Wed Jun 12, 2019 12:29 am at Wed Jun 12, 2019 12:29 am
>
> 
fdtggf wrote: ↑Tue Jun 11, 2019 11:18 pm
hero.npk and hero_skin.npk can't extract textures

I don't have the latest files. Maybe they encrypted the archives now.

I have latest version files,can you take a look?
[https://mega.nz/#!oQ4iyawC!dKaqfxo_f5o6 ... cQw6G_GZEg](https://mega.nz/#!oQ4iyawC!dKaqfxo_f5o6Pw4kyyHck_733P7gxBy3tcQw6G_GZEg)
## Post #82
- Username: tempaccount555
- Rank: beginner
- Number of posts: 27
- Joined date: Sun May 12, 2019 8:14 pm
- Post datetime: 2019-06-15T06:54:29+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Capture.PNG (52.19 KiB) Viewed 586 times

[https://zenhax.com/viewtopic.php?f=17&t=1901](https://zenhax.com/viewtopic.php?f=17&t=1901)
try to use that tool
works for me, and now im just waiting someone to make bms script to extract the npk files
## Post #83
- Username: waru1001
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Oct 25, 2014 11:43 am
- Post datetime: 2019-06-22T15:03:24+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

hey, tempaccount555! thanks, it's work!
## Post #84
- Username: waru1001
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Oct 25, 2014 11:43 am
- Post datetime: 2019-06-22T15:38:04+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Not sure how to fix this

Here's what I have done:
- use F7CExtractor to extract npk to dat files
- browse model using RMA_Upd3 (download from 1st page) to export model to iqe
- convert ktx texture file to png
- Once in Blender. I imported iqe model and map source texture to exported png file. But model texture map seems wrong



(Model: Nuru from Eternal City)
## Post #85
- Username: mushishiro
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 25, 2019 9:10 am
- Post datetime: 2019-09-29T19:19:36+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

can this script extract the latest version of onmyoji?
## Post #86
- Username: mio2610
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 13, 2018 11:38 am
- Post datetime: 2019-10-12T19:07:23+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Hi, I'm having a problem with the .ktx texture files of F7C. 
I used bms script to extract the .ktx from .iqe, but then when I used Mali texture compression tool, I kept having the error of "cannot open image file" 

The textures are what left in my ripping
## Post #87
- Username: ThatFlynnster
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 13, 2019 11:37 am
- Post datetime: 2019-10-13T03:47:48+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

I want to extract the models from Identity V. I'm using the Official PC version, and I can't find the correct npk file for it... Also, the viewer you posted isn't working on my PC. pls help meh...
## Post #88
- Username: douchi
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 29, 2019 10:24 pm
- Post datetime: 2019-10-18T16:13:14+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

If the file name is wrong, can you get the file matching the model name and map name?
## Post #89
- Username: xoLadyCharlotte
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 13, 2019 3:26 am
- Post datetime: 2019-10-26T18:28:58+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Any chance someone can reupload RMA Viewer? It's getting blocked because its infected with malware
## Post #90
- Username: puppy7699
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 02, 2019 1:56 am
- Post datetime: 2019-11-01T18:22:08+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from Acewell ↑Mon Apr 16, 2018 10:11 pm at Mon Apr 16, 2018 10:11 pm
>
> 
being from a mobile game is a good chance they're using some type of mobile compression,
you can open the raw data in PVRTextool and test various formats. 

edit
now i see this byte pattern in the encrypted headers and it is looking like xor based on the results  
Code: Select all7A 7B 7C 7D 7E 7F 80 81 82 83 84 85 86 87 88 89 
8A 8B 8C 8D 8E 8F 90 91 92 93 94 95 96 97 98 99 
9A 9B 9C 9D 9E 9F A0 A1 A2 A3 A4 A5 A6 A7 A8 A9
AA AB AC AD AE AF B0 B1 B2 B3 B4 B5 B6 B7 B8 B9 
BA BB BC BD BE BF C0 C1 C2 C3 C4 C5 C6 C7 C8 C9 
CA CB CC CD CE CF D0 D1 D2 D3 D4 D5 D6 D7 D8 D9 
DA DB DC DD DE DF E0 E1 E2 E3 E4 E5 E6 E7 E8 E9 
EA EB EC ED EE EF F0 F1 F2 F3 F4 F5 F6 F7 F8 F9

using that key reveals a ktx format header and first 4 rows of image data
Code: Select allAB 4B 54 58 20 31 31 BB 0D 0A 1A 0A 01 02 03 04
00 00 00 00 01 00 00 00 00 00 00 00 78 92 00 00
08 19 00 00 00 04 00 00 00 04 00 00 00 00 00 00
00 00 00 00 01 00 00 00 01 00 00 00 00 00 00 00
00 00 10 00 FF 00 00 00 00 00 00 00 0D 57 B7 62
EE 00 EE 00 FF 00 00 00 00 00 00 00 0D 57 B7 62
EE EE EE EE FF 00 00 00 00 00 00 00 0D 57 B7 62
EE EE EE EE FF 00 00 00 00 00 00 00 0D 57 B7 62


bms script to fix the samples
Code: Select all# script for QuickBMS http://aluigi.altervista.org/quickbms.htm

get SIZE asize
get NAME basename
string NAME + .ktx
math SIZE - 0x80
filexor "\x7A\x7B\x7C\x7D\x7E\x7F\x80\x81\x82\x83\x84\x85\x86\x87\x88\x89\x8A\x8B\x8C\x8D\x8E\x8F\x90\x91\x92\x93\x94\x95\x96\x97\x98\x99\x9A\x9B\x9C\x9D\x9E\x9F\xA0\xA1\xA2\xA3\xA4\xA5\xA6\xA7\xA8\xA9\xAA\xAB\xAC\xAD\xAE\xAF\xB0\xB1\xB2\xB3\xB4\xB5\xB6\xB7\xB8\xB9\xBA\xBB\xBC\xBD\xBE\xBF\xC0\xC1\xC2\xC3\xC4\xC5\xC6\xC7\xC8\xC9\xCA\xCB\xCC\xCD\xCE\xCF\xD0\xD1\xD2\xD3\xD4\xD5\xD6\xD7\xD8\xD9\xDA\xDB\xDC\xDD\xDE\xDF\xE0\xE1\xE2\xE3\xE4\xE5\xE6\xE7\xE8\xE9\xEA\xEB\xEC\xED\xEE\xEF\xF0\xF1\xF2\xF3\xF4\xF5\xF6\xF7\xF8\xF9"
log NAME 0x0 0x80
append
filexor ""
log NAME 0x80 SIZE

00000372.ktx opened and converted to png with "Mali Texture Compression Tool"  
00000372.png
the original size is actually 1024x1024 i just scaled it down to fit under the max attachment size.

hey Acewell BRO ! , i used RMA Viewer( download from first page ) to export .dat to OBJ, OBJ so good. But i used Texture Finder to find texture from dat. file it is a problem . Please help me export texture from .dat file. It 's dat from Onmyoji Classic turn base game. !!!!!!!!! Sorry my English !!!
I hope this Topic still active (

[https://imgur.com/zSjcs0J](https://imgur.com/zSjcs0J)
## Post #91
- Username: meff1091
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 01, 2016 8:34 pm
- Post datetime: 2019-12-10T06:35:03+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

any news on marvel super war npk files?
## Post #92
- Username: Caeser
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 11, 2020 8:36 am
- Post datetime: 2020-04-11T00:39:01+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

ZenHax help me brooo i dont know how to make extract all stuffs can you give me vehicle npk with all skins on them cracked for me ? please reply me if you can ily bro
## Post #93
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2020-07-06T17:08:57+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Hello ones!
I wanna know how to rip Onmyoji Arena characters for cosplay
I try tools that are on 1st page, but Quick BMS give me 0 files.
Any chance to get something from that?

I hope, someone still working with that game
## Post #94
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2020-07-07T08:59:49+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from TokiChan ↑Tue Jul 07, 2020 1:08 am at Tue Jul 07, 2020 1:08 am
>
> 
Hello ones!
I wanna know how to rip Onmyoji Arena characters for cosplay
I try tools that are on 1st page, but Quick BMS give me 0 files.
Any chance to get something from that?

I hope, someone still working with that game
[viewtopic.php?f=16&t=20645](https://forum.xentax.com/viewtopic.php?f=16&t=20645)
## Post #95
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2020-07-07T15:28:18+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from alictzelt ↑Tue Jul 07, 2020 4:59 pm at Tue Jul 07, 2020 4:59 pm
>
> 
TokiChan wrote: ↑Tue Jul 07, 2020 1:08 am
Hello ones!
I wanna know how to rip Onmyoji Arena characters for cosplay
I try tools that are on 1st page, but Quick BMS give me 0 files.
Any chance to get something from that?

I hope, someone still working with that game 

viewtopic.php?f=16&t=20645

Thanks!
So, can u say me what I must do shortly?
I decrypt hero1.npk with EXPDdec with key
then I try open it with quick bms, but quick bms still say get 0 files.
What I must to do next?
## Post #96
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2021-01-19T01:49:36+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

This new Netease game here has NPK files [http://hsqsl.163.com/](http://hsqsl.163.com/)
Could we get support for this?

One of the NPK files
[https://drive.google.com/file/d/1zmZScx](https://drive.google.com/file/d/1zmZScx) ... q6NUp/view
## Post #97
- Username: Bapho
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 01, 2020 3:05 am
- Post datetime: 2021-02-01T04:06:49+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

So i tried using this tool on the char NPKs for Masterwork Apocolypse, Netease's newer game, and it works on some models, but others don't load on the viewer and others fail to export.

Here are their Char NPK files
[https://drive.google.com/file/d/1GUqHZv ... sp=sharing](https://drive.google.com/file/d/1GUqHZvxKRCpOeNAB5UPmRd8V--9AiYK0/view?usp=sharing)
## Post #98
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2021-02-01T15:16:25+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

I second Masterwork Apocolypse

Masterwork Apocolypse and SAO Blackswordsman Ace would be wonderful files to explore
## Post #99
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-02-01T16:28:43+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from Bapho ↑Mon Feb 01, 2021 12:06 pm at Mon Feb 01, 2021 12:06 pm
>
> 
Masterwork Apocolypse

Use this: [https://github.com/zhouhang95/neox_tools](https://github.com/zhouhang95/neox_tools) It seems to work fine. I have used F7CExtractor for getting the models out. Then used converter.py.
## Post #100
- Username: BLMTuan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 21, 2021 4:54 pm
- Post datetime: 2021-02-21T09:02:35+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

I used F7CExtractor for getting the models out then  used converter.py as you said but some files get this struct.error: unpack requires a buffer of 4 bytes and cant covert to obj

is there anyway to correct this?
## Post #101
- Username: idk:1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 15, 2021 4:13 am
- Post datetime: 2021-03-14T20:39:05+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

I tried to run RMA Viewer but idk after I extract the program (with a zip extractor program) it kinda dissappears. Anyone knows how to fix this problem or anyone recommend a other viewer to see the 3D models ind IDV (Identity V)
## Post #102
- Username: Chrazer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 24, 2021 2:57 am
- Post datetime: 2021-03-23T19:17:11+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Hello Everyone 
Wish u have a good day
I'm here asking for help, can anyone extract this npk file from netease game? 

[https://www.mediafire.com/file/l3rmg2xo ... l.npk/file](https://www.mediafire.com/file/l3rmg2xou3p393b/model.npk/file)
## Post #103
- Username: UsoppFanGirl
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Apr 08, 2021 11:13 pm
- Post datetime: 2021-04-12T02:36:43+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

When I try and extract some Onmyoji archives using quickbms I get these errors: 

Error: the compressed zlib/deflate input is wrong or incomplete (-3)
Info: algorithm 1
offset 0000000000000000
input size 0x0000000002e30fb8 48435128
output size 0x00000000000032fa 13050
result 0xffffffffffffffff -1

Error: uncompressed data (-1) bigger than allocated buffer (48435000)
It usually means that data is not compressed or uses another algorithm

any way to fix/get around these? Someone said the NPK format has been changed or the script i used may have been outdated.
## Post #104
- Username: sammyispoor
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 18, 2021 4:54 am
- Post datetime: 2021-06-17T20:59:51+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Hi, im having an issue with a certain Netease game named Identity v. There's a certain model i want to save as iqe, but according to my friend its corrupted. this is what pops up when i try to save [ when i click continue it doesn't save ], help is appreciated thank you.

[ screenshot of what im talking about, im not sure how to share images im new to this forum TvT ]

[https://cdn.discordapp.com/attachments/ ... t_2318.png](https://cdn.discordapp.com/attachments/584698692800479232/855189795739402280/Screenshot_2318.png)
[Screenshot (2318).png](https://xentaxbackup.github.io/file/20320_Screenshot (2318).png)
## Post #105
- Username: JustARandomDude
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 31, 2021 3:22 pm
- Post datetime: 2021-07-31T07:27:49+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Which QuickBMs script you've been using?
## Post #106
- Username: klkl22
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 20, 2021 10:26 pm
- Post datetime: 2021-08-20T14:29:17+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Hey! Could you help explain how to use the reimport of the game archive?
We unpack the game files, but they are created in the same folder and with different names without preserving the original names and structure.
But we need to extract the files, modify them and then pack them back. .npk archive files

Please, help.
## Post #107
- Username: flipdark95
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 08, 2016 12:24 pm
- Post datetime: 2021-09-28T06:16:00+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Hey guys, I tried using this tool to extract models from Lord of the Rings: Rise to War, which uses the NPK format to hold all of its assets, but it didn't extract anything. Can I get some help?

Here's one of the NPK files I'm trying to extract.
[https://drive.google.com/file/d/1Qv7JY3 ... sp=sharing](https://drive.google.com/file/d/1Qv7JY3gfoRT5-Y-gFjCjvAsl3FWkoiKa/view?usp=sharing)
## Post #108
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2021-09-29T19:30:03+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from flipdark95 ↑Tue Sep 28, 2021 2:16 pm at Tue Sep 28, 2021 2:16 pm
>
> 
Hey guys, I tried using this tool to extract models from Lord of the Rings: Rise to War, which uses the NPK format to hold all of its assets, but it didn't extract anything. Can I get some help?

Here's one of the NPK files I'm trying to extract.
https://drive.google.com/file/d/1Qv7JY3 ... sp=sharing
[http://aluigi.org/papers/bms/others/nxpk.bms](http://aluigi.org/papers/bms/others/nxpk.bms)
## Post #109
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-29T20:28:12+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Kinda bowman - too low poly to raise my interest and fix it:
.



0000001f-dat.png (52.59 KiB) Viewed 698 times
## Post #110
- Username: flipdark95
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 08, 2016 12:24 pm
- Post datetime: 2021-09-30T07:57:50+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

That's definitely not how they look in-game. I'm mainly looking for character models to use them as references in making higher detail models.
## Post #111
- Username: lpriefer01
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Sep 06, 2020 6:40 am
- Post datetime: 2022-12-09T03:41:55+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

yea the textures dont even extract right using this script we need something else for rise to war
## Post #112
- Username: neradeniye
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 27, 2022 5:46 pm
- Post datetime: 2022-12-27T10:05:27+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

I recently got interested in ripping some identity v models and I want to explain what worked best for me overall incase anyone else is trying to do the same. First you will need to download the pc version of identity v which you can find here - [https://h55na.gdl.easebar.com/identityv ... 211104.exe](https://h55na.gdl.easebar.com/identityv_setup_release_oversea_211104.exe) or you can go to the website [https://idv.163.com/](https://idv.163.com/) and download the game there. You will want to run the game and let it apply the patches so you get the latest downloads then you will want to close the game and refer to this directory: "C:\IdentityV\Documents\res" inside here find the file called chr.npk as this contains the character model files. You will want to use QuickBMS with the script nxpk.bms to extract the files from inside to a bunch of .dat and other files. Inside the .dat files are the models and to view / extract these models you will want to use RMA_Upd3 viewer to view them then save to IQE. (for rigs and just a better export in general) Once you have the IQE version of your model of choice you will need to use IqeBrowser_V2.17 which you can get here - [https://www.moddb.com/mods/r-reinhard/a ... owser-v217](https://www.moddb.com/mods/r-reinhard/addons/iqebrowser-v217) If the download doesn't work then use one of the mirrors until you can get it. Once you have this program open up your IQE file in it and you will want to save as IQM so that you can view and export the model out of Noesis to fbx or whatever you prefer. Once you have the IQM go ahead and open that in Noesis and export it with all the default settings if using blender 2.92 to fbx and you should be able to view the model in blender with a rig. If you want textures you can find them in the same directory as the .dat files albeit they are a mess so I suggest using ninjaripper and dumping the textures from there from the character preview area in the game where you can view different outfits on your chosen character. You then assign those textures to the model in blender however you will likely need to invert the textures for the model in photoshop or some image editing program (flip vertical) and then they will look right on your model.

This is a lengthy process but it worked for me and if anyone else wants to give it a try feel free or reply here I can try to help you if there's any issues. I am curious about getting the models game animations for export to use as well so if anyone knows which files contain the animations or how to extract them please let me know or attempt to figure it out. 

I hope this post follows the right post location as I'm new here and just want to share my findings with everyone so we can better expand upon extracting this game. Thank you.
## Post #113
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2023-01-06T20:14:37+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Is there some alternative to converting Ktx files to png, the Mali Texture Compression Tool is no longer available to download anywhere

I had been extracting the characters for the game Masterwork Apocalypse Genesis, got the models and all the dat files and i found a quickbms script to get the ktx files from the dats but thats where im stuck

Here is an example of one of the ktx


 0001.rar
(218.32 KiB) Downloaded 20 times
## Post #114
- Username: jenny1367
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Aug 19, 2021 3:10 am
- Post datetime: 2023-05-02T07:16:49+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Hello, sorry for bumping up this old thread, but every decryptor I know has failed for the new Identity V encryption from the newest npk files. Have there been new solutions to those? And thanks in advance >< 
encrypted files from newest version [viewtopic.php?t=26676](https://forum.xentax.com/viewtopic.php?t=26676)
Unencrypted from previous version [https://www.mediafire.com/file/pjmz2jq5 ... m.npk/file](https://www.mediafire.com/file/pjmz2jq5kguf4cp/dm65_survivor_m.npk/file)
## Post #115
- Username: Blaze Modz
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Dec 28, 2015 8:00 am
- Post datetime: 2023-06-01T08:34:31+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from jenny1367 ↑Tue May 02, 2023 3:16 pm at Tue May 02, 2023 3:16 pm
>
> 
Hello, sorry for bumping up this old thread, but every decryptor I know has failed for the new Identity V encryption from the newest npk files. Have there been new solutions to those? And thanks in advance >< 
encrypted files from newest version viewtopic.php?t=26676
Unencrypted from previous version https://www.mediafire.com/file/pjmz2jq5 ... m.npk/file

I'm also struggling with this same problem. I used to be able to extract them so easily, now with the new additions, the "_2" versions of the NPKs seem to refuse to extract. I've looked around a lot and according to some posts, Changing the code on line 117 for the NXPK QuickBMS script could possibly fix it, but I've tinkered with it and some recommended values, to no avail.

The code on that line is 'xmath TMP "x - 2"' by default. 250 didn't work and some other values I tried didn't, either. If you ever find a solution to this, Please Please let me know, as I will do the same if I find one ♥
## Post #116
- Username: gardener
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Apr 03, 2023 11:24 am
- Post datetime: 2023-06-04T02:52:58+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from neradeniye ↑Tue Dec 27, 2022 6:05 pm at Tue Dec 27, 2022 6:05 pm
>
> 
I recently got interested in ripping some identity v models and I want to explain what worked best for me overall incase anyone else is trying to do the same. First you will need to download the pc version of identity v which you can find here - https://h55na.gdl.easebar.com/identityv ... 211104.exe or you can go to the website https://idv.163.com/ and download the game there. You will want to run the game and let it apply the patches so you get the latest downloads then you will want to close the game and refer to this directory: "C:\IdentityV\Documents\res" inside here find the file called chr.npk as this contains the character model files. You will want to use QuickBMS with the script nxpk.bms to extract the files from inside to a bunch of .dat and other files. Inside the .dat files are the models and to view / extract these models you will want to use RMA_Upd3 viewer to view them then save to IQE. (for rigs and just a better export in general) Once you have the IQE version of your model of choice you will need to use IqeBrowser_V2.17 which you can get here - https://www.moddb.com/mods/r-reinhard/a ... owser-v217 If the download doesn't work then use one of the mirrors until you can get it. Once you have this program open up your IQE file in it and you will want to save as IQM so that you can view and export the model out of Noesis to fbx or whatever you prefer. Once you have the IQM go ahead and open that in Noesis and export it with all the default settings if using blender 2.92 to fbx and you should be able to view the model in blender with a rig. If you want textures you can find them in the same directory as the .dat files albeit they are a mess so I suggest using ninjaripper and dumping the textures from there from the character preview area in the game where you can view different outfits on your chosen character. You then assign those textures to the model in blender however you will likely need to invert the textures for the model in photoshop or some image editing program (flip vertical) and then they will look right on your model.

This is a lengthy process but it worked for me and if anyone else wants to give it a try feel free or reply here I can try to help you if there's any issues. I am curious about getting the models game animations for export to use as well so if anyone knows which files contain the animations or how to extract them please let me know or attempt to figure it out. 

I hope this post follows the right post location as I'm new here and just want to share my findings with everyone so we can better expand upon extracting this game. Thank you.
ive gotten an error while trying to extract with quickbms script, not sure what im doing wrong TT
## Post #117
- Username: Blaze Modz
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Dec 28, 2015 8:00 am
- Post datetime: 2023-06-05T16:58:34+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from gardener ↑Sun Jun 04, 2023 10:52 am at Sun Jun 04, 2023 10:52 am
>
> 
neradeniye wrote: ↑Tue Dec 27, 2022 6:05 pm
I recently got interested in ripping some identity v models and I want to explain what worked best for me overall incase anyone else is trying to do the same. First you will need to download the pc version of identity v which you can find here - https://h55na.gdl.easebar.com/identityv ... 211104.exe or you can go to the website https://idv.163.com/ and download the game there. You will want to run the game and let it apply the patches so you get the latest downloads then you will want to close the game and refer to this directory: "C:\IdentityV\Documents\res" inside here find the file called chr.npk as this contains the character model files. You will want to use QuickBMS with the script nxpk.bms to extract the files from inside to a bunch of .dat and other files. Inside the .dat files are the models and to view / extract these models you will want to use RMA_Upd3 viewer to view them then save to IQE. (for rigs and just a better export in general) Once you have the IQE version of your model of choice you will need to use IqeBrowser_V2.17 which you can get here - https://www.moddb.com/mods/r-reinhard/a ... owser-v217 If the download doesn't work then use one of the mirrors until you can get it. Once you have this program open up your IQE file in it and you will want to save as IQM so that you can view and export the model out of Noesis to fbx or whatever you prefer. Once you have the IQM go ahead and open that in Noesis and export it with all the default settings if using blender 2.92 to fbx and you should be able to view the model in blender with a rig. If you want textures you can find them in the same directory as the .dat files albeit they are a mess so I suggest using ninjaripper and dumping the textures from there from the character preview area in the game where you can view different outfits on your chosen character. You then assign those textures to the model in blender however you will likely need to invert the textures for the model in photoshop or some image editing program (flip vertical) and then they will look right on your model.

This is a lengthy process but it worked for me and if anyone else wants to give it a try feel free or reply here I can try to help you if there's any issues. I am curious about getting the models game animations for export to use as well so if anyone knows which files contain the animations or how to extract them please let me know or attempt to figure it out. 

I hope this post follows the right post location as I'm new here and just want to share my findings with everyone so we can better expand upon extracting this game. Thank you.

ive gotten an error while trying to extract with quickbms script, not sure what im doing wrong TT

You're likely having the same issue as us. Are you trying to extract one of the character .npks?
## Post #118
- Username: deschamps12
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 05, 2018 11:40 pm
- Post datetime: 2023-07-04T06:28:10+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from akderebur ↑Mon Apr 16, 2018 7:47 am at Mon Apr 16, 2018 7:47 am
>
> 
UPDATE

I was able to finish my tool, thanks to AceWell figuring out the encryption key. Now it can load the skeleton too. Also it seems to work fine with Onmyoji and Crusaders of Light too, at least for the mobile versions.

Here is a preview of the program.



Load your file/folder from the "File" menu. Select the model from the list. Export it as OBJ or IQE (skinned). 
How to open/convert IQE: http://forum.xentax.com/viewtopic.php?p=138153#p138153

For getting the textures read the posts below.

Viewer/b] http://www.mediafire.com/file/m6d90s8j6 ... A_Upd3.rar

F7C File Extractor/b] http://www.mediafire.com/file/z0pyyy6kn ... ractor.rar

Example exported model:

would it be possible to add a batch save option? Or perhaps some more naviagtion controls for the model viewer would work too. I'm having trouble with the models appearing tiny in the model viewer and when i zoom in/out it goes out of frame. It would be faster to look through the models if i could batch export and open in noesis
## Post #119
- Username: DiMickfoxed65
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Feb 13, 2020 12:41 pm
- Post datetime: 2023-07-08T02:15:53+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

About identity V, Litteraly i just spent more time in find where the hell morgana and monokuma are and trying contorl the frikin camera than extracting the .npk :V

I fixed the problem in the bms changing the exact line Blaze Modz sayed (line 117) changing the 2, for 3 (atleast it worked with the chr.npk)


As a big favor, please tell me what .dat is the morgana or monokuma ones :,V
## Post #120
- Username: gardener
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Apr 03, 2023 11:24 am
- Post datetime: 2023-07-16T04:37:59+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from DiMickfoxed65 ↑Sat Jul 08, 2023 10:15 am at Sat Jul 08, 2023 10:15 am
>
> 
About identity V, Litteraly i just spent more time in find where the hell morgana and monokuma are and trying contorl the frikin camera than extracting the .npk :V

I fixed the problem in the bms changing the exact line Blaze Modz sayed (line 117) changing the 2, for 3 (atleast it worked with the chr.npk)


As a big favor, please tell me what .dat is the morgana or monokuma ones :,V

have you had any luck with chr part a and b? the newer skins are in there, i think.
## Post #121
- Username: HenceMAge
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 29, 2023 4:15 pm
- Post datetime: 2023-07-29T08:22:09+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from DiMickfoxed65 ↑Sat Jul 08, 2023 10:15 am at Sat Jul 08, 2023 10:15 am
>
> 
About identity V, Litteraly i just spent more time in find where the hell morgana and monokuma are and trying contorl the frikin camera than extracting the .npk :V

I fixed the problem in the bms changing the exact line Blaze Modz sayed (line 117) changing the 2, for 3 (atleast it worked with the chr.npk)


As a big favor, please tell me what .dat is the morgana or monokuma ones :,V
How did you get that to happen? :0 I get this error instead which is different from that was shown above. It has been a few years since I last extracted any files from this game so I'm very rusty in that regard ;;
## Post #122
- Username: Blaze Modz
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Dec 28, 2015 8:00 am
- Post datetime: 2023-08-06T01:21:22+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from DiMickfoxed65 ↑Sat Jul 08, 2023 10:15 am at Sat Jul 08, 2023 10:15 am
>
> 
About identity V, Litteraly i just spent more time in find where the hell morgana and monokuma are and trying contorl the frikin camera than extracting the .npk :V

I fixed the problem in the bms changing the exact line Blaze Modz sayed (line 117) changing the 2, for 3 (atleast it worked with the chr.npk)


As a big favor, please tell me what .dat is the morgana or monokuma ones :,V

Hey mate! Glad that worked for you! However, that script works just find with the original chr.npk. All of the most recent skins and crossovers (Starting from AoD, as far as I can gather) are compressed into the "chr.part.a" and "chr.part.b" .npk files, which seem to not work with this script. When trying to run those new files through the script, this is the new error it produces.



image_2023-08-05_182110737.png (25.34 KiB) Viewed 356 times
## Post #123
- Username: ReviewOkami
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 28, 2022 10:02 pm
- Post datetime: 2023-08-09T06:30:45+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Do we have any new method or sciprt for Onmyoji RPG ?
## Post #124
- Username: tresvs
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Aug 12, 2023 8:32 am
- Post datetime: 2023-08-12T00:57:41+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

---Identity V---

Hello, i just found a new way to extract the files without quickbms, as it doesn´t work anymore with newer .npk files. I should also mention that this way is not 100% perfect, cause when viewing the models, many of them will be glitched and can't be exported because of the program extracting method that get some files corrupted. 

First, you need to download this program called "Game Extractor" from this link: [https://www.watto.org/extract/full/download/extract.zip](https://www.watto.org/extract/full/download/extract.zip)
After unziping the "extract" zip, just launch the .exe
Once the program is open, and using the right window, you need to select the file you want to open, and double click on it.
After many unnamed files appear listed, press "Select" in the top options and press "Select All", and then, in the bottom right window, select the place where you want to extract the files and do not put no type of conversion. Finally, press the second button on the right with the blue card index, and wait for the files to be extracted.
After this, you just need to open the files as regular with RMA Viewer. 

Im gonna put some images of how somes models show up fine, while others just not, but im sure that we will eventually find a way to solve this. That´s all!



g.png (121.64 KiB) Viewed 316 times
## Post #125
- Username: gardener
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Apr 03, 2023 11:24 am
- Post datetime: 2023-08-12T06:50:31+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from tresvs ↑Sat Aug 12, 2023 8:57 am at Sat Aug 12, 2023 8:57 am
>
> 
---Identity V---

Hello, i just found a new way to extract the files without quickbms, as it doesn´t work anymore with newer .npk files. I should also mention that this way is not 100% perfect, cause when viewing the models, many of them will be glitched because they have different formats than the usual .dat

First, you need to download this program called "Game Extractor" from this link: https://www.watto.org/extract/full/download/extract.zip
After unziping the "extract" zip, just launch the .exe
Once the program is open, and using the right window, you need to select the file you want to open, and double click on it.
After many unnamed files appear listed, press "Select" in the top options and press "Select All", and then, in the bottom right window, select the place where you want to extract the files and do not put no type of conversion. Finally, press the second button on the right with the blue card index, and wait for the files to be extracted.
After this, you just need to open the files as regular with RMA Viewer. 

Im gonna put some images of how somes models show up fine, while others just not, but im sure that we will eventually find a way to solve this. That´s all!
g.png
i'm really excited to try this out! do i need amazing pc specs for it to work, though? i'm doing most of this on a humble laptop ... :'D
i'm also looking for the model of gatto (embalmer skin). were you able to unpack unreleased skins as well?
edit: and did the files have their names? the string of numbers is hard to manage T_T
## Post #126
- Username: tresvs
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Aug 12, 2023 8:32 am
- Post datetime: 2023-08-12T14:06:39+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from gardener ↑Sat Aug 12, 2023 2:50 pm at Sat Aug 12, 2023 2:50 pm
>
> 
tresvs wrote: ↑Sat Aug 12, 2023 8:57 am
---Identity V---

Hello, i just found a new way to extract the files without quickbms, as it doesn´t work anymore with newer .npk files. I should also mention that this way is not 100% perfect, cause when viewing the models, many of them will be glitched because they have different formats than the usual .dat

First, you need to download this program called "Game Extractor" from this link: https://www.watto.org/extract/full/download/extract.zip
After unziping the "extract" zip, just launch the .exe
Once the program is open, and using the right window, you need to select the file you want to open, and double click on it.
After many unnamed files appear listed, press "Select" in the top options and press "Select All", and then, in the bottom right window, select the place where you want to extract the files and do not put no type of conversion. Finally, press the second button on the right with the blue card index, and wait for the files to be extracted.
After this, you just need to open the files as regular with RMA Viewer. 

Im gonna put some images of how somes models show up fine, while others just not, but im sure that we will eventually find a way to solve this. That´s all!
g.png

i'm really excited to try this out! do i need amazing pc specs for it to work, though? i'm doing most of this on a humble laptop ... :'D
i'm also looking for the model of gatto (embalmer skin). were you able to unpack unreleased skins as well?
edit: and did the files have their names? the string of numbers is hard to manage T_T

I think you don't need good specs to do it, it's just file extracting and previewing low poly 3d models. 
Sadly, with the files being corrupted you can't save any model, even if it looks fine in the preview. You can only save as.obj, but it doesn't include the rig of the model. I'm looking for ways to get this files extracted without being corrupted, but I haven't got anything yet.
## Post #127
- Username: gardener
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Apr 03, 2023 11:24 am
- Post datetime: 2023-08-12T17:13:04+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

here's some stuff i found about the different NPKs -

chr.npk is the oldest one, it hasn't been updated in a few years (2021 iirc). includes older skins, unreleased, and beta assets. (soul catcher, lady truth, old bloody textures were found here)
chr.part.a_1.npk and chr.part.b_1.npk are a middleground basically (idk how else to explain this). it has a mix of older stuff and semi-newer stuff (journalist, ashes of memory norton was here).
chr.part.a.npk and chr.part.b.npk are the newest assets of the game. if you're looking for new essence data or newly added characters, look here. (i found the recent danganronpa crossover skins, anniversary ada + emil + joseph here)

use RMAViewer as normal to view them! if you want the new BMS script for the part npks, feel free to pm me
## Post #128
- Username: Blaze Modz
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Dec 28, 2015 8:00 am
- Post datetime: 2023-08-12T19:06:57+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from gardener ↑Sun Aug 13, 2023 1:13 am at Sun Aug 13, 2023 1:13 am
>
> 
here's some stuff i found about the different NPKs -

chr.npk is the oldest one, it hasn't been updated in a few years (2021 iirc). includes older skins, unreleased, and beta assets. (soul catcher, lady truth, old bloody textures were found here)
chr.part.a_1.npk and chr.part.b_1.npk are a middleground basically (idk how else to explain this). it has a mix of older stuff and semi-newer stuff (journalist, ashes of memory norton was here).
chr.part.a.npk and chr.part.b.npk are the newest assets of the game. if you're looking for new essence data or newly added characters, look here. (i found the recent danganronpa crossover skins, anniversary ada + emil + joseph here)

use RMAViewer as normal to view them! if you want the new BMS script for the part npks, feel free to pm me
You're an absolute angel for all your help, thank you so much ♥
## Post #129
- Username: gardener
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Apr 03, 2023 11:24 am
- Post datetime: 2023-08-13T19:47:46+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

if any of you have luck finding identity v files including text (upcoming skin names, letters for birthdays etc) let me know! i've looked through several of the npks with no luck
## Post #130
- Username: tresvs
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Aug 12, 2023 8:32 am
- Post datetime: 2023-08-14T21:31:40+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from gardener ↑Mon Aug 14, 2023 3:47 am at Mon Aug 14, 2023 3:47 am
>
> 
if any of you have luck finding identity v files including text (upcoming skin names, letters for birthdays etc) let me know! i've looked through several of the npks with no luck
If I'm not wrong, usually in video games all the texts are divided into different files according to the translation language, like one for English, Chinese, Japanese, etc. And also, the chinese one should have more and newer texts than the others, since the game its originally chinese
## Post #131
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2023-08-14T22:33:20+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

I recently extracted a few files from a game called Mission Zero and they look to be unencrypted/decompressed now but I can't view the contents with any of the tools in this thread, maybe I'm missing a step, anyone recognize what can be done with these kind of files?:

```
0010h: 00 00 F0 C1 00 00 B4 C2 00 00 C8 42 40 3A 04 42  ..ðÁ..´Â..ÈB@:.B 
0020h: 00 00 20 41 00 00 80 3F 64 00 00 00 64 00 00 00  .. A..€?d...d... 
0030h: 00 00 80 40 D1 8A 00 00 69 01 00 00 41 0B 00 00  ..€@ÑŠ..i...A... 
0040h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................ 
0050h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................ 
0060h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................ 
0070h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................ 
0080h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................ 
0090h: 00 00 00 00 00 00 00 00 04 00 00 00 00 00 00 00  ................ 
00A0h: 80 30 00 00 00 00 41 00 00 00 00 00 00 00 00 00  €0....A......... 
00B0h: 7C 1E 80 10 00 04 23 00 00 00 00 00 00 00 00 00  |.€...#......... 
00C0h: 00 00 00 00 00 00 00 00 00 00 00 00 62 00 00 00  ............b... 
00D0h: C0 03 0C 00 00 00 00 00 00 00 00 00 00 00 00 00  À............... 
00E0h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 30  ...............0 
00F0h: C0 03 00 00 C2 21 03 00 00 00 00 00 00 00 00 00  À...Â!.......... 
0100h: 00 00 D8 77 30 4C 00 00 E0 3F 00 00 80 41 00 C0  ..Øw0L..à?..€A.À 
0110h: 08 00 00 00 00 00 04 C0 00 00 00 04 00 00 00 00  .......À........ 
0120h: 00 00 00 00 00 80 07 00 00 00 00 00 00 00 00 00  .....€.......... 
0130h: 80 FF FF FF FF FF 0F 02 00 00 00 C0 FF 1F F4 7B  €ÿÿÿÿÿ.....Àÿ.ô{ 
0140h: C6 D3 FC FF EF EF FF 37 3C 00 00 00 00 E0 1F 80  ÆÓüÿïïÿ7<....à.€ 
0150h: 09 03 03 00 00 02 08 00 00 00 00 00 00 18 00 00  ................ 
0160h: 00 00 00 00 C0 00 A0 03 81 87 04 40 00 38 02 00  ....À. .
```


```
0010h: ED FA F5 16 01 0D 15 BC 00 00 00 F0 44 53 49 47  íúõ....¼...ðDSIG 
0020h: 00 00 00 01 01 0D 15 B4 00 00 00 08 47 44 45 46  .......´....GDEF 
0030h: 97 0D 32 42 01 0D 16 AC 00 00 06 D2 47 50 4F 53  —.2B...¬...ÒGPOS 
0040h: 6F F5 51 CA 01 0D 1D 80 00 00 A2 E4 47 53 55 42  oõQÊ...€..¢äGSUB 
0050h: 12 48 6B 7B 01 0D C0 64 00 03 15 10 4F 53 2F 32  .Hk{..Àd....OS/2 
0060h: 96 9D 44 95 00 00 01 78 00 00 00 60 63 6D 61 70  –
```


```
0010h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................ 
0020h: 71 1A 05 00 01 24 08 00 24 00 00 00 04 00 04 00  q....$..$....... 
0030h: 00 00 10 00 10 00 00 00 4E 4E 4E 4E 53 82 DA 53  ........NNNNS‚ÚS 
0040h: A9 41 00 8A 5A E7 5C E3 FF 1D FB 9C 54 00 00 00  ©A.ŠZç\ãÿ.ûœT... 
0050h: 08 00 08 00 00 00 20 00 40 00 00 00 4E 4E 4E 4E  ...... .@...NNNN 
0060h: 51 30 F5 1A F3 BF 3E D5 D4 F6 47 56 90 CF F4 38  Q0õ.ó¿>ÕÔöGV
```
## Post #132
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-08-15T01:06:30+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

@GDL: NetEase is using two in-house engines - NeoX and Messiah. Usually you can guess them by game archives, npk and mpk (N and M respectively). This topic is dedicated to NeoX based games, while your game is on Messiah. Don't know about meshes, but textures can be converted with texture script from here, see Netease folder: [viewtopic.php?t=26884](https://forum.xentax.com/viewtopic.php?t=26884)
## Post #133
- Username: gardener
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Apr 03, 2023 11:24 am
- Post datetime: 2023-08-15T19:28:49+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from tresvs ↑Tue Aug 15, 2023 5:31 am at Tue Aug 15, 2023 5:31 am
>
> 
gardener wrote: ↑Mon Aug 14, 2023 3:47 am
if any of you have luck finding identity v files including text (upcoming skin names, letters for birthdays etc) let me know! i've looked through several of the npks with no luck

If I'm not wrong, usually in video games all the texts are divided into different files according to the translation language, like one for English, Chinese, Japanese, etc. And also, the chinese one should have more and newer texts than the others, since the game its originally chinese

i haven't been able to find any of the texts at all. i'm assuming they're hidden within another filetype
## Post #134
- Username: wheretfami
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 25, 2023 3:09 am
- Post datetime: 2023-08-24T19:15:12+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from gardener ↑Wed Aug 16, 2023 3:28 am at Wed Aug 16, 2023 3:28 am
>
> 
tresvs wrote: ↑Tue Aug 15, 2023 5:31 am
gardener wrote: ↑Mon Aug 14, 2023 3:47 am
if any of you have luck finding identity v files including text (upcoming skin names, letters for birthdays etc) let me know! i've looked through several of the npks with no luck

If I'm not wrong, usually in video games all the texts are divided into different files according to the translation language, like one for English, Chinese, Japanese, etc. And also, the chinese one should have more and newer texts than the others, since the game its originally chinese


i haven't been able to find any of the texts at all. i'm assuming they're hidden within another filetype
nope, texts and some other things are stored in script.npk , but output was encrypted


if you're into reverse engineering idv, dm me in discord: mihoyoagent
## Post #135
- Username: aarontaro
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 27, 2023 7:21 am
- Post datetime: 2023-08-27T19:23:09+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

hai everyone :3

i was wondering if anyone had a fix for this error when saving IQE files?


i'm currently ripping files from identity v and i've never encountered this issue except on ONE model (the halberd of silence one, looks like this.)


any help would be greatly appreciated!! i noticed that someone else back in 2021 had the same issue, but i'm not sure if they ever got it fixed?
if it at all helps, i'll include the .dat file that i am trying to save the IQE from.
[https://drive.google.com/file/d/1jCEg7K ... sp=sharing](https://drive.google.com/file/d/1jCEg7KEssElneNjELnjjASyBusi_yR8z/view?usp=sharing)
## Post #136
- Username: SaraKale
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 23, 2023 5:10 pm
- Post datetime: 2023-09-01T11:15:04+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Hello everyone, I need help! Does anyone know the game Xuan Yuan Sword: Dragon Dance Cloud? 
Website: [https://sword.163.com/index.html](https://sword.163.com/index.html), you can find the download link on the right side.
I've also uploaded the char.npk file separately for download: [https://drive.google.com/file/d/1OaB48U ... drive_link](https://drive.google.com/file/d/1OaB48U7oc4uxguBSdNd4z2PDAg2DpCZz/view?usp=drive_link)
I've tried using the quickbms and nxpk.bms scripts to read char.npk,  but it's not working. Do I need to decrypt this file? How can I do that? I'm not a programmer, I'm sorry... If there are any steps, please let me know. I really need your help! Thank you!
## Post #137
- Username: pancakesaurus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 18, 2023 5:36 am
- Post datetime: 2023-09-22T04:46:30+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

Is there a new quickbms scrip for onmyoji npks ?
## Post #138
- Username: Blaze Modz
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Dec 28, 2015 8:00 am
- Post datetime: 2023-10-06T19:02:15+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from aarontaro ↑Mon Aug 28, 2023 3:23 am at Mon Aug 28, 2023 3:23 am
>
> 
hai everyone :3

i was wondering if anyone had a fix for this error when saving IQE files?


i'm currently ripping files from identity v and i've never encountered this issue except on ONE model (the halberd of silence one, looks like this.)


any help would be greatly appreciated!! i noticed that someone else back in 2021 had the same issue, but i'm not sure if they ever got it fixed?
if it at all helps, i'll include the .dat file that i am trying to save the IQE from.
https://drive.google.com/file/d/1jCEg7K ... sp=sharing
Sorry I don't check this forum often, but that model in particular doesn't work, unfortunately. It was one of the main ones I wanted to rip, but the software refuses. Naiad in particular seems to have a lot of skins that refuse to export. The best method is likely to get the model another way or export as OBJ ^^;
## Post #139
- Username: aarontaro
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 27, 2023 7:21 am
- Post datetime: 2023-10-21T01:18:06+00:00
- Post Title: Re: Netease Games Tool + Research (Onmyoji, RoS, RMA etc.)

> Reply from Blaze Modz ↑Sat Oct 07, 2023 3:02 am at Sat Oct 07, 2023 3:02 am
>
> 
aarontaro wrote: ↑Mon Aug 28, 2023 3:23 am
hai everyone :3

i was wondering if anyone had a fix for this error when saving IQE files?


i'm currently ripping files from identity v and i've never encountered this issue except on ONE model (the halberd of silence one, looks like this.)


any help would be greatly appreciated!! i noticed that someone else back in 2021 had the same issue, but i'm not sure if they ever got it fixed?
if it at all helps, i'll include the .dat file that i am trying to save the IQE from.
https://drive.google.com/file/d/1jCEg7K ... sp=sharing

Sorry I don't check this forum often, but that model in particular doesn't work, unfortunately. It was one of the main ones I wanted to rip, but the software refuses. Naiad in particular seems to have a lot of skins that refuse to export. The best method is likely to get the model another way or export as OBJ ^^;

yeah, after looking through the files and finding the duplicates of said model and such i learned that it just. doesnt work and ended up rigging it myself lol
i appreciate the response though!! :3
