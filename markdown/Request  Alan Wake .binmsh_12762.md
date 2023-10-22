## Post #1
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2015-04-13T11:45:21+00:00
- Post Title: Request : Alan Wake .binmsh

Could anyone take a look at these .binmsh files from Alan Wake? Maybe create a python or maxscript-based skeleton/weights extractor for the models?

[http://sta.sh/0174ots6sv5g](http://sta.sh/0174ots6sv5g)
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2015-04-14T03:24:31+00:00
- Post Title: Request : Alan Wake .binmsh

I worked on this format over at the facepunch forums and skin weights were "extractable" at the time, but flagged off in the script. 
I was UNABLE to figure out the BONES, so I figured there was no use enabling it

Anyway here I've enabled the flag for you, having fun FIXING bones:




maxscript:


 BINMSH.zip
Maxscript: Imports Binmsh from PC version of Alan Wake (3.85 KiB) Downloaded 110 times


[http://facepunch.com/showthread.php?t=1 ... st47254771](http://facepunch.com/showthread.php?t=1449233&p=47254771&viewfull=1#post47254771)

> Reply from mariokart64n
>
> format is strange, as we don't get much of a header to work with.
it gives a few counts or sizes for the main vertex and index buffer but then thats it

then you jump past that and land at skeleton and material data blocks and some unknown data??? I'm also missing the skeleton hierarchy info :/
anyway after which you'll finally come to the mesh table, which in most games I see are at the top with the header.
In this format everything seems in reverse, which makes my implementation very UNSTABLE.

as the format does not supply an address to the mesh table I have to parse through the material table to get to it.
The material table is dynamic, so without picking apart the material calls in a disassembler I can only accommodate what I was provided with in the OP's sample.
In other words if there is a new material call the program will land at the wrong address and CRASH :'(

I have created a 3dsmax maxscript that imports the OP's provided sample file. Probably WILL NOT WORK on other files, so don't bother trying
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-14T13:10:46+00:00
- Post Title: Request : Alan Wake .binmsh

impressive work, as always!

> Reply from mariokart64n
>
> Anyway here I've enabled the flag for you, having fun FIXING bones:
surely had. I manually created an array containing the parent ids (face bones unresolved):

```
            20, 24, 25, 9, 21, 28, 29, 30, 24, 32, 33, 34, -1, 9, 37, 38, 9, 40, 41, 9, 43, 44, 27, 46, -- 47
	    9, 48, 49, 18, 51, 52, 18, 54, 55, 18, 57, 58, 18, 60, 61, 18, 63, 64, --65
	    1, 
	    66, 67, -1,-1,-1,-1,-1,-1,-1,-1,-1,-1, -- 78
	    -1,-1,-1,-1,-1,-1,-1,-1,-1,-1,
	    -1,-1,-1,-1,-1,-1,-1,-1,-1,-1,
	    -1,-1,-1,-1,-1,-1,-1,-1,-1,-1,
	    -1,-1,-1,-1,-1,-1,-1,-1,-1,-1,
	    -1,-1,-1,-1,-1,-1,-1,-1)
```

Not sure whether Spine0 should be a child of the pelvis and as always I've spoiled the skinning:



Alice_move.JPG (35.59 KiB) Viewed 367 times
## Post #4
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2015-04-14T16:11:28+00:00
- Post Title: Request : Alan Wake .binmsh

Awesome work as always. Fixing the bones and assigning the materials ...not a problem but some of the weights "don't exist" like in the screenshot...
## Post #5
- Username: d875j
- Rank: advanced
- Number of posts: 52
- Joined date: Sun Jun 17, 2012 10:32 am
- Post datetime: 2015-06-06T04:47:07+00:00
- Post Title: Request : Alan Wake .binmsh

What about map models and coordinates and ect?
## Post #6
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2020-04-25T21:21:14+00:00
- Post Title: Request : Alan Wake .binmsh

Mario updated the script and I'm happy to share it with you. 

 BINMSH_r2020_04_26.zip
(24.46 KiB) Downloaded 69 times



How to use:
Import the Skeleton from the havok File (\Alan Wake\data\ep999-000\skeletons\) into 3dsmax first with:
https://lukascone.wordpress.com/2019/03 ... ax-plugin/
    import settings:
scale = 97
Coord. setup - tick Invert Top
Coord. setup - Back - choose Top from dropdown
Coord. setup - tick Right
Coord. setup - Right - choose Right from dropdown
then run script, flip the toggles around with settings:
Clear scene: OFF
Enable Skin: ON
Flip X Axis of Mesh: ON

Note: it's important that you use the correct skeleton, and thats about it.
also seems all bones called "ragdoll*" can be removed
## Post #7
- Username: gozerian
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 07, 2023 8:45 am
- Post datetime: 2023-08-07T22:34:50+00:00
- Post Title: Request : Alan Wake .binmsh

looks like this thread doesn't see much action.  only place I've found that actually discusses the .binmsh file format however.  because of the longevity of this thread, seems like not all the links are valid anymore.  trying to get a handle on the .binmsh and .binhvk files so i can see them and understand how to work with them.  i'm not a 3ds user however.  was wondering if there were other methods of interacting, viewing, converting these file types?
