## Post #1
- Username: billywws
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 28, 2014 3:43 am
- Post datetime: 2015-10-26T01:40:44+00:00
- Post Title: Sonic and Sega All-Stars Racing .zig and .zif model formats

They have been extracted from Racers.xpac.

These model files hold the tracks and the character models, which I want to extract to 3D software. Not much seems to be known about this format though, let alone ways of extracting the models from it. But apparantly it's a type of archive.

.ZIF example: [http://www.mediafire.com/download/h6f12 ... atcher.zif](http://www.mediafire.com/download/h6f12g1eu50qu47/BillyHatcher.zif)
.ZIG example: [http://www.mediafire.com/download/g6y01 ... atcher.zig](http://www.mediafire.com/download/g6y0174pcrtb2f0/BillyHatcher.zig)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-16T04:48:45+00:00
- Post Title: Sonic and Sega All-Stars Racing .zig and .zif model formats

both samples are zlib compressed, here is a bms script for that  

```
get SIZE asize
get NAME basename
get EXT extension
string NAME p "%s_dec.%s" NAME EXT
clog NAME 0 SIZE SIZE

```
 

the zig file contains model and texture data.
the zif file looks like an index file for the zig file.

first submesh in BillyHatcher.zig



BillyHatcher_zig.png (21.51 KiB) Viewed 341 times
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-04-16T06:28:51+00:00
- Post Title: Sonic and Sega All-Stars Racing .zig and .zif model formats

(well, Ace, how it comes to answer this request one and a half year later?  )

I've cut out the DXT5 file from BillyHatcher.zig_dec at offset 0xCC554 (.. 0x221B44) with header.



AllStarRacing_DXT.JPG (71.41 KiB) Viewed 331 times
## Post #4
- Username: awef
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 28, 2018 3:19 am
- Post datetime: 2018-06-27T23:23:22+00:00
- Post Title: Sonic and Sega All-Stars Racing .zig and .zif model formats

Ummmm ok I'm trying to get 3d models and i have a .sig_dec file.. now what?
## Post #5
- Username: Vovi Ben
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jan 29, 2022 12:04 am
- Post datetime: 2022-09-10T11:40:21+00:00
- Post Title: Sonic and Sega All-Stars Racing .zig and .zif model formats

> Reply from Acewell ↑Sun Apr 16, 2017 12:48 pm at Sun Apr 16, 2017 12:48 pm
>
> 
both samples are zlib compressed, here is a bms script for that  
Code: Select allcomtype zlib_noerror
get SIZE asize
get NAME basename
get EXT extension
string NAME p "%s_dec.%s" NAME EXT
clog NAME 0 SIZE SIZE
 

the zig file contains model and texture data.
the zif file looks like an index file for the zig file.

first submesh in BillyHatcher.zig
BillyHatcher_zig.png
Super Random, but in the Console versions they are different, like there were encrypted,
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1oLjPghV4Peapzb0xvO3yx-qnkOgX5u_5?usp=sharing) 
These are from the xbox Version,
i hope that you can make a quickbms script for that
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-10T15:55:01+00:00
- Post Title: Sonic and Sega All-Stars Racing .zig and .zif model formats

> Reply from Vovi Ben ↑Sat Sep 10, 2022 7:40 pm at Sat Sep 10, 2022 7:40 pm
>
> i hope that you can make a quickbms script for thatChances are low since Ace is gone.  
After using offzip:.
.



MainMenu-zig-offzipped_dat.jpg (107.23 KiB) Viewed 96 times
## Post #7
- Username: Vovi Ben
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jan 29, 2022 12:04 am
- Post datetime: 2022-09-10T19:56:13+00:00
- Post Title: Sonic and Sega All-Stars Racing .zig and .zif model formats

> Reply from shakotay2 ↑Sat Sep 10, 2022 11:55 pm at Sat Sep 10, 2022 11:55 pm
>
> 
Vovi Ben wrote: ↑Sat Sep 10, 2022 7:40 pmi hope that you can make a quickbms script for that
Chances are low since Ace is gone.  
After using offzip:.
.
MainMenu-zig-offzipped_dat.jpg

Oh, Thats Bad, but thank you very much!
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-10T20:51:48+00:00
- Post Title: Sonic and Sega All-Stars Racing .zig and .zif model formats

Sorry, no, he's still there. Sometimes.  

(Just found his last post as of Sat Jul 16, 2022.)
