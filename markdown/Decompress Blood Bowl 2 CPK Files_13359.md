## Post #1
- Username: Ketsumachi
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 24, 2015 9:48 pm
- Post datetime: 2015-09-24T14:01:55+00:00
- Post Title: Decompress Blood Bowl 2 CPK Files

I'm looking for any assistance in unpacking and repacking the CPK files for Blood Bowl 2 (PC). I have dabbled around with trying to unpack them myself, but have been unable to with common methods such as QuickBMS and CriPakTools. QuickBMS's standard CPK script says that the file's format comes up as "UÿC☺" while CriPakTools says the CPK signature is not found. 

The signature of the 4 bytes at offset 0x00000000 do not match the expected in the script. They are 55 98 43 01 and do not match the CPK standard offset.

Link to sample file: [https://www.dropbox.com/s/cchdze6x12zko ... 9.cpk?dl=0](https://www.dropbox.com/s/cchdze6x12zkofs/3D_Characters_DarkElf_0%20%281%29.cpk?dl=0)

Within these CPK files appears to be standard .dds and .nif files for the skins and models of the players, as well as the files that modify the positions of assets (such as the End turn button). I will have a lot of room to work in modding the game, as well as possibly improving the original game based on what is found. The only hurdle is getting past unpacking this odd kind of CPK.
## Post #2
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-09-24T16:40:16+00:00
- Post Title: Decompress Blood Bowl 2 CPK Files

I think that this does it:

```

ImpType Standard;
GoTo 4 0;
Get NFiles Long 0;
GoTo 520 0;
SavePos HOffset 0;

For I = 1 To NFiles;
SavePos FSizeOffset 0;
Get FSize Long 0;
SavePos FOffsetOffset 0;
Get FOffset Long 0;
Get FName String 0;

Log FName FOffset FSize FOffsetOffset FSizeOffset;

Math HOffset += 520;
GoTo HOffset 0;
Next I;
```
## Post #3
- Username: Ketsumachi
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 24, 2015 9:48 pm
- Post datetime: 2015-09-24T16:48:20+00:00
- Post Title: Decompress Blood Bowl 2 CPK Files

I would love to test it out, I'm not entirely familiar with what you've given though. What do I run that through?
## Post #4
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-09-24T16:53:16+00:00
- Post Title: Decompress Blood Bowl 2 CPK Files

I'm using MultiEx commander.

I've found a .bms script here: [http://aluigi.org/papers/bms/others/blood_bowl_2.bms](http://aluigi.org/papers/bms/others/blood_bowl_2.bms).
## Post #5
- Username: Ketsumachi
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 24, 2015 9:48 pm
- Post datetime: 2015-09-24T17:29:41+00:00
- Post Title: Decompress Blood Bowl 2 CPK Files

Okay, so that was able to decompress the file. What would be the way of repacking them?
## Post #6
- Username: ekanspt
- Rank: advanced
- Number of posts: 49
- Joined date: Thu Dec 30, 2010 6:26 am
- Post datetime: 2015-09-24T17:35:28+00:00
- Post Title: Decompress Blood Bowl 2 CPK Files

If you are using multiex, maybe this can help you: [viewtopic.php?f=29&t=5921](http://forum.xentax.com/viewtopic.php?f=29&t=5921).

If you are using quickbms, please read Section 3 of this .txt: [http://aluigi.altervista.org/papers/quickbms.txt](http://aluigi.altervista.org/papers/quickbms.txt).
## Post #7
- Username: Ketsumachi
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 24, 2015 9:48 pm
- Post datetime: 2015-09-24T17:49:21+00:00
- Post Title: Decompress Blood Bowl 2 CPK Files

Wonderful, thank you very much.
## Post #8
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-09-25T23:01:24+00:00
- Post Title: Decompress Blood Bowl 2 CPK Files

Hi guys I wrote a litte command line tool that can be used to extract all the files from all the cpk packages from blood bowl 2

complete extractions takes only a couple of minutes

usage example:

BloodBowl2Unpacker.exe "D:\Games\Blood Bowl 2" "D:\Games\Blood Bowl 2\Extracted\"

so BloodBowl2Unpacker.exe [Installation Folder] [Folder to extract the files to]

make sure your destination folder exists, it will create some subfolders though

all seem to be working, dds, txt, csv, fnt, lua, etc...
although it does extract all the files, it does not convert it to anything other like the cef, dff, psb files and other of course 

Hope this is usefull to someone 

T.
[BloodBowl2Unpacker.zip](https://xentaxbackup.github.io/file/9788_BloodBowl2Unpacker.zip)
## Post #9
- Username: tazdevilal
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 29, 2015 11:16 pm
- Post datetime: 2015-09-29T15:42:55+00:00
- Post Title: Decompress Blood Bowl 2 CPK Files

Not sure how this should be set up. any advice?
## Post #10
- Username: Zetan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 05, 2017 1:42 am
- Post datetime: 2017-01-04T18:01:49+00:00
- Post Title: Decompress Blood Bowl 2 CPK Files

Having some trouble with this.  Is it possible the file structure has changed somewhat in the past year?  When I run it, I get output that looks like this:

```
  - writing
  - writing
  - writing
  - writing
Data_Game_0.cpk
  - writing
  - writing
  - writing
  - writing
  - writing
```


It goes on and on like that, with lots of those "  - writing" lines for each file.  When it's done I'm left with an empty "Extracted" folder and an empty "ExtractedOther" folder in the same directory.
## Post #11
- Username: xelanizul
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Feb 13, 2017 6:43 pm
- Post datetime: 2017-05-21T12:04:03+00:00
- Post Title: Decompress Blood Bowl 2 CPK Files

"When it's done I'm left with an empty "Extracted" folder and an empty "ExtractedOther" folder in the same directory."

Me too
## Post #12
- Username: Ren07
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Oct 12, 2014 2:05 am
- Post datetime: 2017-07-25T14:24:15+00:00
- Post Title: Decompress Blood Bowl 2 CPK Files

Anyone know how to repack?
## Post #13
- Username: Oddie
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 27, 2019 3:00 pm
- Post datetime: 2019-01-27T07:57:21+00:00
- Post Title: Decompress Blood Bowl 2 CPK Files

> Reply from TaylorMouse
>
> Hi guys I wrote a litte command line tool that can be used to extract all the files from all the cpk packages from blood bowl 2

complete extractions takes only a couple of minutes

usage example:

BloodBowl2Unpacker.exe "D:\Games\Blood Bowl 2" "D:\Games\Blood Bowl 2\Extracted\"

so BloodBowl2Unpacker.exe [Installation Folder] [Folder to extract the files to]

make sure your destination folder exists, it will create some subfolders though

all seem to be working, dds, txt, csv, fnt, lua, etc...
although it does extract all the files, it does not convert it to anything other like the cef, dff, psb files and other of course 

Hope this is usefull to someone 

T.

The command prompt force closes when i try to enter any data. Can you please instruct me how to use this?

Thanks
## Post #14
- Username: SnakeBlitzen
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jun 21, 2019 6:03 am
- Post datetime: 2019-06-20T22:08:32+00:00
- Post Title: Decompress Blood Bowl 2 CPK Files

I was able to decompress the BB2 packages with quickbms and then convert all of the 3D files from .cef to .obj with 3D Object Converter but now I'd like to figure out how to use the .motion files to get the animations and apply them to the 3D files (I'm assuming the .motion files contain the animations). 
Has anyone else tried this and were you successful? How did you do it and what have you tried?
## Post #15
- Username: deepty
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 25, 2019 4:25 am
- Post datetime: 2019-09-25T08:06:00+00:00
- Post Title: Decompress Blood Bowl 2 CPK Files

You said you converted .cef files to .obj. Can you please tell me how exactly? When i'm trying to open this bb2 cef with "3d object converter 5.30" it shows error about no valid format or no objects.
You can answer me by mail I sent you in pm.
## Post #16
- Username: CaesarCzech
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 29, 2021 4:47 am
- Post datetime: 2021-10-28T20:56:16+00:00
- Post Title: Re: Decompress Blood Bowl 2 CPK Files

Any one got working script ?  and the unpacker closes when i attempt to input data in.
