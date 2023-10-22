## Post #1
- Username: LinkvsSangoku
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Aug 25, 2013 4:13 pm
- Post datetime: 2013-08-25T09:01:24+00:00
- Post Title: [Request] DragonBall Online Mesh Viewer

Hello everyone, i'm new here and i'm french (sorry if my english isn't perfect)

Well i need a little help, does you have a way to read meshes from .DFF and animations from .AMN files from DBO (.PAK Files extracted) ?

I found a little trick to read some .DFF files (only work on some .dff i get dummy with other)

I tried to find a similarity in the headers of these files .DFF but I do not see how they can help me.

Anyone have a solution to use those files correctly ?

I upload some mesh and animations files here [http://www.mediafire.com/download/5cl0v ... nd_ANM.rar](http://www.mediafire.com/download/5cl0v7xheaunzxs/DFF_and_ANM.rar)

DBO Developper are NTL.
Publisher: Netmarble (KR) Cayenne Tech (Taiwan & Hong Kong)
Link for the game: [http://dbo.wasabii.com.tw/](http://dbo.wasabii.com.tw/)
Thank you for your help
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-08-25T13:05:29+00:00
- Post Title: [Request] DragonBall Online Mesh Viewer

> Reply from LinkvsSangoku
>
> Well i need a little help, does you have a way to read meshes from .DFF and animations from .AMN files from DBO (.PAK Files extracted) ?'yes' for dff files:
[](http://www.pic-upload.de/view-20522249/n_gkn_a1.dff.jpg.html), submesh head

If you're having some basic understanding of vertices and faces (and some coding skills)
I can tell you how to get the meshes on your own.
## Post #3
- Username: LinkvsSangoku
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Aug 25, 2013 4:13 pm
- Post datetime: 2013-08-25T14:43:03+00:00
- Post Title: [Request] DragonBall Online Mesh Viewer

i don't have any skills in 3D.

I'm looking at the Wiki page XentaX and tutorials from this topic [viewtopic.php?f=29&t=3739](http://forum.xentax.com/viewtopic.php?f=29&t=3739) to learn "basics"

So if you redirecting me in a tutorial for this it's would be nice

And can you give a try in the "n_hmy_m_b2.dff" file ?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-08-25T20:07:41+00:00
- Post Title: [Request] DragonBall Online Mesh Viewer

> Reply from LinkvsSangoku
>
> I'm looking at the Wiki page XentaX and tutorials from this topic viewtopic.php?f=29&t=3739 to learn "basics"

So if you redirecting me in a tutorial for this it's would be nicechrrox tut is a good one.
After you read it I can give you some details for DragonBall dffs.
But so far I did only get one kind of submesh. There are other data to be explored.

> And can you give a try in the "n_hmy_m_b2.dff" file ?
[](http://www.pic-upload.de/view-20527779/n_hmy_m_b2.dff.jpg.html)
## Post #5
- Username: LinkvsSangoku
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Aug 25, 2013 4:13 pm
- Post datetime: 2013-08-25T20:14:36+00:00
- Post Title: [Request] DragonBall Online Mesh Viewer

i read it.
I better understand the functioning of the files and how to spot in the case of the tuto
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-08-26T06:36:31+00:00
- Post Title: [Request] DragonBall Online Mesh Viewer

So here's a short approach on DragonBall online meshes (dff)
Basic knowledge of 3D formats assumed.

Sample n_hmy_m_b2.dff

May not apply to other samples.So don't be confused.  

Skeletal bones being contained ("Bip01 L Foot") not handled here.

First of all the face indices to be found. Maybe BYTE or (unsigned) int.
int as 2 (WORD) or 4 bytes (DWORD)

Faces consisting of 3 (triangles) or 4 indices (quads).

Scrolling through the mesh file using a hexeditor the face index table easily to be found
looking like a swizzled ASCII table (N.Q.R., b.a.c. or something like that).

One table's starting offset to be 0x50B0E (yes, tend to start the search from file's end).

Looks like having 4 indices per faces. It's no quads because the uncommon 00 00 index to be overread.
Each index of WORD size.

For wavefront obj format the faceindices are starting from 1 instead of 0 so a one needs to be added to each index.

First three faces:

f 21/21 58/58 5/5 
f 73/73 5/5 74/74 
f 22/22 18/18 59/59 

The notation says: first face's vertices are vertex 21,58,5
first face's texture coords are tex 21,58,5

Ignored normals because they can be created in blender automatically.
If to be used normals the notation would be f 21/21/21 58/58/58 5/5/5
(But some formats go like this: f 21/15/15 58/16/16 5/17/17 for example) 

End of face index table at 0x50EAD. So face count would be 116 (928/8)

928 = 0x3A0 = 0x50EAE - 0x50B0E

Last three faces:
f 12/12 15/15 17/17 
f 35/35 1/1 39/39 
f 12/12 17/17 1/1 

Now searching the vectors of vertices, normals and the texture coords.
Vertices and normals being composed of 3 floats (x,y,z), texture coords of 2 floats.

(square root of) Sum of square of the normals components being one (the length of the vectors). This way normals to be identified easily.

Position of tables in the files may vary. Often the order is vertices, normals, texture coords, faces.

In this case it starts with the table of tex coords then table of face indices follows.
Then vertices/normals table follows at 0x50EAE. (I thought - but was a hoax; true start is at 0x50EC6)

Ends at 0x515E5.
Means we have a block size of 1824. 3 floats occupy 12 bytes. 1824/12=152

In this case it's a vertices and a normals block. So there are 76 vertices followed by 76 normals.

The vertex count 0x4C (= 76  dec.) is 4C 00 00 00 in little endian notation.
Should be found somewhere in the file. In this sample it's at 0x508A6.
(Although there are 21 other findings.)

The first 3 verts:
v  0.206444 -0.003008 0.096340
v  0.197505 0.003211 -0.140815
v  0.143018 0.000008 0.136271

 And the last three:
v  -0.382032 0.145165 -0.214877
v  -0.290796 0.125715 -0.214021
v  -0.335196 0.136866 -0.217663

(Vertex block ends at 0x51255. Normals block ends at 0x515E5.)

Last not least the tex coords block. To be found at 0x508AE.
Yes, it's located before the face index block.

Texture coords consist of two floats (2D coords x,y) in the range of 0.0 .. 1.0.

First tex coord pair:
vt 0.300640 0.505262 

Last one:
vt 0.085109 0.699195 

Other face index blocks in this file containing FF FF.

Usually being a marker for ending of TriStrips.
Not applying in this case imho. Not sure how to handle these blocks.

So this was a crash course only. May contain errors.
Nevertheless: HTH
## Post #7
- Username: LinkvsSangoku
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Aug 25, 2013 4:13 pm
- Post datetime: 2013-08-26T09:23:10+00:00
- Post Title: [Request] DragonBall Online Mesh Viewer

Ok i'll try that thank you!

Theres is a way to "automated" the process? Like an extension for 3DsMax or other log ?
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-08-26T10:27:00+00:00
- Post Title: [Request] DragonBall Online Mesh Viewer

If you knew python you could write a dff importer (python script) for blender or Noesis.

(For me it's more convenient to write some C code.)

If I find some time I could modify my FungWan mesh extractor for DragonBall online.
But before the format needs further exploration.
## Post #9
- Username: LinkvsSangoku
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Aug 25, 2013 4:13 pm
- Post datetime: 2013-08-26T10:44:45+00:00
- Post Title: [Request] DragonBall Online Mesh Viewer

i don't know Python

Is there any coder who could make that or a thread for a request ?
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-08-27T16:41:12+00:00
- Post Title: [Request] DragonBall Online Mesh Viewer

Here's an extractor:
.


 DBallExtract.zip
(38.79 KiB) Downloaded 38 times
## Post #11
- Username: LinkvsSangoku
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Aug 25, 2013 4:13 pm
- Post datetime: 2013-08-28T10:18:44+00:00
- Post Title: [Request] DragonBall Online Mesh Viewer

Hi
Thanks for your extracor.
It's working fine in some .DFF
but with some files, i get strange meshes

Picture from the file "n_gkn_a1.dff"


I have two question about your extractor too, i need to open a .DFF file then press one of the two buttons, but why i need to close the exctractor for having the complete file (if i not closing the windows, .OBJ files are 0Kb)

The second is, does you need an archive with models to improve your extractor ?

And there is a way to conserve the Texture positionnement in meshes ?
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-08-28T11:40:51+00:00
- Post Title: [Request] DragonBall Online Mesh Viewer

Picture from the file "n_gkn_a1.dff"
[](http://www.pic-upload.de/view-20550588/n_gkn_a1.dff.obj.jpg.html) I used the left button.

> Reply from LinkvsSangoku
>
>  (if i not closing the windows, .OBJ files are 0Kb)The file is closed when the extractor is closed, yes. Because it was a log file before. Should be changed (some day).

> The second is, does you need an archive with models to improve your extractor ?Nope. The models are not that detailed. But you may upload a model that the extractor does not extract correctly. (Always try other button on a fail.)

> And there is a way to conserve the Texture positionnement in meshes ?What does that mean exactly? (In blender you load a texture file into the UV editor, then you move/mirror it to fit on the UV map. Is it this you mean?)
## Post #13
- Username: LinkvsSangoku
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Aug 25, 2013 4:13 pm
- Post datetime: 2013-08-29T11:27:09+00:00
- Post Title: [Request] DragonBall Online Mesh Viewer

> Reply from shakotay2
>
> Picture from the file "n_gkn_a1.dff"
How does you get a view like that ?

> Reply from shakotay2
>
> The file is closed when the extractor is closed, yes. Because it was a log file before. Should be changed (some day).
Ok i understand

> Reply from shakotay2
>
> Nope. The models are not that detailed. But you may upload a model that the extractor does not extract correctly. (Always try other button on a fail.)
i have other models : [http://www.mediafire.com/download/ycjka ... Meshes.rar](http://www.mediafire.com/download/ycjkawck8jzke0m/Meshes.rar)

> Reply from shakotay2
>
> What does that mean exactly? (In blender you load a texture file into the UV editor, then you move/mirror it to fit on the UV map. Is it this you mean?)
i mean textures files are "automatly" positionned in-game and DFF files contain the positioning of the texture and is there a way to see what file the mesh use in blender?
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-08-29T14:26:07+00:00
- Post Title: [Request] DragonBall Online Mesh Viewer

> Reply from LinkvsSangoku
>
> How does you get a view like that ?? blender bascis:
select mesh, choose edit mode, RMB on windows border, "Split Area", choose UV editor.


> i have other modelsthx - looks like a third button is needed. has to wait 'til my next spare hours.

> is there a way to see what file the mesh use in blender?Didn't find a texture extension (.dds, .tga, whatever) in the dffs. Search in DragonBall folder for files named n_gkn_a1 for example with other extension than .dff. One of these (if any) might be the corresponding texture file.

edit: there are the names B_Kinto_1..B_Kinto_9 contained in the dff
but this seem not to be material ore texture names because there are only 3 submeshes.
## Post #15
- Username: r3d
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 22, 2012 6:38 pm
- Post datetime: 2013-08-29T18:04:58+00:00
- Post Title: [Request] DragonBall Online Mesh Viewer

Hi, I am a soft-dev myself and I'd love to join the discussion. I have tried to do that some time ago but failed. Glad to see someone going further.

Is your software open source or are you willing to share it? If not, can you more or less sum up the the format? The description above is not really organized and I maybe you have found out something new 

Not to mention I will love to help with any bug fixing
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-08-30T08:20:59+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

I uploaded an improved version some posts above.

[](http://www.pic-upload.de/view-20568277/ud6_d_f3_001_dff.jpg.html)

> Reply from r3d
>
> Is your software open source or are you willing to share it?My coding style is too sloppy as to reveal it to the (sometimes very harsh) criticism of the public.
So sry: no.

> If not, can you more or less sum up the the format?The above crash course is containing 90% of the info you need, imho.
The format itself being relative simple:

Be informed that it doesn't start from file offset 0x0.
The beginning of the data and addr of face count is determined by a pattern search. 
(to clearify this due to r3d's hint. Thx for it.)

```
vertex count DWORD
unknown DWORD  (01 000000?)

start of tex coords block
tex 2 floats

tri faces, indices f1, f2, 00, f3 unsigned ints	// 00 00 to be skipped
gap of 24 bytes
vertices 3 floats
normals 3 floats
```
For buildings there's some kind of 2nd texture coords block to be skipped ( verts count * 8 )

The main job is to find the offsets of the different blocks (texture coords, face indices, vertices).

Often pattern search is very helpful. I used "paint name" for the 1st button (in the 1st version) 
and 01000000.

You'll experience many findings for the 01000000 pattern in ud6_c_f3_001.dff
so the trick is - as always - to determine the right ones.

Here's an example how to get them:

```
         //if (cnt==18)		// Achtung! Wird VOR Ausgabe incr.
         //    l=l;          // debug point
         offs= dwSM_offsaddr[l] ; if (offs<offs2) goto _next ;
         if ( (*(pFBuf+offs+8)==0)&&(*(pFBuf+offs+9)==0)) goto _next ;
         if ( (*(pFBuf+offs+6)==0)&&(*(pFBuf+offs+7)==0)&&(*(pFBuf+offs+8)==0)) goto _next ;
         if ( (*(pFBuf+offs-4)==0)&&(*(pFBuf+offs-3)==0)) {		// dort face index 2, imma 00 00
            cnt++ ; fprintf( stream, "g submesh_%d_3\n", cnt) ;    
            offs -= 6 ;			                                // algo=1 statt 3
            FindStringInBuf_DragonBall_onl(offs, dwFileSize, nValue, 1, lastFaceNo) ;	// &offs in fct def.
            offs2= offs ;
         }
_next: ;
}
```

I won't bother to explain this because it was just some "trial and error".
## Post #17
- Username: LinkvsSangoku
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Aug 25, 2013 4:13 pm
- Post datetime: 2013-08-30T14:58:41+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

Wow, nice update, i found other meshes who doesen't work with one of the three buttons
[http://www.mediafire.com/download/b4sdi ... 001_02.dff](http://www.mediafire.com/download/b4sdi8q1dasix3h/dwc_temple_001_02.dff) and [http://www.mediafire.com/download/b4jbx ... gku_b2.dff](http://www.mediafire.com/download/b4jbx3w6sa8bvcw/n_gku_b2.dff)

I have one other question, can you try to conserve material list for the mapping ?
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-08-30T19:43:01+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

> Reply from LinkvsSangoku
>
> Wow, nice update, i found other meshes who doesen't work with one of the three buttons [...]dwc_temple_001_02.dff and [...]n_gku_b2.dffwell, the fst one is weird. Don't know how to handle. The 2nd one has an invalid texture block (18 x FFFFFFFF FFFFFFFF at 0x394D0) which I skipped manually. I won't handle every single irregular dff but here's the obj: [http://www.uploadmb.com/dw.php?id=1377891048](http://www.uploadmb.com/dw.php?id=1377891048)

> I have one other question, can you try to conserve material list for the mapping ?Still don't understand. Same goes with 
> Reply from LinkvsSangoku
>
> i mean textures files are "automatly" positionned in-gameYou are talking about texture coords in the dffs?

I don't have a texture to test but the UV maps seem to be o.k. in blender.
So maybe you can explain what you want to do or what exactly the problem is.
## Post #19
- Username: r3d
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 22, 2012 6:38 pm
- Post datetime: 2013-11-18T22:15:06+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

Just a slow poke reaction from me but is the data little endian? I am a bit confused here
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-18T22:46:51+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

yep, little endian. (You can't use hex2obj for the n_hmy_m_b2.dff (see previous crash course)
because there is an uncommon 4th face index 00 00.)
## Post #21
- Username: r3d
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 22, 2012 6:38 pm
- Post datetime: 2013-11-19T22:59:46+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

Thx 

Some new questions have arisen in my head. 

1) Do the meshes always use 1 texture?
2) Is the amount of tex-coords equal #faces *3 ?
3) In case of buildings why do we skip verts count*8 ? Where does the 8 come from?
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-20T00:16:24+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

> Reply from r3d
>
> Thx 

Some new questions have arisen in my head. 

1) Do the meshes always use 1 texture?
2) Is the amount of tex-coords equal #faces *3 ?
3) In case of buildings why do we skip verts count*8 ? Where does the 8 come from?
1) afair I had no texture files so I don't know. Search for the texture files of a sample
(see my post of Aug. 29th about the B_Kinto_x strings in a dff) and you'll know it.

2)afair after 3 months is vertextcount==normalscount==texcount

3) did we skip? You really could help my if you gave me a quotation 

(I'll go to sleep now...)
## Post #23
- Username: r3d
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 22, 2012 6:38 pm
- Post datetime: 2013-11-20T23:23:27+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

> Reply from shakotay2
>
> r3d wrote:Thx 

Some new questions have arisen in my head. 

1) Do the meshes always use 1 texture?
2) Is the amount of tex-coords equal #faces *3 ?
3) In case of buildings why do we skip verts count*8 ? Where does the 8 come from?
1) afair I had no texture files so I don't know. Search for the texture files of a sample
(see my post of Aug. 29th about the B_Kinto_x strings in a dff) and you'll know it.

