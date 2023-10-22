## Post #1
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2015-08-25T11:52:57+00:00
- Post Title: [PS2] Noddy and the Magic Book .CP2 and .PC

Can anyone help me rip these files? Thought of getting the car off the game for a parody/joke mod, so if anyone's up to cracking these archives open, feel free to ask me for the aforementioned archives.
## Post #2
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2015-11-06T03:53:22+00:00
- Post Title: [PS2] Noddy and the Magic Book .CP2 and .PC

Sorry for the bump, but anyone?
## Post #3
- Username: huckleberrypie
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-11-07T14:02:52+00:00
- Post Title: [PS2] Noddy and the Magic Book .CP2 and .PC

File sample?
## Post #4
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2015-11-16T00:30:09+00:00
- Post Title: [PS2] Noddy and the Magic Book .CP2 and .PC

> Reply from Gh0stBlade
>
> File sample?

Sorry for the late reply, but here's a zippyshare link to some of the archives. I really wanted to get the car from the game so I can convert it to GTA San Andreas, and since ripping it off through PCSX2 won't cut it, maybe extracting it straight from the archives will help. 

[http://www66.zippyshare.com/v/zYFTpoC5/file.html](http://www66.zippyshare.com/v/zYFTpoC5/file.html)
## Post #5
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2015-11-22T13:33:36+00:00
- Post Title: [PS2] Noddy and the Magic Book .CP2 and .PC

Again sorry for the bump, but is anyone up to cracking this format?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-22T15:12:11+00:00
- Post Title: [PS2] Noddy and the Magic Book .CP2 and .PC

dunno what you mean by "cracking", the 3D format turns out to be simple with some offset (8 bytes) between the face indices:



L11_PC.JPG (98.07 KiB) Viewed 96 times


But you may try to "crack" the uvs.
## Post #7
- Username: huckleberrypie
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-11-22T17:56:06+00:00
- Post Title: [PS2] Noddy and the Magic Book .CP2 and .PC

Files don't look packed. **GFX.pc files contain texture data. Looks like 8bit with a palette.
## Post #8
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2015-11-24T14:00:41+00:00
- Post Title: [PS2] Noddy and the Magic Book .CP2 and .PC

So the game's by and large simple enough to tinker with, right? How would I be able to open and convert the textures then? Also, how hard would it be to dechiper the UVW mapping scheme? I don't mind redoing them myself, but of course that would be way too tedious.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-25T06:19:04+00:00
- Post Title: [PS2] Noddy and the Magic Book .CP2 and .PC

> Reply from huckleberrypie
>
> Also, how hard would it be to dechiper the UVW mapping scheme?
He, who never tries will never know. 



NoddiesPlane_.jpg (178.73 KiB) Viewed 76 times



> I don't mind redoing them myself, but of course that would be way too tedious....
## Post #10
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2015-11-25T13:30:06+00:00
- Post Title: [PS2] Noddy and the Magic Book .CP2 and .PC

Thank you thank you thank you so much for the aid dude, much appreciated. Now, should I expect the same offsets/values to work consistently on most if not all models?

As for UV maps, what I meant was I don't mind manually redoing them myself, but as much as possible I would like to have them intact as well.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-25T14:05:17+00:00
- Post Title: [PS2] Noddy and the Magic Book .CP2 and .PC

> Reply from huckleberrypie
>
> Now, should I expect the same offsets/values to work consistently on most if not all models?how should that work? Each model/level having its individual vertex/face indices counts.
There's a chance that the start address of face indices (0x0034) might be the  same for most levels, but not sure.

The offset of 8 bytes after each three DWORD face indices should not change (but i checked two levels only).

Here's what I got from a GFX, seems to use some tiling/swizzling?


L9GFXgreyscale-cut.jpg (235.51 KiB) Viewed 69 times
## Post #12
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2015-11-26T06:46:31+00:00
- Post Title: [PS2] Noddy and the Magic Book .CP2 and .PC

Alright, I'd like to try out your Hex2Obj tool, but I have next to no clue as to how to find them offsets for me to rip the models, even with the tutorial you wrote.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-26T11:38:16+00:00
- Post Title: [PS2] Noddy and the Magic Book .CP2 and .PC

The tutorial was written to get simple models.
*.PC files are not too simple.

Here's a picture (L9.PC) which might help to find the startaddress of the vertices.
I've marked the last three faces (with 3 DWORD face indices each) using rectangles
and placed an arrow pointing to the first vertex.



L9_PC-startOfVertices.jpg (123.19 KiB) Viewed 60 times


HTH
## Post #14
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2015-11-26T13:55:56+00:00
- Post Title: [PS2] Noddy and the Magic Book .CP2 and .PC

> Reply from shakotay2
>
> The tutorial was written to get simple models.
*.PC files are not too simple.

Here's a picture (L9.PC) which might help to find the startaddress of the vertices.
I've marked the last three faces (with 3 DWORD face indices each) using rectangles
and placed an arrow pointing to the first vertex.
L9_PC-startOfVertices.jpg
HTH
What about the face indices? Where should I start? And as much as I'd like to do a Maxscript of this, it's beyond what I am able to come up with atm.
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-27T16:52:26+00:00
- Post Title: [PS2] Noddy and the Magic Book .CP2 and .PC

did you try 0x0034 as startaddress for the face indices?
## Post #16
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2015-11-28T00:57:06+00:00
- Post Title: Re: [PS2] Noddy and the Magic Book .CP2 and .PC

> Reply from shakotay2
>
> did you try 0x0034 as startaddress for the face indices?

Already did, but I'm still unable to save the file as an .obj.
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-28T17:26:33+00:00
- Post Title: Re: [PS2] Noddy and the Magic Book .CP2 and .PC

Please be more specific.
Is the mesh correctly displayed after you entered the addresses/counts and pressed 'mesh'?

If so use File/SaveAs mesh to create an obj file.

Assure that you've write access to the folder you're working in.
## Post #18
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2015-11-29T11:50:40+00:00
- Post Title: Re: [PS2] Noddy and the Magic Book .CP2 and .PC

> Reply from shakotay2
>
> Please be more specific.
Is the mesh correctly displayed after you entered the addresses/counts and pressed 'mesh'?

If so use File/SaveAs mesh to create an obj file.

Assure that you've write access to the folder you're working in.
Sorry for the vague reply. What I meant was I'm getting error messages saying that the obj file is invalid upon clicking Save or Mesh, even if the addresses/counts seem reasonable. I just have no idea on how to pull this off without having to ask you guys about it.
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-29T13:02:24+00:00
- Post Title: Re: [PS2] Noddy and the Magic Book .CP2 and .PC

please show your H2O parameters (and upload the model sample in case it's not contained in your uploaded DATA.rar)
## Post #20
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2015-12-01T09:03:15+00:00
- Post Title: Re: [PS2] Noddy and the Magic Book .CP2 and .PC

> Reply from shakotay2
>
> please show your H2O parameters (and upload the model sample in case it's not contained in your uploaded DATA.rar)
I couldn't save the H2O parameters you requested, so here's a screenshot, if it helps:


And here's the sample .PC mesh which I'm trying to open:
[http://www15.zippyshare.com/v/GIVUXGRE/file.html](http://www15.zippyshare.com/v/GIVUXGRE/file.html)
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-01T09:41:36+00:00
- Post Title: Re: [PS2] Noddy and the Magic Book .CP2 and .PC

(thx, I have that L9.PC already from your previous upload.)

I'm seriously asking myself WHY you don't use 0x0034 as the starting address for the face indices?
(See, life could be very easy if you did what you're advised to do.  )



L9_PC.jpg (132.25 KiB) Viewed 53 times



Also try to solve your saving problems.
If an H2O file exists simply rename it manually from L9_0.H2O to L9_0x.H2O for example.
(U should find it in the same folder where the L9.PC resides.)
## Post #22
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2015-12-02T00:08:08+00:00
- Post Title: Re: [PS2] Noddy and the Magic Book .CP2 and .PC

There, it works now. I also forgot to note that I forgot to copy the .PC meshes to a writable folder, hence why I get errors upon exporting. My question here is, how do I determine the count on Step 1? In the case of L9.PC, it's 19344.
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-02T00:43:07+00:00
- Post Title: Re: [PS2] Noddy and the Magic Book .CP2 and .PC

> Reply from huckleberrypie
>
> how do I determine the count on Step 1? In the case of L9.PC, it's 19344.have a look at the picture in my post as of Nov. 26th, 12:38 pm
to find the end address of face indices (FIs) block. Calculate length of FIs' block by subtracting 0x34.

0x1F800 - 0x34 = 128972 dec. 
Each face consists of 3 FIs (DWords) -> 12 bytes + additional 8 bytes = 20
128972 / 20 = 6448 faces; 6448 * 3 = 19344 face indices

btw: 6448*20=128960 but I'm too tired to be more precise...good night
## Post #24
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2015-12-02T02:51:22+00:00
- Post Title: Re: [PS2] Noddy and the Magic Book .CP2 and .PC

> Reply from shakotay2
>
> huckleberrypie wrote:how do I determine the count on Step 1? In the case of L9.PC, it's 19344.have a look at the picture in my post as of Nov. 26th, 12:38 pm
to find the end address of face indices (FIs) block. Calculate length of FIs' block by subtracting 0x34.

0x1F800 - 0x34 = 128972 dec. 
Each face consists of 3 FIs (DWords) -> 12 bytes + additional 8 bytes = 20
128972 / 20 = 6448 faces; 6448 * 3 = 19344 face indices

btw: 6448*20=128960 but I'm too tired to be more precise...good night

Sorry for inconveniencing you, but thanks! Should the address be constant or do I have to expect a different address for every file?
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-02T11:29:44+00:00
- Post Title: Re: [PS2] Noddy and the Magic Book .CP2 and .PC

> Reply from huckleberrypie
>
> Should the address be constant or do I have to expect a different address for every file?

> Reply from shakotay2
>
> huckleberrypie wrote:Now, should I expect the same offsets/values to work consistently on most if not all models?how should that work? Each model/level having its individual vertex/face indices counts.
## Post #26
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2015-12-02T12:48:12+00:00
- Post Title: Re: [PS2] Noddy and the Magic Book .CP2 and .PC

> Reply from shakotay2
>
> huckleberrypie wrote:Should the address be constant or do I have to expect a different address for every file?
shakotay2 wrote:huckleberrypie wrote:Now, should I expect the same offsets/values to work consistently on most if not all models?how should that work? Each model/level having its individual vertex/face indices counts.

Lol I almost forgot. Looks like I have to hunt them down then, but how?
## Post #27
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-02T13:23:14+00:00
- Post Title: Re: [PS2] Noddy and the Magic Book .CP2 and .PC

> Reply from huckleberrypie
>
> Looks like I have to hunt them down then, but how?

> Reply from shakotay2
>
> huckleberrypie wrote:how do I determine the count on Step 1? In the case of L9.PC, it's 19344.have a look at the picture in my post as of Nov. 26th, 12:38 pm
to find the end address of face indices (FIs) block.With "startaddress of face indices" (0x0034)
and face indices count entered hex2obj will tell you the vertex count (scroll down left lower listbox) 
after you've pressed the 'go1' button.

For vertices' start address use the aforementioned picture as an inspiration.

You're on your own now,  huckleberrypie.

Good luck.
