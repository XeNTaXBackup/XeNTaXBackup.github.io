## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-11-27T07:01:01+00:00
- Post Title: AssaultFire Upk Assets Extractor

A tool for extracting/converting skeletal/static meshes & textures from the upk archives of AssaultFire even if the headers are encrypted.

Since I've added skin support to my binary FBX builder, this became my first released tool with skeleton support. Though it was merely intended to be a test, the results turned out to be far better than expected, despite the horrible skin format.   

Features:
-Converting skeletal/static meshes to FBX format with material groups, lower LODs are ignored;
-Converting textures to PVR format, currently supported formats including DXT1, DXT5, L8 and ARGB32;

Usage:
Double click on the executable and follow the leads, or use batch commands.

Notes:
1. Files sharing the same names will be overwritten. Mostly those are thumbnail textures and other useless data.
2. Upk files suffixed by "_SF" are compressed, so you need to do the same thing AGAIN on the resulting upk files.
3. Some low res textures from the compressed upk arcs are ignored coz I have no interest in supporting them.

Some examples of the characters:


[AFUpkExtractor.zip](https://xentaxbackup.github.io/file/16300_AFUpkExtractor.zip)
## Post #2
- Username: phay008
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 11, 2016 11:59 am
- Post datetime: 2018-11-30T03:54:23+00:00
- Post Title: AssaultFire Upk Assets Extractor

Thank you so much!!!!Is AssaultFire a First Person Shooter game?
## Post #3
- Username: Naomi9
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Nov 30, 2018 6:46 pm
- Post datetime: 2018-11-30T10:49:29+00:00
- Post Title: AssaultFire Upk Assets Extractor

Thank you !!!What program do you use for 3D design?
## Post #4
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2018-11-30T11:39:42+00:00
- Post Title: AssaultFire Upk Assets Extractor

sorry but ive no idea how to deal with PRV , is there anyway to convert that into PNG or something common?
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-11-30T12:03:57+00:00
- Post Title: AssaultFire Upk Assets Extractor

> Reply from phay008
>
> Thank you so much!!!!Is AssaultFire a First Person Shooter game?
Guess so.  

> Reply from Naomi9
>
> Thank you !!!What program do you use for 3D design?
3Ds Max.

> Reply from wansf
>
> sorry but ive no idea how to deal with PRV , is there anyway to convert that into PNG or something common?
You'll need PVRTexTool to view/convert them. Also you can use the following batch command to convert them to png:

```
for %%f in (*.pvr) do PVRTexToolCLI.exe -i "%%f" -d -f r8g8b8a8
```

Of course you have to place the location of PVRTexToolCLI into the environment variable PATH first if you want to run it under any locations.
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-11-30T12:04:23+00:00
- Post Title: AssaultFire Upk Assets Extractor

Updated v1.1.1.
Fixed a few issues.

Tested on almost all files.
## Post #7
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2018-11-30T13:03:35+00:00
- Post Title: AssaultFire Upk Assets Extractor

> Reply from Bigchillghost
>
> phay008 wrote:Thank you so much!!!!Is AssaultFire a First Person Shooter game? 
Guess so.  
Naomi9 wrote:Thank you !!!What program do you use for 3D design?
3Ds Max.
wansf wrote:sorry but ive no idea how to deal with PRV , is there anyway to convert that into PNG or something common?
You'll need PVRTexTool to view/convert them. Also you can use the following batch command to convert them to png:
Code: Select allfor %%f in (*.pvr) do PVRTexToolCLI.exe -i "%%f" -d -f r8g8b8a8
Of course you have to place the location of PVRTexToolCLI into the environment variable PATH first if you want to run it under any locations.

thanks
## Post #8
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2018-12-01T02:01:18+00:00
- Post Title: AssaultFire Upk Assets Extractor

oh they hv no bones
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-05-29T11:41:11+00:00
- Post Title: AssaultFire Upk Assets Extractor

Updated v1.2.1.
Now skin info is supported!
## Post #10
- Username: FakessIDos
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Apr 24, 2019 12:53 am
- Post datetime: 2019-11-26T15:59:58+00:00
- Post Title: AssaultFire Upk Assets Extractor

Thank you very much,But it doesn't seem to support animation,This is a pity.Can you make it support export animations?That would be great!!!!!Thank you again!!!
## Post #11
- Username: FakessIDos
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Apr 24, 2019 12:53 am
- Post datetime: 2019-12-04T14:34:04+00:00
- Post Title: AssaultFire Upk Assets Extractor

I'm sorry to bother you again,Recently,tencent china Testing a game,The name is called CROSSFIRE HD,Like AssaultFire, it's a first-person FPS game.The game was made by UE3,But the UPK file is encrypted,I will upload an example, I hope you can help me.THANK YOU AGAIN!!!!!!!!!!!!!    
EXAMPLE LINK:[https://1drv.ms/u/s!AsJ4OJwflp2NgR54u4j ... I?e=IZgsZA](https://1drv.ms/u/s!AsJ4OJwflp2NgR54u4jigildHC9I?e=IZgsZA)
## Post #12
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-12-05T03:03:06+00:00
- Post Title: AssaultFire Upk Assets Extractor

> Reply from FakessIDos ↑Wed Dec 04, 2019 10:34 pm at Wed Dec 04, 2019 10:34 pm
>
> The game was made by UE3,But the UPK file is encrypted
Nothing is encrypted in this file. Go ask the author of umodel.
## Post #13
- Username: FakessIDos
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Apr 24, 2019 12:53 am
- Post datetime: 2019-12-05T07:40:43+00:00
- Post Title: AssaultFire Upk Assets Extractor

Thank you for your attention,But I get an error unpacking with UMODEL
## Post #14
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2019-12-09T16:13:13+00:00
- Post Title: AssaultFire Upk Assets Extractor

Awesome Tool！
By the way,clould you please export something else from this game？Such as the sounds from CookedPC\Sounds.
## Post #15
- Username: 1349985342
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 06, 2019 2:56 pm
- Post datetime: 2020-08-20T07:10:19+00:00
- Post Title: AssaultFire Upk Assets Extractor

Hello, could you please share the source code of the tool? Or I really hope that your tool can support one-key batch automatic extraction of UPK files in multiple folders.Because CookedPC has so many UPK folders, it's inefficient to manually click one by one.
## Post #16
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-08-20T10:28:48+00:00
- Post Title: Re: AssaultFire Upk Assets Extractor

> Reply from 1349985342 ↑Thu Aug 20, 2020 3:10 pm at Thu Aug 20, 2020 3:10 pm
>
> 
could you please share the source code of the tool?
Absolutely no.

> Reply from 1349985342 ↑Thu Aug 20, 2020 3:10 pm at Thu Aug 20, 2020 3:10 pm
>
> 
Because CookedPC has so many UPK folders, it's inefficient to manually click one by one.
If you don't understand how to use batch commands, google for it.
## Post #17
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2020-11-27T12:57:46+00:00
- Post Title: Re: AssaultFire Upk Assets Extractor

Thankyou for the extractor Bigchillghost, works fine, much appreciated.

After downloading PVRTexTool, when trying to open any of the .pvr files I recieve an error message 'This file cannot be opened'

Attached sample character file:

[https://drive.google.com/file/d/1aAweAu ... sp=sharing](https://drive.google.com/file/d/1aAweAuyK9SaEovHtcqu13LJwWMzVoxLE/view?usp=sharing)

Thanks
## Post #18
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-11-28T05:37:35+00:00
- Post Title: Re: AssaultFire Upk Assets Extractor

> Reply from X3D ↑Fri Nov 27, 2020 8:57 pm at Fri Nov 27, 2020 8:57 pm
>
> 
After downloading PVRTexTool, when trying to open any of the .pvr files I recieve an error message 'This file cannot be opened'
Yeah, it appears that PVRTexTool had introduced some bugs since v2019 R2.  Reinstall your PVRTexTool to v2018 R2 instead:
[https://www.imaginationtech.com/develop ... downloads/](https://www.imaginationtech.com/developers/powervr-sdk-tools/legacy-downloads/)

P.S. Version 2019 R1.1 will work too but I just don't appreciate the old fashion UI.
## Post #19
- Username: BeatKom
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 03, 2018 10:34 am
- Post datetime: 2021-01-24T19:24:18+00:00
- Post Title: Re: AssaultFire Upk Assets Extractor

Hello,
thank you for your tool!
But I found a few weapon upk files of this game where the tool only extracts their meshes but not textures,
could you please help to look into them?
sample files: [https://drive.google.com/file/d/121kE8C ... sp=sharing](https://drive.google.com/file/d/121kE8CJTehWa3RbpxDUBEfNqnvnLvze6/view?usp=sharing)
## Post #20
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-01-27T16:10:55+00:00
- Post Title: Re: AssaultFire Upk Assets Extractor

> Reply from BeatKom ↑Mon Jan 25, 2021 3:24 am at Mon Jan 25, 2021 3:24 am
>
> 
But I found a few weapon upk files of this game where the tool only extracts their meshes but not textures,
could you please help to look into them?
Quick patch:
[AFUpkExtractor-2021-01-28.zip](https://xentaxbackup.github.io/file/19402_AFUpkExtractor-2021-01-28.zip)
## Post #21
- Username: BeatKom
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 03, 2018 10:34 am
- Post datetime: 2021-01-27T17:09:15+00:00
- Post Title: Re: AssaultFire Upk Assets Extractor

Great! Thanks a lot!
## Post #22
- Username: ice
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 12, 2019 1:24 am
- Post datetime: 2021-01-31T16:21:46+00:00
- Post Title: Re: AssaultFire Upk Assets Extractor

Can export animations be supported？Or convert to an Upk file supported by Umodel！
## Post #23
- Username: Timiy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 04, 2021 3:50 pm
- Post datetime: 2021-02-04T07:54:56+00:00
- Post Title: Re: AssaultFire Upk Assets Extractor

AssaultFire Upk Assets Extractor
## Post #24
- Username: DMGAME
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Mar 24, 2021 4:45 pm
- Post datetime: 2021-04-07T07:56:34+00:00
- Post Title: Re: AssaultFire Upk Assets Extractor

Can it support extracting maps?
## Post #25
- Username: LHLingHyun
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Mar 01, 2021 10:48 pm
- Post datetime: 2021-04-22T14:52:45+00:00
- Post Title: Re: AssaultFire Upk Assets Extractor

Although the game version is the latest, there may be some older files in the game.After unpacking, there is no model, only texture files.
[https://drive.google.com/file/d/1qYnlrX ... sp=sharing](https://drive.google.com/file/d/1qYnlrX-tVLxz62v6ncQrKK5o_maVwxzu/view?usp=sharing)
## Post #26
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-04-24T09:28:05+00:00
- Post Title: Re: AssaultFire Upk Assets Extractor

> Reply from LHLingHyun ↑Thu Apr 22, 2021 10:52 pm at Thu Apr 22, 2021 10:52 pm
>
> 
Although the game version is the latest, there may be some older files in the game.After unpacking, there is no model, only texture files.
These files contain static meshes without any dummy bones and the vertex structure is different. But I have no time and desire to deal with it at the moment. You may check if the tool still work for the majority of the characters.
## Post #27
- Username: LHLingHyun
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Mar 01, 2021 10:48 pm
- Post datetime: 2021-04-24T18:55:20+00:00
- Post Title: Re: AssaultFire Upk Assets Extractor

There is a game in the same studio as AssaultFire, using the same game engine. If you have time and interest, I hope you can unpack it. For me you are the most likely to complete it, thank you very much. Here are some samples file.[https://drive.google.com/file/d/1q3P3zR ... sp=sharing](https://drive.google.com/file/d/1q3P3zRWGB7ENlzkWZHunjhmC1jGhgyys/view?usp=sharing)
## Post #28
- Username: DMGAME
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Mar 24, 2021 4:45 pm
- Post datetime: 2021-06-25T07:10:52+00:00
- Post Title: Re: AssaultFire Upk Assets Extractor

> Reply from Bigchillghost ↑Sat Apr 24, 2021 5:28 pm at Sat Apr 24, 2021 5:28 pm
>
> 
LHLingHyun wrote: ↑Thu Apr 22, 2021 10:52 pm
Although the game version is the latest, there may be some older files in the game.After unpacking, there is no model, only texture files.

These files contain static meshes without any dummy bones and the vertex structure is different. But I have no time and desire to deal with it at the moment. You may check if the tool still work for the majority of the characters.
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1-yPKm91vpHfDfrkprcTXolohcIF3L0nC?usp=sharing), [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/18YObfE1anNyTzUTc1wUUJwVI3UgNdAR3?usp=sharing)
Hello there，these files Why Unpacking error？？
## Post #29
- Username: Taoan0211
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 25, 2022 8:09 pm
- Post datetime: 2022-02-25T12:12:01+00:00
- Post Title: Re: AssaultFire Upk Assets Extractor

CrossFire HD
## Post #30
- Username: boy1and2
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 05, 2022 1:29 am
- Post datetime: 2022-03-04T17:39:20+00:00
- Post Title: Re: AssaultFire Upk Assets Extractor

When I try to unpack this file, I see that there is no texture for the face, I think the program is ignoring it
[https://drive.google.com/file/d/13dpWns ... sp=sharing](https://drive.google.com/file/d/13dpWnsrS0SOYzTJA1qRzo7KSJO_6sVET/view?usp=sharing)
## Post #31
- Username: jhgf
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 17, 2023 11:06 pm
- Post datetime: 2023-04-17T15:29:05+00:00
- Post Title: Re: AssaultFire Upk Assets Extractor


## Post #32
- Username: DMGAME
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Mar 24, 2021 4:45 pm
- Post datetime: 2023-05-02T16:55:52+00:00
- Post Title: Re: AssaultFire Upk Assets Extractor

Hello, are you interested in having a look at it again? Recently, the game developer seems to have modified the model and the skeleton, I packaged the model back to the game, the skeleton is wrong, can you help to have a look？
Here are the latest client files
[https://drive.google.com/drive/folders/ ... share_link](https://drive.google.com/drive/folders/1EanhwT2tJsL5Vjk-52OSyx5qeKH0gsWu?usp=share_link)
[ZR588U2~~Q$[~C5ILJ9SICM.png](https://xentaxbackup.github.io/file/23760_ZR588U2~~Q$[~C5ILJ9SICM.png)
## Post #33
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-05-03T01:39:23+00:00
- Post Title: Re: AssaultFire Upk Assets Extractor

> Reply from DMGAME ↑Wed May 03, 2023 12:55 am at Wed May 03, 2023 12:55 am
>
> 
the game developer seems to have modified the model and the skeleton
I have no idea what you're talking about. Tool works fine at my end.



FamilyADA_Body_001.jpg (29.64 KiB) Viewed 140 times



> Reply from DMGAME ↑Wed May 03, 2023 12:55 am at Wed May 03, 2023 12:55 am
>
> 
I packaged the model back to the game, the skeleton is wrong
Packing anything back is never my concern so good luck with that.
## Post #34
- Username: DMGAME
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Mar 24, 2021 4:45 pm
- Post datetime: 2023-05-06T15:54:56+00:00
- Post Title: Re: AssaultFire Upk Assets Extractor

What I want to say is that bone abnormalities occurred after I extracted the model and imported the UDK.  I think maybe there is something wrong with my operation.....  abandon Packing back Game....

Thanks all the same
## Post #35
- Username: degurechaff19
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 02, 2023 4:23 am
- Post datetime: 2023-06-04T16:58:29+00:00
- Post Title: Re: AssaultFire Upk Assets Extractor

does anyone know how or where i can get the animations ?
## Post #36
- Username: Kamuazz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 11, 2021 10:59 pm
- Post datetime: 2023-06-22T15:25:42+00:00
- Post Title: Re: AssaultFire Upk Assets Extractor

Hello, are you interested in taking a look at this file? The file is unpacked with only the model and no texture.

[https://drive.google.com/file/d/18sARc8 ... drive_link](https://drive.google.com/file/d/18sARc8YZ_SzICfPXApybsg6Vgn_SlTXu/view?usp=drive_link)
