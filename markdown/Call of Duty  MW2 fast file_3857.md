## Post #1
- Username: Gagarin
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Nov 11, 2009 7:17 pm
- Post datetime: 2009-11-11T13:39:34+00:00
- Post Title: Call of Duty : MW2 fast file

Hey there guys. yesteaday was release MW2. 

Can someone help me with extracting source files ?

Here is an example
[localized_code_pre_gfx_mp.zip](https://xentaxbackup.github.io/file/2523_localized_code_pre_gfx_mp.zip)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-11T15:03:03+00:00
- Post Title: Call of Duty : MW2 fast file

there is a zlib block in the middle which contains the 2 files I have attached.
the rest of the data is unknown, not xor/rot with a fixed byte and if it's compressed it uses an unknown algorithm
[blah.zip](https://xentaxbackup.github.io/file/2524_blah.zip)
## Post #3
- Username: Gagarin
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Nov 11, 2009 7:17 pm
- Post datetime: 2009-11-11T15:15:29+00:00
- Post Title: Call of Duty : MW2 fast file

thx. How u can extracted them ?

previous fast file version contains 12-bytes header and zlib archive "78 DA"

But now in this version I didn't know how to extract them. Now .ff have 13 (??) bytes header and no zlib bytes
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-11T15:18:33+00:00
- Post Title: Call of Duty : MW2 fast file

I simply extracted the first block at offset 0x4015 through a scanning with offzip.
then I opened the extracted file and noticed it had other zlib blocks in it and so I did another scan and renamed the files using the names found in that file before the zlib blocks.
## Post #5
- Username: Gagarin
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Nov 11, 2009 7:17 pm
- Post datetime: 2009-11-11T15:23:28+00:00
- Post Title: Call of Duty : MW2 fast file

ahhh, it's hard for me =(

Can u write about ur "manual" more detailed ? If is not so hard ,surely
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-11T16:06:20+00:00
- Post Title: Call of Duty : MW2 fast file

ok, I try.
I have used [offzip](http://aluigi.org/mytoolz.htm#offzip) for the job.
I didn't know what type of data was contained in the file so I launched offzip in scan mode for checking if there was a zlib block somewhere:

```
offzip -S localized_code_pre_gfx_mp.ff 0 0
```
and it reported a block at offset 0x4015 so I launched it in scan+extract mode to dump it:

```
offzip -a localized_code_pre_gfx_mp.ff output_folder 0
```

now I opened the obtained file 00004015.dat with a hex editor to check what it contained and I noticed the 0x78 byte after the first filename "default_mp.cfg" so I simple did the same as before launching offzip with -S and then -a for extracting the compressed zlib blocks.

the last step was renaiming the two files using the names found in that file.
that's all
## Post #7
- Username: Gagarin
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Nov 11, 2009 7:17 pm
- Post datetime: 2009-11-11T16:32:25+00:00
- Post Title: Call of Duty : MW2 fast file

ok, thx so much. all works fine i'm extracter two .dat files. But I didn't understnd what names are they. I mean how I can rename them right ?
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-11T16:35:00+00:00
- Post Title: Call of Duty : MW2 fast file

if you watch in 00004015.dat you see a name at offset 0x68 followed by the zlib data, that's the first name of the first dumped file.
the second one is at offset 0x13e
## Post #9
- Username: Gagarin
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Nov 11, 2009 7:17 pm
- Post datetime: 2009-11-11T16:54:46+00:00
- Post Title: Call of Duty : MW2 fast file

ok , thx , all working fine now

well, this method is good for few-some files. But if I extracted much files in different folders - it's so hard to rename them and put into right folders

thx again
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-11T17:00:43+00:00
- Post Title: Call of Duty : MW2 fast file

this is NOT a definitive method, I simply told you how I got those 2 files but there is all the rest of the FF archive to figure first
## Post #11
- Username: Gagarin
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Nov 11, 2009 7:17 pm
- Post datetime: 2009-11-11T17:20:50+00:00
- Post Title: Call of Duty : MW2 fast file

I understood. Do u have any ideas how to extract files more easily ?
## Post #12
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-11-11T19:40:22+00:00
- Post Title: Call of Duty : MW2 fast file

Any clue where should be game font(s) & sub-text, if I want to translate it
## Post #13
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-11-12T11:28:54+00:00
- Post Title: Call of Duty : MW2 fast file

Activision don't like modding in CODmw2 maybe this is the reason the ff's of multiplayer are crypted.  
And more info here:
[viewtopic.php?p=33117#p33117](http://forum.xentax.com/viewtopic.php?p=33117#p33117)
## Post #14
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2009-11-14T03:01:05+00:00
- Post Title: Call of Duty : MW2 fast file

The files ending or starting with "_mp" will not load if they're modified on the Xbox 360, they encrypt a hash with RSA. I'm not sure if they do the same for the PC files.
## Post #15
- Username: iamLXM
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 26, 2009 10:07 pm
- Post datetime: 2010-01-05T13:24:12+00:00
- Post Title: Call of Duty : MW2 fast file

> Reply from Caboose
>
> The files ending or starting with "_mp" will not load if they're modified on the Xbox 360, they encrypt a hash with RSA. I'm not sure if they do the same for the PC files.

compraring with COD4:MW, every .ff file related to MP is encrpted, add some byte to check the file between offset 00 000CH - 00 4014H , total 16,393 Bytes. After 00 4015H, it is a zlib block after 00 4014H, the same to COD4:MW .ff.

I wonder who can recovering the iw4mp.exe to cr*ck the .ff
## Post #16
- Username: Gagarin
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Nov 11, 2009 7:17 pm
- Post datetime: 2010-01-12T20:51:39+00:00
- Post Title: Re: Call of Duty : MW2 fast file

How I can generate the encrypt code ? Is this possible ?

The data before block 0x4015 (where is zlib packing starting) is not alone. Every mp file contains file ending data. It's always starting with ASCII "$.....\.." (24 06 0F 0E 0A 1A 5C 09 07). It's different for any mp file but have the same data. So for example for localized_code_post_gfx_mp.ff (english version) it's 3775 bytes. For patch_mp.ff - 7802 bytes total. And first 3775 are the same with localized_code_post_gfx_mp.ff...

As I think after zlib packing some tool (may be) generate the header and the "footer" (file end)

Any suggestions about it? May be any public encrypt key or something else
## Post #17
- Username: peshkohacka
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jan 22, 2009 6:20 am
- Post datetime: 2010-01-17T16:12:57+00:00
- Post Title: Re: Call of Duty : MW2 fast file

> Reply from iamLXM
>
> Caboose wrote:The files ending or starting with "_mp" will not load if they're modified on the Xbox 360, they encrypt a hash with RSA. I'm not sure if they do the same for the PC files.

compraring with COD4:MW, every .ff file related to MP is encrpted, add some byte to check the file between offset 00 000CH - 00 4014H , total 16,393 Bytes. After 00 4015H, it is a zlib block after 00 4014H, the same to COD4:MW .ff.

I wonder who can recovering the iw4mp.exe to cr*ck the .ff

I found a few places where the code could start, but seems pointless, cause the files are SHA-256 checked, so even if they are loaded by the MP client, the host of the p2p connection would probably refuse them. Anyway im interested into exploring the content of this files, so if anyone could help me with creating the algo, it would be a step. At least in SP we would be able to mod something.
## Post #18
- Username: Jurko
- Rank: veteran
- Number of posts: 86
- Joined date: Fri Jan 22, 2010 9:35 pm
- Post datetime: 2010-01-26T17:14:14+00:00
- Post Title: Re: Call of Duty : MW2 fast file

I heard that it could go with simplyzip.
Not know how?
