## Post #1
- Username: Loginoux
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 13, 2015 5:25 pm
- Post datetime: 2016-07-28T20:48:41+00:00
- Post Title: [Help] Hex2obj

Hi there...
I need help to find "Face indices" "vertices" and "UVs" from a simple 3d file format... I tried to look at the tutorial himself but i don't understand how they do it...
If someone have another tutorial or any help about hex2obj it will be very kind to show me it   
Thanks
## Post #2
- Username: vandarel
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Dec 30, 2015 5:55 am
- Post datetime: 2016-07-30T22:17:31+00:00
- Post Title: [Help] Hex2obj

Hello,
me too, i don't understand
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-31T04:12:18+00:00
- Post Title: [Help] Hex2obj

You should tell where you got stuck with the tutorial so that I can improve it.

There is no general recipe how to get the vertices, even for simple models.
For the face indices (FIs) the rule is: search for a scrambled alphabet.

Problem is: not every scrambled alphabet you find in 3D data represents FIs.

Simple 3D model formats use floats (4 bytes) for the vertices. (Half float vertices
or even shorts (WORD, 2 bytes) are harder to recognize.)

To find vertices (v) you'll need to find patterns. 

From the tutorial it says:
v: xx xx xx nn with nn= 42..44 (these are rough values only, can also be 3F, 40)

where v is a 4 bytes little endian value.
And 'yes', nn can also be 3D, 3E, or even 37 - my bad.
(Also BD if the MSB is set but that's beyond this tutorial.)

Don't know what this is: bytes, floats, endianess? Google for it.

But you don't need to know it. All you have to know is how to recognize patterns.
(If you can't: well, then you're lost - as simple as that.)

Let's have another look at the tutorial sample, hw_bu_000.bm.mod

The scrambled alphabet is to be found somewhere at file offset 0x3B00.
These face indices are integer numbers - they just count the vertices.

The integers consist of two bytes here. 20 00 (little endian) is 0x0020 or 32 decimal.

First vertex has the number 00 so search for the start of the face indices list
at 0x398D. There it reads 00 00 01 00 02 00, this is 0, 1, 2 in decimal.

This means that the vertices 0, 1 and 2 are used to construct the first face (triangle)
of the model.

(Won't bother how to find the end of the face indices list. It's at 0x4844.)

Now for the vertices - I've randomly marked some of them by rectangles:



tut_sample_hw_bu.jpg (150.9 KiB) Viewed 1119 times

You'll find the start address 0x56 by experience or trial & error.

In hex2obj toggle the 'noPtC' (no PointCloud) button to 'PtCld'.

Enter 56 (without the 0x) as vertices startaddress in step 3.
Leave the mode button in step 2 as 'seq' (sequential).
Press the 'mesh' button.

The point cloud of the upper body pops up.

Enter 398D as a face indices start address in step 1. Switch back to 'noPtC'.
Change the count from 500 to 100 or 150, as you wish.

Scroll down in the lower left list box. It reads: max face index: 142.
Enter this value as a count in step 3.

Press the 'go3' button. You happen to see a mesh, don't you?

Looks broken? Yeah, because we didn't use all FIs.

Calculate the number of FIs in two steps: a) you've to subtract the FIs' startaddress (0x398D)
from the endaddress+1 (0x4845) -> 0xEB8= 3768 bytes.

That's the size of the face indices block. b) Divide it by two (since the FIs
are two byte integers) -> FIs count= 1884.

hex2obj: enter 1884 as a count in step 1. Press 'go1', in the listbox there's a
max face index of 457 displayed. It's the highest vertex number.
So we enter this value as a count in step 3.

Pressing 'go3' shows the full upper body of the model.
## Post #4
- Username: devmode
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Jun 07, 2016 2:51 am
- Post datetime: 2016-08-02T00:01:08+00:00
- Post Title: [Help] Hex2obj

shakotay2 , 

I'm also "stuck" in your tutorial at the "start address of normals" step:

Previous we getting the size of the uv list = 0xE48

Next, in searching of the uvs start addresses you explain so We should "calculate back" from 12 bytes before, subtract 0xC from FIStart (0x398D), subtract 0xE48 from result and get 0x2B39.

Size of normals list is 0x156C

But for getting the start addresses of normals we need 0x2B2E - 0x156 = 0x15C2.
How obtained 0x2B2E instead 0x2B39?
0x2B2E that's 0x2B39 - 0xB?
You not explain it in tutorial.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-02T04:41:18+00:00
- Post Title: [Help] Hex2obj

