## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-08-13T17:30:39+00:00
- Post Title: Wolfenstein X360 .spk file

having trouble figuring out this file, seems encryption/compressed somehow as i cant find anything in hex.

A little help?

[http://www.megaupload.com/?d=0JG22HON](http://www.megaupload.com/?d=0JG22HON)
## Post #2
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2009-08-19T17:54:26+00:00
- Post Title: Wolfenstein X360 .spk file

file is zipped withouth header


starts @offset 10
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-08-19T19:19:05+00:00
- Post Title: Wolfenstein X360 .spk file

Is there anyway to unzip it then?

Also here is one from the pc version.

[http://www.megaupload.com/?d=GGWA0MUI](http://www.megaupload.com/?d=GGWA0MUI)
## Post #4
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2009-08-19T20:31:36+00:00
- Post Title: Wolfenstein X360 .spk file

[http://aluigi.org/mytoolz/offzip.zip](http://aluigi.org/mytoolz/offzip.zip)


well file is not a complette mp3 maby u must delet some from the hex, in my test its worked fine
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-08-19T22:14:24+00:00
- Post Title: Wolfenstein X360 .spk file

Thanks it works!!

But it doesnt work on the 360 file
## Post #6
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-08-20T19:29:24+00:00
- Post Title: Wolfenstein X360 .spk file

is NOt ZIP it's Zlib.
Try to put your unzlibed example in sound/music/blacksun_combat_final_lp, i dont' know it this it's the folder or thew file, just try 

I modified the headers and now i know how use the precomp program with this 

I attach a precomped example used different zlib mode and i hope it works, just unzip it and go to cmd and type

```

```


Then copy the file to your game if it works will be good

Here it's the attachment

```

```
## Post #7
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-08-20T21:44:53+00:00
- Post Title: Wolfenstein X360 .spk file

Hmm i would of hoped the 360 used xma, ahh well.
## Post #8
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-08-20T22:00:06+00:00
- Post Title: Wolfenstein X360 .spk file

sorry for the Pc mistake (well it works for PC not for xbox360)
About xbox360..actually i have no idea
## Post #9
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-08-20T22:40:52+00:00
- Post Title: Wolfenstein X360 .spk file

So that was a pc sample you posted?
## Post #10
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-08-20T22:48:41+00:00
- Post Title: Wolfenstein X360 .spk file

From here:
[viewtopic.php?p=31265#p31265](http://forum.xentax.com/viewtopic.php?p=31265#p31265)
## Post #11
- Username: cryogen
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Aug 25, 2009 6:07 pm
- Post datetime: 2009-08-25T10:29:03+00:00
- Post Title: Wolfenstein X360 .spk file

Hi, I tried to extract sounds with offzip from an spk file of wolfenstein and now I got two files 00000010.dat and 00000012.dat...
Now, how may I convert these in normal wav or mp3 or whatever readable files?
I'm reading the entire post again and again but I'm not good like u with these things...Could someone post the entire process in doing this?
Thx

Andrew
## Post #12
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-08-25T11:36:57+00:00
- Post Title: Wolfenstein X360 .spk file

Go to the little extractor thread page 10 it has no support for wolfenstein spk files, and just use the cmd tool.
