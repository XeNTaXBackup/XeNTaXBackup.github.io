## Post #1
- Username: theBloodone
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 10, 2012 8:22 pm
- Post datetime: 2012-06-10T12:29:32+00:00
- Post Title: Wolfenstein (2009) .spk Packer?

Hi, folks.   

Is there a .spk packer or a way to pack a .spk archive that is used in the last Wolfenstein game?  

I know that there is an unpacker for the .spk/.mpk and packer for the .mp3 files made by bellox, but not for the .spk archives...
## Post #2
- Username: theBloodone
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 10, 2012 8:22 pm
- Post datetime: 2012-06-10T12:32:59+00:00
- Post Title: Wolfenstein (2009) .spk Packer?

Sorry for the double post = browser bug
## Post #3
- Username: sergeantjackie
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 04, 2012 7:19 pm
- Post datetime: 2012-08-04T11:26:08+00:00
- Post Title: Wolfenstein (2009) .spk Packer?

Hi All, i'm new here.

i have tested the game if it's working with the unpacked files, but it's not working..

Is there anyone who can do something about repacking the .spk files?

I want to do some modding, but i can't do nothing because there are no .spk or .mpk packing tool(s)

theBloodone, the thread is in the wrong place
## Post #4
- Username: sergeantjackie
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 04, 2012 7:19 pm
- Post datetime: 2012-09-11T14:18:46+00:00
- Post Title: Wolfenstein (2009) .spk Packer?

*bump* (one month passed since my last post)
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-17T19:46:19+00:00
- Post Title: Wolfenstein (2009) .spk Packer?

Moved to right forum.
## Post #6
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2012-10-03T19:57:48+00:00
- Post Title: Wolfenstein (2009) .spk Packer?

you don't need a repacker file

-repair the .pk4 files with winrar and decompress all files in base

-decompress all spk files with the spk extractor and put the folders in base folder (I don't remember very well)

- create a shortcut and in destination add this: "+set com_allowconsole 1 +set com_SingleDeclFile 0" (unquoted)

now the game work with all files decompressed , you can change the characters , mod the scripts, change sounds etc
## Post #7
- Username: MJ12
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 08, 2012 12:55 pm
- Post datetime: 2012-11-07T13:28:00+00:00
- Post Title: Wolfenstein (2009) .spk Packer?

> Reply from luxox18
>
> you don't need a repacker file

-repair the .pk4 files with winrar and decompress all files in base

-decompress all spk files with the spk extractor and put the folders in base folder (I don't remember very well)

- create a shortcut and in destination add this: "+set com_allowconsole 1 +set com_SingleDeclFile 0" (unquoted)

now the game work with all files decompressed , you can change the characters , mod the scripts, change sounds etc

You mean all the .spk files include those in map & streampack folders？ I've tried that, but not working...please help
## Post #8
- Username: ZerOHearth
- Rank: advanced
- Number of posts: 62
- Joined date: Sun Jun 13, 2010 5:32 pm
- Post datetime: 2013-06-09T10:19:07+00:00
- Post Title: Wolfenstein (2009) .spk Packer?

> Reply from MJ12
>
> I've tried that, but not working...please helpMe, too. Not working.
## Post #9
- Username: Blexs12
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 30, 2023 2:18 am
- Post datetime: 2023-04-29T18:31:40+00:00
- Post Title: Wolfenstein (2009) .spk Packer?

> Reply from luxox18 ↑Thu Oct 04, 2012 3:57 am at Thu Oct 04, 2012 3:57 am
>
> 
you don't need a repacker file

-repair the .pk4 files with winrar and decompress all files in base

-decompress all spk files with the spk extractor and put the folders in base folder (I don't remember very well)

- create a shortcut and in destination add this: "+set com_allowconsole 1 +set com_SingleDeclFile 0" (unquoted)

now the game work with all files decompressed , you can change the characters , mod the scripts, change sounds etc
Please tell me how? Are you still alive
## Post #10
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2023-06-05T09:54:36+00:00
- Post Title: Wolfenstein (2009) .spk Packer?

You can unpack *.pk4 with 7Zip. After unpack put unpacked folders to the base folder and rename extension of *.pk4 to something else. *.pk4_.
For spk/mpk use this unpacker and do the same as for *.pk4.

```
https://www.moddb.com/games/wolfenstein/downloads/wolfenstein-spk-mpk-extractor-v02
```

Well after some test it seems that mpk must be re-packed in order to work.
Also i found cvar "stream_looseFileMode" for loading unpacked mpk archive but it's dissabled in final build and can't be anabled unless you found a function in the exe to enable id permanently.

Seems like mpk is major file and spk are minor. mpk "map pak" spk "stream pak"
Procedure was unpack mpk and put unpacked content to the base folder, then unpack all spk and put to the base and then I did a debug which shows me this:

```
Last Error: rvBackgroundLoadAndDecompressFile::Operate: Failed to open file maps/game/trainyard/trainyard.mpk.
```


Well seems like game doesn't like decompressed files.

```
ERROR: rvBackgroundLoadAndDecompressFile::Operate: Error: Inflate data: Unknown compression method
```


Also found these...

```
Specifies whether asset loading is allowed on a find operation.  
0 - Asset loading on find is not allowed.  This should simulate stream pack loading in loose file mode.
1 - Assets will load with a warning.
2 - Assets will load with no warning (set automatically for tools.
3 - Assets will fail to load with no warning.

stream_looseFileMode
1 - Use the streaming system in loose file mode.
2 - use loose file mode only if a pack doesn't exist.
```
