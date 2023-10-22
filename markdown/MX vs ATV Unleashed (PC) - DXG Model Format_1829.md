## Post #1
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-12T22:05:24+00:00
- Post Title: MX vs ATV Unleashed (PC) - DXG Model Format

Here's a sample DXG file...I'm sure it's a DirectX Geometry file.

You guys are doing so well with everything with this game!

It's an outhouse.  

Thanks again guys.
[nat05_outhouse.zip](https://xentaxbackup.github.io/file/691_nat05_outhouse.zip)
## Post #2
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-18T11:46:52+00:00
- Post Title: MX vs ATV Unleashed (PC) - DXG Model Format

Any luck this 3D format?
## Post #3
- Username: Extreme
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Mar 26, 2006 8:21 am
- Post datetime: 2006-04-18T23:32:09+00:00
- Post Title: MX vs ATV Unleashed (PC) - DXG Model Format

I found the perfect example they left 2 of the same models in there but in different formats one is SLT (the 3d format) 
And the other is DXG (the game file) so if someone can work out how to convert the dxg 2 slt and back again that would be it 

3d files
[http://www.mcm2extreme.com/uploads/monstertruck6.zip](http://www.mcm2extreme.com/uploads/monstertruck6.zip)

And the golf cart is in there lol


Extreme
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-19T04:29:36+00:00
- Post Title: MX vs ATV Unleashed (PC) - DXG Model Format

Could it not be that the SLT is the actual model that refers to textures in the DXG?
## Post #5
- Username: Hunter
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 17, 2006 12:52 pm
- Post datetime: 2006-04-19T06:37:20+00:00
- Post Title: MX vs ATV Unleashed (PC) - DXG Model Format

I personaly have not heard of a directx geometry format, however the dxg file you have here is most definately a model format.

if you jump to offset 0x014E you'll see:

```
word TriangleStripLength;
```


following these data will be a triangle strip style list of faces. Each item in this list is a word(unsighed short) vertex buffer index.  The length of this list is described as above(in this case 0x01B0 items, 0x0360 bytes).

Next up will be the list of vertices(in this case 0x011B verts).  Each vertex has 8 floats (in this case total size of vertex buffer is 0x2360).  I'm going to make a wild assumption, and say that the vertex format is as follows:

```
float y;
float z;
float normalx;
float normaly;
float normalz;
float tu;
float tv; 
```


This is the most standard format for simple verts, I'd be very surprised if it was incorrect.  

I haven't looked much at the data in the header before these data.  I'm guessing it will list name of model, bounding box, material properties(including a link to a texture or two), possibly scaling and/or origin, and maybe other properties used for physics.  To make a converter from this point, one would only have to figure out the header data.

Hopefully this helps.
## Post #6
- Username: Extreme
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Mar 26, 2006 8:21 am
- Post datetime: 2006-04-19T12:44:21+00:00
- Post Title: MX vs ATV Unleashed (PC) - DXG Model Format

Hunter it looks like u know what u r talking about but u have lost me a bit there sorry, I donâ€™t even know how to look In the header. 
all this code is very new to me 
I know the SLT is the geometry and it looks like its inside the dxg we have a max plugin that exports to SLT its use for a game called mcm2 
Iv got a small program that converts a slt 2 lwo if that would help anyone?



P.S whats the best program to look into the headers and the code
Thanks 


Extreme
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-19T13:29:45+00:00
- Post Title: MX vs ATV Unleashed (PC) - DXG Model Format

Try Hex Workshop from BreakPoint Software
## Post #8
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-19T13:55:51+00:00
- Post Title: MX vs ATV Unleashed (PC) - DXG Model Format

Extreme, I don't think these guys know what MCM2 (like you and me) is...what he mean is a game called... Motocross Madness 2 by Microsoft, which was developed by a company called Rainbow Studios.  Which are the same people who made MX vs. ATV Unleashed.

Hope this clearified things.
## Post #9
- Username: Extreme
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Mar 26, 2006 8:21 am
- Post datetime: 2006-04-19T16:01:26+00:00
- Post Title: MX vs ATV Unleashed (PC) - DXG Model Format

Yeah sorry about that.
 My head is in a shed reading all this code 
and i dont have a clue what im looking for lol

Thanks Mr.Mouse 
Iv got that program now I need to learn how to work it now   

Extreme
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-19T17:48:22+00:00
- Post Title: MX vs ATV Unleashed (PC) - DXG Model Format

FYI:

Tutorial about those SLT files:

[http://www.harmoniccycle.com/hc/3d-g-mcm2-tut-obj01.htm](http://www.harmoniccycle.com/hc/3d-g-mcm2-tut-obj01.htm)
## Post #11
- Username: Extreme
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Mar 26, 2006 8:21 am
- Post datetime: 2006-04-19T19:33:31+00:00
- Post Title: MX vs ATV Unleashed (PC) - DXG Model Format

Yeah Iv made a few hundred of them on my site 
[http://www.mcm2extreme.com/files/pafile ... egory&id=6](http://www.mcm2extreme.com/files/pafiledb.php?action=category&id=6)
The slt isnâ€™t the problem its getting the dxg to slt 
Thanks
## Post #12
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-19T19:34:01+00:00
- Post Title: MX vs ATV Unleashed (PC) - DXG Model Format

By the way, Extreme is absolutely right. The DXG files look to be binary SLT files. The similarities are right there. It should be possible to convert the DXG2SLT.
## Post #13
- Username: bruceatk
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Apr 03, 2006 1:50 am
- Post datetime: 2006-04-19T20:28:04+00:00
- Post Title: MX vs ATV Unleashed (PC) - DXG Model Format

In MCM 2 they had an SLT(ext) and SLB(inary) files.  I believe the DXG is an SLB with more capabilities.

Bruce
## Post #14
- Username: Kamshaft
- Rank: VIP member
- Number of posts: 43
- Joined date: Thu Mar 30, 2006 1:18 am
- Post datetime: 2006-04-19T20:52:12+00:00
- Post Title: MX vs ATV Unleashed (PC) - DXG Model Format

> Reply from Mr.Mouse
>
> By the way, Extreme is absolutely right. The DXG files look to be binary SLT files. The similarities are right there. It should be possible to convert the DXG2SLT.

Awesome! Then we'll be able to add our own object to the game! yay!
## Post #15
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-20T04:43:10+00:00
- Post Title: MX vs ATV Unleashed (PC) - DXG Model Format

Well, I'mnot saying *I* could write a converter,I'm just saying I see there's similarities that should make it possible, theoretically. Bruce's comment however makes it more difficult, as extra capabilities are unknown to me. 

There are more coders out here though, perhaps anyone can give a shot at creating a converter.

I'm not really that much into graphic formats, others should perhaps qualify more?
## Post #16
- Username: ocr_smokngrn
- Rank: VIP member
- Number of posts: 27
- Joined date: Mon Apr 03, 2006 11:57 am
- Post datetime: 2006-04-22T06:28:57+00:00
- Post Title: 

[http://turbo.gamedev.net/undelphix.asp](http://turbo.gamedev.net/undelphix.asp) 
"Quite simply, UnDelphiX is a unofficial version of DelphiX powered by the official JEDI DirectX headers. It also has various "Better English" error messages, comments, and samples. It also will include DXG and DXW editors with full source."

Does maybe this have anything to do with dxg?
## Post #17
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-04-22T06:42:16+00:00
- Post Title: 

I tried that before, but it was something different. The DXG files are ASCII files, and they should be binary. No such luck I'm afraid. 

But thanks for trying to find something!
## Post #18
- Username: ocr_smokngrn
- Rank: VIP member
- Number of posts: 27
- Joined date: Mon Apr 03, 2006 11:57 am
- Post datetime: 2006-04-22T07:11:59+00:00
- Post Title: 

yeah im just reaching for anything at this point...
## Post #19
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-04-22T10:45:46+00:00
- Post Title: 

Funny   
as Google brings only this as a reference to "dxg" at first:  
[http://discussion.autodesk.com/thread.j ... dID=333785](http://discussion.autodesk.com/thread.jspa?threadID=333785)
and ....
this very Xentax thread as the second reference.
## Post #20
- Username: kevincolin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 14, 2006 11:21 am
- Post datetime: 2006-05-12T14:59:11+00:00
- Post Title: 

Any news guys?
## Post #21
- Username: LaRocket
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 27, 2006 11:52 pm
- Post datetime: 2006-06-27T16:05:29+00:00
- Post Title: 

> Reply from Extreme
>
> 
And the golf cart is in there lol


Extreme

what program are you using to view that golf cart? that may aid in another utility I had an idea for to help ease the process of creating skins.
## Post #22
- Username: Extreme
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Mar 26, 2006 8:21 am
- Post datetime: 2006-06-30T19:04:32+00:00
- Post Title: 

Thats Milkshape but i can see that being any help I hound a few slt files in there not dxg











Extreme
## Post #23
- Username: +COTAY
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon May 21, 2018 5:54 pm
- Post datetime: 2018-06-04T12:02:17+00:00
- Post Title: 

Hey, maybe Im getting banned for reviving this super old post, but Im starting to learn how to mod this game now in 2018 and I'd like to know if you guys already made some texture converter so I can use it.
Thanks in advance
