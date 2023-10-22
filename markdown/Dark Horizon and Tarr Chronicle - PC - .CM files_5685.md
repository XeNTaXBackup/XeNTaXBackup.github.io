## Post #1
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-01-02T00:07:52+00:00
- Post Title: Dark Horizon and Tarr Chronicle - PC - .CM files

hello
can anyone help me to convert this format ??? to obj or 3ds ...
it seems Dark Horizon and Tarr Chronicle share the same format of models, from Paradox games

[http://www.filedropper.com/darkhorizon](http://www.filedropper.com/darkhorizon)

thx
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-01-02T00:11:45+00:00
- Post Title: Dark Horizon and Tarr Chronicle - PC - .CM files

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-01-02T00:14:54+00:00
- Post Title: Dark Horizon and Tarr Chronicle - PC - .CM files

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-01-02T00:54:17+00:00
- Post Title: Dark Horizon and Tarr Chronicle - PC - .CM files

If no one helps you before i get to it i can convert this mesh into max but i am buys with a project at the moment.
But the format is very basic and should be easy for most people who know about models.
## Post #5
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-01-03T17:52:48+00:00
- Post Title: Dark Horizon and Tarr Chronicle - PC - .CM files

he chrox and wath you think abouth this files are from Saint Seiya Hades, files extracted i post a download of the files and preview in txt of the files content.

[viewtopic.php?f=16&t=5644&start=15](http://forum.xentax.com/viewtopic.php?f=16&t=5644&start=15)
## Post #6
- Username: nightFlarer
- Rank: beginner
- Number of posts: 33
- Joined date: Thu May 13, 2010 3:25 pm
- Post datetime: 2011-01-04T06:33:56+00:00
- Post Title: Dark Horizon and Tarr Chronicle - PC - .CM files

I'll have a go at it, I haven't done this before but thanks to mariokart64n for his tutorials I am pretty confident that I can do it 

The model file seems pretty straight forward. This is what I've done so far, just give a couple hours and I'll be done.
[](http://img403.imageshack.us/i/cmwip.jpg/)
## Post #7
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-01-04T16:55:01+00:00
- Post Title: Dark Horizon and Tarr Chronicle - PC - .CM files

it look promising .. thx
## Post #8
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2011-01-04T20:43:30+00:00
- Post Title: Dark Horizon and Tarr Chronicle - PC - .CM files

> Reply from CZW
>
> it look promising .. thx

Are you Thierry M. from France ?
## Post #9
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-01-05T14:09:32+00:00
- Post Title: Dark Horizon and Tarr Chronicle - PC - .CM files

> Reply from Karpati
>
> CZW wrote:it look promising .. thx

Are you Thierry M. from France ?

look on your PM ...
## Post #10
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2011-01-11T07:07:31+00:00
- Post Title: Dark Horizon and Tarr Chronicle - PC - .CM files

> Reply from nightFlarer
>
> I'll have a go at it, I haven't done this before but thanks to mariokart64n for his tutorials I am pretty confident that I can do it 

The model file seems pretty straight forward. This is what I've done so far, just give a couple hours and I'll be done.

no news ???
## Post #11
- Username: nightFlarer
- Rank: beginner
- Number of posts: 33
- Joined date: Thu May 13, 2010 3:25 pm
- Post datetime: 2011-01-11T22:54:30+00:00
- Post Title: Dark Horizon and Tarr Chronicle - PC - .CM files

It's almost finished, thanks to mario for fixing up my script.
There's supposed to be multiple meshes in each model file but we only know how to read the first mesh, hopefully chrrox can finish up the script so it can read the other meshes.

Here's the maxscript:

```


fname = getOpenFileName \ 
caption:"Quazar Studio's Model File" \
types:"Quazar Studio's Model File(*.cm)|*.cm" \
f = fopen fname "rb"

clearlistener()

Face_array=#()
Vert_array=#()
UV_array=#()

ukn1=readlong f #unsigned
ukn2=readlong f #unsigned
ukn3=readlong f #unsigned
ukn4=readlong f #unsigned

fseek f 196 #seek_cur -- skips over stuff I don't know yet


count=1 --sets loop to only execute once
for y = 1 to count do( -- master loop, will build for each new set of verts.. but wont be able to loop yet due to too many ukns
ukn5=readlong f #unsigned
ukn6=readlong f #unsigned
ukn7=readlong f #unsigned
sectionID=readlong f #unsigned --?? ID's which Section the cursor is at?
pad=readlong f #unsigned -- always 0 ??
sectionCount=readlong f #unsigned
sectionSize=readlong f #unsigned --??

for x = 1 to sectionCount do( -- vertex loop
vx=readfloat f
vy=readfloat f
vz=readfloat f
nx=readfloat f
ny=readfloat f
nz=readfloat f
tv=readfloat f
tu=readfloat f
        
append Vert_array[vx,vy,vz]
append UV_array[tv,tu,0]
)

fseek f (288*2) #seek_cur -- skips random section?? repeats twice between verts and faces


ukn8=readlong f #unsigned
ukn9=readlong f #unsigned
ukn10=readlong f #unsigned
sectionID=readlong f #unsigned --?? ID's which Section the cursor is at?
pad=readlong f #unsigned -- always 0 ??
sectionCount=readlong f #unsigned
sectionSize=readlong f #unsigned --??

for x = 1 to sectionCount/3 do( -- vertex loop. divide by 3 because we are reading 3 values each time wee loop
fa=readlong f #unsigned +1
fb=readlong f #unsigned +1
fc=readlong f #unsigned +1
append Face_array[fa,fb,fc]
)       
        
        

msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
for j = 1 to UV_array.count     do setTVert  msh j UV_array[j]
for j = 1 to Face_Array.count   do setTVFace msh j Face_Array[j]
) --end of master loop

Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
gc()
fclose f
```
