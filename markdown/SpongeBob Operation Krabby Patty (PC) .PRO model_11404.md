## Post #1
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2014-04-10T21:13:16+00:00
- Post Title: SpongeBob Operation Krabby Patty (PC) .PRO model

This game uses .pro as a model format. The only program I've found that can read them is quick3D, but it just crashes when it tries to load them. They look fairly simple, so here's literally all the models in the game. There's not very many.
[https://www.dropbox.com/s/8aqpsm9ygyxv8 ... p_Pros.zip](https://www.dropbox.com/s/8aqpsm9ygyxv8jg/sbopkp_Pros.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-11T09:23:55+00:00
- Post Title: SpongeBob Operation Krabby Patty (PC) .PRO model

> Reply from lemurboy12
>
> They look fairly simple, [...]from what you see ingame?
They're not simple enough to be extracted by hex2obj (except as a point cloud).



sponge_pro.JPG (41.1 KiB) Viewed 160 times
## Post #3
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2014-04-11T19:40:06+00:00
- Post Title: SpongeBob Operation Krabby Patty (PC) .PRO model

> Reply from shakotay2
>
> lemurboy12 wrote:They look fairly simple, [...]from what you see ingame?
They're not simple enough to be extracted by hex2obj (except as a point cloud).
sponge_pro.JPG
Is that as far as it can get?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-12T05:35:43+00:00
- Post Title: SpongeBob Operation Krabby Patty (PC) .PRO model

what?

Here's a modified version 0.22a of hex2obj:
[Hex2obj_0.22a.zip](http://www.uploadmb.com/dw.php?id=1397280590)

It's the exe file only. So you'll need to download the complete version of hex2obj from my sigs link
to get it working.

You have to enter 49 as a "face's offset" into the edit box right to the 'std' button.

Use this h2o file for boat2s.pro, Object04:
0x453 81
Vb1
18 99
0xE5 48
040000
0x0 255

I tried an UVpos of 14 and Word_UV but seems is not.
Maybe UVs are merged as full floats into the face indices block - didn't check this.

There's further submeshes in this pro file:
S_R_Arm
S_L_ARM
Line09

S_L_SHOE
Object01
Cylinder14
Sphere07
Cylinder12
Cylinder13
Cylinder08

They are marked by a sequence of 8 x FF or 12 x FF.

h2o file for S_R_ARM:
0xF7A 120
Vb1
18 99
0xCAE 39
040000
0x0 255

Don't forget to enter the 49 offset!

For start of vertices and face index block (sponge.PRO) have a look at this picture:



sponge.counts.JPG (40.83 KiB) Viewed 140 times



Don't forget to multiply the face count (0xB8) with 3 to get the face indices count (552 dec.) for hex2obj.
## Post #5
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2014-04-12T14:59:52+00:00
- Post Title: SpongeBob Operation Krabby Patty (PC) .PRO model

err..... what? I was thinking more of a quickbms script. All that is way far ahead of what I know.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-12T16:12:19+00:00
- Post Title: SpongeBob Operation Krabby Patty (PC) .PRO model

might take some time 'till someone will write a quickbms script for you...

Meanwhile you could try out hex2obj. It's a tool designed for noobs
and it's easier to use than you might think of.

Load boat2s.pro and boat2s.h2o into hex2obj.
Press the mesh button:



boat2s.jpg (80.46 KiB) Viewed 121 times



boat2s.h2o is a simple text file containing the data shown in my previous post.

All you have to do to get further submeshes from boat2s.pro is
to find the startaddresses of face indices and vertices and the face indices count.
(The vertex count is calculated automatically.)

[](http://www.pic-upload.de/view-22848127/boat2s_addresses.jpg.html)
## Post #7
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2014-04-12T18:00:09+00:00
- Post Title: SpongeBob Operation Krabby Patty (PC) .PRO model

I'm trying to get all the values for BOAT3.PRO, but I don't know what I'm doing. Where do I start?
## Post #8
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2014-04-12T18:34:22+00:00
- Post Title: SpongeBob Operation Krabby Patty (PC) .PRO model

Actually, nevermind. I found out that the game uses the engine Power Render, and the SDK has a model viewer. Thanks for your help, though.
## Post #9
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-04-13T16:18:20+00:00
- Post Title: SpongeBob Operation Krabby Patty (PC) .PRO model

> Reply from lemurboy12
>
> Actually, nevermind. I found out that the game uses the engine Power Render, and the SDK has a model viewer. Thanks for your help, though.

The 3D Object Converter supports the Power Render .pro format since about 9-10 years.
[http://3doc.i3dconverter.com](http://3doc.i3dconverter.com)