2)afair after 3 months is vertextcount==normalscount==texcount

3) did we skip? You really could help my if you gave me a quotation 

(I'll go to sleep now...)

At 2) It is perfectcly fine for a vertex to have as many normals as the faces that vertex builds (preserve edges etc). Sake for tex coords, 1 vertx - many faces 
At 3) You said  : "For buildings there's some kind of 2nd texture coords block to be skipped ( verts count * 8 )". Where does the 8 come from?
## Post #24
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-21T00:10:42+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

> Reply from r3d
>
> At 3) You said  : "For buildings there's some kind of 2nd texture coords block to be skipped ( verts count * 8 )". Where does the 8 come from?Ok, texture coords block (must have overread this yesterday  ).

2D texture coords x and y as floats, each float consisting of 4 bytes
## Post #25
- Username: r3d
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 22, 2012 6:38 pm
- Post datetime: 2013-11-22T20:34:34+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

Quite frankly I am a bit confused.

These are the first bytes of w_axe_01b.dff :

10 00 00 00 E7 6A 00 00 65 00 02 1C

The 10 00 00 00 pattern occurs in every file. I assumed it it to be skipped.
E7 6A 00 00 is the face count - 27367 I'm ok with that
but 

 65 00 02 1C in little endian is 469893221 . I mean THIS many vertices? Sth's gotta be wrong here.
