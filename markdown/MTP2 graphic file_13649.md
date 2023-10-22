## Post #1
- Username: Wesker90
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 08, 2015 3:51 pm
- Post datetime: 2015-12-10T08:37:43+00:00
- Post Title: MTP2 graphic file

Hello everyone, I'm trying to edit the mtp2 files of Berserk for ps2, all the textures and some images are in mtp2, as of now I've understand that the mtp2 format is a special type of tm2 swizzled.

I've an mtp2 converter but it doesn't work with the mtp2 of this game, only with mtp2d, because in the header it is written MTP2T, MTP2E  etc... there are various letters and symbols after mtp2.




I've managed to view somehow these mtp2 files, but they are swizzled twice, and even game graphic studio can't view them properly.





If someone can help me I'll be really greatful. Thanks for your time.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-12-10T20:33:20+00:00
- Post Title: MTP2 graphic file

Examples?
## Post #3
- Username: Wesker90
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 08, 2015 3:51 pm
- Post datetime: 2015-12-10T21:41:04+00:00
- Post Title: MTP2 graphic file

Hi Mr. Mouse, here's the file structure:

mtp_header { // 16bytes
byte[4] magic, "MTP2 "
byte[4] buffer offset
byte[4] buffer size
byte[2] unknown, always 1
byte[2] count
}

texture_entry { // 68bytes
byte[4] offset * 0x0100
byte[4] unknown, always 0x02
byte[2] compression??, usually 0x13 or 0x14
byte[2] unknown, usually 0x00
byte[4] unknown, value seems progressive
byte[12] padding? all 0's
byte[2] texture height
byte[2] texture width
byte[4] size * 0x0100
byte[16] padding? all 0's
string[16] texture name
}

And here's the file with an mtp2 converter(that don't work with this one) and its converted tm2 found in the game too.

Download: [mtp2+tm2](http://www.mediafire.com/download/zkxfapb57bc8g76/mtp2%2Btm2.rar)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-10T23:36:40+00:00
- Post Title: MTP2 graphic file

please provide proper linking instead of anonymous parts of information:

[viewtopic.php?f=18&t=8715](http://forum.xentax.com/viewtopic.php?f=18&t=8715)

So everyone can see mariokart64n was on a good way.

WHY don't you tell that?
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-12-12T00:12:10+00:00
- Post Title: MTP2 graphic file

WTF ? Indeed, WHY didn't you tell that? 

shakotay2, good catch.
