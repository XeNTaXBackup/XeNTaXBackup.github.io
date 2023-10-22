## Post #1
- Username: MinXWin
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Dec 12, 2020 12:20 am
- Post datetime: 2020-12-11T16:52:10+00:00
- Post Title: Help Extracting Models From Atmosphir

Okay, firstly, hello hello! I am super new here.. My name is Min. Pleasure to meet you all! Hopefully I've posted this in the correct section! Apologies if I am messing anything up!

So, I have been trying, and failing, to rip models from this old version of a PC game. I am a major newbie to this, but I've gone through a few different tools attempting to extract the models from this game into something Blender, or 3DS Max will read.  I've tried NinjaRipper, 3DRipperDX, and poked about with Model Researcher... all to no avail. Now, there is a very high chance this is user error, I am super new at this. Both NinjaRipper and 3DRipperDX produce nothing when pressing the "rip" hotkey, and I've experimented opening the games many files in local_db, but apart from seeing comments in the HEXview, I've again come up with nothing.


I am sure this is probably a super basic stumbling point, I've only been experimenting with this stuff for about three weeks now. But if anyone has any tips, or if anyone feels willing to give it a whirl themselves, I would be so so grateful! 
Download Here 
If you do attempt it, it's worth noting to get to a section were you could actually rip models from, you'll need to click on "Design" not "Play" in the design page, you'll be able to click and place some blocks! The play button doesn't actually work anymore...haha

If anyone is able to help me out, that would be so awesome-rad. Thank you in advance!

 EDIT:also worth noting the sharing of this install is entirely within the good will of its creators. The game is and always was a free product, and given it's original site is now defunct, the sharing of it has kept it aloft for many a years! Thought I'd share before I accidentally step on any toes.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-12-12T16:32:15+00:00
- Post Title: Help Extracting Models From Atmosphir

Getting some vertices (search for "array/vertex") from 116 file ("hanging platform"):
.



hanging_platform.png (97.93 KiB) Viewed 173 times


Seems there's an issue with the faces or - more likely- I accidentally used vertex colors for scaling (per vertex!, hahaha).
Without  this it looks different (right part of pic) but still not correct, I assume.
## Post #3
- Username: MinXWin
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Dec 12, 2020 12:20 am
- Post datetime: 2020-12-14T04:07:15+00:00
- Post Title: Help Extracting Models From Atmosphir

> Reply from shakotay2 ↑Sun Dec 13, 2020 12:32 am at Sun Dec 13, 2020 12:32 am
>
> 
Without  this it looks different (right part of pic) but still not correct, I assume.

Oh, thank you so much for the quick reply! I am so so grateful! I am still so inexperienced with this stuff

Haha, yeah "hanging platform" probably refers to an item that looks like this 

Are you using Model Researcher? Haha, I've got a lot to learn

Particularly, I've been hunting for the model for a character named Cameron. after a ton of digging, I've found four files 572, 664, 573, 571 which refer to a "cameron_mesh" but so far no luck in actually converting it to a viewable object file. Especially since some seem to be animation files, concerning the bones and poses..
I think file number 571 is the most promising but I could be completely misreading things

Thank you so much again!
## Post #4
- Username: MinXWin
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Dec 12, 2020 12:20 am
- Post datetime: 2020-12-15T07:48:11+00:00
- Post Title: Help Extracting Models From Atmosphir

Been experimenting for a night or two-- and I've not had any success yet. But I've done a lot of tutorial reading/watching. I've been opening the local_db files in Model Researcher. Skipping past the header bit in the offset and slowly incrementing the padding... ehh nothing but point clouds thus far.

So after doing a mass search it seems 571 is cameron's mesh, haha.. no luck yet. But question!  In the image below, I've noticed most of the data sort of forms into these vertical bars. Firstly between 00 - 02, then 05 - 0a, then 0d - 0f.. With padding set to 2, the reading point aligns perfectly with these bars... Is that promising, or just happenstance?? I'm obviously still getting nothing but garbled mess, just curious of this should inspire hope or not. 


also is this format even brute force-able this way?? Like, does this look.. I don't know, encrypted or is that something that you can even tell visually?


if anyone wants investigate this specific file, I've gone and [uploaded it as an individual file](https://www.mediafire.com/file/wfrijgk8oj8cd39/571/file) since its only like 200KB sooo if you'd like to take a look, but dont want to download the whole game
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-12-15T09:28:31+00:00
- Post Title: Help Extracting Models From Atmosphir

Guess, you'll need to use Bigchillghost's AMR.
.



116_hex.png (43.6 KiB) Viewed 36 times


This is for "hanging platform", black rectangles contain the first vertex (doubles).
edit: had to correct this from "floats" to "doubles" (big thanx to Bigchillghost for the hint!)

Face indices start at 0x31B9 (DWords, 4 bytes). Count is 318 (dec), DWord at 0x31B5.
## Post #6
- Username: MinXWin
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Dec 12, 2020 12:20 am
- Post datetime: 2020-12-15T11:40:45+00:00
- Post Title: Help Extracting Models From Atmosphir

Ah, coding would be to... like tell MR how to interpret the bytes?

Also, quick aside -- in your original post where you were able to get something to render, if that was MR as I assume, what "type" were you using for the vertices? The tutorial I was fallowing was using "short-unsigned" ... is that applicable here? Or were you using float here?