## Post #26
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-11-22T20:45:55+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

it might be 2 short values.
## Post #27
- Username: r3d
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 22, 2012 6:38 pm
- Post datetime: 2013-11-22T20:49:42+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

He said those are DWORDS
## Post #28
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-11-22T20:53:45+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

he was just looking at the format quickly with a few samples.
online games tend to change model formats alot in the same games.
he most likely always saw the 2nd short value as 00 so amused it was a long.
did you look at the vertex section?
how much data is there i am willing to bet it matches the first short.
## Post #29
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-22T21:39:18+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

> Reply from chrrox
>
> he was just looking at the format quickly with a few samples.
online games tend to change model formats alot in the same games.Yep, that's correct. Thx, chrrox, for the clearing. 

> Reply from r3d
>
> He said those are DWORDSAtm I'm unsure about your intention.

If you read the thread carefuly you'll see that not all models are handled by the Mesh Viewer.
The crash course was about n_hmy_m_b2.dff
iirc I never saw this axe. Did the Mesh viewer extract w_axe_01b.dff correctly?

Guess no. So if you'll find that there are dozens of similar models I could have a look at them.
And maybe bug fix the viewer if required.
But as I stated somewhere above I won't handle every single dff separately.

Why do you think "65 00 02 1C" being the vertices count?
Did I post this? Then a quotation please.