> Reply from devmode
>
> But for getting the start addresses of normals we need 0x2B2E - 0x156 = 0x15C2.
How obtained 0x2B2E instead 0x2B39?
0x2B2E that's 0x2B39 - 0xB?
You not explain it in tutorial.I didn't feel the necessity to explain that because it's plain to see when looking at
hw_bu_000.bm in a hex editor. It's just a string (and a DWord, the length) to skip:



hw_bu-2B2E.JPG (41.85 KiB) Viewed 1091 times
## Post #6
- Username: IAmTheClayman
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Aug 01, 2016 8:46 am
- Post datetime: 2016-08-02T21:00:48+00:00
- Post Title: [Help] Hex2obj

As a fellow noob who just had an epiphany about all this in the past 24 hours maybe I can help out. Can you attach a copy of the file you're trying to work with?
## Post #7
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-08-21T11:03:55+00:00
- Post Title: [Help] Hex2obj

What if the format is saved in a way that the face indices first then the UV list? The tutorial assumes that the file format is UV list first then face indices right? because the start address is calculated by subtracting from the start address of the face indices?
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-21T13:59:43+00:00
- Post Title: [Help] Hex2obj

> Reply from majidemo
>
> What if the format is saved in a way that the face indices first then the UV list?should not matter because you enter the addresses for FIs and uvs independently.

> The tutorial assumes that the file format is UV list first then face indices right?It does for the tutorial sample.

> because the start address is calculated by subtracting from the start address of the face indices?This is just for the tutorial .bm sample that is sequential (was one of the first formats I used hex2obj on). (Meanwhile I experienced that most formats use 'blocked' or 'mixed' mode.)

Finding the uvs' start address in sequential mode is a "matter of experience" (as you can read in the tut).
It also says that there's no common  recipe but 'yes', you normally are on a promising track of finding uvs' start address in sequential mode when 
subtracting the uvs' block size from the FIs' start address.
## Post #9
- Username: Sckoofer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Nov 08, 2016 1:00 am
- Post datetime: 2016-11-07T17:11:30+00:00
- Post Title: [Help] Hex2obj

