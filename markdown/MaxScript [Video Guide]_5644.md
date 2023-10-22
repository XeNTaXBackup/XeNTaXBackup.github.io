## Post #1
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-12-27T23:06:51+00:00
- Post Title: MaxScript [Video Guide]

during my free time off during the holidays I wanted to make a video guide on how to use MaxScript aka 3dsmax to import models. 

I'm fairly new to maxscript, or programing in general so please forgive me if I got a thing here or there wrong. 

[http://www.youtube.com/watch?v=1ORnfYnlXOw](http://www.youtube.com/watch?v=1ORnfYnlXOw)
[http://www.youtube.com/watch?v=dbPLKe-yMmY](http://www.youtube.com/watch?v=dbPLKe-yMmY)
[http://www.youtube.com/watch?v=CEwSgXxkZMc](http://www.youtube.com/watch?v=CEwSgXxkZMc)
[http://www.youtube.com/watch?v=NeQYfxi8KW4](http://www.youtube.com/watch?v=NeQYfxi8KW4)
[http://www.youtube.com/watch?v=rcPfA4ix6WM](http://www.youtube.com/watch?v=rcPfA4ix6WM)
[http://www.youtube.com/watch?v=LPxlqN6OoI4](http://www.youtube.com/watch?v=LPxlqN6OoI4)
[http://www.youtube.com/watch?v=1dAIMdb-xYQ](http://www.youtube.com/watch?v=1dAIMdb-xYQ)

the PMD samples I got from the MikUMikuDance, some PMD were packed with the program.

[http://www.geocities.jp/higuchuu4/index_e.htm](http://www.geocities.jp/higuchuu4/index_e.htm)

and here is the sample script I did in the video

```
clearlistener()


fn ReadFixedString bstream fixedLen =
(
	local str = ""
	for i = 1 to fixedLen do
	(
		str0 = ReadByte bstream #unsigned
		if str0!=0xFD AND str0!=0xFC do str+= bit.intAsChar str0
	)
	str
)


Face_array=#()
Vert_array=#()
UV_array=#()


fileName =ReadFixedString f 3
fileVersion=readfloat f
modelName=ReadFixedString f 20
comments=ReadFixedString f 256


count=readlong f #unsigned


for x = 1 to count do(

vx=readfloat f
vy=readfloat f
vz=readfloat f
p4=readfloat f
p5=readfloat f
p6=readfloat f
tu=readfloat f
tv=readfloat f
p9=readshort f
p10=readshort f
p11=readshort f
append Vert_array[vx,vz,vy]
append UV_array[tu,tv,0]
)



count=readlong f #unsigned

print count


for x = 1 to count/3 do(
fa=readshort f #unsigned+1
fb=readshort f #unsigned+1
fc=readshort f #unsigned+1
append Face_array[fc,fb,fa]
)



msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
msh.name=modelName
-- convertTo msh PolyMeshObject
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]


Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
gc()
fclose f


```









Functions
functions are script operations that you can call at any time later in your script.

so say for example I want to spell hello world a few times, I would make a function that I could call later
example:
fn hw(
print "hello"
print "world"
)

I've now created a function, that can now be called by using the designator "hw".
so the advantage to this, is that instead of printing hellowworld over and over again when I need it. I can just type hw, and that earlier operation gets carried out
so in short a functions allow you to save space by being able to repeat an earlier defined operation.

below are some common functions I copied off of chrrox, which were handy to me. which also can be used to help you read different endians, such as reading from xbox360 game files

readBEshort, lets you read 2bytes in reversed order.. which is actually right to left.

```
short = readshort fstream #unsigned
short = bit.swapBytes short 1 2
return short
) 
```


readBElong, lets you read 4bytes in big endian, aka reversed order (which is actually right to left)

```
long = readlong fstream
long = bit.swapBytes long 1 4
long = bit.swapBytes long 2 3
return long
)
```


readHalfFloat, aka 16bit floats. max doesnt have a default read function on its own. this is for little endian.
if you want to reverse the byte order for bing endian (xbox360) then change the hf= line. instead of readshort, replace with. readBEshot
but make sure the readBEshort function gets paste before this. otherwise how can you call something that doesnt exist yet.

```
    hf=readshort fstream #unsigned
    sign = bit.get hf 16
    exponent = (bit.shift (bit.and hf (bit.hexasint "7C00")) -10) as integer - 16
    fraction = bit.and hf (bit.hexasint "03FF")
    if sign==true then sign = 1 else sign = 0
    exponentF = exponent + 127
    outputAsFloat = bit.or (bit.or (bit.shift fraction 13) \
    (bit.shift exponentF 23)) (bit.shift sign 31)
    return bit.intasfloat outputasfloat*2
    )
```


for reading a 32bit float, only in reversed order.. same speel as before. you'll need for xbox360

```
    fpt=readfloat fstream
    itger = bit.floatAsInt fpt
    hih = bit.intashex itger
    while hih.count < 8 do hih = "0" + hih
    shn = (substring hih 7 2) + \
    (substring hih 5 2) + \
    (substring hih 3 2) + \
    (substring hih 1 2)
    bit.intAsFloat (bit.hexasint shn)
    )
```


for reading text ONLY. its handy cause the default maxscript readstring doesnt normally let you set a character reading limit.

```
    local str = ""
    for i = 1 to fixedLen do
    (
        str += bit.intAsChar (ReadByte bstream #unsigned)
    )
    str
)
```
## Post #2
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2010-12-28T01:34:28+00:00
- Post Title: MaxScript [Video Guide]

Are you trying to get the capture data (from a kinect..being used in MikUMikuDance app) into max?!? That would be AWESOME. I just DL'ed MikUMikuDance (v4.03 english version, yay!) and apparently you can reapply bone settings to make other skeletal rigs work with that app. So, in a very roundabout (and decidedly NOT user friendly) way, you could get a character into MikUMikuDance and reorient the bone assignments, then use the kinect to get your mo-cap and then export that back into max to then reapply to that character. (I guess?)
## Post #3
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2010-12-28T06:45:56+00:00
- Post Title: MaxScript [Video Guide]

Amazing video tutorial, i just finish to see it few minutes ago the tutorial isn't complete but i understand that, make this videos for us (the noobs) is a hard work, i will study the videos more carefully and post some noobs questiosn about it... thanks a lot Mario!! 

Postdata to Mario: I LOL  with the joke of file extension, hello kitty files !!!

Postdata to SLIFallen: Thanks for the "original idea"  but the topic is not about Kinetic... Just use the converter of MMD animations to max, use google for find it

Postdata to some moderator: This need be in tutorial forum i don't Know why Mario put the topic here lol
## Post #4
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2010-12-28T11:06:53+00:00
- Post Title: MaxScript [Video Guide]

> Reply from FEATHER
>
> Postdata to SLIFallen: Thanks for the "original idea"  but the topic is not about Kinetic... Just use the converter of MMD animations to max, use google for find it

Indeed. Thanks for clearing that up. Kinect is simply a new way to animate the MMD characters. As I said, a roundabout way (for now) to get Kinect capture data into max, but it's a start!

I dont see this converter you speak of. I think thats in fact, what mariocart64 is after: [http://www.vocaforum.com/showthread.php?t=1644](http://www.vocaforum.com/showthread.php?t=1644) 

???
## Post #5
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-12-29T21:36:16+00:00
- Post Title: MaxScript [Video Guide]

I have here $100dlls, i am greath fan of saint seiya series, i have 2 options pay you for a script to import the models with textures in max or donate to xentax or pay a external coder to make one scrypt,  i really love this series and search this models by 4 years.

Tread with files format samples, fatduck tell me he not have pc just now but he advance on this investigation

[viewtopic.php?f=16&t=5525](http://forum.xentax.com/viewtopic.php?f=16&t=5525)
## Post #6
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-12-29T23:21:03+00:00
- Post Title: MaxScript [Video Guide]

i thought the files were encrypted?

if you need the models ASAP, just use 3dvia on the pcsx2 emu
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-12-29T23:39:11+00:00
- Post Title: MaxScript [Video Guide]

He really is desperate for those models.  Great job by the way mariokart64n!! Cool tut!
## Post #8
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-12-30T03:36:35+00:00
- Post Title: MaxScript [Video Guide]

I'm having a hard time uploading the 5th video, youtube keeps failing on it. I've tried a dozen different codecs, and I ony get shoty quality. hopefully I'll get it figured out  soon and upload the rest of the videos.

the aim is to get more people involved with maxscript, besides chrrox and fact duck. who seem to use this as a primary model importing method. since maxscript is soo easy many n00bs should be able to pick this up.
## Post #9
- Username: jcarl904
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Apr 12, 2010 11:08 pm
- Post datetime: 2010-12-30T07:26:37+00:00
- Post Title: MaxScript [Video Guide]

Hope you can get that last video uploaded and thank you again for sharing this with us.
## Post #10
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-12-30T18:09:33+00:00
- Post Title: MaxScript [Video Guide]

> Reply from mariokart64n
>
> i thought the files were encrypted?

if you need the models ASAP, just use 3dvia on the pcsx2 emu

I try with 3d ripper but every time the models are flated because the coordenate z are mising, this its because the pcsx2 emulators use overlay system.
## Post #11
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-12-30T18:10:47+00:00
- Post Title: MaxScript [Video Guide]

> Reply from Mr.Mouse
>
> He really is desperate for those models.  Great job by the way mariokart64n!! Cool tut!

Yeaaaa i love this series
## Post #12
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-12-30T21:06:32+00:00
- Post Title: MaxScript [Video Guide]

people dont know the differece between no z axis, and just reallly flat. scale the Y axis by 20 000 000 x and the mesh should unfold. this only works with 3dvia.
## Post #13
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-12-30T22:01:20+00:00
- Post Title: MaxScript [Video Guide]

yes bro but scale vertex by vertex of this axis to make the model its a crazy work, can take a lots and lots of time. any idea? maybe something maxscript can combine 2 captures, or something filter to unpack the files from the post of the models unripeed.
## Post #14
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-12-31T04:31:08+00:00
- Post Title: MaxScript [Video Guide]

you've misunderstood what I meant, and I dont think clarification would even matter
## Post #15
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-12-31T17:57:43+00:00
- Post Title: MaxScript [Video Guide]

Yes, cause im new on this and you are expert, mesed up vertex from point 0 to 20 000 000 put all the X vertex in the same position i test in milkshape with other models cause 3DVIA cant capture the models only textures with this configuration

This its the configuration of the EMULATOR


This its the captured data you can see the window to the right


I use koichi senada plugin in max to load the 3dxml files generated by 3DVIA PRINT SCREEN


3DVIA only capture texture files png, not capure vertex data, maybe the configuration of the emulator its wrong, i dont know, you are the expert, i come here xentax cause people tell me here the people its good and all can help to all.

Maybe this can be more ussefull for you 
[viewtopic.php?f=16&t=5525](http://forum.xentax.com/viewtopic.php?f=16&t=5525)

Abouth this you tell clarification would even matter, you are expert now because in the past other give you clarification. yes yes yes im a noob and noobs are despreciable.

I try with your video but looks blur i cant read the lethers bro, can upload with more quality? thanks.
## Post #16
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-12-31T18:31:57+00:00
- Post Title: Re: MaxScript [Video Guide]

all the videos I uploaded were 1GB, since they are 1080p. but you have to enable on youtube.... otherwise youtube shows videos at their low settings to save their bandwidth



but you'd better have a good connection, cause they were 1GB each when I uploaded them
## Post #17
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2010-12-31T21:41:15+00:00
- Post Title: Re: MaxScript [Video Guide]

As far as I know you can't rip from pcsx2 because there is a lack of a Z coordinate (depth). If you want the models from the game you're going to have to get them from the files themselves.
## Post #18
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-01-01T00:24:25+00:00
- Post Title: Re: MaxScript [Video Guide]

um nope.. I can rip models with both 3dripperDX and 3dvia... people think I'm lying or something I use to do it all the time <_<

the problem is some models back cull, so geometry goes missing, or sometimes texture coordinates are badly lost. the method is just not reliable cause your at the mercy of the PCSX2 support list.



[http://i38.tinypic.com/5peviu.jpg](http://i38.tinypic.com/5peviu.jpg)





I use to do this on a forum, but nobody really paid attention to it. so i'm going to correct this disccusion one last time. you CAN rip from pcsx2, the meshes HAVE z depth

x=Side-to-Side
y=Front-to-Back
z=Up-to-Down
## Post #19
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-01-03T22:22:26+00:00
- Post Title: Re: MaxScript [Video Guide]

Well i shure you not liyng and you can rip models, but something idea how to configure the emulator pcsx2 to do this? also i read in other forums only 3d via works and 3d ripper not works.
## Post #20
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-01-03T22:26:56+00:00
- Post Title: Re: MaxScript [Video Guide]

also wath version of 3d via you use please?
## Post #21
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-01-12T06:41:29+00:00
- Post Title: Re: MaxScript [Video Guide]

Thanks for the guide.
I have a question concerning MaxScript [Video Guide].
Xbox360 bob file is available?
## Post #22
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-01-12T21:16:09+00:00
- Post Title: Re: MaxScript [Video Guide]

not sure I see vertices in that file? wrong file maybe?
## Post #23
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-01-13T03:18:50+00:00
- Post Title: Re: MaxScript [Video Guide]

> Reply from mariokart64n
>
>  not sure I see vertices in that file? wrong file maybe?
Sorry. I wrote down the wrong consol name.
Bob file from PS3 game.
## Post #24
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-01-13T05:18:19+00:00
- Post Title: Re: MaxScript [Video Guide]

I dont think its a model file..... ps3 or xbox360 doesnt matter.. it can come from the stupid moon, its not a model
## Post #25
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2011-06-17T18:22:03+00:00
- Post Title: Re: MaxScript [Video Guide]

Awesome videos!
I used to see only garbage but now I can actually see things like vertices and other data chunks using a hex editor.
Currently working on Star Ocean: The Last Hope.
Want to use Lymle in this scene I'm working on:
[http://mrfuzzlebum.deviantart.com/#/d3hs8ss](http://mrfuzzlebum.deviantart.com/#/d3hs8ss)

I would've never thought this stuff could be so much fun; it's like a treasure hunt.  ٩(-̮̮̃-̃)۶
