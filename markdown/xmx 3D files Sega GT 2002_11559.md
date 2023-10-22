## Post #1
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2014-06-01T14:43:49+00:00
- Post Title: xmx 3D files Sega GT 2002

Hello guys i've been looking 1 year ago how to extract the sega gt '02, I got it at the end but there are files with extension .xmx I looked a lot of pages at google without luck, someone know if exits a tool/program to open or convert to other format like .obj? I guess not   

Here is a 3D with .xmx format
[DoZero.rar](https://xentaxbackup.github.io/file/7409_DoZero.rar)
## Post #2
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-06-02T03:50:16+00:00
- Post Title: xmx 3D files Sega GT 2002

Oh man this game has some cool models. I always wanted jottio caspita  can u upload it to? Sorry I don't have coding skills
## Post #3
- Username: Guerra8888
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 06, 2010 10:47 am
- Post datetime: 2014-06-04T13:51:26+00:00
- Post Title: xmx 3D files Sega GT 2002

nice cars... very interesting
## Post #4
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2014-06-04T23:05:44+00:00
- Post Title: xmx 3D files Sega GT 2002

Shouldn't be too difficult to crack this format up and convert it to OBJ. In the file, there are sections like Material, Vertex, Index-List etc. You can even clearly see the vertex-coordinates and indices. But for now I'm unable to find anything about offset's or size's. Do you have a smaller file?

EDIT://
As it seems, these files aren't standalone-files. It looks like each file has a reference file. Can't find any information about vertex-stride, vertex-count etc. As I already requested; Can you provide a smaller file? Huge files are always more difficult to reverse...
## Post #5
- Username: Guerra8888
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 06, 2010 10:47 am
- Post datetime: 2014-06-06T21:50:31+00:00
- Post Title: xmx 3D files Sega GT 2002

would be great to see these models
## Post #6
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2014-06-07T15:09:57+00:00
- Post Title: xmx 3D files Sega GT 2002

Here is a small .xmx, i guess is the fan from showroom
[garage_01a_fan.rar](https://xentaxbackup.github.io/file/7446_garage_01a_fan.rar)
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-06-07T17:51:44+00:00
- Post Title: xmx 3D files Sega GT 2002

using hex2obj (view link in my sig):



dom_zero_01a_body.JPG (40.79 KiB) Viewed 263 times


(There seem to be superfluous faces inside the chassis when viewing the obj in blender for example.)

There are 18 assumed starts of face indices blocks (0000 0100 0200...) after 0x2E9E8. Didn't check them.
## Post #8
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2014-06-07T20:23:48+00:00
- Post Title: xmx 3D files Sega GT 2002

car.png (37.51 KiB) Viewed 256 times


So, I have some good news for you.

```
==============================
Byte { 16 } - Header
{
     Byte { 8 } - File Identification ("LDMXXOBX") -> "XboxModel"
     Dword { 4 } - Number Of Sections (see below)
     Dword { 4 } - File Size - 16 byte (Header Size)
}

Byte { x } - Section
{
     Byte { 4 } - Section Name
     if Section Name  == "LEDM" -> "Model"
        then
        {
             Byte { 41 } - Unknown
             Dword { 4 } - Vertex Count (see below)
        }
      Byte { x } - Unknown
}

To get the vertices, just read the next bytes till there comes "XTRV" ("Vertex"). When you reached this section, the data is:
Byte { x } - Section
{
     Byte { 4 } - Section Name
     if Section Name  == "XTRV" -> "Vertex"
        then
        {
             Float { 4 } - Vertex X
             Float { 4 } - Vertex Y
             Float { 4 } - Vertex Z
             Float { 4 } - Unknown

             Float { 4 } - UV X
             Float { 4 } - UV Y
        }
}
```


There are other sections like "RTAM" -> "Material" or "MNXTVPRG" -> "GroupVertex". I think it's obvious what they are describing.
After the "XTRV"-Section, immadiately the "XDNI" -> "Index" starts. That section starts as any section too with it's "Section Name" ( Byte { 4 } ).

(legend: "->" (without quotes) means "could mean")
==============================

So, thats what I found so far. As it looks, the UV in the VBO starts somewhere around the 16th byte. As for now, I was not able to find any information about the Face count. The "MNXTVPRG" should be analyzed a bit deeper that I did. When somebody is able to find some more relevant information like offset to VBO and/or Facecount, I'm ready to write a small application to convert this to the obj-format. But anyway, it is going to be hard to convert the models back to .xmx...
## Post #9
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2014-06-08T01:50:45+00:00
- Post Title: xmx 3D files Sega GT 2002

Are very good news for me, not know nothing about programming but this is really great, no want to return to .xmx just edit the 3D   
Thanks for your time
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-06-08T08:26:58+00:00
- Post Title: xmx 3D files Sega GT 2002

```

010D0   02 00 00 00 00 00 00 00  4D 4E 58 54 56 50 52 47   ........MNXTVPRG
010E0   8C 01 00 00 00 00 00 00 >66 0C 00 00 00 00 00 00  -- vertex count
010F0  >2C 16 00 00 00 00 00 00  00 00 00 00 00 00 00 00  -- face indices count
```

vertex count is 0xC66 = 3174 , face indices count is 0x162C = 5676 -> 1892 faces

Not sure about the face indices count. as from the list it should be 5772.
edit: pivke seems to be right, 162C looks like an offset

There's another chassis at 0x13FFC but I got a point cloud only because I don't know which face indices belonging to it. Same goes for 0x2698C, but there are 1369 vertices only.
(You can increase the point's size by pressing 'p' in hex2obj. shift-p to decrease)
## Post #11
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2014-06-08T11:43:58+00:00
- Post Title: xmx 3D files Sega GT 2002

Hey shakotay2,

nice, you've did some research of the Groups. We quite get more far  

So, I've looked at your results, but I think the structure has some other order. What do you think about this:


MNXTVPRG8C01000000000000660C0000000000002C16

MNXTVPRG = "GroupVertex" (obvious)
8C01000000000000 = Unknown
660C = Vertex Count for this group (0x0C66 = 3174 vertices of 7719 total vertices)
000000000000 = Unknown
2C16 = Offset to VERTEX-section (0x162C = Begin-Of-"XTRV"-Section -= 16 byte) (Those 16 byte could be some general information about vertices, maybe flags?!)

I think what I wrote above is quite right. Because everything starts making sense for now. So the "MODEL"-section keeps things like total Total-Vertex-Count and Total-Face-Count, just as the section ID says. And the "GROUPVERTEX"-section is like grouping in *.obj-files.

So what we have to do for now, is checking the "GROUPVERTEX"-section for counts, and offsets. And check if the offsets are "array"-offsets or "byte"-offsets.

Keep up the good work, the circle about this formats is gonna be closing
## Post #12
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-06-10T19:41:07+00:00
- Post Title: xmx 3D files Sega GT 2002

KarinFutoGT,

I finished the hacking of the .xmx format. Here I attached the converted .obj/mtl files to check out the result.
Next day I will upload an application and you can see your .xmx object directly without any tricks.
If you will confirm that works correctly, I will share the missing information.

(I must shut down my PC now...)
[xmx_to_obj.zip](https://xentaxbackup.github.io/file/7458_xmx_to_obj.zip)
## Post #13
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2014-06-10T20:40:51+00:00
- Post Title: xmx 3D files Sega GT 2002

@Karpati
Cool, good work! Could you share your research with us? Would be interesting
## Post #14
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2014-06-11T06:11:53+00:00
- Post Title: xmx 3D files Sega GT 2002

Thanks for all just tried right now and uv works correctly
## Post #15
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-06-11T12:30:27+00:00
- Post Title: xmx 3D files Sega GT 2002

Please could you upload more models? Jottio Caspita
## Post #16
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2014-06-11T12:59:15+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

> Reply from TomWin
>
> Please could you upload more models? Jottio Caspita

This forum is not a warez site buddy
## Post #17
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-06-11T14:11:42+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

> Reply from KarinFutoGT
>
> TomWin wrote:Please could you upload more models? Jottio Caspita

This forum is not a warez site buddy

indeed
## Post #18
- Username: Guerra8888
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 06, 2010 10:47 am
- Post datetime: 2014-06-11T18:28:10+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

Nice work... THX
## Post #19
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-06-11T19:02:38+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

@KarinFutoGT,

You can download and use the latest (unpublished yet officially) version of 3D Object Converter using this link:
[http://www.i3dconverter.com/3doc/downlo ... rtable.zip](http://www.i3dconverter.com/3doc/downloads/3doc_v5.321_portable.zip)
## Post #20
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-06-11T19:16:42+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

@KarinFutoGT,

Can you tell me which file contains the texture bitmap files?

And which utility did you use to extract the .xmx files from the .afs files?
## Post #21
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-06-11T19:57:16+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

@pivke.

     if Section Name  == "LEDM" -> "Model"
        then
        {
             Byte { 36 } - Unknown
             Dword { 4 }  NumOfVRTSGroups
             skip the other unnecessary bytes
        } 


VRTSGroup Structure
              Byte { 8 }       - Unknown
              Dword { 4 }    - Vertex_Counter
              Byte { 4 }       - Unknown
              Dword { 4 }     - Vertex_FileOffset   (add 4*4 to get the real fileoffset!)
              Byte { 24 }      - Unknown
              Dword { 4 }     - Vertex Size
              Byte { 16 }      - Unknown
              Dword { 4 }     - Face_FileOffset   (add 4*4 to get the real fileoffset!)
              Dword { 4 }     - Num_StripPoints  (Number of Triangle strip points)
## Post #22
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2014-06-11T19:58:54+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

> Reply from Karpati
>
> @KarinFutoGT,

You can download and use the latest (unpublished yet officially) version of 3D Object Converter using this link:
http://www.i3dconverter.com/3doc/downlo ... rtable.zip

Don't load all the faces and it say bad poly and can't export
## Post #23
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2014-06-11T20:00:18+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

> Reply from Karpati
>
> @KarinFutoGT,

Can you tell me which file contains the texture bitmap files?

And which utility did you use to extract the .xmx files from the .afs files?

Textures are in .dds, you can found on pic_xxxxx.zip files, for example "pic_celica_gt4.zip"
## Post #24
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-06-11T20:06:24+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

Thank you for your information.

I have this disk:   Sega_GT_2002_and_JSRF_bundle_pack  and it has not .zip files...
## Post #25
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2014-06-11T20:09:15+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

I have the single version so is just the Sega GT nothing more
## Post #26
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2014-06-11T20:23:32+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

Soo yes i need to pay 40 € to get the full version and export correctly, nice joke
## Post #27
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2014-06-11T20:57:28+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

> Reply from Karpati
>
> @KarinFutoGT,

Can you tell me which file contains the texture bitmap files?

And which utility did you use to extract the .xmx files from the .afs files?

Universal AFS File Extractor/Rebuilder V 3.8
## Post #28
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2014-06-11T21:39:25+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

@Karpati
Cool, great work!
## Post #29
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2014-06-12T03:09:04+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

Here are the textures too [https://www.mediafire.com/?873sf215emqr33s](https://www.mediafire.com/?873sf215emqr33s)
## Post #30
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-06-12T05:14:30+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

> Reply from KarinFutoGT
>
> Don't load all the faces and it say bad poly and can't export

The standard Triangle Fan algorithm generates too many bad triangles from the .xmx files and reports it to the user. As you can see it loads the correct triangles only.
## Post #31
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-06-12T05:16:26+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

> Reply from KarinFutoGT
>
> Soo yes i need to pay 40 € to get the full version and export correctly, nice joke

It is not a joke, I promissed you a model viewer only...
## Post #32
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2014-06-12T05:50:42+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

> Reply from Karpati
>
> KarinFutoGT wrote:Don't load all the faces and it say bad poly and can't export  

The standard Triangle Fan algorithm generates too many bad triangles from the .xmx files and reports it to the user. As you can see it loads the correct triangles only.

Thanks for explain
## Post #33
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2014-06-12T05:53:45+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

> Reply from Karpati
>
> KarinFutoGT wrote:Soo yes i need to pay 40 € to get the full version and export correctly, nice joke  

It is not a joke, I promissed you a model viewer only...

Only a viewer? What about convert to .obj  
I don't want to belittle all the hard work but i make this thread because i want to rip models, to see models i have already a xbox
## Post #34
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-06-12T06:39:36+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

> Reply from KarinFutoGT
>
> Only a viewer? What about convert to .obj  
I don't want to belittle all the hard work but i make this thread because i want to rip models, to see models i have already a xbox

You can convert to .obj format using this program.

I note in your first post you wrote about a 'tool/program' not about the 'free tool/program'.
## Post #35
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2014-06-12T07:53:54+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

Thanks for explaining 
Now I know that here I have to ask for anything more because they charge
## Post #36
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-06-13T04:19:35+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

looks like this tool reads 3d models correct and it possible to export them to lwo. However there s missing UV map
## Post #37
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-06-13T09:53:16+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

> Reply from TomWin
>
> looks like this tool reads 3d models correct and it possible to export them to lwo. However there s missing UV map

The LightWave 3D v5.x .lwo format does not support the UV datas.

Use the LightWave 3D Lscript .ls or the Wavefront .obj format.
## Post #38
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-06-13T12:12:35+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

> Reply from Karpati
>
> TomWin wrote:looks like this tool reads 3d models correct and it possible to export them to lwo. However there s missing UV map 

The LightWave 3D v5.x .lwo format does not support the UV datas.

Use the LightWave 3D Lscript .ls or the Wavefront .obj format.
That one exports model skipping every 5th poly
## Post #39
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2014-06-13T12:41:28+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

> Reply from TomWin
>
> Karpati wrote:TomWin wrote:looks like this tool reads 3d models correct and it possible to export them to lwo. However there s missing UV map 

The LightWave 3D v5.x .lwo format does not support the UV datas.

Use the LightWave 3D Lscript .ls or the Wavefront .obj format.
That one exports model skipping every 5th poly

Yes because you need to have the registered 3d object = pay 40 € is not a problem pay for a program with a large list of formats but is not good if you only want the xmx format
## Post #40
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-06-13T15:53:26+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

yes and even worst if you dont need all the cars :S
## Post #41
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-06-15T00:41:36+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

What about Sega GT Online from 2004? It has more cars


EDIT:
World Racing 2 conversion 

1989 Jiotto Caspita
## Post #42
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2014-06-15T15:11:23+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

I've tried some formats but you lost uv mapping   
How you as used to convert?
## Post #43
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-06-15T20:01:03+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

> Reply from KarinFutoGT
>
> I've tried some formats but you lost uv mapping   
How you as used to convert?

I used obj model and rebuilt missing polys, some materials like body, plastic, black things etc no need textures, so I used that parts from lwo model.
## Post #44
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2014-06-15T20:15:28+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

I think is better to remap than do those steps   I need everyhing mapped to make templates and paint and then make lods
## Post #45
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-06-15T21:12:07+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

> Reply from KarinFutoGT
>
> I think is better to remap than do those steps   I need everyhing mapped to make templates and paint and then make lods

ah, then is too much work, maybe someone else can make 3dsmax script for import those files, is too complicated fixing these models.
## Post #46
- Username: nosfornos
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Dec 21, 2011 4:16 pm
- Post datetime: 2014-07-08T11:41:55+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

Can you convert some .xmx files(Sega GT 2002) to .obj?
I want...:
Alfa Romeo 145
Alfa Romeo 156
Alfa Romeo GTV
Mazda Autozam AZ-1
Fiat Barchetta
Honda Beat
Honda Integra Type-R(DC2)
Mitsubishi Lancer Evolution IV
Nissan Skyline(R30)
Subaru Alcyone SVX
Toyota Celica GT-Four(ST205)

I'd appreciate it if you convert.....
## Post #47
- Username: egregiousguy
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Oct 29, 2018 1:15 pm
- Post datetime: 2020-09-03T23:43:53+00:00
- Post Title: Re: xmx 3D files Sega GT 2002

Sorry for resurrecting an old board but I came across this board awhile back looking to see if there was any documentation on the xbox xmx file format which is also used for House of the Dead III.  I spent a few days and managed to get a HotD3 script running (with a few minor texture errors) but I wanted to see how well my same script worked with Sega GT 2002 and it seemed to work just fine (with a few modifications).  No textures since I don't have them but It seems like some of the materials don't use external textures either (unlike HotD3 which uses mainly textures).
[dom_zero.png](https://xentaxbackup.github.io/file/18690_dom_zero.png)