Hi, I copy your tutorial and post in the Zenhax forum.
Dont worry, i say that no was me who created the H2O and the tutorial.
i just copy and paste there, because not have tutorials about it.
And i have a question too:
I want to access the game models of the ratatouille game, i had make a tutorial about "how to replace textures of the any game, simple using hexeditor, dragon upacker and paint." But i dont know how to open the game models for replace them.
If i decompile the game folder i can extract the meshes of character, objects, map?
With your program?
Or not?
Thank you so much!
[http://zenhax.com/viewtopic.php?f=4&t=3351](http://zenhax.com/viewtopic.php?f=4&t=3351)
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-11-07T17:48:52+00:00
- Post Title: [Help] Hex2obj

> Reply from Sckoofer
>
> Dont worry, i say that no was me who created the H2O and the tutorial.
I would not worry even if you told it were yours.  

> If i decompile the game folder i can extract the meshes of character, objects, map?
depends on - you'll need to upload a supposed model file.
## Post #11
- Username: Sckoofer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Nov 08, 2016 1:00 am
- Post datetime: 2016-11-07T22:44:23+00:00
- Post Title: [Help] Hex2obj

Thank you so much. 
Here [https://mega.nz/#!5VZDyQDQ!RK5PeSiLbTvh ... sWfFWonTto](https://mega.nz/#!5VZDyQDQ!RK5PeSiLbTvhLu4z0iVKLdDxegIA-HC3wsWfFWonTto)
I cannot download more on mega, but i can upload!  
If dont work: [http://www.4shared.com/file/TD8Lbylnce/CT_online.html](http://www.4shared.com/file/TD8Lbylnce/CT_online.html)
See for me if i can extract the models, or not.
And the more important, if i can change the coordinates of the objects, and how to do it.  
Thank you so much again.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-11-08T18:23:20+00:00
- Post Title: [Help] Hex2obj

> Reply from Sckoofer
>
> See for me if i can extract the models, or not.CT.DPC contains hundreds of DXT1, DXT5 strings.
So may contain textures, maybe compressed

> And the more important, if i can change the coordinates of the objects, and how to do it.
that's not a matter of hex2obj - it's modding; look for threads/ forums which deal with that, please.
## Post #13
- Username: Sckoofer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Nov 08, 2016 1:00 am
- Post datetime: 2016-11-08T20:30:58+00:00
- Post Title: [Help] Hex2obj

.
WAIT! I won decompile the file! With quickBMS.Please, help me, just one more time   
[http://www.4shared.com/rar/lI3zlRM_ce/C ... piled.html](http://www.4shared.com/rar/lI3zlRM_ce/CT_decompiled.html)
Please, you are my last hope.
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-12-09T23:21:34+00:00
- Post Title: [Help] Hex2obj

chunk files; continuing from this thread:
[viewtopic.php?f=16&t=13675&start=45](http://forum.xentax.com/viewtopic.php?f=16&t=13675&start=45)

@ekmek: handling the chunk file
I show the steps which should be plain to see  for any noob;
if you don't, well, then I fear I can't help.

address 0x5CCE0: start of face indices (FI) list

search for 000001000200, next addresses 0x63F28 and 0x65D88, assumed starts of FIs lists

size of first submeshes FIs' list:
0x63F28 -0x5CCE0= 0x7248= 29256

FIs count: 14628 (words= 2 bytes per index)
resulting in a vertex count of 4848 (lower left listbox)

Finding the FVF size; well, that requires some experience; 
you'll gain it after having dealed with some dozens of different mesh formats:

from a glance at the beginning of the file I'd guess for 44.

ShortAll didn't work here, so I switched to half floats.



heads_jingxu_chunk.JPG (155.63 KiB) Viewed 964 times



Getting the uvs positon is another hurdle for most people; use "trial 'n error"
if the standard addresses for ShortAll/HF formats (from 12, in multiples of four, 16, 20 etc.) don't work.

In this case it's 40.
## Post #15
- Username: ekmek
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 29, 2016 2:53 am
- Post datetime: 2016-12-09T23:54:25+00:00
- Post Title: [Help] Hex2obj

Thanks!  That makes more sense. Let me mess around with it
## Post #16
- Username: ekmek
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 29, 2016 2:53 am
- Post datetime: 2016-12-13T17:31:19+00:00
- Post Title: Re: [Help] Hex2obj

I replicated what you did fine.

But when messing with other chunk files I was trying to figure our how you got:

"5CCE0: start of face indices (FI) list"


It's not clear in the tutorial to me. How did you get that number?

As I go through this I plan on helping out on your tutorial for noobs.  written by a noob for noobs!
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-12-13T22:56:51+00:00
- Post Title: Re: [Help] Hex2obj

> Reply from ekmek
>
> But when messing with other chunk files I was trying to figure our how you got:

"5CCE0: start of face indices (FI) list"
Assumed first face to consist of 0, 1, 2 (-> 1, 2, 3 in one based wavefront format)
so search for 000001000200 (little endian of 0000 0001 0002).

Doesn't work always because the first face might consist of other vertices, may 3,4,5 or something else.
## Post #18
- Username: ekmek
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 29, 2016 2:53 am
- Post datetime: 2016-12-13T23:07:52+00:00
- Post Title: Re: [Help] Hex2obj

> Reply from shakotay2
>
> ekmek wrote:But when messing with other chunk files I was trying to figure our how you got:

"5CCE0: start of face indices (FI) list"
Assumed first face to consist of 0, 1, 2 (-> 1, 2, 3 in one based wavefront format)
so search for 000001000200 (little endian of 0000 0001 0002).

Doesn't work always because the first face might consist of other vertices, may 3,4,5 or something else.

ah, ok. I guess this where the hex editor comes in.


Do you recommend one?
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-12-14T03:08:22+00:00
- Post Title: Re: [Help] Hex2obj

My most preferred one is WinHex. But any other should do which has a decent search feature.

For me a byte grouping of 8 plus 8 is totally important (which HxD v 1.7.70 for example lacks of).



WinHex.JPG (69.49 KiB) Viewed 205 times
## Post #20
- Username: thunderkai
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Dec 09, 2016 8:09 am
- Post datetime: 2016-12-15T01:57:45+00:00
- Post Title: Re: [Help] Hex2obj

I can not get any mesh to display on the attached file
some screenshots: [http://imgur.com/a/kdUBC](http://imgur.com/a/kdUBC)
[knyitm001.zip](https://xentaxbackup.github.io/file/12055_knyitm001.zip)
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-12-15T08:05:52+00:00
- Post Title: Re: [Help] Hex2obj

face indices start address is correct; but it's 5 submeshes, search for 000001000200 to find the different startaddresses
next find: 0xFF04 (delta 0x2FF4 related to 0xCF10-> delta/2= 6138 face indices;  vertex count= 1180)

Why set start of vertices to 0x1387? That's not senseful.

calculation CF10 + 35934x2= 0x1E7CC shows where to search for vertices.



knyitm001.JPG (82.32 KiB) Viewed 199 times
