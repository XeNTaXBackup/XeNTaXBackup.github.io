## Post #1
- Username: barankaplan7878
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 06, 2017 11:40 pm
- Post datetime: 2018-07-05T20:28:59+00:00
- Post Title: [PC] City Racing ".msh" and ".dat" Files

I don't know how to open these ".msh" and ".dat" files. There are ".obj" files too but they have very small sizes. I want to edit these models, can anyone help me?

".obj", ".dat" and ".msh" files(".dat" files in the "msh" folder):
[https://drive.google.com/file/d/1IiRBg0 ... sp=sharing](https://drive.google.com/file/d/1IiRBg06w7VoOdw8Yh62evyLuQdC6aYXf/view?usp=sharing)

Thanks
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-06T05:13:57+00:00
- Post Title: [PC] City Racing ".msh" and ".dat" Files

point cloud is perfect but for some reason the face indices don't seem to fit



police-msh.jpg (53.86 KiB) Viewed 119 times
## Post #3
- Username: barankaplan7878
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 06, 2017 11:40 pm
- Post datetime: 2018-07-06T09:45:04+00:00
- Post Title: [PC] City Racing ".msh" and ".dat" Files

> Reply from shakotay2
>
> point cloud is perfect but for some reason the face indices don't seem to fit
police-msh.jpg

How you opened it?
## Post #4
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-07-06T11:03:03+00:00
- Post Title: [PC] City Racing ".msh" and ".dat" Files

> Reply from barankaplan7878
>
> 
How you opened it?
Hex2obj.

Here is the first mesh from "Main.msh" in the "01" folder. 



I first though vertex blocks are 64 bytes but there are actually 2 sets of vertex blocks each with 32 bytes blocks. So index start - (64 * vertex count) or  (32 * vertex count) to get to the start of the vertex blocks. This kinda reminded me of Skyforge.
## Post #5
- Username: barankaplan7878
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 06, 2017 11:40 pm
- Post datetime: 2018-07-06T11:37:34+00:00
- Post Title: [PC] City Racing ".msh" and ".dat" Files

> Reply from akderebur
>
> barankaplan7878 wrote:
How you opened it?
Hex2obj.

Here is the first mesh from "Main.msh" in the "01" folder. 



I first though vertex blocks are 64 bytes but there are actually 2 sets of vertex blocks each with 32 bytes blocks. So index start - (64 * vertex count) or  (32 * vertex count) to get to the start of the vertex blocks. This kinda reminded me of Skyforge.

I want to replace these models, what should I do?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-06T12:07:25+00:00
- Post Title: [PC] City Racing ".msh" and ".dat" Files

@akderebur: great!
How'd you know that vertex start address is 0x2A0, not 0xC0?
## Post #7
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-07-06T12:40:12+00:00
- Post Title: [PC] City Racing ".msh" and ".dat" Files

> Reply from shakotay2
>
> 
How'd you know that vertex start address is 0x2A0, not 0xC0?
First I checked the smaller vertex blocks near the end of the file and saw that vertex data is always 2 sets of 32 bytes blocks, so 64 * vertex count bytes in total. For the first mesh I also started from 0xC0, but when you start from there and go until index start, you end up with 142688 bytes. Divided by 64 it is 2229.5. It had to be same as vertex count (2222), so I figured I should start at a later offset. At the end I did index start (0x22E20) - (2222 * 64) and ended up with 0x2A0.
## Post #8
- Username: barankaplan7878
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 06, 2017 11:40 pm
- Post datetime: 2018-07-06T12:52:15+00:00
- Post Title: [PC] City Racing ".msh" and ".dat" Files

Anyone can tell me how to edit these files?
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-06T13:26:17+00:00
- Post Title: [PC] City Racing ".msh" and ".dat" Files

> Reply from barankaplan7878
>
> Anyone can tell me how to edit these files?well, did you ever edit/replace a model of any other 3D game?
If 'no' be informed that it's a VERY hard task in general. If you don't believe me search the forum for threads where an "obj to whatever3Dformat" conversion has been done. Guess there's not too many.

You'd need a FULL format analysis for such, without that it's senseless.

(If you're an experienced modder you might know that it's possible to edit static models as long as the new vertex count doesn't exceed the original one. Left over vertices have to be set to zero then.)

A "whatever3Dformat to obj" conversion generally can be done without a full format conversion.
See the 100s of threads where this has been done, especially using hex2obj.

This is what I recommend to start with, understanding the use of hex2obj or similar, i.e. Lazov's 3D Model Researcher for example or Model Inspector from Herbert3000.

You also might read Bigchillghost's tutorial about Reverse Engineering a Game Model.
## Post #10
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-07-09T11:23:26+00:00
- Post Title: [PC] City Racing ".msh" and ".dat" Files

what 'City Racing' you refering to, barankaplan7878?
## Post #11
- Username: barankaplan7878
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 06, 2017 11:40 pm
- Post datetime: 2018-07-10T09:27:32+00:00
- Post Title: [PC] City Racing ".msh" and ".dat" Files

> Reply from Tosyk
>
> what 'City Racing' you refering to, barankaplan7878?

This
