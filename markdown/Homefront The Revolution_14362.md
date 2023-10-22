## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2016-05-18T11:32:06+00:00
- Post Title: Homefront The Revolution

Anyone who has the executable has obtained the unique decryption key to decrypt the PAK files?

Game uses denuvo BTW.
## Post #2
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-05-18T18:37:46+00:00
- Post Title: Homefront The Revolution

dont think this will be possible.... Not sure
## Post #3
- Username: m0xf
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 17, 2012 1:57 am
- Post datetime: 2016-05-18T20:01:40+00:00
- Post Title: Homefront The Revolution

Key:

```
unsigned char g_RSAKeyData[140] = {
    0x30, 0x81, 0x89, 0x02, 0x81, 0x81, 0x00, 0xAF, 0x4E, 0xD4, 0xBC, 0xCE, 0x5D, 0xB5, 0x0B, 0x13,
    0x63, 0xD1, 0xBA, 0x9E, 0xC9, 0x29, 0xA7, 0x3F, 0x70, 0x2A, 0x9E, 0xE4, 0x51, 0x2D, 0x6E, 0x68,
    0x8A, 0xDC, 0xFB, 0xFA, 0x88, 0xC8, 0xAB, 0x22, 0x58, 0x74, 0xB7, 0x7A, 0x86, 0x28, 0x70, 0x0F,
    0x10, 0x1B, 0x58, 0xC5, 0xFB, 0x30, 0x91, 0x6F, 0x73, 0x18, 0x68, 0x57, 0x77, 0xF2, 0xD6, 0xDD,
    0x30, 0xC3, 0x65, 0x54, 0x5E, 0xD2, 0x09, 0xC8, 0xF3, 0x51, 0xE5, 0x5E, 0xFC, 0x5A, 0x01, 0xA7,
    0x79, 0x72, 0x24, 0x3C, 0x34, 0x8A, 0x14, 0xCF, 0xF4, 0x35, 0x0E, 0x5D, 0xBD, 0x18, 0x44, 0x11,
    0x9A, 0xB9, 0x77, 0x21, 0xA0, 0x97, 0x46, 0x8C, 0xA4, 0x23, 0xCC, 0x9E, 0x78, 0xC3, 0xDD, 0x1D,
    0x9A, 0xB0, 0x18, 0xF3, 0xD3, 0x42, 0xE2, 0xEB, 0xD8, 0xA4, 0xE5, 0x07, 0x72, 0xAE, 0x16, 0x53,
    0x24, 0xA4, 0x85, 0xC1, 0x36, 0x12, 0xD1, 0x02, 0x03, 0x01, 0x00, 0x01
};

```
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2016-05-19T03:05:41+00:00
- Post Title: Homefront The Revolution

Sweet!
how to implement this key?
## Post #5
- Username: Sajjad Rahim
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 07, 2015 5:04 pm
- Post datetime: 2016-05-19T11:33:43+00:00
- Post Title: Homefront The Revolution

Can someone re upload pakdecrypt source? or pakdecrypt compiled for homefront
## Post #6
- Username: cameleot
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jun 21, 2011 1:42 am
- Post datetime: 2016-05-20T08:20:36+00:00
- Post Title: Homefront The Revolution

Also would like a compiled pakdecrypt for Homefront.

I tried compiling with the above key but the decrypted files end up being 0kb only. Here are the source files for Cryengine 3 and Warface (CryEngine 4) pakdecrypts:

