## Post #1
- Username: Sadiosys
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 23, 2011 5:17 pm
- Post datetime: 2011-11-23T13:59:20+00:00
- Post Title: Cosmic break [.kar] files

Hello Xentax!
Cosmic break - japanese MMOFPS(massive multiplayer online first person shooter).
All game resources like textures, sounds and maybe main game executable are packed inside of .kar archives with some algorithm.
[http://rghost.ru/32042611](http://rghost.ru/32042611)
[http://rghost.ru/32042681](http://rghost.ru/32042681)
stage.kar - maps(maybe some images inside)
 sample01.nsd -...
 sample02.nsd -...
 sample03.nsd - these files are maps created with ingame map editor so they arent inside .kar archive
 CosmicBreak.exe - launcher that starts game and updates it; launcher downloads udates in form of small udpate_0911.kar files and later merges them with existing game archives.
 cb.kar - was inside of folder Cosmicbreak/programs/ and it seems to be main game exe or something like that
 setting.kar - was near cb.kar
 cosmic.exe - this was near cb.kar; now some info i got. Game can be started via launcher or via cosmic.exe with parameter "launch". When cosmic.exe started it accesses different dlls, java VM(game built using some java technology and has Cosmicbreak/jre folder), and then cb.kar. After this game accesses different archives with images/sounds/etc and game window appears.
[http://rghost.ru/31488321](http://rghost.ru/31488321) - images.kar - images, and I think that there might be .png 
Thats game client if it helps(500mb only):
[http://download.getamped.com/CosmicBreakSetup_eng.exe](http://download.getamped.com/CosmicBreakSetup_eng.exe)

I need to extract game resources like models, sounds, images. Packing it back will be wonderful too but not must have. Too bad I  Im not knowledgeable enough to understand how game decrypts resources.
UPLOADED FILES AGAIN.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-13T23:39:10+00:00
- Post Title: Cosmic break [.kar] files

Sorry for necropost. [Here](http://www.progamercity.net/code-specific/5067-java-cosmic-break-kar-encryption-decryption-algo.html) java classes for work with KAR archives. Maybe some one make unpacker
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-14T00:43:07+00:00
- Post Title: Cosmic break [.kar] files

Can you post it here? My account's gone lurker mode again LOL
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-14T06:00:14+00:00
- Post Title: Cosmic break [.kar] files

Here
[KarSource_Full.rar](https://xentaxbackup.github.io/file/5661_KarSource_Full.rar)
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-14T16:39:02+00:00
- Post Title: Cosmic break [.kar] files

Ok Java Tool by toptaran 

Launch:

```

-l afilename #list files from [afilename] kar archive
-x afilename efilename ofilename passwod
  extract [efilename] to [ofilename] [afilename] kar archive
  [password] optional
```

Listing:

```
java -jar "KarSource.jar" -l "img.kar"
```

Extracting:

```
java -jar "KarSource.jar" -x "img.kar" "/arena/cg_loadingstg1_poyeen05.png" "D:/Out/arena/cg_loadingstg1_poyeen05.png"
```


Files encrypted.
[KarExt.zip](https://xentaxbackup.github.io/file/5662_KarExt.zip)
## Post #6
- Username: futaradragon
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Feb 15, 2014 3:34 pm
- Post datetime: 2014-02-15T10:15:39+00:00
- Post Title: Cosmic break [.kar] files

I try to test 
java -jar "KarSource.jar" -x "image.kar" "/arena/cg_loadingstg1_poyeen05.png" "E:/cosmicbreak/cg_loadingstg1_poyeen05.png"
but I can't open "cg_loadingstg1_poyeen05.png" extracted from image.kar file
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-02-15T11:36:31+00:00
- Post Title: Cosmic break [.kar] files

> Reply from futaradragon
>
> I try to test 
java -jar "KarSource.jar" -x "image.kar" "/arena/cg_loadingstg1_poyeen05.png" "E:/cosmicbreak/cg_loadingstg1_poyeen05.png"
but I can't open "cg_loadingstg1_poyeen05.png" extracted from image.kar file
Because files inside encrypted. For decrypt need password. Ask to toptaran pwd.
## Post #8
- Username: futaradragon
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Feb 15, 2014 3:34 pm
- Post datetime: 2014-02-15T11:47:11+00:00
- Post Title: Cosmic break [.kar] files

> Reply from Ekey
>
> 
Because files inside encrypted. For decrypt need password. Ask to toptaran pwd.

Thankyou vary much.
Do you have contact with him? I don't have anything about him. I can read game map binary but need resource for relocate them.
## Post #9
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-02-15T20:48:48+00:00
- Post Title: Cosmic break [.kar] files

> Reply from futaradragon
>
> 
Thankyou vary much.
Do you have contact with him?
No sorry.
## Post #10
- Username: futaradragon
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Feb 15, 2014 3:34 pm
- Post datetime: 2014-02-16T08:08:36+00:00
- Post Title: Cosmic break [.kar] files

Here Custom Map with NPCs
(Normal Map Editor Can't add NPC to map)
[Link](http://www.youtube.com/watch?v=9DRV7oMx1-U&feature=youtu.be)
## Post #11
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-02-16T14:03:12+00:00
- Post Title: Cosmic break [.kar] files

Maybe later i make tool for unpack with decrypt file data.
## Post #12
- Username: futaradragon
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Feb 15, 2014 3:34 pm
- Post datetime: 2014-02-17T02:34:37+00:00
- Post Title: Cosmic break [.kar] files

> Reply from Ekey
>
> Maybe later i make tool for unpack with decrypt file data.

Thankyou very much ^^
If decrypt tool finish, I will make custom map editor tool for customize more than normal editor.
## Post #13
- Username: futaradragon
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Feb 15, 2014 3:34 pm
- Post datetime: 2014-02-21T14:48:37+00:00
- Post Title: Cosmic break [.kar] files

I will wait everyday for decrypt tool; Thankyou for help ^^;
## Post #14
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-02-21T19:40:54+00:00
- Post Title: Cosmic break [.kar] files

I do not plan now anything.
## Post #15
- Username: futaradragon
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Feb 15, 2014 3:34 pm
- Post datetime: 2014-02-22T03:32:53+00:00
- Post Title: Cosmic break [.kar] files

> Reply from Ekey
>
> I do not plan now anything.
 not a problem because I know when I can use files in stage.kar; That mean I can make more tools for customize map more and more fun in cosmicbreak; I can wait.
## Post #16
- Username: futaradragon
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Feb 15, 2014 3:34 pm
- Post datetime: 2014-04-17T04:27:43+00:00
- Post Title: Re: Cosmic break [.kar] files

And... When decrypt tool finish?..
## Post #17
- Username: Cerivano
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 19, 2014 2:44 am
- Post datetime: 2014-11-18T18:46:58+00:00
- Post Title: Re: Cosmic break [.kar] files

Could you tell me how you're making custom stages with NPCs in them? I've been looking into it for a while now, if you can help, it'd be appreciated.
## Post #18
- Username: futaradragon
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Feb 15, 2014 3:34 pm
- Post datetime: 2014-11-19T02:26:17+00:00
- Post Title: Re: Cosmic break [.kar] files

> Reply from Cerivano
>
> Could you tell me how you're making custom stages with NPCs in them? I've been looking into it for a while now, if you can help, it'd be appreciated.

I make map in my editor program. Not in offical stage editor program. But I don't know some asset files in kar format that can help me make all npc add to custom map. I try to decompress kar file but fail everytime.
## Post #19
- Username: futaradragon
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Feb 15, 2014 3:34 pm
- Post datetime: 2015-12-31T02:21:48+00:00
- Post Title: Re: Cosmic break [.kar] files

I already release "Cosmic Map Breaker" program this program can help for create epic map
link here
[http://www.cosmicbreakfanforum.com/t159 ... map-editor](http://www.cosmicbreakfanforum.com/t15900-cosmic-map-breaker-the-cosmic-break-extra-map-editor)
But I need to unpack stage.kar for use NPC ID in them
## Post #20
- Username: OniZero
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 13, 2022 12:36 am
- Post datetime: 2022-05-12T16:52:23+00:00
- Post Title: Re: Cosmic break [.kar] files

Apologies for the mega necro but here's a leak of the cosmic break files from the old beta test

<links deleted by moderator, sharing assets is forbidden here>
