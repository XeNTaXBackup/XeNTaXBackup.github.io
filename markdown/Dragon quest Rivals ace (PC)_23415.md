## Post #1
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2021-02-08T09:10:18+00:00
- Post Title: Dragon quest Rivals ace (PC)

I'm interested in extracting the files of the game, but i don't know where to start or if others have already developed a tool for it. in the files there is 2 folders, Chara and Data- i thought that it would be easy to find the files where the characters may be, but when i checked it, it only had 2 folders for characters, with that for the two folders it had one .c3b file and a .tga- which i don't think it is a tga file as when i try to open it, it fails to open. if i had to guess, character 1 and 2 are Terry and Jessica, as those are the two characters in the tutorial while the game finishes downloading, I thought that when it was done it would add more files to the folders but nope, i don't know if the rest of the assets are. either they are in the .bins in the data folder, or stored somewhere else on my pc. if anyone is willing to help that will be appreciated.
## Post #2
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-02-08T09:56:57+00:00
- Post Title: Dragon quest Rivals ace (PC)

I checked it before. The PC and mobile versions have compressed and encrypted files for cocos2D.
The Switch version can acquire unencrypted data. I was able to play c3b on Cocos Editor, but there is no way to convert it.

Files for DQ Rivals cannot be loaded with previously someone created Noesis or blender plugins.
I'm no longer interested in this game and have deleted all the files so I can't do any new information or validation.
## Post #3
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2021-02-08T10:52:51+00:00
- Post Title: Dragon quest Rivals ace (PC)

that is a shame, but at least this gives me some lead, any further information i can find i will post here
## Post #4
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-06-29T12:38:38+00:00
- Post Title: Dragon quest Rivals ace (PC)

