## Post #1
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-03-10T16:57:44+00:00
- Post Title: S3TC convertor: where?

I have files like the example attached, where i can found a program to convert to tga and viceversa?
Any program like nvdxt or "The compressonator"?

The Header of the file it's "S3TCDXT5" 

Thaaanks  
[1.ZIP](https://xentaxbackup.github.io/file/1085_1.ZIP)
## Post #2
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2007-03-10T23:08:26+00:00
- Post Title: S3TC convertor: where?

Well you could just modify the header to be DXT5 (.dds). 
You can see the dimensions at  0x8 & 0xC.  Then could edit or convert it to tga if you want via plugins/converters.
## Post #3
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2007-04-10T18:53:20+00:00
- Post Title: S3TC convertor: where?

I tried to code a S3TC decompressor a while back but it don't handle alpha channels

I'm not sure if you would be interested in that :P

the file is not a proper dds
after editing the header it still doesn't look alright but it is clearly a bird upside down ...
## Post #4
- Username: SparedLife
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Mar 07, 2004 1:37 pm
- Post datetime: 2007-05-11T01:20:30+00:00
- Post Title: S3TC convertor: where?

Is anyone still interested in this? It's not a problem to build a tool to convert back and forth. The files are DXT5, it's just a matter of swapping headers.
 I don't have enough info to make a reliable tool though. I see he sent 1.dds but do these DDS files have actual filenames or is that it? Was this a standalone DDS or was it ripped from a library? Are there other DXT formats?


 whoa weird I just noticed the post dates 10th

Edit again:
 Ok I took a blind stab at it. This program will look at a DDS file or any file for that matter and check the header for S3TC. If it finds the identifier then it will convert the file to a standard DDS file in the DXT format defined in the S3TC header (in the example I got it was a DXT5) with no mips. It will also save the alpha but does not rightside up the graphic.
 The user edits the DDS and saves back in the original format with the original name and with mips. This program will read the saved original header and replace the standard DDS header back to S3TC.

[http://www.spared-life.com/SparedLifeFi ... r-S3TC.zip](http://www.spared-life.com/SparedLifeFiles/SLConverter-S3TC.zip)

Works on the 1 file in the sample given. Hope it works for the rest.
## Post #5
- Username: Isilfor
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Jul 20, 2010 12:01 am
- Post datetime: 2010-07-26T17:30:44+00:00
- Post Title: S3TC convertor: where?

> The requested URL /SparedLifeFiles/SLConverter-S3TC.zip was not found on this server.
Please reupload.