For n_hmy_m_b2.dff it looks like this

050890   02 1C 01 00 00 00 48 0D  00 00 65 00 02 1C 37 00
0508A0   01 00 74 00 00 00 4C 00  00 00 01 00 00 00 6F ED

The bold bytes being the vertex count - 65 00 02 1C only being a pattern helping to find the start of the vertices block.
## Post #30
- Username: r3d
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 22, 2012 6:38 pm
- Post datetime: 2013-11-23T13:14:48+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

My I've never had such problem when the other person would just forget his quotes 

> face count DWORD
>
> vertex count DWORD
>
> unknown DWORD  (01 000000?)
>
> 
>
> start of tex coords block
>
> tex 2 floats
>
> 
>
> tri faces, indices f1, f2, 00, f3 unsigned ints   // 00 00 to be skipped
>
> gap of 24 bytes
>
> vertices 3 floats
>
> normals 3 floats

You described it as the file structre. The way people usually  do it  is that they just iterate through the structure. And if you mention first thing as DWORD I assume you stick to the way people usually do it and actualy mean the first 4 bytes as a DWORD face count. Well obviously it isn't as the first 4 bytes are 00 00 00 01. Though the next sequence might be
## Post #31
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-23T14:21:10+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

> Reply from r3d
>
> My I've never had such problem when the other person would just forget his quotesMaybe I'm misunderstanding you - so no offense.
But you're simply stealing my time if you don't quote things I posted nearly 3 months ago.
I don't need to help you. i'm doing this in my spare time.

