## Post #1
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-08T13:32:35+00:00
- Post Title: Planet Hot Wheels .MXS files

Hello everybody!

I've got a HUGE problem with this ex-mmo racing game that someone has recovered: Planet hot Wheels, there are these files (the most of this) in .MXS... so:

I tryed to ripping they with 3D Ripper DX, 3D Ripper, Ninjaripper, OGLE, etc. but without success.

I try to open the .MXS Files with Maxwell Render, but it give me this message:

[https://www.dropbox.com/s/dh0oyn62g70ng ... r.jpg?dl=0](https://www.dropbox.com/s/dh0oyn62g70ngfk/Error.jpg?dl=0)

I try to open with Maxwell plugin on Blender, but without success.

What can I do before I become crazy   

P.s.

The files are very old (2005), and I don't think it use DirectX or OpenGL...

The .ZIP of the game that someone has recovered:
[https://www.dropbox.com/s/njr7inatfr3y5 ... 5.rar?dl=0](https://www.dropbox.com/s/njr7inatfr3y5ce/Planet_Hot_Wheels_highway35.rar?dl=0)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-08-08T19:11:43+00:00
- Post Title: Planet Hot Wheels .MXS files

> Reply from Fiammanera628
>
> I tryed to ripping they with 3D Ripper DX, 3D Ripper, Ninjaripper, OGLE, etc. but without success.yeah, some formats seem to be a little bit tricky for ripping...  

Then some basic 3D knowledges are to come in handy:



63corvette.jpg (110.6 KiB) Viewed 250 times


I guess we need to apply some scaling factors(s) from here:

```
		*NODE_NAME "mdlCRSplitwindowvette_fr"
		*INHERIT_POS 0 0 0
		*INHERIT_ROT 0 0 0
		*INHERIT_SCL 0 0 0
		*TM_ROW0 0.00000022	-0.87412584	0.00000005
		*TM_ROW1 -0.00000002	0.00000003	0.87412596
		*TM_ROW2 -0.87412578	-0.00000019	-0.00000000
		*TM_ROW3 -0.33553852	-0.48163451	0.17693397
		*TM_POS -0.33553852	-0.48163451	0.17693397
		*TM_ROTAXIS -0.57735038	0.57735026	0.57735020
		*TM_ROTANGLE 2.09439492
		*TM_SCALE 0.87412584	0.87412596	0.87412578
		*TM_SCALEAXIS -0.19394371	-0.95159769	0.23842743
		*TM_SCALEAXISANG 0.30556968
	}
```
## Post #3
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-08T19:42:08+00:00
- Post Title: Planet Hot Wheels .MXS files

How did you do it??? have you ripped or open the file?? HOW???  

And what do you mean with "I guess we need to apply some scaling factors(s) from here"? I mean, where you use the code/script??

Yeah, I'm very surprised/confused
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-08-08T20:02:10+00:00
- Post Title: Planet Hot Wheels .MXS files

> Reply from Fiammanera628
>
> How did you do it??? have you ripped or open the file?? HOW???I used hex2obj (view 2nd link in my sig).

> And what do you mean with "I guess we need to apply some scaling factors(s) from here"? I mean, where you use the code/script??For example *TM_SCALEAXIS -0.19394371	-0.95159769	0.23842743, it's from the .MXS file.

In blender I used z * 2.5, looks ok to me:



63corvette.jpg (181.36 KiB) Viewed 243 times


Creation of mesh plus tverts is a little bit tricky because we've an extra MESH_TFACELIST here.
(The models are somewhat low poly so my motivation for a make_obj implementation is low, too.)

Maybe using Model Researcher is the better choice for this format?

Nope, it isn't because the free version doesn't support uint (unsigned short, to be precise), afaics.
Anyways; I'll leave the tmr template here:
(keep in mind to multiply "faces_count" and "uvs_index_count" by 3 in case you want to use the parameters with hex2obj)

```
    "file" : "63corvette.MXS",

    "vertices_offset" : "0x0701A",
    "vertices_count" : 2065,
    "vertices_padding" : 0,
    "vertices_type" : "Short_sign",
    "vertices_format" : "XYZ",
    "vertices_padding_inter" : 0,

    "faces_offset" : "0x0a09a",
    "faces_count" : 4162,
    "faces_padding" : 2,
    "faces_type" : "Short",
    "faces_format" : "Triangles",
    "faces_padding_inter" : 0,

    "read_uvsi" : 1,

    "uvs_offset" : "0x0122ed",
    "uvs_count" : 5695,
    "uvs_padding" : 0,
    "uvs_type" : "Short_sign",
    "uvs_format" : "UV",
    "uvs_padding_inter" : 0,

    "uvs_index_offset" : "0x017c1c",
    "uvs_index_count" : 4162,
    "uvs_index_padding" : 0,
    "uvs_index_type" : "Short",
    "uvs_index_format" : "Triangles",
    "uvs_index_padding_inter" : 0,

    "byte_order" : "<",
    "invert_x" : 0,
    "invert_y" : 0,
    "invert_z" : 0

}
```


Should not be too hard to code a model format scanner which searches for ASCII strings, there's all the info you need, for example:
*MESH_NUMVERTEX 2065
*MESH_NUMFACES 4162
*MESH_VERTEX_LIST

For the 63corvette there's 18 submeshes (maybe "default") of which 5 seem to be relevant.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-08-09T13:21:00+00:00
- Post Title: Planet Hot Wheels .MXS files

seems I need to flip texture and uvs?



63Corvettw-tex.jpg (122.61 KiB) Viewed 231 times
## Post #6
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-09T13:37:47+00:00
- Post Title: Planet Hot Wheels .MXS files

Ehm... I think the right side is turned on the left, but the other things is ok, if it is that you mean.

Ehm... about extract .mxs files with hex2obj... i try to understand something, but I dont' understand anything. sorry  

Can you tell me how you can understand where is the meshes inside? (I open the .mxs file with Hex Workshop)
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-08-09T14:16:57+00:00
- Post Title: Planet Hot Wheels .MXS files

> Reply from Fiammanera628
>
>  Can you tell me how you can understand where is the meshes inside? (I open the .mxs file with Hex Workshop)I don't have the time for detailed explanations, sorry. There's tutorials for such.
(view link in my sig).

Maybe someone takes up the task and writes a script; the format looks simple (despite of using shorts and extra tverts faces).
## Post #8
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-09T14:43:40+00:00
- Post Title: Planet Hot Wheels .MXS files

Oh... ok

Another question: you leave to me a tmr template... where I use the code of tmr template
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-08-09T15:08:37+00:00
- Post Title: Planet Hot Wheels .MXS files

[viewtopic.php?f=33&t=16163&p=139477&hil ... er#p139477](http://forum.xentax.com/viewtopic.php?f=33&t=16163&p=139477&hilit=researcher#p139477)

But the free version doesn't use unsigned shorts, as I wrote, so here's an obj file with hex2obj data and face indices from MR (was the quickest way to get them):


 63corvette - usigned.zip
(80.53 KiB) Downloaded 25 times
## Post #10
- Username: thorh62
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 10, 2018 11:45 am
- Post datetime: 2018-08-09T17:55:41+00:00
- Post Title: Planet Hot Wheels .MXS files

Could you please explain the settings that you used to get the vertices using hex2obj? I chose shorts for the vertices but I get unreasonable numbers. maybe take a screenshot of hex2obj so that we can study the settings you chose?
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-08-09T19:37:28+00:00
- Post Title: Planet Hot Wheels .MXS files

using the latest version: [viewtopic.php?f=29&t=10894&p=142434&hil ... al#p142434](http://forum.xentax.com/viewtopic.php?f=29&t=10894&p=142434&hilit=+actual#p142434)



63corvette_mesh.jpg (96.36 KiB) Viewed 213 times
## Post #12
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-09T20:03:14+00:00
- Post Title: Planet Hot Wheels .MXS files

So strange... I download the program from your sign and put the same data you put and it give me this:

[https://www.dropbox.com/s/hdgplhzgtduob ... 4.jpg?dl=0](https://www.dropbox.com/s/hdgplhzgtduob3m/Immagine4.jpg?dl=0)
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-08-09T20:55:55+00:00
- Post Title: Planet Hot Wheels .MXS files

you probably missed to check the checkbox next to the "ShortAll" combobox
(No checkbox present? view the link to the LATEST version in my previous post.)
## Post #14
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-09T21:18:36+00:00
- Post Title: Planet Hot Wheels .MXS files

OK! I got it! But I don't understand anyways... where are the "a09a" and "701a" from?

And what is it the noPtC set to "2"??
## Post #15
- Username: N/A
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Sep 17, 2014 11:15 pm
- Post datetime: 2018-08-09T22:02:27+00:00
- Post Title: Planet Hot Wheels .MXS files

> Reply from Fiammanera628
>
> OK! I got it! But I don't understand anyways... where are the "a09a" and "701a" from?
The hex starting addresses (offsets) are probably matched by finding the "MESH_VERTEX_LIST {" and "*MESH_FACE_LIST {" tags to get the offsets.

Also wanted to say this, but *.mxs files are modified *.ase text files... except they store list data in binary form. (Meaning Mousepad can't really read it)
And no, it's not a Maxwell render file.
The first string literally says where it comes from.
## Post #16
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-10T12:41:50+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

The .mxs file isnt' from Maxwell Render is the only thing I understand...
## Post #17
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-11T11:37:30+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

OK, I open one of the cars (THANKS A LOT thorh62!), the Chevy Nomad... the first sring is write: "3DSMAX_ENGINE1EXPORTB2 200", but on the 63 corvette is write: "3DSMAX_ENGINE1EXPORTFP 200";

With Model Researcher, the Chevy Nomad looks correct, but the 63 Corvette looks like this: [https://www.dropbox.com/s/mzetwz5mgs1fz ... e.jpg?dl=0](https://www.dropbox.com/s/mzetwz5mgs1fz1l/Immagine.jpg?dl=0)

Why?

thorn62 tells me that the files with first string "3DSMAX_ENGINE1EXPORTFP 200" has the verticles stored on another format. Is this the verticles blocked mode write on the tut of Hex2obj
## Post #18
- Username: N/A
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Sep 17, 2014 11:15 pm
- Post datetime: 2018-08-11T15:16:33+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

The first string is important, cause it gives the hint as to what 3d modelling package it comes from.
The variants are (I looked at the .text section of the exe to get the possible names):
Tags:
 - "3DSMAX_ENGINE1EXPORT (Only seen in HW:Turbo Driver so far)
 - "3DSMAX_ENGINE1EXPORTB (seems to be unused)
 - "3DSMAX_ENGINE1EXPORTB2
 - "3DSMAX_ENGINE1EXPORTFP
Possible versions:
 - 100 (Hypothetical dev version)
 - 200
 - 300 (Hypothetical dev version)
 - 400
 - 500 (Hypothetical dev versiont)
 - 600 (This is what HW:Racing Circuit throws up... but by then the format is a complete binary file)

To take it further, when you look at what's in common with the tags you get
  *3dsmax_Engine1Export
Replace Engine1 with a variable, and you get the text mask
  *3dsmax_<a>Export<b>

When searching for something similar, [this:](https://wiki.beyondunreal.com/Legacy:ASE_File_Format) comes up.
(Which explains almost everything)
There the string used there is *3DSMAX_ASCIIEXPORT
And the format is native to a well know 3d modeling package.

Also, from the tmr template that @shakotay2 posted for the vette, seems like the verticies for FP packed versions are stored as shorts then rescaled.
"vertices_type" : "Short_sign"
Which explains why I wasn't able to calculate what data type it was stored in. (Mind you, it's like reading c structs)

To make it even more obvious, it even lists the scene file it came from a few lines down. (with an extension of *.max)
## Post #19
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-11T16:27:09+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

O...K? i dont' get anything. But I noticed there is a structure on the file, yes, but I don't know how to handle the vertex...

I mean, I know the count is "2065", ok, but the "0x0701A" from the shakotay2's tmr I don't understand where it comes from...   

the other valor (the faces) I get when they are from.
## Post #20
- Username: N/A
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Sep 17, 2014 11:15 pm
- Post datetime: 2018-08-11T17:09:50+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

> Reply from Fiammanera628
>
> O...K? i dont' get anything. But I noticed there is a structure on the file, yes, but I don't know how to handle the vertex...

I mean, I know the count is "2065", ok, but the "0x0701A" from the shakotay2's tmr I don't understand where it comes from...   

the other valor (the faces) I get when they are from.
The last part of the version string decides how the vertex list is stored.

[s]
I mentioned where it comes from..
It's the starting address of the vertex list when I replied to you earlier.
(ie shortly after the count)

You'd need a hex editor to find the offset, unless you can automate the process.

Also, ENGINE1EXPORTFP variants store the vertex lists in binary form.
So eg 1.0 -> 0x0000803f, assuming the platform you are studying is little endian.

ENGINE1EXPORT versions (as found in HW:Turbo Driver) are pure text files, so you delete the node id, and user properties, and you get an *.ase file you can import with any program that supports that format.[/s]
Seems to be off by 12 bytes...
## Post #21
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-11T17:42:48+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

so I tryed to delete the "*NODE_ID" and save the file in .ASE format, but, when I tryed to open it with 3ds max gave me this error (3ds max because I read that it can open the .ASE files):

[https://www.dropbox.com/s/gywdwgi9g2h37 ... e.ASE?dl=0](https://www.dropbox.com/s/gywdwgi9g2h37jr/63corvette.ASE?dl=0)

So, what should I do   

p.s. I leave the .ASE file, if someone want to ceck it.

[https://www.dropbox.com/s/gywdwgi9g2h37 ... e.ASE?dl=0](https://www.dropbox.com/s/gywdwgi9g2h37jr/63corvette.ASE?dl=0)
## Post #22
- Username: N/A
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Sep 17, 2014 11:15 pm
- Post datetime: 2018-08-11T18:20:48+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

> Reply from Fiammanera628
>
> so I tryed to delete the "*NODE_ID" and save the file in .ASE format, but, when I tryed to open it with 3ds max gave me this error (3ds max because I read that it can open the .ASE files):

https://www.dropbox.com/s/gywdwgi9g2h37 ... e.ASE?dl=0

So, what should I do   

p.s. I leave the .ASE file, if someone want to ceck it.

https://www.dropbox.com/s/gywdwgi9g2h37 ... e.ASE?dl=0

> Reply from N/A
>
> 
ENGINE1EXPORT versions (as found in HW:Turbo Driver) are pure text files, so you delete the node id, and user properties, and you get an *.ase file you can import with any program that supports that format.[/s]
Read between the lines...
The 63corvette is an ENGINE1EXPORTFP variant. It obviously doesn't work by editing the file with a text editor.
Any normal plugin built for *.ase files are not capable of reading the lists in a binary format.

Also, you spelt check wrong...
[rd_40.7z](https://xentaxbackup.github.io/file/14733_rd_40.7z)
## Post #23
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-11T19:34:19+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

So? what I have to do?
## Post #24
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-13T11:07:11+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

> thorn62 tells me that the files with first string "3DSMAX_ENGINE1EXPORTFP 200" has the verticles stored on another format.

So, is possible that the verticles lists are stored on files .jrm from the "carena" zip?

an example is attached here.

[https://www.dropbox.com/s/2w55fbqxnysmk ... 5.jrm?dl=0](https://www.dropbox.com/s/2w55fbqxnysmkza/hwdeora35.jrm?dl=0)

Also I give you the 1st release of Planet Hot Wheels (the "Carena" zip)

[https://www.dropbox.com/s/lj1csowyyainn ... 5.rar?dl=0](https://www.dropbox.com/s/lj1csowyyainnid/Planet_Hot_Wheels_carena_10_17_05.rar?dl=0)

I hope this help you.
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-08-13T21:16:53+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

getting the mxs meshes (tested with 2 models only, uvs support now, EXPORTB2 support):


 Make_obj-PlanetHotWheels.zip
(66.51 KiB) Downloaded 29 times


As always: use it on your own risk!
Have fun with the scaling, chassis in blender y *2.5
windows: y * 1.5, z * 0.4 as a first start

(view the pic in my post as of 15th August to see which models might work)
## Post #26
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-13T22:33:38+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

shakotay2, I've taken the Demo version of Model Researcher Pro, is possible to write a script for these .mxs files with "3DSMAX_ENGINE1EXPORTFP 200", if it works?
## Post #27
- Username: N/A
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Sep 17, 2014 11:15 pm
- Post datetime: 2018-08-13T23:39:58+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

> Reply from Fiammanera628
>
> So? what I have to do?
My suggestion is to take something built to read 3DSMax *.ase files and modify it to read *.mxs files.
If the original script is well designed, it should be a "short" hop away from properly interpreting the file.

> Reply from Fiammanera628
>
> thorn62 tells me that the files with first string "3DSMAX_ENGINE1EXPORTFP 200" has the verticles stored on another format.
So, is possible that the verticles lists are stored on files .jrm from the "carena" zip?
And what Thor says is true.
But what you interpreted/concluded is incorrect. [s](Also doesn't make logical sense.)[/s]
The Carena build is an older version of the same game. 
So essentially *.mxs files superseded the role of *.jrm files in later versions of the same game engine.
And in HW:Racing Circuit, *.bws/*.bwo files replaced the role of *.MXS files. (The PHW game engine refers to objects in the *.MXS as *.MXO, files but whatever...)

*.jrm files are an older mesh format. [s](Cuz Shockwave...)[/s]
Chunk based <fourCC string> <Chunk size><contents> if I recall from when I manually tore down Hyperliner.
## Post #28
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-14T09:40:41+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

> My suggestion is to take something built to read 3DSMax *.ase files and modify it to read *.mxs files.
>
> If the original script is well designed, it should be a "short" hop away from properly interpreting the file.

I've only found this link with an article of .ASE read/import for 3ds Max, but I'm not sure if is this that you mean.

[https://blenderartists.org/t/3ds-max-as ... ipt/307120](https://blenderartists.org/t/3ds-max-ase-import-script/307120)
## Post #29
- Username: N/A
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Sep 17, 2014 11:15 pm
- Post datetime: 2018-08-14T17:58:18+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

Not really sure how useful that page is considering it's age.
It might work, but you know, ymmv.
## Post #30
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-14T18:08:28+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

> Reply from N/A
>
> Not really sure how useful that page is considering it's age.
It might work, but you know, ymmv.

Mh... but I don't understand why from an .MXS file, we are now talking about an .ASE file... ok, the scructure are the same, but they are 2 different files, no?
## Post #31
- Username: N/A
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Sep 17, 2014 11:15 pm
- Post datetime: 2018-08-14T19:17:01+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

Yes, they're not the same, 
But when you compare the files, outside of list data list (for FP, B2, and B variants), userproperties, version tag, node id, etc.
They're identical.

And therefore it's reasonable to conclude that *.mxs are derived from *.ase files.
So even though it's not the same, it makes sense to modify an *.ase parser into a *.mxs parser instead of making it from scratch.
## Post #32
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-14T19:26:32+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

Ok, I understand. But there is a way to convert the .mxs to .ase and vice-versa?
## Post #33
- Username: N/A
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Sep 17, 2014 11:15 pm
- Post datetime: 2018-08-14T19:33:17+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

Not exactly possible, since *.mxs files has minute differences, w.r.t. the format.
1 example is the node id which is a hash of what seems to be like the node name. (Essential for speeding up loading times but doesn't exist in *.ase files)
Another is the list data in *.mxs files are stored in different formats which are designed to remove unnecessary info  (Especially bad for vertex data, as it can be stored in 3 different formats)

Unless you figure out a way to fill in the missing data. Then good luck.
## Post #34
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-14T20:05:57+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

But, in my opinion, if you can read the .mxs files with "3DSMAX_ENGINE1EXPORTB2	200", without problems, I think is not so many difference with an .mxs with "3DSMAX_ENGINE1EXPORTFP	200"... 

Ah, I can't understand anything anymore...
## Post #35
- Username: N/A
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Sep 17, 2014 11:15 pm
- Post datetime: 2018-08-14T23:33:57+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

> Reply from Fiammanera628
>
> But, in my opinion, if you can read the .mxs files with "3DSMAX_ENGINE1EXPORTB2	200", without problems, I think is not so many difference with an .mxs with "3DSMAX_ENGINE1EXPORTFP	200"... 

Ah, I can't understand anything anymore...
It's not so different... if you know what data type it is. (signed shorts that are then scaled to the final size)
But if you don't know what it is, (ie not float32) like I was for years, then it makes a huge difference as there could be infinite possibilities to interpret the same chunk of data.

Also forgot to mention this... casting scene data to an *.obj file is bad cause you're casting out alot of useful (or leftover) scene data.
Like cameras, lights, animation info, etc
But for static models, it's not a problem.
## Post #36
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-15T10:06:33+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

> It's not so different... if you know what data type it is. (signed shorts that are then scaled to the final size)
>
> But if you don't know what it is, (ie not float32) like I was for years, then it makes a huge difference as there could be infinite possibilities to interpret the same chunk of data.

Ok, there are infinite possibilities of interpreting the data files. But, the method of skip this: "{.." and put 2 on Face Padding, is useful or not?

Anb another question: "FP" on "EXPORT" means...?  

And I've got a problem that affect the whole affair: I never study computer programming, so I don't understand very much what you say... Can you all explain it simply? Thank you.
## Post #37
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-08-15T12:46:14+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

I've updated the tool in my post as of August, 13th with uv support:



PlanetHotWheels_uv.jpg (195.9 KiB) Viewed 76 times


to do: scaling (maybe some day)

(from carena: 4pl_thitech.mxs, ok)
## Post #38
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-15T13:33:10+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

> Reply from shakotay2
>
> I've updated the tool in my post as of August, 13th with uv support:
PlanetHotWheels_uv.jpg
to do: scaling (maybe some day)

(from carena: 4pl_thitech.mxs, ok)

It only works with Blender?

Ok, I open it with 3ds Max 2010 but with 2018 version it can't open...
## Post #39
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2018-08-15T17:33:52+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

> Reply from shakotay2
>
> I've updated the tool in my post as of August, 13th with uv support:

If I run the Make_obj-notP-PHotW.exe it can't open the dll_makeh2o.dll.
## Post #40
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-08-15T17:44:41+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

> Reply from Karpati
>
> If I run the Make_obj-notP-PHotW.exe it can't open the dll_makeh2o.dll.My bad. I've updated the zip in the post as of August, 13th, thanks!

EXPORTB2 supported now. Advantage of these models is: you don't have to do any scalings. 



Fordf150-mxs-B2.jpg (174.52 KiB) Viewed 71 times


@Fiammanera628: yeah, your solution with the folder is cool! (But I've added the missing dlls to the zip now.)
## Post #41
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-15T17:52:13+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

> @Fiammanera628: yeah, your solution with the folder is cool! (But I've added the missing dlls to the zip now.)

Oh, Thank you! Shakotay2, I've got a question for you: is possible to open the "ENGINE1EXPORTFP" with Model Researcher by Lazov? I don't know, with a script, maybe...
## Post #42
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-08-15T18:13:01+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

My solutions generally are coded in 'C'; I didn't use python scripting with MR. So I don't know whether it's possible.
This is simply a matter of time (and I'm not a friend of python  ).

I generally don't waste time with other approaches if there's an existing working solution.

edit: well, I finally realized what the problem was with the mirrored writing on the texture.

It's senseless to mirror, rotate, whatever the uvs - you simply have to scale chassis y with -1.
(uvs scaled down by 16.)



63corvette-Text.jpg (67.68 KiB) Viewed 63 times
## Post #43
- Username: N/A
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Sep 17, 2014 11:15 pm
- Post datetime: 2018-08-15T19:09:53+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

Python has the struct module when it comes to working with binary stuff. (Which I'm heavily relying on for reading HW:Racing Circuit files atm)
But I'm not familiar with MR's api.
Though I'm aware Python does have C-language bindings. (Which is what Noesis uses I think)

Python variable types aren't strictly enforced like it is in C or Java. (which is both a blessing if you're lazy, but a curse in terms of type checking and memory efficiency)
## Post #44
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-15T19:25:23+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

> Reply from shakotay2
>
> edit: well, I finally realized what the problem was with the mirrored writing on the texture.

It's senseless to mirror, rotate, whatever the uvs - you simply have to scale chassis y with -1.
(uvs scaled down by 16.)
63corvette-Text.jpg

Oh, really? Until now, I was reflecting the object with Symmetry  

for the Script:

Oh. And there is a method for convert from a C script to a Py language? (noob question, I repeat, I never study computer programming   )
## Post #45
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-18T20:01:44+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

Any news about this "3DSMAX_ENGINE1EXPORTFP 200"?
## Post #46
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-08-19T06:21:32+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

> Reply from Fiammanera628
>
> for the Script:

Oh. And there is a method for convert from a C script to a Py language? (noob question, I repeat, I never study computer programming   )Those methods don't produce "ready to use" scripts, afaik. (Besides "C2py" is nothing I deal with.)

> Reply from Fiammanera628
>
> Any news about this "3DSMAX_ENGINE1EXPORTFP 200"?Speaking of what? The scaling?
I had problems to get suiting values from the ASCII snippets in the mxs file:

```
	*NODE_ID "11431620"
	*NODE_PARENTID "11433b00"
	*NODE_NAME "mdlCRSplitwindowvette_bk"
	*NODE_PARENT "splitwindowvette_regpoints"
	*NODE_USERPROPERTIES {
		castshadows
	}
	*NODE_TM {
		*NODE_NAME "mdlCRSplitwindowvette_bk"
		*INHERIT_POS 0 0 0
		*INHERIT_ROT 0 0 0
		*INHERIT_SCL 0 0 0
		*TM_ROW0 -0.87412530	-0.00000012	-0.00000001
		*TM_ROW1 -0.00000001	0.00000010	0.87412578
		*TM_ROW2 -0.00000012	0.87412578	-0.00000021
		*TM_ROW3 0.00131213	1.01437813	0.21495363
		*TM_POS 0.00131213	1.01437813	0.21495363
		*TM_ROTAXIS 0.00000005	-0.70710683	-0.70710671
		*TM_ROTANGLE 3.14159274
		*TM_SCALE 0.87412530	0.87412584	0.87412572
		*TM_SCALEAXIS 1.00000000	0.00000001	0.00000001
		*TM_SCALEAXISANG 0.78539819
	}
	*MESH {
```
There's only 13 (instead of 18) *GEOMOBJECT" and I can't identify objects like "mdlCRSplitwindowvette_bk" (might be possible by looking at the vertex counts); 
also TM_SCALEAXIS values are zero sometimes.

You might wait for Karpati; maybe he has more luck with fixing the scaling.
## Post #47
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-19T09:00:11+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

Ok, then I'll wait for Karpati. We hope well
## Post #48
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-20T16:41:59+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

HUGE GOOD NEWS!!!!

I'VE DO IT!!! IS HERE!! the correct size 63corvette!!



Eh... I became crazy for that
## Post #49
- Username: Bumper3241
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 15, 2018 3:30 pm
- Post datetime: 2019-05-28T14:57:30+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

> Reply from shakotay2 ↑Wed Aug 15, 2018 8:46 pm at Wed Aug 15, 2018 8:46 pm
>
> 
I've updated the tool in my post as of August, 13th with uv support:
PlanetHotWheels_uv.jpg
to do: scaling (maybe some day)

(from carena: 4pl_thitech.mxs, ok)

So, how do you scale these ones properly? So far, the ones that need it are:

'63 Corvette
27/7
Ballistic
Corvette Stingray
Dodge Charger
Deora 2
Muscle Tone
Vulture
Power Pipes
Power Rocket
Quarter Mile Coupe
Road Rocket
Side Draft
Silver Bullet
Switchback
Chrysler Thunderbolt
Wild Thing
and Sweet 16 just plain doesn't work, no matter what I do.

I hope you're able to help me with this, thank you.
## Post #50
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-05-28T17:53:44+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

> Reply from Bumper3241 ↑Tue May 28, 2019 10:57 pm at Tue May 28, 2019 10:57 pm
>
> So, how do you scale these ones properly?
You'll need to ask Fiammanera628:

> Reply from Fiammanera628 ↑Tue Aug 21, 2018 12:41 am at Tue Aug 21, 2018 12:41 am
>
> 
(I don't have the time to work on it.)
## Post #51
- Username: Bumper3241
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Oct 15, 2018 3:30 pm
- Post datetime: 2019-05-28T18:14:49+00:00
- Post Title: Re: Planet Hot Wheels .MXS files

> Reply from Fiammanera628 ↑Tue Aug 21, 2018 12:41 am at Tue Aug 21, 2018 12:41 am
>
> 
HUGE GOOD NEWS!!!!

I'VE DO IT!!! IS HERE!! the correct size 63corvette!!



Eh... I became crazy for that

May I ask how you fixed the scaling? Or can you fix the cars I listed in my post above?
