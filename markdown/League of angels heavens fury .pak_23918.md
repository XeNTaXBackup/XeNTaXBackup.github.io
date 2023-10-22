## Post #1
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-05-20T16:15:13+00:00
- Post Title: League of angels heavens fury .pak

Hello!I was trying to get the models inside the .pak files of this game, a  mate that checking it says is compressed (LZMA) and encrypted (CRC32 + XOR (enc table (4096))). To be honest don't know how to a make a bms script that can do it, but what I could say is that the game updates while you playing, so it open the .pak or generate another to add the new data. Another solution is get the cdn from where it downloads the assets, and get the data throught it, anyways if you unzip the game.zip there is a log file maybe someone more experienced can find it usefull for decrypt the file! hope so! Thanks in advance.
 
[https://www.mediafire.com/file/6hfpic95 ... Y.zip/file](https://www.mediafire.com/file/6hfpic95hy7gzyf/LOA_HEAVENS_FURY.zip/file)
## Post #2
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-05-27T06:35:09+00:00
- Post Title: League of angels heavens fury .pak

!bump!
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2021-11-08T18:16:53+00:00
- Post Title: League of angels heavens fury .pak

Repo with my code [here](https://github.com/Ekey/LoAHF.PAK.Tool/)
## Post #4
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-11-15T05:02:41+00:00
- Post Title: League of angels heavens fury .pak

> Reply from Ekey ↑Tue Nov 09, 2021 2:16 am at Tue Nov 09, 2021 2:16 am
>
> 
Repo with my code here
! I just tested the tool! It was unpacking unknows files but it thrown error at certain point, and also the unpacked files have JMT1DXT1 and JMT1COLA in their headers xD. You were able to get any 3d model?  



1.png (28.57 KiB) Viewed 235 times
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2021-11-15T13:46:29+00:00
- Post Title: League of angels heavens fury .pak

> Reply from moonpaladin ↑Mon Nov 15, 2021 1:02 pm at Mon Nov 15, 2021 1:02 pm
>
> 
! I just tested the tool! It was unpacking unknows files
Just copy the Projects folder to the executable folder and you get files with real names 

like this 


> Reply from moonpaladin ↑Mon Nov 15, 2021 1:02 pm at Mon Nov 15, 2021 1:02 pm
>
> 
it thrown error at certain point
There is a library in the data_1.pak archive, this file compressed with non standard method. I have a code to check of this file, provided that it knows its real name and not a hash. Due to the fact that you did not copy the Projects folder to the executable folder, it could not identify real name of this file and called SNAPPY.iDecompress function instead of SNAPPY.iDecompressByOffset. This has been [fixed](https://github.com/Ekey/LoAHF.PAK.Tool/commit/00c21713b0ade0781c141578ca4a5a9787e57f44) anyway 

> Reply from moonpaladin ↑Mon Nov 15, 2021 1:02 pm at Mon Nov 15, 2021 1:02 pm
>
> 
unpacked files have JMT1DXT1 and JMT1COLA in their headers xD
Yeah, it's a custom formats of textures

> Reply from moonpaladin ↑Mon Nov 15, 2021 1:02 pm at Mon Nov 15, 2021 1:02 pm
>
> 
You were able to get any 3d model?
I don't work with 3D Models or Textures. You can try to ask it in [this forum section](https://forum.xentax.com/viewforum.php?f=16)
## Post #6
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-11-15T14:30:22+00:00
- Post Title: League of angels heavens fury .pak

Thank you Ekey! it worked
## Post #7
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2021-11-20T06:12:22+00:00
- Post Title: League of angels heavens fury .pak

> Reply from moonpaladin ↑Mon Nov 15, 2021 10:30 pm at Mon Nov 15, 2021 10:30 pm
>
> 
Thank you Ekey! it worked

could you please share ur compiled unpacker.exe to me? i dun hv any knowledge to do that so please
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2021-11-20T10:21:02+00:00
- Post Title: League of angels heavens fury .pak

> Reply from wansf ↑Sat Nov 20, 2021 2:12 pm at Sat Nov 20, 2021 2:12 pm
>
> 
could you please share ur compiled unpacker.exe to me? i dun hv any knowledge to do that so please
[https://github.com/Ekey/LoAHF.PAK.Tool/releases](https://github.com/Ekey/LoAHF.PAK.Tool/releases)
## Post #9
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2021-11-20T12:13:48+00:00
- Post Title: League of angels heavens fury .pak

> Reply from Ekey ↑Sat Nov 20, 2021 6:21 pm at Sat Nov 20, 2021 6:21 pm
>
> 
wansf wrote: ↑Sat Nov 20, 2021 2:12 pm
could you please share ur compiled unpacker.exe to me? i dun hv any knowledge to do that so please 

https://github.com/Ekey/LoAHF.PAK.Tool/releases

THANKS!
## Post #10
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2021-11-23T16:11:25+00:00
- Post Title: League of angels heavens fury .pak

> Reply from Ekey ↑Sat Nov 20, 2021 6:21 pm at Sat Nov 20, 2021 6:21 pm
>
> 
wansf wrote: ↑Sat Nov 20, 2021 2:12 pm
could you please share ur compiled unpacker.exe to me? i dun hv any knowledge to do that so please 

https://github.com/Ekey/LoAHF.PAK.Tool/releases

Hi Ekey,

Thanks for the tool. It works perfectly. Anyway I found a new GTarcade game , League of Angels: chaos , recently released. Your tool works with those .pak too anyway some filenames are missing. If you want to take a look here you find some samples [viewtopic.php?f=10&t=24762&p=179802#p179802](https://forum.xentax.com/viewtopic.php?f=10&t=24762&p=179802#p179802)
## Post #11
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2021-11-23T22:38:03+00:00
- Post Title: League of angels heavens fury .pak

This game is currently in closed beta testing, APK and IPA are not available for downloading.

Does anyone have an IPA for iOS?
## Post #12
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2021-11-26T14:10:26+00:00
- Post Title: League of angels heavens fury .pak

> Reply from Ekey ↑Wed Nov 24, 2021 6:38 am at Wed Nov 24, 2021 6:38 am
>
> 
This game is currently in closed beta testing, APK and IPA are not available for downloading.

Does anyone have an IPA for iOS?

No .ipa available. Only apk (90 mb) + download in game of 700-800 mb of .pak.