> You described it as the file structre. The way people usually  do it  is that they just iterate through the structure. And if you mention first thing as DWORD I assume you stick to the way people usually do it and actualy mean the first 4 bytes as a DWORD face count. Well obviously it isn't as the first 4 bytes are 00 00 00 01. Though the next sequence might beYou're totally right. Thanks for the hint. I corrected the concerning post.

I hope our communication will work better in the future.  

Have a nice weekend.
## Post #32
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-09-06T21:42:49+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

here's an updated extractor for m_cmt_a1.dff and n_bul_a1.dff which can be extracted using the go4 button:

> Reply from shakotay2 ↑Wed Aug 28, 2013 12:41 am at Wed Aug 28, 2013 12:41 am
>
> 
.



m_cmt_a1---n_bul_a1.JPG (38.33 KiB) Viewed 165 times


The right model seems to be missing some submeshes - didn't bother, why.
## Post #33
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2014-09-11T04:20:08+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

?!
how to extract .dff from .pak file?
some textures was extracted using the Dragon UnPacker

nobody answer this topic
[viewtopic.php?f=10&t=4224](http://forum.xentax.com/viewtopic.php?f=10&t=4224)
## Post #34
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-09-11T08:40:43+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

you're not expected to get an answer in the wrong subforum then.

A search for DBO unpacker in the inet might help. (Didn't use it since I don't have any pak file so can't tell whether it's the right one.)
## Post #35
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2014-09-12T20:21:44+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

> Reply from shakotay2
>
> you're not expected to get an answer in the wrong subforum then.

A search for DBO unpacker in the inet might help. (Didn't use it since I don't have any pak file so can't tell whether it's the right one.)
oh sorry, and thank you!!
## Post #36
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2016-05-27T13:53:16+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

I'm trying to convert these models for a long time, someone could explain how to use the extractor correctly? I read the post more is still a little confusing to me, could someone explain to me the procedure?
## Post #37
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-27T14:32:48+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

talking about DBallExtract.exe? It's not heavily tested, just with two dff models, as explained in its opening screen.

Try out one of the three go buttons - if it doesn't work you're lost then, sry.
(I've the older version here, new one seems to have 4 buttons - should work similar, though.)

Import the created obj file with the blender wavefront obj import option 'separate by group' then move the submeshes manually to the correct positions, if required.



n_gkn_a1-dff.jpg (58.57 KiB) Viewed 102 times
## Post #38
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2016-05-27T17:03:01+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

Thank you very much. I managed to do the procedure correctly. Now I just need to fix the model's pose. Thank you.
[goku.png](https://xentaxbackup.github.io/file/10976_goku.png)
## Post #39
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2016-05-27T17:15:34+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

For those who want to download the models, textures and other resources has a pack this link.

[https://mega.nz/#!1Zw0GbSY!EZHiblW97XrG ... M0-q5Xq94c](https://mega.nz/#!1Zw0GbSY!EZHiblW97XrG9yj1AVvacmQf3flmWjhPrM0-q5Xq94c)
## Post #40
- Username: dswd2015
- Rank: veteran
- Number of posts: 87
- Joined date: Fri Sep 04, 2015 5:33 am
- Post datetime: 2016-06-03T16:55:19+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

I have a question, how to export the model in FBX correctly? Every time I do it to open in 3d max the model appears all black. Can anyone give me a tip?
## Post #41
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-22T03:39:37+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

> Reply from shakotay2 ↑Sun Sep 07, 2014 5:42 am at Sun Sep 07, 2014 5:42 am
>
> 
here's an updated extractor for m_cmt_a1.dff and n_bul_a1.dff which can be extracted using the go4 button: http://www.uploadmb.com/dw.php?id=1410039340
m_cmt_a1---n_bul_a1.JPG
The right model seems to be missing some submeshes - didn't bother, why.

Shakotayyy!xD! Do you still have those dff extractors?   please reupload them if you have
## Post #42
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-22T03:53:31+00:00
- Post Title: Re: [Request] DragonBall Online Mesh Viewer

nvm found it :p