The service will end soon. All I have is the terry file I tried during the test.
In the PC / Mobile version, the files are compressed and encrypted. Only the Switch version is unencrypted and available.
[terry.PNG](https://xentaxbackup.github.io/file/20383_terry.PNG)
## Post #5
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2021-07-01T20:53:46+00:00
- Post Title: Dragon quest Rivals ace (PC)

interesting. how long before the servers are down permanently or is that unknown?
## Post #6
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-07-02T01:46:08+00:00
- Post Title: Dragon quest Rivals ace (PC)

Jul 05.
It will end soon. Since the PC version and mobile version are compressed and encrypted, only the Switch version can be used.
## Post #7
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2021-07-02T06:14:09+00:00
- Post Title: Dragon quest Rivals ace (PC)

i should get the files from the switch then, and soon
## Post #8
- Username: Redistrer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 12, 2019 10:16 pm
- Post datetime: 2021-08-26T03:18:09+00:00
- Post Title: Dragon quest Rivals ace (PC)

I could not find any way to convert c3b files. (I found a converter that can convert fbx to c3b though).
Cocos supports playing c3b files, but there is no way to export them. Also, I don't know how to import animated c3b files.

> Reply from einherjar007 ↑Tue Jun 29, 2021 8:38 pm at Tue Jun 29, 2021 8:38 pm
>
> 
The service will end soon. All I have is the terry file I tried during the test.
In the PC / Mobile version, the files are compressed and encrypted. Only the Switch version is unencrypted and available.
How can I import 3D model c3b/Animation c3b into Noesis?
## Post #9
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-08-30T08:38:24+00:00
- Post Title: Dragon quest Rivals ace (PC)

> Reply from Redistrer ↑Thu Aug 26, 2021 11:18 am at Thu Aug 26, 2021 11:18 am
>
> 
I could not find any way to convert c3b files. (I found a converter that can convert fbx to c3b though).
Cocos supports playing c3b files, but there is no way to export them. Also, I don't know how to import animated c3b files.
einherjar007 wrote: ↑Tue Jun 29, 2021 8:38 pm
The service will end soon. All I have is the terry file I tried during the test.
In the PC / Mobile version, the files are compressed and encrypted. Only the Switch version is unencrypted and available.

How can I import 3D model c3b/Animation c3b into Noesis?

It is possible to play c3b models and c3b animations by creating your own viewer with Cocos Editor. I did it before. However, it is just the content that is played in the cocos engine, and it cannot be converted to a general file such as fbx.
As a general, cocos files are irreversible. Also, since it works with OpenGL, Ninja Ripper cannot be used.
## Post #10
- Username: einherjar007
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-08-30T12:03:34+00:00
- Post Title: Dragon quest Rivals ace (PC)

cocos2d is open source so someone could make a noesis plugin to load them if they want.
[https://github.com/cocos2d/cocos2d-x/bl ... tion3D.cpp](https://github.com/cocos2d/cocos2d-x/blob/v4/cocos/3d/CCAnimation3D.cpp)
## Post #11
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-08-30T13:02:25+00:00
- Post Title: Dragon quest Rivals ace (PC)

I actually made a script for that game with anim support a while ago, completely forgot to release it. Will clean it and release it this week


> Reply from chrrox ↑Mon Aug 30, 2021 8:03 pm at Mon Aug 30, 2021 8:03 pm
>
> 
cocos2d is open source so someone could make a noesis plugin to load them if they want.
https://github.com/cocos2d/cocos2d-x/bl ... tion3D.cpp

Why did I bother... Fortunately it was simple enough
## Post #12
- Username: iguniisu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 17, 2019 12:12 am
- Post datetime: 2021-10-25T18:10:00+00:00
- Post Title: Dragon quest Rivals ace (PC)

> Reply from Joschka ↑Mon Aug 30, 2021 9:02 pm at Mon Aug 30, 2021 9:02 pm
>
> 
I actually made a script for that game with anim support a while ago, completely forgot to release it. Will clean it and release it this week

chrrox wrote: ↑Mon Aug 30, 2021 8:03 pm
cocos2d is open source so someone could make a noesis plugin to load them if they want.
https://github.com/cocos2d/cocos2d-x/bl ... tion3D.cpp


Why did I bother... Fortunately it was simple enough

Any news on this? I've been trying to fix a script for the same format based on the structure from [https://github.com/cocos2d-x/fbx-conv/b ... innary.cpp](https://github.com/cocos2d-x/fbx-conv/blob/8104a81d298d4dafd94c10751e44aad7dea7a44a/src/modeldata/WriteBinnary.cpp) and getting nowhere.
## Post #13
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-26T05:05:33+00:00
- Post Title: Dragon quest Rivals ace (PC)

> Reply from iguniisu ↑Tue Oct 26, 2021 2:10 am at Tue Oct 26, 2021 2:10 am
>
> 

Any news on this? I've been trying to fix a script for the same format based on the structure from https://github.com/cocos2d-x/fbx-conv/b ... innary.cpp and getting nowhere.

I just completely forgot about it, will post it this evening
## Post #14
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2021-10-26T17:00:41+00:00
- Post Title: Dragon quest Rivals ace (PC)

Script uploaded : [https://github.com/Joschuka/fmt_c3b](https://github.com/Joschuka/fmt_c3b)
Just select a model c3b and the textures will be auto loaded. When prompted, select an anim folder if you want to load anims.

Only tested on the Switch files, many thanks to einherjar007 for the overall information about the filesystem and the differences between platforms and to DKDave for his Medarot script, this one is a direct upgrade of his work.
## Post #15
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2021-10-27T15:44:20+00:00
- Post Title: Dragon quest Rivals ace (PC)

the game is completely disappear from the earth 
would be really appreciate if someone could upload full assets , please
## Post #16
- Username: ryburgers
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 09, 2021 6:39 am
- Post datetime: 2021-12-26T02:31:59+00:00
- Post Title: Re: Dragon quest Rivals ace (PC)

I agree with above, it is a shame that there are currently zero 3D models floating around from this game. Has anyone considered working on it or sharing assets?

I would gladly do it myself, and upload everything to models resource. But I only found out about this game a week ago. There's no way to download it anymore. There are some great character models in this game, but they will die forever if we don't try to preserve it. Even if someone just shares the relevant data/c3b sections, then we can have more eyes on it. If someone still has the files, please don't delete it.
## Post #17
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-01-16T22:36:09+00:00
- Post Title: Re: Dragon quest Rivals ace (PC)

The game is using standard aes-128-cbc encryption, except that the key and IV are statically generated at runtime. Attached script was tested on mobile version of Dragon Quest Rivals Ace v3.8.0 and samples from [this topic](https://zenhax.com/viewtopic.php?f=9&t=16374).

I suppose tga textures are using ETC1 compression (for more info read [here](http://www.mhgames.org/2012/03/android-development-loading-etc1-textures-from-ndk)).

Update: Script is updated to automatically decompress decrypted assets in case if they're compressed (like samples from the linked topic).

Update 2: Updated script can now convert/fix tga textures for usage with etc1tool from Android SDK platform tools, available [here](https://developer.android.com/studio/releases/platform-tools). Simply run script on already decrypted and decompressed texture and it will be replaced with fixed one, just don't forget to launch quickbms with "-w" option to allow write operations.



 dq_rivals_decrypt-convert.zip
(671 Bytes) Downloaded 32 times