[https://www.mediafire.com/?fydzpc4lzcvvg3e](https://www.mediafire.com/?fydzpc4lzcvvg3e)
## Post #7
- Username: Gazyi
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 15, 2014 11:07 pm
- Post datetime: 2016-05-20T14:40:51+00:00
- Post Title: Homefront The Revolution

Compiled it.
Doesn't work. Maybe localizations have different keys or key is incorrect? An application memory dump and sample file can help.
## Post #8
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2016-05-20T17:41:04+00:00
- Post Title: Homefront The Revolution

Doesn't Work. Gives me a 0kb file.
## Post #9
- Username: m0xf
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 17, 2012 1:57 am
- Post datetime: 2016-05-24T17:17:45+00:00
- Post Title: Homefront The Revolution

Key is correct. I extracted ZIP central directory (file names), but the contents of the file is not decrypted correctly. I think there some layer for fast seeking or something similar.
## Post #10
- Username: m0xf
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 17, 2012 1:57 am
- Post datetime: 2016-07-10T10:01:20+00:00
- Post Title: Homefront The Revolution

Homefront: The Revolution game .pak extractor

Supported only v1.0.67.8905

Usage:
1. Copy dinput8.dll into Homefront_The_Revolution\Bin64\ drectory
2. Start game exe
3. See Bin64\extracted\*.
[hf2extract.zip](https://xentaxbackup.github.io/file/11278_hf2extract.zip)
## Post #11
- Username: Highflex
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 23, 2014 12:41 am
- Post datetime: 2016-07-12T10:28:39+00:00
- Post Title: Homefront The Revolution

> Reply from m0xf
>
> Homefront: The Revolution game .pak extractor

Supported only v1.0.67.8905

Usage:
1. Copy dinput8.dll into Homefront_The_Revolution\Bin64\ drectory
2. Start game exe
3. See Bin64\extracted\*.

Nice work but the game got updated recently, do you think you can provide a new version?

It crashes with my steam version :/
## Post #12
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2016-08-08T11:15:56+00:00
- Post Title: Homefront The Revolution

Any chance to update the extractor for the new version?
I uploaded the 1.0.6.5408 exe, if it's of any help.

[https://www.dropbox.com/s/h2xmykopvz92o ... e.rar?dl=0](https://www.dropbox.com/s/h2xmykopvz92otq/homefront2_release.rar?dl=0)

Thanks!
## Post #13
- Username: sven489
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 19, 2014 2:57 am
- Post datetime: 2016-09-11T13:59:17+00:00
- Post Title: Homefront The Revolution

Heyy that does not work :/

I have the Original on Steam and the newest version. 
Can someone help me ?  

THX on all
## Post #14
- Username: m0xf
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 17, 2012 1:57 am
- Post datetime: 2017-03-25T07:20:10+00:00
- Post Title: Homefront The Revolution

Update for extractor.

Supported version 1.0.78.1055 (Homefront.The.Revolution-PLAZA)
[hf2extract2.zip](https://xentaxbackup.github.io/file/12685_hf2extract2.zip)
## Post #15
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2017-03-26T02:52:55+00:00
- Post Title: Homefront The Revolution

> Reply from m0xf
>
> Update for extractor.

Supported version 1.0.78.1055 (Homefront.The.Revolution-PLAZA)

I have just the regular steam version of this game and this extractor is not working for me. Any suggestions on how to make it work? Thank you in advance for any help.
## Post #16
- Username: JDog
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Mar 26, 2017 3:14 pm
- Post datetime: 2017-03-26T07:23:30+00:00
- Post Title: Re: Homefront The Revolution

I'm getting an 0xc0000142 error. Has this been tested with Windows 10, BTW? I'm interested in trying to dump the contents of the game archives to see what cut content might be lurking there, and also I'm extremely interested in the possibility of modding the PC version by making it load files from outside the pak files first. I feel the game has huge modding potential.
## Post #17
- Username: ahm3draxa
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 27, 2017 2:55 am
- Post datetime: 2017-03-27T05:45:46+00:00
- Post Title: Re: Homefront The Revolution

> Reply from m0xf
>
> Homefront: The Revolution game .pak extractor

Supported only v1.0.67.8905

Usage:
1. Copy dinput8.dll into Homefront_The_Revolution\Bin64\ drectory
2. Start game exe
3. See Bin64\extracted\*.

Hello!
when i pasted the updated version of extractor PLAZA edition with the same version of Game.exe file it gave me an error of (0xc0000142)
i pasted the dinput.dll in main directory of Homeftont_The_Revolution\Bin64\
is there anything that i'm missing?
Please help.
## Post #18
- Username: m0xf
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 17, 2012 1:57 am
- Post datetime: 2017-03-29T15:50:40+00:00
- Post Title: Re: Homefront The Revolution

It was problem with windows 10. I fixed extractor, try it.
[hf2extract3.zip](https://xentaxbackup.github.io/file/12710_hf2extract3.zip)
## Post #19
- Username: JDog
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Mar 26, 2017 3:14 pm
- Post datetime: 2017-03-30T02:53:13+00:00
- Post Title: Re: Homefront The Revolution

Thanks. There is some pretty interesting stuff in here. What appears to be a lot of cutscene remnants, unused music, and a lot of TimeSplitters 2 files, including music, voice acting, and files for every single level. Which I find... strange. Wonder whether it would be possible to jerry rig the TimeSplitters 2 "demo" to be able to play all the missions?

It's a pity the extractor has to dump everything, because I'd like to be able to just dump specific archives. Still, better than nothing. I guess the problem this presents, though, is the game's use of compiled script files and the likely difficulty making it read outside pak files first.
## Post #20
- Username: Highflex
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 23, 2014 12:41 am
- Post datetime: 2017-04-05T12:00:09+00:00
- Post Title: Re: Homefront The Revolution

Hey m0xf,

The tool works great and i see all of the extracted assets but i fear some stuff is missing,

extracted\objects\characters\cast contains all the main characters model files, but from what i see the .skinm files are not there, and i believe they actually store the mesh data while .skin stores the skeleton and general info, any idea why this happens?
## Post #21
- Username: JDog
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Mar 26, 2017 3:14 pm
- Post datetime: 2017-04-05T13:04:22+00:00
- Post Title: Re: Homefront The Revolution

I have noticed it doesn't seem to be dumping all the files in certain circumstances. For example, in my second dump attempt, the various bik2 video files were missing.
## Post #22
- Username: Highflex
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 23, 2014 12:41 am
- Post datetime: 2017-04-05T13:46:38+00:00
- Post Title: Re: Homefront The Revolution

> Reply from JDog
>
> I have noticed it doesn't seem to be dumping all the files in certain circumstances. For example, in my second dump attempt, the various bik2 video files were missing.

Do you have any .skinm files inside the objects/characters/cast folder? They all seem to be missing for me, unless i am misunderstanding the model format so far
## Post #23
- Username: InKviZ
- Rank: advanced
- Number of posts: 51
- Joined date: Mon Sep 29, 2014 12:57 am
- Post datetime: 2017-06-02T12:01:04+00:00
- Post Title: Re: Homefront The Revolution

I want to localize this game. Archives of the text I unpacked. But XML text format encoded in the bin. 
Who will help me decode text??? Here is a link to a file with text: [https://files.fm/u/dcmgk8b5](https://files.fm/u/dcmgk8b5)
## Post #24
- Username: JDog
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Mar 26, 2017 3:14 pm
- Post datetime: 2017-06-04T09:34:54+00:00
- Post Title: Re: Homefront The Revolution

> Reply from InKviZ
>
> I want to localize this game. Archives of the text I unpacked. But XML text format encoded in the bin. 
Who will help me decode text??? Here is a link to a file with text: https://files.fm/u/dcmgk8b5
I tested the XML decompiler tool people have been using for Prey, but it unfortunately doesn't work. Dambuster must've made some changes, I assume. It's a pity pretty much zero effort has gone into modding Homefront: TR because the game would greatly benefit from it. Meanwhile Prey already has mods.
## Post #25
- Username: JDog
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Mar 26, 2017 3:14 pm
- Post datetime: 2017-12-23T06:11:45+00:00
- Post Title: Re: Homefront The Revolution

> Reply from dragbody
>
> m0xf wrote:Update for extractor.

Supported version 1.0.78.1055 (Homefront.The.Revolution-PLAZA)

I have just the regular steam version of this game and this extractor is not working for me. Any suggestions on how to make it work? Thank you in advance for any help.
I think it probably doesn't work because a month or so after the PLAZA release, a hotfix exe patch was released.
## Post #26
- Username: JDog
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Mar 26, 2017 3:14 pm
- Post datetime: 2018-04-02T11:18:22+00:00
- Post Title: Re: Homefront The Revolution

> Reply from m0xf
>
> It was problem with windows 10. I fixed extractor, try it.
The extractor has been broken since the game's April 2017 exe update. Any chance you'll update the extractor?

I really wish someone would make a repacking tool, too, but that's probably a pipe dream.
## Post #27
- Username: m0xf
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Aug 17, 2012 1:57 am
- Post datetime: 2018-07-04T16:04:50+00:00
- Post Title: Re: Homefront The Revolution

Game use brotli compression. I made new decryption tool.
Now it not required game exe and can process single .pak file.

To repack archive (or use normal zip in game) you need to patch game exe, becouse pak files are signed.

[https://yadi.sk/d/0Irz7uCA3YmV4b](https://yadi.sk/d/0Irz7uCA3YmV4b)
## Post #28
- Username: testgcd
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 30, 2021 3:27 am
- Post datetime: 2021-03-29T19:46:55+00:00
- Post Title: Re: Homefront The Revolution

> Reply from m0xf ↑Thu Jul 05, 2018 12:04 am at Thu Jul 05, 2018 12:04 am
>
> 
To repack archive (or use normal zip in game) you need to patch game exe, becouse pak files are signed.

I'm not very tech savvy, does this mean it cannot be done? There is no repacker?
