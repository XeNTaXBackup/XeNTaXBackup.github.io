## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-04-24T14:55:02+00:00
- Post Title: Samurai Shodown: Sen .k2mp

I'm trying to figure out .k2mp model format. 
I have problem with face indices, maybe someone could help me with them? 
Here's sample character file [http://www.mediafire.com/?8cew8426adpzbw8](http://www.mediafire.com/?8cew8426adpzbw8)
And here's basic script for this file, it loads sword model. Thanks in advance.

> fname = getOpenFileName \
>
> caption:"Open .K2MP from Mesh folder" \
>
> types:"Samurai Shodown Sen Mesh(*.K2MP)|*.K2MP" \
>
> historyCategory:"Samurai Shodown SenObjectPresets"
>
> f = fopen fname "rb"
>
> clearlistener()
>
> 
>
> Face_array=#()
>
> Vert_array=#()
>
> UV_array=#()
>
> 
>
> fseek f 0x1A9A #seek_set
>
> vertcount=readlong f
>
> print vertcount
>
> 
>
> for x = 1 to vertcount/3 do(
>
> 
>
> vx=readfloat f
>
> vy=readfloat f
>
> vz=readfloat f
>
> append Vert_array[vx,vy,vz] 
>
> )
>
> 
>
> unk1=readshort f
>
> indices=readlong f
>
> print indices
>
> 
>
> FaceDirection = 1
>
> f1 = Readlong f +1   
>
> f2 = Readlong f +1   
>
> for i = 3 to indices-1 do (   
>
> f3 = Readlong f +1
>
> FaceDirection *= 1   
>
> if (f3 != f1) AND (f3 != f2) then (  
>
> if FaceDirection > 0 then append Face_array [f1,f2,f3]     
>
> else append Face_array [f1,f3,f2]
>
> )
>
> f1 = f2    
>
> f2 = f3
>
> )
>
> 
>
> fseek f 0x6B76 #seek_set
>
> uvcount=readlong f
>
> fseek f 0x6 #seek_cur
>
> 
>
> for x = 1 to uvcount do(
>
> tu=readfloat f 
>
> tv=readfloat f 
>
> append UV_array[tu,tv,0]
>
> )
>
> 
>
> msh = mesh vertices:Vert_array faces:Face_array
>
> msh.numTVerts = UV_array.count
>
> buildTVFaces msh
>
> for j = 1 to UV_array.count do setTVert msh j UV_array[j]
>
> for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
>
> 
>
> Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
>
> 
>
> fclose f
[blade.jpg](https://xentaxbackup.github.io/file/6349_blade.jpg)
## Post #2
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2013-04-25T07:36:05+00:00
- Post Title: Samurai Shodown: Sen .k2mp

It is a container file, so it have dozens of meshes. It uses the DirectX Binary format internally: 'xof 0303bin 0032'

After the face counter, every face have the followings:

'Number of Vertices in the actual Face': 4 bytes Long
After this
'Number of Vertices in the actual Face' * 4 bytes Long Pointers

See the converted file..
[pl00_obj.zip](https://xentaxbackup.github.io/file/6352_pl00_obj.zip)
## Post #3
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-04-25T12:48:47+00:00
- Post Title: Samurai Shodown: Sen .k2mp

Karpati, thanks you very much for help   Everything works perfect now, I know .k2mp it's container with a lot of models inside. Texture are straight .dds but also grouped in .k2mp file.
[SSS.jpg](https://xentaxbackup.github.io/file/6353_SSS.jpg)
## Post #4
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2013-04-25T13:35:52+00:00
- Post Title: Samurai Shodown: Sen .k2mp

Did you position the subobjects manually in your 3d modeler program?
## Post #5
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-04-26T07:18:19+00:00
- Post Title: Samurai Shodown: Sen .k2mp

Yes, I positioned them manually in 3ds max.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-04-27T00:02:52+00:00
- Post Title: Samurai Shodown: Sen .k2mp

If it's a direct3D file they probably have frame transforms or something.
## Post #7
- Username: BobDope
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Dec 22, 2011 5:56 pm
- Post datetime: 2013-05-01T06:55:50+00:00
- Post Title: Samurai Shodown: Sen .k2mp

As I am a complete noob, could someone post an updated script (like the first one, that imports a sword), that works on the entire character?

I would be very thankful.

If it (or another one) could be used to get the textures as well, that would be great.

Thank you for your efforts and sorry for the inconveniance.
## Post #8
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2013-05-01T16:04:23+00:00
- Post Title: Samurai Shodown: Sen .k2mp

> Reply from zaramot
>
> Karpati, thanks you very much for help   Everything works perfect now, I know .k2mp it's container with a lot of models inside. Texture are straight .dds but also grouped in .k2mp file.

I really love the Samurai Shodown game, give me lots of memorys, for me the best one its the Samurai Shodown II, afther this game the company fuck the game with RUSH SLASH MODES and back front movement in screen and lots of things to Lost the original game esence, i shure this its Genjuro, hope u can share the characters files i really like them   .
## Post #9
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2014-01-04T16:58:40+00:00
- Post Title: Samurai Shodown: Sen .k2mp

> Reply from Karpati
>
> It is a container file, so it have dozens of meshes. It uses the DirectX Binary format internally: 'xof 0303bin 0032'

After the face counter, every face have the followings:

'Number of Vertices in the actual Face': 4 bytes Long
After this
'Number of Vertices in the actual Face' * 4 bytes Long Pointers
??? hmm its too difficult for my kinky brain   

zaramot. would you be able to rewrite your script?
## Post #10
- Username: kjw2254
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Feb 04, 2011 11:31 pm
- Post datetime: 2014-01-18T02:31:08+00:00
- Post Title: Samurai Shodown: Sen .k2mp

me too
## Post #11
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2014-02-19T06:10:55+00:00
- Post Title: Samurai Shodown: Sen .k2mp

hey...at least...would you give me some hints on what to do?
## Post #12
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-02-19T10:06:39+00:00
- Post Title: Samurai Shodown: Sen .k2mp

If you want those model very much, you could use this script to load each part manually

```
caption:"Open .K2MP from Mesh folder" \
types:"Samurai Shodown Sen Mesh(*.K2MP)|*.K2MP" \
historyCategory:"Samurai Shodown SenObjectPresets"
f = fopen fname "rb"

fn ReadFixedString bstream fixedLen =
(
	local str = ""
	for i = 1 to fixedLen do
	(
		str += bit.intAsChar (ReadByte bstream #unsigned)
	)
	str
)	

clearlistener()

Face_array=#()
Vert_array=#()
UV_array=#()

--find string "Mesh" remember offset and put it here
fseek f 0x19D4A #seek_set
fseek f 0xE #seek_cur
vertcount=readlong f
print vertcount

for x = 1 to vertcount/3 do(
vx=readfloat f
vy=readfloat f
vz=readfloat f
append Vert_array[vx,vz,vy] 
)

unk1=readshort f
count=readlong f
faces=readlong f	
print faces


for x = 1 to faces do (
fcount=readlong f	
fa=readlong f + 1
fb=readlong f + 1
fc=readlong f + 1
append Face_array [fc,fb,fa] 	
)	

id=readshort f
NameSecSize=readlong f
SecName=ReadFixedString f NameSecSize
fseek f 0xE #seek_cur	
ncount=readlong f	
print ncount
for x = 1 to ncount/3 do(
n1=readfloat f
n2=readfloat f
n3=readfloat f
)

unk1=readshort f
ncount=readlong f
nfaces=readlong f	
print nfaces


for x = 1 to nfaces do (
nfcount=readlong f	
na=readlong f + 1
nb=readlong f + 1
nc=readlong f + 1	
)	
	
unk2=readshort f	
id=readshort f
NameSecSize=readlong f
SecName=ReadFixedString f NameSecSize
fseek f 0xE #seek_cur	
uvcount=readlong f	
print uvcount	

Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))	

for x = 1 to uvcount/2 do(
tu=readfloat f 
tv=readfloat f*-1 
append UV_array[tu,tv,0]
)

msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]


fclose f
```


I will not finish script for this game till distant future, models are very low-poly with low textures and format is bit annoying. Maybe you could import them with tools for DirectX Binary format?! I don't know
## Post #13
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2014-02-19T21:26:31+00:00
- Post Title: Samurai Shodown: Sen .k2mp

really thank you for the help!
textures(PL**TEX1P.K2MP/K2T) is the simple DXT dds formats.
## Post #14
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-02-20T08:27:21+00:00
- Post Title: Samurai Shodown: Sen .k2mp

[/quote]
??? hmm its too difficult for my kinky brain[/quote]

The DirectX format stores the faces as N-sided polygons:

If 'Number of Vertices in the actual Face'=3 it is a triangle,
If 'Number of Vertices in the actual Face'=4 it is a quadrangle,
etc...

If 'Number of Vertices in the actual Face'=3 you must read 3 long (pointer to the vertex table)
If 'Number of Vertices in the actual Face'=4 you must read 4 long (pointer to the vertex table).
etc...
## Post #15
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2014-02-20T20:38:51+00:00
- Post Title: Samurai Shodown: Sen .k2mp

thanks, but...
> each part manually
? what 'part'...?
However, I understand that you have lost interest in this topic already.
Thank you so much...
## Post #16
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-02-20T20:54:26+00:00
- Post Title: Re: Samurai Shodown: Sen .k2mp

Each .k2mp file it's container - there are many model parts inside. For example in this one (file I've gave a link in first post), there are 20 parts  Find this string xof 0303bin 0032 in any hexeditor, then find sting mesh, remember offset after this word and paste it in my "script", it will load this part or try somehow use tools for .x format - they should import those models somehow. At least it's a some solution, bad one but - you can get entire char model in a couple of minutes - but without bones off course.

P.S. OMG I became mega-veteran with this post
## Post #17
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2014-02-21T16:24:10+00:00
- Post Title: Re: Samurai Shodown: Sen .k2mp

thanks and congrats mega-veteran!
## Post #18
- Username: Ayuvir
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Mar 20, 2011 9:24 pm
- Post datetime: 2014-04-07T09:56:59+00:00
- Post Title: Re: Samurai Shodown: Sen .k2mp

I don't understand what you're supposed to copy on the script... I have tried copying the string mesh + offset and all kinds of combinations and all I get is an error code or 3DS Max tries to load "something" indefinitely which causes a memory leak and I'm forced to shutdown my laptop...

Can you please explain exactly what the string mesh is?



I apologize but I don't understand hex editors very well.
## Post #19
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-04-07T10:08:27+00:00
- Post Title: Re: Samurai Shodown: Sen .k2mp

if you run Jaeder Naub. It can auto extract .x files with its file scanner.
[blog/?tag=strobe](http://forum.xentax.com/blog/?tag=strobe)
## Post #20
- Username: Ayuvir
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Mar 20, 2011 9:24 pm
- Post datetime: 2014-04-07T11:59:27+00:00
- Post Title: Re: Samurai Shodown: Sen .k2mp

I got a bunch of .xof files by scanning one of the K2MP files...is there a way to open them?
## Post #21
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-04-07T12:16:27+00:00
- Post Title: Re: Samurai Shodown: Sen .k2mp

I think, you should rename them from .xof to .x and try to import them with DirectX importer, for 3ds max for example or in Blender. If they wouldn't work I'll try to explain how to import them in "my way" with script.
## Post #22
- Username: Ayuvir
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Mar 20, 2011 9:24 pm
- Post datetime: 2014-04-07T12:54:48+00:00
- Post Title: Re: Samurai Shodown: Sen .k2mp

I'm getting an error when importing the .x files on 3DS Max-- maybe because the plugin I'm using is for 2013 while I'm using 2014.

Edit: Tried with Blender and it's not working either... maybe the .xof files extracted from the K2MP with Jaeder are corrupted?
I'm at a complete loss here.
## Post #23
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-04-07T13:41:45+00:00
- Post Title: Re: Samurai Shodown: Sen .k2mp

Maybe, if you could obtain native .x model, you could compare header from original DirectX format with  file extracted with Jaeder, and then swap them.
## Post #24
- Username: Ayuvir
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Mar 20, 2011 9:24 pm
- Post datetime: 2014-04-07T13:59:47+00:00
- Post Title: Re: Samurai Shodown: Sen .k2mp

-
## Post #25
- Username: tjrgk1029
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 18, 2015 2:55 pm
- Post datetime: 2016-01-28T09:45:47+00:00
- Post Title: Re: Samurai Shodown: Sen .k2mp

this topic ended?
