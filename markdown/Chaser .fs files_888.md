## Post #1
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-30T13:48:28+00:00
- Post Title: Chaser .fs files

You can make tool for Chaser .fs files?
I can send file.
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-31T13:09:30+00:00
- Post Title: Chaser .fs files

If you could post the file here on the boards, we will be able to take a look at it. I hope the file isn't too big 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-31T14:27:06+00:00
- Post Title: Chaser .fs files

[quote="friendsofwatto"]If you could post the file here on the boards, we will be able to take a look at it. I hope the file isn't too big 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org) 
I dont know how paste file? Where option paste file??? 
I send file in email adress. 
Look at.
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-31T15:35:04+00:00
- Post Title: Chaser .fs files

FORMAT

[0] - 0
[1] - DATA BLOCK (RESOURCES (actually text files))

Now, go to the end of the file (EOF). 

[EOF-4] - Tailstart (32-bit value pointing to the start of the tail)

The Tailheader:

[Tailstart-3] - Tailsize (32-bit value)
[4-7] - UNKNOWN (8192)
[8-11] - Size of Archivestring (?)
[12-15] - number of directories? No, probably something different
[16-19] - Size of the resource string block (RESSIZE) (you'll need it)
[20-23] - Filenumber (number of resources, string entries etc.)
[24-(24+RESSIZE)] - the Resource string block, a list of null-terminated strings. 
[(24+RESIZE+1)-(EOF-4)] - Resource info: Offset (32-bit), then Size (32-bit) in the same order as the Resource string block, repeat Filenumber times ofcoz. 

Easy huh!
## Post #5
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-31T16:25:07+00:00
- Post Title: Chaser .fs files

> Reply from Mr.Mouse
>
> FORMAT

[0] - 0
[1] - DATA BLOCK (RESOURCES (actually text files))

Now, go to the end of the file (EOF). 

[EOF-4] - Tailstart (32-bit value pointing to the start of the tail)

The Tailheader:

[Tailstart-3] - Tailsize (32-bit value)
[4-7] - UNKNOWN (8192)
[8-11] - Size of Archivestring (?)
[12-15] - number of directories? No, probably something different
[16-19] - Size of the resource string block (RESSIZE) (you'll need it)
[20-23] - Filenumber (number of resources, string entries etc.)
[24-(24+RESSIZE)] - the Resource string block, a list of null-terminated strings. 
[(24+RESIZE+1)-(EOF-4)] - Resource info: Offset (32-bit), then Size (32-bit) in the same order as the Resource string block, repeat Filenumber times ofcoz. 

Easy huh!
Very Good, 
Ammm......  You can make tool for Extraction and Packing .fs files . Not MultiEx plugin. MultiEX Programm write error in my OS . Please!
## Post #6
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-09-01T05:41:51+00:00
- Post Title: Chaser .fs files

Yes, and in DTA format(Mafia) i think what maybe uses LZO compression method. 
How you think?
## Post #7
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-09-01T11:55:56+00:00
- Post Title: Chaser .fs files

Thanks, I got your email.

I will take a look into the format, and try to come up with a packer for you. If it can be done, I will let you know when it is ready.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #8
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-09-04T12:38:49+00:00
- Post Title: Chaser .fs files

Hi again,

I have written a plugin for my Game Extractor program that should allow you to read and write Chaser *.fs files - however, as with all packers, I cannot guarentee that it will work in-game (oftern the games do a check to see if the file has been altered).

But, we can always try. You can get Game Extractor (and the FS plugin) from [http://www.watto.org/extract](http://www.watto.org/extract)

Good luck, I hope it works OK for you.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #9
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-09-05T10:24:28+00:00
- Post Title: Chaser .fs files

> Reply from friendsofwatto
>
> Hi again,

I have written a plugin for my Game Extractor program that should allow you to read and write Chaser *.fs files - however, as with all packers, I cannot guarentee that it will work in-game (oftern the games do a check to see if the file has been altered).

But, we can always try. You can get Game Extractor (and the FS plugin) from http://www.watto.org/extract

Good luck, I hope it works OK for you.

WATTO
watto@watto.org
http://www.watto.org

Thanks, 
I download you program, but this recuered JAVA Software??? Where i get it??? 
Thanks for you support!
## Post #10
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-09-05T11:57:20+00:00
- Post Title: Chaser .fs files

Yes, Java is required.

You can get java from [http://www.java.com](http://www.java.com), or you can find a direct link from my website.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