I am probably asking a bunch of really basic questions, but I do genuinely thank you for being so willing to help!
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-12-15T13:15:42+00:00
- Post Title: Help Extracting Models From Atmosphir

No, I didn't use MR - some C coding on the fly using floats.
But obviously I'm missing something - the vertices need a special treatment, I guess.
Maybe sort them by those "indices", 0x20, 0x40, 0x80...?
Or use a threshold (that worked for a 3D format with a similar problem), at no avail here.
Also we've lots of doubles here.

To get the face indices I use hex2obj (view link in my sig).
## Post #8
- Username: MinXWin
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Dec 12, 2020 12:20 am
- Post datetime: 2020-12-15T22:16:57+00:00
- Post Title: Help Extracting Models From Atmosphir

Ahh, thank you for all the help! A lot to learn about for me, haha..

Really wish I managed to get NinjaRipper working but hit a similar dead end. I am encouraged by the fact that I've been able to find the exact file I am looking for, so it is obviously there... I'll just need to figure out how interpret the hexadecimal into something usable. So the path forward is like... clear, I guess. I've heard that some projects people spend months at properly brute forcing a method, and oh god do I hope that isn't what I am looking at here, hahaha 

I wonder if the duplicates could be the UV coordinates been some how packaged along side the verts... I don't know
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-12-15T22:52:47+00:00
- Post Title: Help Extracting Models From Atmosphir

> Reply from MinXWin ↑Wed Dec 16, 2020 6:16 am at Wed Dec 16, 2020 6:16 am
>
> I wonder if the duplicates could be the UV coordinates been some how packaged along side the verts...Guess 'no' (near to 100%  ), search for array/tex_uv_0, there's the uv data to be found.
## Post #10
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-12-16T11:20:30+00:00
- Post Title: Help Extracting Models From Atmosphir

> Reply from MinXWin ↑Tue Dec 15, 2020 3:48 pm at Tue Dec 15, 2020 3:48 pm
>
> 
if anyone wants investigate this specific file, I've gone and uploaded it as an individual file since its only like 200KB sooo if you'd like to take a look, but dont want to download the whole game
Using AMR (check the 2nd link in my sig):



571.png (135.68 KiB) Viewed 91 times



Edit: the structure is kinda similar to FBX:

```
	long	strLen
	char	attrName[strLen]
	byte	dataTypeFlag // 0x15: double; 0x17: byte; 0x14: int32
	long	elementCount // vertexCount*vecLen
	byte	attrData[elementCount*dataTypeSize]

```


> Reply from shakotay2 ↑Tue Dec 15, 2020 9:15 pm at Tue Dec 15, 2020 9:15 pm
>
> 
Maybe sort them by those "indices", 0x20, 0x40, 0x80...?
Or use a threshold (that worked for a 3D format with a similar problem)
Which format is it?
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-12-16T12:56:39+00:00
- Post Title: Help Extracting Models From Atmosphir

Oh, shxt, can't remember having ever seen a 3D format using double for the vertices...  
.



who_the_hell_uses_double_for vertices.png (26.21 KiB) Viewed 82 times
## Post #12
- Username: MinXWin
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Dec 12, 2020 12:20 am
- Post datetime: 2020-12-16T14:47:15+00:00
- Post Title: Help Extracting Models From Atmosphir

> Reply from Bigchillghost ↑Wed Dec 16, 2020 7:20 pm at Wed Dec 16, 2020 7:20 pm
>
> 
Using AMR (check the 2nd link in my sig):
OHMYGOSH, thank you so so much-- haha, with copying off your homework, I literally had it done in like 2 minutes... Haha, major major props to you! 

Haha, thank you to everyone who helped, shakotay2 as well! I am slapping myself for not mentioning that the game exclusively used doubles, as I had known that, having messed around in cheat engine with it.. Haha, should've said that earlier!

For going forward, extracting other models..What do you guys recommend using? Like what was your workflow for extracting these two models? Model Researcher has a great hex viewer, but I don't think I am able to select doubles as the data type, and AMR did an amazing job with the values you gave me, but I am not sure what method I should use for finding the needed addresses for other objects.

Well thank you all so so much for all this!
## Post #13
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-12-17T00:36:22+00:00
- Post Title: Help Extracting Models From Atmosphir

> Reply from MinXWin ↑Wed Dec 16, 2020 10:47 pm at Wed Dec 16, 2020 10:47 pm
>
> 
For going forward, extracting other models..What do you guys recommend using? Like what was your workflow for extracting these two models?... I am not sure what method I should use for finding the needed addresses for other objects.
First you need a proper hex editor. HexEdit is recommended. Get it from the link in this post.
[viewtopic.php?p=139002#p139002](viewtopic.php?p=139002#p139002)
For addresses, just use that example as a base and check the string identifiers before those addresses. The structure of the data is mentioned in my previous post. You can get the vertex count by dividing the element count with the attribute's vector length, or use the Calculated button of AMR to get it from the digest of the polygon indices.
## Post #14
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2020-12-17T00:51:36+00:00
- Post Title: Help Extracting Models From Atmosphir

> Reply from Bigchillghost ↑Thu Dec 17, 2020 8:36 am at Thu Dec 17, 2020 8:36 am
>
> 
First you need a proper hex editor. HexEdit is recommended. Get it from the link in this post.
viewtopic.php?p=139002#p139002
I use SweetScape 010 as my hex editor.
It allows you to write mini programs.
