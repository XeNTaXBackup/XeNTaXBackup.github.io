## Post #1
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2013-10-04T17:46:49+00:00
- Post Title: Final Fantasy IX World Map viewer Source Code

Hey Guys

For quite some time now this FF9 World Map viewer made by Zidane on the Quimm forums has been floating around.
Link to that, plus Source is here:[https://www.dropbox.com/sh/azf19y7homu8qnj/u-JOQibN1q](https://www.dropbox.com/sh/azf19y7homu8qnj/u-JOQibN1q)

The issue is that the source is in Blitz3D, a piece of software I know absolutely nothing whatsoever about at all.

The source code, the .bb files, contain information on the offsets amongst all other information on how the World Map format actually works.

I'd very much like to extract those 3D models along with the textures and play around with them in 3D software for a while.

I imagine very few people have Blitz3D, so I've saved the source as a .txt and placed that in the dropbox too.

Hopefully someone else is interested in the same thing and may be able to make heads or tails of that source, I've other files from Zidane that I can provide if anyones interested in those too.

- WalkMesh Viewer/extractor
- Some Anim/Post extractors that I've not tested yet, but these are also supported by Noesis.
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2013-10-06T16:46:26+00:00
- Post Title: Final Fantasy IX World Map viewer Source Code

I'm surprised this hasn't had more interest honestly.

I'll keep the files in my dropbox for a few more weeks so anyone can take them if they want, after than I'll likely remove them.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-10-06T17:15:55+00:00
- Post Title: Final Fantasy IX World Map viewer Source Code

> Reply from lionheartuk
>
> I'm surprised this hasn't had more interest honestly.Well, ok, then let's share some thoughts on this.  

It's good (but not enough) to upload some files on a request. I had a look into WorldMapSourece.txt.
So this seems part of loading a mesh:

```
	SeekStream fl,tmp1+mesh[i]
	numvert=ReadByte(fl)
	ReadByte(fl)
	numtri=ReadShort(fl)
	VertPointer=ReadInt(fl)
	TriPointer=ReadInt(fl)
	SeekStream(fl,tmp1+vertpointer)
	
	For j=0 To (numvert-1)
	VertX[j]=ReadSShort(fl)/1024.0
	VertY[j]=-ReadSShort(fl)/1024.0
	VertZ[j]=ReadSShort(fl)/1024.0
	ReadShort(fl)
	Next
```

But you can't expect someone wasting time on an uncomplete "subject" - i.e. you should have provided a suiting model sample - at least.  

(I usually spend 15 to 20 min to get model data of a format new to me. If on no avail I "cancel" it.)

Then you wrote that anims are supported by Noesis.
So meshes are not? If so, is there a reason why?
## Post #4
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2013-10-06T20:43:05+00:00
- Post Title: Final Fantasy IX World Map viewer Source Code

> Reply from shakotay2
>
> lionheartuk wrote:I'm surprised this hasn't had more interest honestly.Well, ok, then let's share some thoughts on this.  

It's good (but not enough) to upload some files on a request. I had a look into WorldMapSourece.txt.
So this seems part of loading a mesh:
Code: Select allFor i=0 To 3
	SeekStream fl,tmp1+mesh[i]
	numvert=ReadByte(fl)
	ReadByte(fl)
	numtri=ReadShort(fl)
	VertPointer=ReadInt(fl)
	TriPointer=ReadInt(fl)
	SeekStream(fl,tmp1+vertpointer)
	
	For j=0 To (numvert-1)
	VertX[j]=ReadSShort(fl)/1024.0
	VertY[j]=-ReadSShort(fl)/1024.0
	VertZ[j]=ReadSShort(fl)/1024.0
	ReadShort(fl)
	Next
But you can't expect someone wasting time on an uncomplete "subject" - i.e. you should have provided a suiting model sample - at least.  

(I usually spend 15 to 20 min to get model data of a format new to me. If on no avail I "cancel" it.)

Then you wrote that anims are supported by Noesis.
So meshes are not? If so, is there a reason why?

The zip file I provided contains both world map files 1.map and 2.map, they're 5mb each, along with all the textures, though I've also added the original .raw files extracted from the game disc itself.

The animations and models for the characters and enemies are supported by Noesis yeah, those are in .db files, however those are a different format to the world map meshes.

Also Noesis is able to view the character textures but unable to view the field textures.

On the FF9 disc extracted using NOESIS, Dir12 contains the world map data, whilst Dir3 (i believe) contains the world map textures, and the other world map models that're controllable, like chocobo and airships, plus the shadows of those objects.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-10-07T06:07:27+00:00
- Post Title: Final Fantasy IX World Map viewer Source Code

ok, understand. The whole 0.map being "the sample".  

With this cleared out here is what I got so far reading data from 0.map by stepping through WorldMapSource.txt (in mind):

WorldGridW= 24
WorldGridH= 20

V1=2

(seek > 0x1000)

-> function loadSetka2(fil,1,1,13)

tmp1= 0x1000

ffs%=524548
point%=18432

dffs%= 8
mesh[0]=    24
mesh[1]=  4028
mesh[2]=  8216
mesh[3]= 12140

seek > 0x1018
numvert= 118
numTri= 189

VertPointer= 0x3C
TriPointer= 0x3EC

(seek > 0x103C)

//reading 118 vertices

```
v 8.000000 62.466797 58.000000 
v 7.675781 63.165039 58.481445 
v 7.675781 62.676758 58.481445 
v 8.000000 62.890625 58.916016 
v 8.000000 63.378906 58.916016 
v 2.000000 63.316406 59.892578 
v 0.715820 0.000000 59.000000 
v 2.000000 0.000000 60.039063 
v 2.551758 63.316406 57.777344 
v 1.797852 0.000000 57.000000 
v 2.117188 0.000000 57.613281 
v 4.000000 0.000000 60.146484 
v 3.208008 63.316406 59.295898 
v 3.338867 0.000000 59.663086 
v 7.000000 63.488281 59.101563 
v 8.000000 0.000000 59.062500 
v 2.865234 63.316406 60.000000 
v 3.012695 0.000000 60.146484 
v 0.947266 63.316406 59.000000 
v 0.819336 0.000000 57.951172 
v 1.671875 63.316406 57.990234 
v 1.050781 63.316406 58.163086 
v 6.000000 63.679688 59.577148 
v 7.000000 0.000000 59.248047 
v 2.000000 63.316406 59.000000 
v 8.000000 61.965820 56.255859 
v 7.617188 61.685547 56.000000 
v 7.617188 61.553711 56.250000 
v 7.284180 61.770508 56.809570 
v 8.000000 62.458008 56.656250 
v 7.258789 61.783203 56.333008 
v 8.000000 62.241211 56.562500 
v 2.000000 0.000000 62.000000 
v 1.000000 0.000000 63.000000 
v 2.000000 0.000000 63.000000 
v 1.000000 0.000000 61.000000 
v 1.000000 0.000000 62.000000 
v 1.000000 0.000000 0.000000 
v 2.000000 0.000000 0.000000 
v 3.000000 0.000000 62.000000 
v 3.000000 0.000000 63.000000 
v 3.000000 0.000000 61.000000 
v 3.000000 0.000000 0.000000 
v 4.000000 0.000000 62.000000 
v 4.000000 0.000000 63.000000 
v 4.000000 0.000000 0.000000 
v 6.000000 0.000000 62.000000 
v 5.000000 0.000000 63.000000 
v 6.000000 0.000000 63.000000 
v 5.000000 0.000000 61.250000 
v 5.000000 0.000000 62.000000 
v 5.000000 0.000000 0.000000 
v 6.000000 0.000000 0.000000 
v 7.000000 0.000000 62.000000 
v 7.000000 0.000000 63.000000 
v 7.000000 0.000000 61.000000 
v 7.000000 0.000000 0.000000 
v 8.000000 0.000000 63.000000 
v 8.000000 0.000000 61.916992 
v 8.000000 0.000000 60.903320 
v 7.000000 0.000000 60.000000 
v 8.000000 0.000000 0.000000 
v 0.000000 0.000000 63.000000 
v 0.000000 0.000000 62.000000 
v 3.715820 0.000000 60.707031 
v 0.786133 0.000000 60.000000 
v 0.000000 0.000000 61.000000 
v 0.000000 0.000000 59.000000 
v 1.135742 0.000000 57.000000 
v 0.000000 0.000000 56.000000 
v 0.000000 0.000000 57.000000 
v 0.000000 0.000000 0.000000 
v 8.000000 62.955078 58.000000 
v 8.000000 62.492188 58.493164 
v 2.333984 0.000000 56.000000 
v 2.000000 63.316406 57.000000 
v 2.480469 63.006836 56.000000 
v 1.671875 0.000000 57.778320 
v 4.000000 63.316406 60.000000 
v 5.000000 0.000000 60.460938 
v 5.000000 63.535156 60.314453 
v 6.000000 0.000000 59.723633 
v 3.000000 63.006836 56.000000 
v 3.000000 63.188477 57.000000 
v 4.000000 63.087891 56.000000 
v 4.000000 62.835938 57.000000 
v 4.000000 62.998047 58.000000 
v 7.082031 63.344727 58.075195 
v 5.000000 63.368164 59.000000 
v 4.000000 63.083008 59.000000 
v 4.838867 63.087891 56.000000 
v 6.000000 63.423828 59.000000 
v 8.000000 62.901367 57.071289 
v 6.946289 61.757813 56.954102 
v 6.447266 60.680664 56.508789 
v 6.657227 60.787109 56.254883 
v 6.775391 60.762695 56.000000 
v 6.270508 60.709961 56.729492 
v 5.901367 60.823242 57.098633 
v 6.763672 61.841797 57.445313 
v 5.419922 61.757813 56.500000 
v 4.810547 62.090820 57.190430 
v 5.555664 61.580078 57.444336 
v 6.222656 62.095703 57.960938 
v 6.397461 61.182617 56.000000 
v 5.547852 61.500977 56.000000 
v 5.000000 62.343750 58.000000 
v 7.310547 61.329102 56.000000 
v 7.833984 61.919922 56.000000 
v 8.000000 62.081055 56.000000 
v 8.000000 62.449219 56.775391 
v 0.000000 0.000000 58.000000 
v 6.000000 0.000000 60.000000 
v 8.000000 0.000000 59.847656 
v 2.000000 0.000000 60.871094 
v 1.513672 0.000000 56.000000 
v 6.000000 0.000000 61.000000 
v 0.000000 0.000000 60.000000 
```

Now missing: subroutine CreateMesh()

Anyway - my 20 min have expired...

But with little coding skills someone should be able to continue this. It's no mysterious science.
## Post #6
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2013-10-07T08:51:38+00:00
- Post Title: Final Fantasy IX World Map viewer Source Code

> Reply from shakotay2
>
> ok, understand. The whole 0.map being "the sample".  

With this cleared out here is what I got so far reading data from 0.map by stepping through WorldMapSource.txt (in mind):

WorldGridW= 24
WorldGridH= 20

V1=2

(seek > 0x1000)

-> function loadSetka2(fil,1,1,13)

tmp1= 0x1000

ffs%=524548
point%=18432

dffs%= 8
mesh[0]=    24
mesh[1]=  4028
mesh[2]=  8216
mesh[3]= 12140

seek > 0x1018
numvert= 118
numTri= 189

VertPointer= 0x3C
TriPointer= 0x3EC

(seek > 0x103C)

//reading 118 vertices
Code: Select all#    0x103c
v 8.000000 62.466797 58.000000 
v 7.675781 63.165039 58.481445 
v 7.675781 62.676758 58.481445 
v 8.000000 62.890625 58.916016 
v 8.000000 63.378906 58.916016 
v 2.000000 63.316406 59.892578 
v 0.715820 0.000000 59.000000 
v 2.000000 0.000000 60.039063 
v 2.551758 63.316406 57.777344 
v 1.797852 0.000000 57.000000 
v 2.117188 0.000000 57.613281 
v 4.000000 0.000000 60.146484 
v 3.208008 63.316406 59.295898 
v 3.338867 0.000000 59.663086 
v 7.000000 63.488281 59.101563 
v 8.000000 0.000000 59.062500 
v 2.865234 63.316406 60.000000 
v 3.012695 0.000000 60.146484 
v 0.947266 63.316406 59.000000 
v 0.819336 0.000000 57.951172 
v 1.671875 63.316406 57.990234 
v 1.050781 63.316406 58.163086 
v 6.000000 63.679688 59.577148 
v 7.000000 0.000000 59.248047 
v 2.000000 63.316406 59.000000 
v 8.000000 61.965820 56.255859 
v 7.617188 61.685547 56.000000 
v 7.617188 61.553711 56.250000 
v 7.284180 61.770508 56.809570 
v 8.000000 62.458008 56.656250 
v 7.258789 61.783203 56.333008 
v 8.000000 62.241211 56.562500 
v 2.000000 0.000000 62.000000 
v 1.000000 0.000000 63.000000 
v 2.000000 0.000000 63.000000 
v 1.000000 0.000000 61.000000 
v 1.000000 0.000000 62.000000 
v 1.000000 0.000000 0.000000 
v 2.000000 0.000000 0.000000 
v 3.000000 0.000000 62.000000 
v 3.000000 0.000000 63.000000 
v 3.000000 0.000000 61.000000 
v 3.000000 0.000000 0.000000 
v 4.000000 0.000000 62.000000 
v 4.000000 0.000000 63.000000 
v 4.000000 0.000000 0.000000 
v 6.000000 0.000000 62.000000 
v 5.000000 0.000000 63.000000 
v 6.000000 0.000000 63.000000 
v 5.000000 0.000000 61.250000 
v 5.000000 0.000000 62.000000 
v 5.000000 0.000000 0.000000 
v 6.000000 0.000000 0.000000 
v 7.000000 0.000000 62.000000 
v 7.000000 0.000000 63.000000 
v 7.000000 0.000000 61.000000 
v 7.000000 0.000000 0.000000 
v 8.000000 0.000000 63.000000 
v 8.000000 0.000000 61.916992 
v 8.000000 0.000000 60.903320 
v 7.000000 0.000000 60.000000 
v 8.000000 0.000000 0.000000 
v 0.000000 0.000000 63.000000 
v 0.000000 0.000000 62.000000 
v 3.715820 0.000000 60.707031 
v 0.786133 0.000000 60.000000 
v 0.000000 0.000000 61.000000 
v 0.000000 0.000000 59.000000 
v 1.135742 0.000000 57.000000 
v 0.000000 0.000000 56.000000 
v 0.000000 0.000000 57.000000 
v 0.000000 0.000000 0.000000 
v 8.000000 62.955078 58.000000 
v 8.000000 62.492188 58.493164 
v 2.333984 0.000000 56.000000 
v 2.000000 63.316406 57.000000 
v 2.480469 63.006836 56.000000 
v 1.671875 0.000000 57.778320 
v 4.000000 63.316406 60.000000 
v 5.000000 0.000000 60.460938 
v 5.000000 63.535156 60.314453 
v 6.000000 0.000000 59.723633 
v 3.000000 63.006836 56.000000 
v 3.000000 63.188477 57.000000 
v 4.000000 63.087891 56.000000 
v 4.000000 62.835938 57.000000 
v 4.000000 62.998047 58.000000 
v 7.082031 63.344727 58.075195 
v 5.000000 63.368164 59.000000 
v 4.000000 63.083008 59.000000 
v 4.838867 63.087891 56.000000 
v 6.000000 63.423828 59.000000 
v 8.000000 62.901367 57.071289 
v 6.946289 61.757813 56.954102 
v 6.447266 60.680664 56.508789 
v 6.657227 60.787109 56.254883 
v 6.775391 60.762695 56.000000 
v 6.270508 60.709961 56.729492 
v 5.901367 60.823242 57.098633 
v 6.763672 61.841797 57.445313 
v 5.419922 61.757813 56.500000 
v 4.810547 62.090820 57.190430 
v 5.555664 61.580078 57.444336 
v 6.222656 62.095703 57.960938 
v 6.397461 61.182617 56.000000 
v 5.547852 61.500977 56.000000 
v 5.000000 62.343750 58.000000 
v 7.310547 61.329102 56.000000 
v 7.833984 61.919922 56.000000 
v 8.000000 62.081055 56.000000 
v 8.000000 62.449219 56.775391 
v 0.000000 0.000000 58.000000 
v 6.000000 0.000000 60.000000 
v 8.000000 0.000000 59.847656 
v 2.000000 0.000000 60.871094 
v 1.513672 0.000000 56.000000 
v 6.000000 0.000000 61.000000 
v 0.000000 0.000000 60.000000 
Now missing: subroutine CreateMesh()

Anyway - my 20 min have expired...

But with little coding skills someone should be able to continue this. It's no mysterious science.

Thankyou for those 20 minute ^___^

I'm trying to learn how to code noesis plugins, its just a very slow process as I've only a few moments a day to dedicate to it, thankyou once again.
