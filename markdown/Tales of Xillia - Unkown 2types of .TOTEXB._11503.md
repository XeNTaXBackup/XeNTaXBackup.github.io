## Post #1
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-12T15:26:33+00:00
- Post Title: Tales of Xillia - Unkown 2types of .TOTEXB.

Hi, I deleted my latest post since I found what was the problem.
There are unknown 2types of .TOTEXB files. Here is it. [https://www.mediafire.com/?xl8gww1aflwu2vo](https://www.mediafire.com/?xl8gww1aflwu2vo)

 Since chrrox's DDS script does not containing
'if type == 0x85', so 19010.TOTEXB can not be converted correctly. Look at it.

<another type> Header - 19010.TOTEXB


So, I think

```
putVarChr MEMORY_FILE2 0x?? 0x?? byte
endif

```
should be added to bms script but I wonder what is the value of '??'.
However, the most important thing for me is the font file. It has a unique value.

<font file> Header - 19996.TOTEXB


All of the other files at 0xC and 0x13 is 0, however font file is not 0 but 01 at 0xC and 10 at 0x13.
So 'get null short 1' should be changed for 19996.TOTEXB. What does 10 means..?
And How could I modified chrrox's DDS script..? In the chrrox's script, there are already 'if type == 0x86' but all of other files at 0x13 is 0.
So font file is different from other 0x86 types. I need some help.   

I upload chrrox's bms script rather than post it. Because it is too long.
[tozDDS.zip](https://xentaxbackup.github.io/file/7326_tozDDS.zip)
## Post #2
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-15T10:55:05+00:00
- Post Title: Tales of Xillia - Unkown 2types of .TOTEXB.

Can someone explain what is this file..?

[https://www.mediafire.com/?909ravuqm8x8cmz](https://www.mediafire.com/?909ravuqm8x8cmz)
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-05-15T22:58:22+00:00
- Post Title: Tales of Xillia - Unkown 2types of .TOTEXB.

looks like font-related files.
## Post #4
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-16T01:54:53+00:00
- Post Title: Tales of Xillia - Unkown 2types of .TOTEXB.

> Reply from howfie
>
> looks like font-related files.

 Yeah. I agree with you. But it is hard to figure it out..
For all of the other types, there are no problems to convert it to DDS.


But the 2 unknown types which I mentioned has broken image.
For example, 19996.TOTEXP .
Look at 19996.TOTEXB, the dimension of the image should be 512x512 and DTX1 because 02 at 0x15.

But if I watch it on width 1024 via TextureFinder v2.1, it seems different.
<WIDTH 1024, SHIFT 0>


<WIDTH 1024, SHIFT 8>
## Post #5
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2014-05-16T10:16:27+00:00
- Post Title: Tales of Xillia - Unkown 2types of .TOTEXB.

good news:
encoding is actually DXT5, and the dimensions are indeed 512 x 512.
that one file contains sixteen pages of 512x512 DXT5 images.

bad news:
i think data is swizzled. neither morton nor XGUntileSurface. doesn't seem complex.
sorry, don't have time to spend to figure it out. it's something simple though, maybe perhaps as easy as
[http://fgiesen.wordpress.com/2011/01/17 ... swizzling/](http://fgiesen.wordpress.com/2011/01/17/texture-tiling-and-swizzling/)
## Post #6
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-16T12:00:05+00:00
- Post Title: Tales of Xillia - Unkown 2types of .TOTEXB.

> Reply from howfie
>
> good news:
encoding is actually DXT5, and the dimensions are indeed 512 x 512.
that one file contains sixteen pages of 512x512 DXT5 images.

bad news:
i think data is swizzled. neither morton nor XGUntileSurface. doesn't seem complex.
sorry, don't have time to spend to figure it out. it's something simple though, maybe perhaps as easy as
http://fgiesen.wordpress.com/2011/01/17 ... swizzling/

Thanks. Now, I just waiting for someone who can afford it.
## Post #7
- Username: powoct
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 12, 2011 5:59 pm
- Post datetime: 2014-05-17T15:12:27+00:00
- Post Title: Tales of Xillia - Unkown 2types of .TOTEXB.

> Reply from albert1905
>
> howfie wrote:good news:
encoding is actually DXT5, and the dimensions are indeed 512 x 512.
that one file contains sixteen pages of 512x512 DXT5 images.

bad news:
i think data is swizzled. neither morton nor XGUntileSurface. doesn't seem complex.
sorry, don't have time to spend to figure it out. it's something simple though, maybe perhaps as easy as
http://fgiesen.wordpress.com/2011/01/17 ... swizzling/

Thanks. Now, I just waiting for someone who can afford it.

DXT1
[20140517231123.jpg](https://xentaxbackup.github.io/file/7344_20140517231123.jpg)
## Post #8
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-17T16:13:37+00:00
- Post Title: Tales of Xillia - Unkown 2types of .TOTEXB.

> Reply from powoct
>
> albert1905 wrote:howfie wrote:good news:
encoding is actually DXT5, and the dimensions are indeed 512 x 512.
that one file contains sixteen pages of 512x512 DXT5 images.

bad news:
i think data is swizzled. neither morton nor XGUntileSurface. doesn't seem complex.
sorry, don't have time to spend to figure it out. it's something simple though, maybe perhaps as easy as
http://fgiesen.wordpress.com/2011/01/17 ... swizzling/

Thanks. Now, I just waiting for someone who can afford it.

DXT1
Wow. Amazing. How did you do that?
Could you show me the way how to deswizzle and swizzle again..? Is it possible to edit the font file..?
## Post #9
- Username: powoct
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 12, 2011 5:59 pm
- Post datetime: 2014-05-18T05:47:27+00:00
- Post Title: Tales of Xillia - Unkown 2types of .TOTEXB.

font edit test
## Post #10
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-18T09:17:11+00:00
- Post Title: Tales of Xillia - Unkown 2types of .TOTEXB.

> Reply from powoct
>
> font edit test

Uhm.. Why did you just post a image..?
## Post #11
- Username: jrush
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Oct 25, 2012 6:10 pm
- Post datetime: 2014-05-18T20:52:07+00:00
- Post Title: Tales of Xillia - Unkown 2types of .TOTEXB.

I have a small question. Does this mean we can now rip models from the game?
## Post #12
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-19T00:09:35+00:00
- Post Title: Tales of Xillia - Unkown 2types of .TOTEXB.

> Reply from jrush
>
> I have a small question. Does this mean we can now rip models from the game?

 No. It's not. The subject of this thread is not concerned with model. It's about 2D texture.
But anyway.. since powoct doesn't explain anything so niether one of us can understand it.
## Post #13
- Username: Hideki
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 06, 2017 10:37 am
- Post datetime: 2017-09-10T02:24:06+00:00
- Post Title: Tales of Xillia - Unkown 2types of .TOTEXB.

I know this thread is dead, but did anyone ever figure out how powoct was able to decode the page that he did from this texture?


> Reply from powoct
>
> 

DXT1
