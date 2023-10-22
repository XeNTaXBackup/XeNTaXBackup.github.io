## Post #1
- Username: timeman
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Oct 01, 2016 7:31 pm
- Post datetime: 2019-06-23T07:27:59+00:00
- Post Title: [Half Solved]r16g16_unorm Color Problem

Hello!
[03701.bin](https://www.dropbox.com/s/vj5yeazq6kjyvns/03701.bin?dl=0)


That's what i get from 03701.bin, I realllly don't konw about graphic format....
I used Rawtexture get the image



I've tried many graphic type, r16g16_unorm is the best, as a result.
But the color is not right.

Another type of image like this.
[00252.bin](https://www.dropbox.com/s/0ud2hwlapf1zoi7/00252.rar?dl=0)
Size, filesize, offset set as above
Rawtexture: 1280x720 0x80 r16g16_unorm, it's worked like above read.

Question1:
So, Would anyone tell me why and How to deal with these format images

This is another package, maybe compressed, i have no idea about this file
[unknown.bin](https://www.dropbox.com/s/rm0fsiu4jyi7k45/FACE.7z?dl=0)

Question2:
Would anyone tell me, what this is and how to extract it!

Any help will be greatly appreciated!!! Thank you first of all...
## Post #2
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2019-06-23T19:51:21+00:00
- Post Title: [Half Solved]r16g16_unorm Color Problem

> Reply from timeman ↑Sun Jun 23, 2019 3:27 pm at Sun Jun 23, 2019 3:27 pm
>
> 

I've tried many graphic type, r16g16_unorm is the best, as a result.
But the color is not right.

Looks like this is just ARGB32 packing. Not sure, is this tools supports it.
## Post #3
- Username: timeman
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Oct 01, 2016 7:31 pm
- Post datetime: 2019-06-24T00:58:46+00:00
- Post Title: [Half Solved]r16g16_unorm Color Problem

> Reply from aspadm ↑Mon Jun 24, 2019 3:51 am at Mon Jun 24, 2019 3:51 am
>
> 
timeman wrote: ↑Sun Jun 23, 2019 3:27 pm

I've tried many graphic type, r16g16_unorm is the best, as a result.
But the color is not right.


Looks like this is just ARGB32 packing. Not sure, is this tools supports it.

Thank your reply!
no this option.
Would you tell me how to batch these format???
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-06-24T06:42:25+00:00
- Post Title: [Half Solved]r16g16_unorm Color Problem

what is the full game name and platform from which the samples came?
## Post #5
- Username: timeman
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Oct 01, 2016 7:31 pm
- Post datetime: 2019-06-24T10:29:27+00:00
- Post Title: [Half Solved]r16g16_unorm Color Problem

> Reply from Acewell ↑Mon Jun 24, 2019 2:42 pm at Mon Jun 24, 2019 2:42 pm
>
> 
what is the full game name and platform from which the samples came?

ps3 super robot wars z jiokuhen \ face \ folder
most of the archives are the same structure.
So, help me .plz acewell!!! thank you
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-06-25T07:08:34+00:00
- Post Title: [Half Solved]r16g16_unorm Color Problem

okay here is Noesis python script to open your 2 samples.  


 tex_SuperRobotWarsZJigokuhen_PS3_bin.zip
(690 Bytes) Downloaded 20 times


supports argb8888, top level mip only
## Post #7
- Username: timeman
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Oct 01, 2016 7:31 pm
- Post datetime: 2019-06-25T08:16:10+00:00
- Post Title: [Half Solved]r16g16_unorm Color Problem

> Reply from Acewell ↑Tue Jun 25, 2019 3:08 pm at Tue Jun 25, 2019 3:08 pm
>
> 
okay here is Noesis python script to open your 2 samples.   
tex_SuperRobotWarsZJigokuhen_PS3_bin.zip
supports argb8888, top level mip only
Thank you so so much acewell, it did a great work!
in Line 12, if bs.readBytes(4) != b'\x01\x05\x00\x00': return 0
if I comment this line, it still work for some other file.  
Like this file, 

Thank you for your great job.

if you have time,
Would you like to tell me something about unknown.bin?
