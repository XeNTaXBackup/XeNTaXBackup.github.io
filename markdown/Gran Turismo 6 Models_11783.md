## Post #1
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-08-13T19:14:32+00:00
- Post Title: Gran Turismo 6 Models

Well,hello there  

I've been reading posts here for a year,but only now I have registered my account  

But anyway,I want you guys to take a look at this!
We now can extract GT6.VOL file from Gran Turismo 6

It contains a lot of important things,Like Cars and tracks,so it would be absolutely awesome and amazing,if you can convert them to usual 3D formats!   

Since I don't know,how to decrypt data,I leave a link with some examples.  
This archive contains 1 "Premium" (highly detailed) car,one "Standart" car and a racetrack
Also a screenshot of all the extracted folders with files is attached...

I hope you can do something with theese files!  

Examples:
[http://www.mediafire.com/download/82dz6 ... d8/GT6.rar](http://www.mediafire.com/download/82dz697zdj7i1d8/GT6.rar)
## Post #2
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-13T21:09:26+00:00
- Post Title: Gran Turismo 6 Models

> Reply from Ferrari formula 1
>
> We now can extract GT6.VOL file from Gran Turismo 6
How??
## Post #3
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-08-14T08:14:20+00:00
- Post Title: Gran Turismo 6 Models

> Reply from Chipicao
>
> Ferrari formula 1 wrote:We now can extract GT6.VOL file from Gran Turismo 6
How??

I found a decrypting programm called GTtool here (post #15) 
[http://www.ps3hax.net/showthread.php?t= ... post782240](http://www.ps3hax.net/showthread.php?t=36878&page=2&p=782240&viewfull=1#post782240)
I couldn't really beleive that it works,but it worked on my friend's 32 bit PC!  
*Just all my PC's are 64 bit*

I'm happy you are here,Chipicao!
## Post #4
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-14T08:38:45+00:00
- Post Title: Gran Turismo 6 Models

...also first time here, thanks to forums 25th anny , as Ferrari said, it is possible to extract whole game disk now, in fact, I extracted all on my 64bit, win 8.1 with the tool.

But sad thing is, that I have no clue what to do with specific files. From names one can tell what is what, for cars i presume that those are archives that contain mesh and textures, for tracks, there are bunch of files with different extensions, same here, one can tell what they are for thanks to extensions.

We'd apprechiate if someone who knows what he's doing would look into this.

Thanks in advace guys... 

Cheers...

Sent from my HTC M7
## Post #5
- Username: flatz
- Rank: advanced
- Number of posts: 58
- Joined date: Mon Nov 21, 2011 2:31 pm
- Post datetime: 2014-08-14T17:54:11+00:00
- Post Title: Gran Turismo 6 Models

I'm an author of gttool. Yes, now you can extract GT5/GT6 archives.
Archive's format is a bit complex, they use a custom crypto algorithm and B-trees for file table entries, names, etc. Also they use encryption for some files like sqlite databases, movies, etc. I can decrypt them, however there are some files (like movies and maybe some other files) with keys stored inside the compiled script. Also I've reversed the cache system with such weird naming schema.
I'm not at home at the moment but I'll release my source code tomorrow.
Also I have a little progress on meshes but their format is a complex too and requires some time which I don't have. That's why I've discontinued a work on GT. Maybe we will find some other guys here.
## Post #6
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-08-14T18:07:45+00:00
- Post Title: Gran Turismo 6 Models

That would be amazing,because i can rip cars only from Gran Turismo 2 and Gran Turismo PSP  

You did great work by decrypting an archive!
## Post #7
- Username: flatz
- Rank: advanced
- Number of posts: 58
- Joined date: Mon Nov 21, 2011 2:31 pm
- Post datetime: 2014-08-15T14:25:43+00:00
- Post Title: Gran Turismo 6 Models

Unfortunately I can't attach it here, so here is the source code and binary: [http://zenhax.com/viewtopic.php?f=9&t=76](http://zenhax.com/viewtopic.php?f=9&t=76)
## Post #8
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-15T15:53:03+00:00
- Post Title: Gran Turismo 6 Models

> Reply from flatz
>
> Unfortunately I can't attach it here, so here is the source code and binary: http://zenhax.com/viewtopic.php?f=9&t=76

...thanks man for your effort!

Cheers...
## Post #9
- Username: ForteMaster
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-08-15T18:13:34+00:00
- Post Title: Gran Turismo 6 Models

What do you mean, you cannot attach it?


 gttool_src_bin.7z
(178.39 KiB) Downloaded 437 times
## Post #10
- Username: flatz
- Rank: advanced
- Number of posts: 58
- Joined date: Mon Nov 21, 2011 2:31 pm
- Post datetime: 2014-08-15T18:42:19+00:00
- Post Title: Gran Turismo 6 Models

> Reply from Mr.Mouse
>
> What do you mean, you cannot attach it?
gttool_src_bin.7z
There are two keys inside. Is it legal to publish them?
## Post #11
- Username: flatz
- Rank: advanced
- Number of posts: 58
- Joined date: Mon Nov 21, 2011 2:31 pm
- Post datetime: 2014-08-15T20:14:07+00:00
- Post Title: Gran Turismo 6 Models

To decrypt some encrypted files (like databases from GT5) you can use this snippet:

```
	uint32_t data_size = -1;
	read_file("system.db", &data, &data_size);
	crypt_segment(data, data_size, 0);
	write_file("system.db.out", data, data_size);

```

You need to place it just before volume.close(); at main.cpp. Don't forget to include file.h at the top.
## Post #12
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-16T00:59:01+00:00
- Post Title: Gran Turismo 6 Models

So far, I can see vertices and faces inside the body_s files.

[](http://i.gyazo.com/ca9a103d39363a407970db424549ea67.png) [](http://i.gyazo.com/d77d903cf7ddd5955dc3d4d7bb5db324.png) [](http://i.gyazo.com/708d7ba7946bee9c33a90fb7ea8bec61.png) [](http://i.gyazo.com/da1b6a7d32688b5049d159ffb8e791a9.png) [](http://i.gyazo.com/b2c65d2ab381f26bfb9010ddbb721f81.png) [](http://i.gyazo.com/f356356f7bfeafd7bb11280461a6257f.png)

I'm not fully parsing the mdl3 info, more of a raw attempt at model extraction.  Still looking for UV data.
## Post #13
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-08-16T03:36:53+00:00
- Post Title: Gran Turismo 6 Models

> Reply from EcheloCross
>
> So far, I can see vertices and faces inside the body_s files.



I'm not fully parsing the mdl3 info, more of a raw attempt at model extraction.  Still looking for UV data.

My God this is amazing!  

I guess there are some meshes like glass,bosy and others?  

You rock!
## Post #14
- Username: flatz
- Rank: advanced
- Number of posts: 58
- Joined date: Mon Nov 21, 2011 2:31 pm
- Post datetime: 2014-08-16T06:54:44+00:00
- Post Title: Gran Turismo 6 Models

> Reply from EcheloCross
>
> So far, I can see vertices and faces inside the body_s files.



I'm not fully parsing the mdl3 info, more of a raw attempt at model extraction.  Still looking for UV data.
Well done! There are also shaders parameters, bone hierarchy, materials and many other data, it can be a pain to extract them all. 
By the way here is a decrypted system.db from GT5: [http://rghost.ru/57494655](http://rghost.ru/57494655)
It is a SQLite database inside PDIPREAL container, you need to remove the header of 0x200 bytes and cut everything after 0x188200 because it is "decrypted" zeroes (an encrypted file have a padding of all zeroes after this offset).
## Post #15
- Username: PseT
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Jun 15, 2014 7:57 pm
- Post datetime: 2014-08-16T09:56:25+00:00
- Post Title: Gran Turismo 6 Models

Hello, 

Question probably stupid, but how to read the file is in ISO GT6?
Is it possible to extract the circuits? Red Bull Ring and Mount Panorama interests me
## Post #16
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-16T11:00:23+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from EcheloCross
>
> So far, I can see vertices and faces inside the body_s files.



I'm not fully parsing the mdl3 info, more of a raw attempt at model extraction.  Still looking for UV data.

...man, you are awesome! Did you have any progress with tracks maybe?

Cheers...
## Post #17
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-16T11:48:31+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from PseT
>
> Hello, 

Question probably stupid, but how to read the file is in ISO GT6?
Is it possible to extract the circuits? Red Bull Ring and Mount Panorama interests me

...download winrar and total commander, it will be much easier for you to work with files. Regarding extraction, as you can see in one of the previous posts, EcheloCross managed to get his hands on mesh of the car, not complete one but it is big progress. We'll need to wait a bit...

Cheers...
## Post #18
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-16T21:58:36+00:00
- Post Title: Re: Gran Turismo 6 Models

@EcheloCross, can you tell us secret how you did all that? I'd like to look into those 3d models 

Cheers...
## Post #19
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-16T22:20:56+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from rex1825
>
> @EcheloCross, can you tell us secret how you did all that? I'd like to look into those 3d models 

Cheers...

use offzip -1 -a -z -15 body_s outputFolder 0

this will create 1 file from the body_s that is merged and decompressed

inside the new file, you'll see vertices as 32bit big endian floats in a 12 byte stride, and faces as 16bit big endian unsigned shorts in a stride of 6

the addresses will be different in each decompressed body_s, look for 0x00, 0x00, 0x00, 0x01, 0x00, 0x02 for the faces data, the vertices will be directly before them for the current mesh object
## Post #20
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-16T22:48:45+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from EcheloCross
>
> rex1825 wrote:@EcheloCross, can you tell us secret how you did all that? I'd like to look into those 3d models 

Cheers...

use offzip -1 -a -z -15 body_s outputFolder 0

this will create 1 file from the body_s that is merged and decompressed

inside the new file, you'll see vertices as 32bit big endian floats in a 12 byte stride, and faces as 16bit big endian unsigned shorts in a stride of 6

the addresses will be different in each decompressed body_s, look for 0x00, 0x00, 0x00, 0x01, 0x00, 0x02 for the faces data, the vertices will be directly before them for the current mesh object

...I presume same goes for courses also?

Cheers...
## Post #21
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-16T22:58:37+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from rex1825
>
> 

...I presume same goes for courses also?

Cheers...

just about the same, the rwy files have a different setup than the body files
the track pic is from crs/c136.rwy, it contains 2 vertex blocks that outline the track roadway, and a faces block that I think goes with the 2nd vertex block, but remains to be seen
its corresponding pacb (crs/c136x) contains multiple mdl3 files that work almost the same way as the info in the body_s files, the vertices have a larger than 12 byte stride though (16 or 28 I've seen so far).  

I'm still going through trying to figure out what is what.
## Post #22
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-16T23:19:25+00:00
- Post Title: Re: Gran Turismo 6 Models

Thanks for your effort man...

Cheers...
## Post #23
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-17T00:26:31+00:00
- Post Title: Re: Gran Turismo 6 Models

...BTW, it is same for GT5 and GT6 right?
## Post #24
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-17T00:41:00+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from EcheloCross
>
> rex1825 wrote:@EcheloCross, can you tell us secret how you did all that? I'd like to look into those 3d models 

Cheers...

use offzip -1 -a -z -15 body_s outputFolder 0

this will create 1 file from the body_s that is merged and decompressed

inside the new file, you'll see vertices as 32bit big endian floats in a 12 byte stride, and faces as 16bit big endian unsigned shorts in a stride of 6

the addresses will be different in each decompressed body_s, look for 0x00, 0x00, 0x00, 0x01, 0x00, 0x02 for the faces data, the vertices will be directly before them for the current mesh object

...OK, sorry maybe this is a bit too much now, I've got from body_s file a 00000000.neo file and inside when looking trhough HxD I found only one 0x00, 0x00, 0x00, 0x01, 0x00, 0x02. So, before that are vertexes and after it's mesh, but how does a 3D program recognize this (like 3DS Max)? If it's too complicated don't bother explaining at all. 

Cheers...
## Post #25
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-08-17T11:59:01+00:00
- Post Title: Re: Gran Turismo 6 Models

That's the best that could happen after Forza models extractor.

Sorry than I can't help I'm not programmer, but thanks a lot for the hard work, time and effort.
## Post #26
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-17T15:53:53+00:00
- Post Title: Re: Gran Turismo 6 Models

idk about gt5, never touched it.

> Reply from rex1825
>
> 
...OK, sorry maybe this is a bit too much now, I've got from body_s file a 00000000.neo file and inside when looking trhough HxD I found only one 0x00, 0x00, 0x00, 0x01, 0x00, 0x02. So, before that are vertexes and after it's mesh, but how does a 3D program recognize this (like 3DS Max)? If it's too complicated don't bother explaining at all.

You need to parse the binary data and write it to a format that a 3d program can read.  

I use c# primarily for binary parsing, but it can be done in any language.
I suggest wavefront obj if you're new to 3d formats, as its all text.

(There is a tool somewhere on this forum that will probably to it) [viewtopic.php?f=29&t=10894](http://forum.xentax.com/viewtopic.php?f=29&t=10894)
I've never used it, so don't ask.
## Post #27
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-17T16:22:51+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from EcheloCross
>
> idk about gt5, never touched it.
rex1825 wrote:
...OK, sorry maybe this is a bit too much now, I've got from body_s file a 00000000.neo file and inside when looking trhough HxD I found only one 0x00, 0x00, 0x00, 0x01, 0x00, 0x02. So, before that are vertexes and after it's mesh, but how does a 3D program recognize this (like 3DS Max)? If it's too complicated don't bother explaining at all. 


You need to parse the binary data and write it to a format that a 3d program can read.  

I use c# primarily for binary parsing, but it can be done in any language.
I suggest wavefront obj if you're new to 3d formats, as its all text.

(There is a tool somewhere on this forum that will probably to it) viewtopic.php?f=29&t=10894
I've never used it, so don't ask.

I work in 3D for long time, but it is kinda new all this with hidden data 

It is not so easy as it seems, but thanks anyway...

Thanks m8
## Post #28
- Username: nosfornos
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Dec 21, 2011 4:16 pm
- Post datetime: 2014-08-18T04:59:52+00:00
- Post Title: Re: Gran Turismo 6 Models

No contents
## Post #29
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-19T02:19:41+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from EcheloCross
>
> So far, I can see vertices and faces inside the body_s files.

     

I'm not fully parsing the mdl3 info, more of a raw attempt at model extraction.  Still looking for UV data.

...nice progress
## Post #30
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-19T02:33:58+00:00
- Post Title: Re: Gran Turismo 6 Models

BTW, are all meshes mirrored?

Cheers...
## Post #31
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-19T13:37:34+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from rex1825
>
> BTW, are all meshes mirrored?

Cheers...

No, the full mesh is stored.  Cars may look symmetrical, but they're not.

Some do contain rear view mirrors meshes though.
## Post #32
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-19T13:58:52+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from EcheloCross
>
> rex1825 wrote:BTW, are all meshes mirrored?

Cheers...

No, the full mesh is stored.  Cars may look symmetrical, but they're not.

Some do contain rear view mirrors meshes though.

...well on those pics I see all mirrored, that's why I asked, the track that you extracted is mirrored, and also the fiat 500essesse is mirrored... so I wonder
## Post #33
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-19T14:38:22+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from EcheloCross
>
> rex1825 wrote:BTW, are all meshes mirrored?

Cheers...

No, the full mesh is stored.  Cars may look symmetrical, but they're not.

Some do contain rear view mirrors meshes though.
He means vertex positions. You need to negate x
## Post #34
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-19T15:16:55+00:00
- Post Title: Re: Gran Turismo 6 Models

Yeah, makes sense now.  I knew I had to -vX, just wasn't doing it.
## Post #35
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-19T16:17:21+00:00
- Post Title: Re: Gran Turismo 6 Models

...thanks guys for progress, keep the good work! 

Cheers...
## Post #36
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-20T00:50:17+00:00
- Post Title: Re: Gran Turismo 6 Models

Working on it myself...

[](http://www.imagebam.com/image/c26b1c346112402) [](http://www.imagebam.com/image/75c186346111775) 

I made a small tool to convert textures (only those already extracted, for example .img): [TXS2DDS](http://www.mediafire.com/download/6xxgylxgdvp1ji0/TXS2DDS.zip)
Model textures are in \crs\*.texstream. I was able to extract them with offzip but it seems their headers are stored someplace else, possibly in model files.

There seems to be more geometry data in \crs\*.shapestream files, also extractable with offzip.
## Post #37
- Username: flatz
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-08-20T03:51:40+00:00
- Post Title: Re: Gran Turismo 6 Models

i have 2 beta scripts that might help with the format.
[gt6.7z](https://xentaxbackup.github.io/file/7682_gt6.7z)
## Post #38
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-20T10:00:50+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from chrrox
>
> i have 2 beta scripts that might help with the format.

It is maybe dumb question, but how do you load this or use it?

Cheers...
## Post #39
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-20T15:03:41+00:00
- Post Title: Re: Gran Turismo 6 Models

...wondering how many LODs do cars and tracks have, I presume that tracks have only one, maybe two lods, but cars? I know that those premium cars have like 200k polys, did anyone find them and opened? Just wondering how detailed cars in fact are.

Cheers...
## Post #40
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-20T15:20:33+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from rex1825
>
> ...wondering how many LODs do cars and tracks have, I presume that tracks have only one, maybe two lods, but cars? I know that those premium cars have like 200k polys, did anyone find them and opened? Just wondering how detailed cars in fact are.

Cheers...

The Aston Marton in my pic is from its hd/body_s
## Post #41
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-20T15:54:23+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from EcheloCross
>
> rex1825 wrote:...wondering how many LODs do cars and tracks have, I presume that tracks have only one, maybe two lods, but cars? I know that those premium cars have like 200k polys, did anyone find them and opened? Just wondering how detailed cars in fact are.

Cheers...

The Aston Marton in my pic is from its hd/body_s

...yeah but premium vehicles have like 10-15MB file size I think, at least that's what I saw till now

Edit: Srry, whole folder is about that size
## Post #42
- Username: PseT
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Jun 15, 2014 7:57 pm
- Post datetime: 2014-08-20T17:53:27+00:00
- Post Title: Re: Gran Turismo 6 Models

How to decompress a GT6 iso (gt.vol) file in windows folder?

Thanks
## Post #43
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-20T18:25:14+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from PseT
>
> How to decompress a GT6 iso (gt.vol) file in windows folder?

Thanks

...use the tool from the link in 3rd post.

Cheers...
## Post #44
- Username: PseT
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Jun 15, 2014 7:57 pm
- Post datetime: 2014-08-20T19:17:37+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from rex1825
>
> PseT wrote:How to decompress a GT6 iso (gt.vol) file in windows folder?

Thanks

...use the tool from the link in 3rd post.

Cheers...

Ok, but Gttool does not work on a 64bit OS !!

thanks
## Post #45
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-20T19:30:14+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from PseT
>
> rex1825 wrote:PseT wrote:How to decompress a GT6 iso (gt.vol) file in windows folder?

Thanks

...use the tool from the link in 3rd post.

Cheers...

Ok, but Gttool does not work on a 64bit OS !!

thanks

...it worked on my PC, there is no other tool except this one!
## Post #46
- Username: flatz
- Rank: advanced
- Number of posts: 58
- Joined date: Mon Nov 21, 2011 2:31 pm
- Post datetime: 2014-08-20T19:41:56+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from PseT
>
> rex1825 wrote:PseT wrote:How to decompress a GT6 iso (gt.vol) file in windows folder?

Thanks

...use the tool from the link in 3rd post.

Cheers...

Ok, but Gttool does not work on a 64bit OS !!

thanks
It works fine and I've wrote it on 64-bit OS.
## Post #47
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-20T19:57:22+00:00
- Post Title: Re: Gran Turismo 6 Models

I've got the _s file table, mesh info table, and fvf table parsed now.  Getting all meshes from body_s in 1 swoop.
## Post #48
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-20T20:26:24+00:00
- Post Title: Re: Gran Turismo 6 Models

...is there any table that states what is what car, since unpacked gt.vol file only gives names like 0000,0001,0002... in folders with similar names. And tracks as C001, T001 etc?

Cheers...
## Post #49
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-20T23:48:06+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from EcheloCross
>
> I've got the _s file table, mesh info table, and fvf table parsed now.  Getting all meshes from body_s in 1 swoop.

BTW, if you guys are really into it, this is how PD showed that mesh looks like in their premium high lod model:


I am sure that it is hidden inside of those files 

Cheers...
## Post #50
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-21T01:59:30+00:00
- Post Title: Re: Gran Turismo 6 Models

^-- that is concept art, or used in the pre-rendered (BINK video)/(*.pam).

The pics below are from various "hq" models:
## Post #51
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-21T04:41:02+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from EcheloCross
>
> ^-- that is concept art, or used in the pre-rendered (BINK video)/(*.pam).
No, premium models are indeed very hi-poly. Google GT6 screenshots and you'll see, particularly the interior.
## Post #52
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-21T10:18:15+00:00
- Post Title: Re: Gran Turismo 6 Models

...yeap, premium models have more lods that standard models, since they are used for photo mode and when in photo mode models just shine.

I don't recall how good were track meshes from previous GT games, are these any improved?

Cheers...
## Post #53
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-21T10:21:43+00:00
- Post Title: Re: Gran Turismo 6 Models

Here is render from ingame of Lamborghini Miura, now with that low mesh this is simply not possible. I know they made a lot of improvements to the engine itself, but mesh is mesh.

[http://wallpaperswide.com/download/gran ... 0x2160.jpg](http://wallpaperswide.com/download/gran_turismo_5_lamborghini_miura-wallpaper-3840x2160.jpg)

Here is another one:



Edit: lol how to reduce size of the pic shown on forum?
Cheers...
## Post #54
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-21T10:46:06+00:00
- Post Title: Re: Gran Turismo 6 Models

^ And btw he means in-game render (photo mode).

I know they bragged about adaptive tessellation, but I don't think they could get those results.
## Post #55
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-21T10:49:54+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from Chipicao
>
> ^ And btw he means in-game render (photo mode).

I know they bragged about adaptive tessellation, but I don't think they could get those results.

After all it is a PS3, yeah ingame reder, but also when you move camera around in so called photo mode, you can see how detailed car mesh is... So it does render in realtime, wich means that is should have or some really complex algorithm, wich I doubt since PS3 hardware isn't so strong or it has really better meshes somewhere hidden.

BTW what is poly count of those meshes you guys extracted, because PD clamed that their premium car models have like 200k polys

Cheers...
## Post #56
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-21T13:42:11+00:00
- Post Title: Re: Gran Turismo 6 Models

I don't know where they are stored then.  If you guys find something you think is a premium model, let me know.

How do I get to that screen in-game?  I can log what files are accessed in the debugger.
## Post #57
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-21T13:49:36+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from EcheloCross
>
> I don't know where they are stored then.  If you guys find something you think is a premium model, let me know.

How do I get to that screen in-game?  I can log what files are accessed in the debugger.

...well on main menu in GT6 on the most right there is a photo mode, or how is it called. You choose one of the premium cars, and go there to make photos.
Or while watching replay there should be also a photo mode, where you can move camera around and make pictures with high lod car mesh.

In GT5 I think it was accessible from main menu also, it was like a camera icon or something...

Cheers...
## Post #58
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-21T14:12:12+00:00
- Post Title: Re: Gran Turismo 6 Models

```
000000000000596b, /5Q/GM, projects/gt6/photo/photo.adc
0000000000005a1c, /5R/D0, scripts/gt6/util/PhotoModeUtil.adc
0000000000005967, /5J/K0, projects/gt6/photo/gpb/PhotoProject.gpb
00000000000000a3, /K/DN, sound_gt/se/gt5photo.sgd
0000000000005779, /5S/O2, scene/script/s0113
0000000000003c8b, /5D/CH, character/bg014
0000000000000069, /K/BU, character/cc.bin
00000000000020d7, /5K/47, car/0062/0003/info
00000000000020d4, /54/NX, car/0062/0003/hq/body
0000000000002b02, /58/BK, tire/hq/m0004
00000000000020d5, /5W/M9, car/0062/0003/hq/body_s
0000000000002b02, /58/BK, tire/hq/m0004
00000000000020d6, /55/BS, car/0062/0003/hq/wheel
00000000000027e0, /5W/77, car/decken/a.00
0000000000005746, /58/P2, scene/misc/lp0005
000000000000574e, /5H/5Q, scene/misc/se0025
0000000000005778, /5W/BG, scene/script/s0112
000000000000574a, /5K/PP, scene/misc/rw0006
0000000000005777, /5B/8Z, scene/script/s0111
0000000000005875, /5O/J3, motion/m0051
0000000000005876, /5D/96, motion/m0052
0000000000005877, /5H/PV, motion/m0053
0000000000005878, /5Q/3J, motion/m0054
00000000000057f8, /5S/XJ, scene/script/s0262
0000000000003de9, /5J/KW, character/ma07
0000000000003e34, /5A/JT, character/mf07
0000000000005870, /56/9U, motion/m0041
000000000000577a, /5K/C9, scene/script/s0114
000000000000577b, /59/JX, scene/script/s0115
000000000000577c, /5D/QU, scene/script/s0116
000000000000577d, /5V/6P, scene/script/s0117
000000000000577e, /56/TY, scene/script/s0118
000000000000577f, /57/7I, scene/script/s0119
0000000000005780, /5M/AR, scene/script/s0120
0000000000005781, /5Q/SM, scene/script/s0121
0000000000005782, /5R/CB, scene/script/s0122
0000000000005783, /5E/HC, scene/script/s0123
0000000000005784, /5C/QZ, scene/script/s0124
0000000000005785, /5I/KN, scene/script/s0125
0000000000005786, /5B/85, scene/script/s0126
0000000000005787, /58/W4, scene/script/s0127
0000000000005788, /5S/OI, scene/script/s0128
0000000000005787, /58/W4, scene/script/s0127
0000000000005786, /5B/85, scene/script/s0126
0000000000005785, /5I/KN, scene/script/s0125
0000000000005784, /5C/QZ, scene/script/s0124
0000000000005783, /5E/HC, scene/script/s0123
0000000000005782, /5R/CB, scene/script/s0122
0000000000005781, /5Q/SM, scene/script/s0121
0000000000005780, /5M/AR, scene/script/s0120
000000000000577f, /57/7I, scene/script/s0119
000000000000577e, /56/TY, scene/script/s0118
000000000000577d, /5V/6P, scene/script/s0117
000000000000577c, /5D/QU, scene/script/s0116
000000000000577b, /59/JX, scene/script/s0115
000000000000577a, /5K/C9, scene/script/s0114
000000000000577b, /59/JX, scene/script/s0115
000000000000577a, /5K/C9, scene/script/s0114
0000000000005856, /5D/D7, scene/script/s0375
0000000000005856, /5D/D7, scene/script/s0375
0000000000005856, /5D/D7, scene/script/s0375
000000000000593b, /5M/QT, projects/gt6/garage/gpb/GarageProject.gpb
0000000000005966, /5O/VX, projects/gt6/photo/gpb/PhotoObjectSettingRoot.gpb
000000000000593a, /5U/GA, projects/gt6/garage/gpb/CarSelectPopup.gpb
0000000000000053, /K/CF, projects/gt6/garage/gpb/CarOrderPopup.gpb
00000000000026d6, /5V/ES, car/0228/0008/info
00000000000026d3, /5W/0U, car/0228/0008/hq/body
00000000000027e0, /5W/77, car/decken/a.00
00000000000026d4, /57/KR, car/0228/0008/hq/body_s
00000000000026d5, /56/JE, car/0228/0008/hq/wheel
0000000000002b06, /5E/2J, tire/hq/m0252
0000000000002b06, /5E/2J, tire/hq/m0252
0000000000005802, /59/H5, scene/script/s0275
000000000000577b, /59/JX, scene/script/s0115
000000000000577a, /5K/C9, scene/script/s0114
0000000000005856, /5D/D7, scene/script/s0375
000000000000593b, /5M/QT, projects/gt6/garage/gpb/GarageProject.gpb
0000000000005966, /5O/VX, projects/gt6/photo/gpb/PhotoObjectSettingRoot.gpb
000000000000593a, /5U/GA, projects/gt6/garage/gpb/CarSelectPopup.gpb
0000000000002709, /5U/0I, car/0228/0014/info
0000000000002706, /57/JK, car/0228/0014/hq/body
000000000000270b, /5P/MB, car/0228/0014/meter
0000000000002707, /56/0D, car/0228/0014/hq/body_s
0000000000002b24, /5Q/UK, tire/hq/m0022
0000000000002b24, /5Q/UK, tire/hq/m0022
0000000000002708, /5M/TM, car/0228/0014/hq/wheel
00000000000027e0, /5W/77, car/decken/a.00
0000000000005802, /59/H5, scene/script/s0275
000000000000593a, /5U/GA, projects/gt6/garage/gpb/CarSelectPopup.gpb
0000000000005856, /5D/D7, scene/script/s0375

```


I only see hq/body* being accessed in the photo mode.  Any car in particular I should use?
## Post #59
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-21T14:19:06+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from EcheloCross
>
> 
I only see hq/body* being accessed in the photo mode.  Any car in particular I should use?

...cheapest Premium car that you can buy, like that Fiat Abarth 500 essesse... I think it is cheap

Cheers...
## Post #60
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-21T14:27:02+00:00
- Post Title: Re: Gran Turismo 6 Models

...BTW, do you know what folder and what file in that folder is what car?

Cheers...
## Post #61
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-21T14:28:03+00:00
- Post Title: Re: Gran Turismo 6 Models

Abarth 500 '09 in photo mode

```
00000000000024a1, /5O/Z5, car/0140/0001/info
000000000000249e, /5E/3P, car/0140/0001/hq/body
000000000000249f, /5P/JU, car/0140/0001/hq/body_s
00000000000024a3, /5H/ZT, car/0140/0001/meter
0000000000002b02, /58/BK, tire/hq/m0004
0000000000002b02, /58/BK, tire/hq/m0004
00000000000024a0, /5J/V1, car/0140/0001/hq/wheel
00000000000027e0, /5W/77, car/decken/a.00
0000000000005803, /5K/27, scene/script/s0274
0000000000005856, /5D/D7, scene/script/s0375

```
## Post #62
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-21T14:34:27+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from EcheloCross
>
> Abarth 500 '09 in photo mode

...so this is it, it seems that it does some software miracles hm?

Thanks for your time m8, cheers...
## Post #63
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-21T14:38:56+00:00
- Post Title: Re: Gran Turismo 6 Models

this is from car/0140/0001/interior, but I didn't see it getting loaded in the debugger
## Post #64
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-21T14:45:50+00:00
- Post Title: Re: Gran Turismo 6 Models

...that's strange. What should be car/decken/a.00?
And also does car/0140/0001/info has something to do with mesh?
## Post #65
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-21T15:18:49+00:00
- Post Title: Re: Gran Turismo 6 Models

Not much data in the "info" file


There is a lot of data in the body_s that isn't being parsed yet.  Maybe they put them in that data.
It looks like a 48bit stride where I'm not parsing data.
## Post #66
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-21T15:28:43+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from rex1825
>
> ...that's strange. What should be car/decken/a.00?
All files in car/decken/ are 64x64 black textures with a strange alpha channel that maybe looks like an overlay effect or something.

Updated TXS2DDS tool to handle them: [http://www.mediafire.com/download/6xxgy ... XS2DDS.zip](http://www.mediafire.com/download/6xxgylxgdvp1ji0/TXS2DDS.zip)
## Post #67
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-21T15:34:16+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from EcheloCross
>
> Not much data in the "info" file


There is a lot of data in the body_s that isn't being parsed yet.  Maybe they put them in that data.
It looks like a 48bit stride where I'm not parsing data.
...maybe that's it then. That picture looks odd though, looks like Engine Management Diagram for engine torque/power curves @ different input values and rpm 


> Reply from Chipicao
>
> rex1825 wrote:...that's strange. What should be car/decken/a.00?
All files in car/decken/ are 64x64 black textures with a strange alpha channel that maybe looks like an overlay effect or something.

Updated TXS2DDS tool to handle them: http://www.mediafire.com/download/6xxgy ... XS2DDS.zip
...maybe those are made for different track and their HDR and reflection 


...thanks guys
## Post #68
- Username: PseT
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Jun 15, 2014 7:57 pm
- Post datetime: 2014-08-21T16:03:27+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from rex1825
>
> 

...it worked on my PC, there is no other tool except this one!

Strange gttool crash on my PC !
## Post #69
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-21T16:06:39+00:00
- Post Title: Re: Gran Turismo 6 Models

That pic is from the info file, not the body_s, the info files are too small to be detailed meshes.

Have a look at scene/script/s0375.

There is a line in there that may be doing the mesh smoothing

```

```


Also, the large concept art pic looks like quads, not tris.
## Post #70
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-08-21T16:24:31+00:00
- Post Title: Re: Gran Turismo 6 Models

So maybe it does actually do all that with tessellation. Interesting...
## Post #71
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-08-21T17:21:33+00:00
- Post Title: Re: Gran Turismo 6 Models

What we get now is definetly not the lod0

"standart" cars have only 1 lod, I am sure, because they were imported from ps2 era (gt3\gt4)

Premium cars have at least 3 levels ov detail.

I"ve played gt5 and gt6 a lot and I'm sure about what I"m talking about;)

So, lod 0 should be photomode lod, it has both interior and exterior in amazing detail (it is much more detailed, than forza 5, you can see the difference on screenshots)

Alfa romeo on screenshot from polyphony digital presentation is real lod0

Next one-track photomode(not in photomode location) you can see a little difference in detail

Next-ingame opponents on various distances, they should have some lod's

Tessellation doesn't plays any role here, because gt5 had the same detail without it 

Also, if you will look at the screenshots, of course you will see epic detail, where every little part, every button is highly dtailed  

They are just hidden somewhere, I am sure...


About textures with strange alpha layers- Polyphony digital always had them since gt3 for some reaso (mabye because of non-pc platform)
I saw it first time while ripping models from gtpsp, cars have strange alpha layers, and sometimes they don't have them at all.
Imagene yourself texture, which is a 100% blue cube, it have only one colour and nothing like any layers or words, but in the game it turns to sponsor stickers on cars somehow O_o

So, they always had strange formats, codes and powerful protection.

Highest lod should be hidden somewhere, I'm 100% sure
## Post #72
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-08-21T17:39:14+00:00
- Post Title: Re: Gran Turismo 6 Models

Sorry for double posting 
I'm on my mobile phone now, so I can't post images here,I will return to my pc at sunday 

Just take a look here-theese are screenshots from the official polyphony digital presentation of gt6
[http://www.google.com/search?q=gran+tur ... CAcQ_AUoAQ](http://www.google.com/search?q=gran+turismo+6+adaptive+tessellation&client=ms-android-samsung&site=webhp&source=lnms&tbm=isch&sa=X&ei=-yv2U-_JEZGP4gTj3YCIDA&ved=0CAcQ_AUoAQ)

I also want to mention, that adaptive tessellation works only on the one thing:when your rival is getting far away, the game may not change a lod of a car, but use a tesselation to make it look better.

I saw it 3 times, when lexus was leading in the race:rear window was jamming a little, just like if  I use a "reduce amoun of polygons" in cinema4d

All the details are must be hidden there
## Post #73
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-21T18:14:38+00:00
- Post Title: Re: Gran Turismo 6 Models

...this transitions between lods are more obvious on GT5, since GT6 has that dynamic transition with tesselation.

I hope you crack it guys 

Cheers...
## Post #74
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-21T22:06:51+00:00
- Post Title: Re: Gran Turismo 6 Models

Can someone extract me this track, need only mesh. It's from GT3 

[http://www.mediafire.com/download/630fx ... oute11.zip](http://www.mediafire.com/download/630fxd9jo8vil6m/SpecialStageRoute11.zip)

Thanks...
## Post #75
- Username: 0xqk
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Aug 12, 2014 8:38 am
- Post datetime: 2014-08-23T01:38:40+00:00
- Post Title: Re: Gran Turismo 6 Models

hi folks, for a first time post, I'd like to offer something - instead of asking any crap questions...

> Reply from rex1825
>
> is there any table that states what is what car

Yes, there is. I've got it down for quite some months now. But, I don't like to get anything of that knwoledge into the wild public.
So "rex1825" - feel lucky as you've won a "gimme 10" voucher.

Name 10 Cars(either in game body ID or general ID or extracted folder modelcode)/COURSES NAMES while telling me what ID/NAME yout want (English Name, like the game would display them).
And I'll post their extracted counter part like exact name/body id/modelcode/whatnot in return..

I haven't automated their name extraction, as I'm not interested about that for like some months anymore.
I would have a "manual" look into a database for these car names/body id/modelcode/other relation/you name it.

And no, it's not a file that flatz's tool (btw, I bow down before his work for like a third time) would decrypt. GT5/Academy'13/GT6 will internally work with even more decrypt algo's for the file I'm looking at.

So, either take my offer or refuse it 

Regards, q-k
## Post #76
- Username: flatz
- Rank: advanced
- Number of posts: 58
- Joined date: Mon Nov 21, 2011 2:31 pm
- Post datetime: 2014-08-23T06:36:06+00:00
- Post Title: Re: Gran Turismo 6 Models

Hello, again! I haven't included a different stream cipher into my source code earlier because I haven't found a time to refactor some of its functions (generate_key_stream and generate_key), but they works fine. However I've tested them only on GT5. I think this algorithm is the general one and should work on several files, but you need to specify a correct seed to decrypt the file you want. I've included a seed for MOVIE/tv_451_120285132.pam (from GT5), so you can try to decrypt this one if you add these snippets of code into my source code and compile it:  [http://pastie.org/private/zssddzm7yqsoibn8s6xr9a](http://pastie.org/private/zssddzm7yqsoibn8s6xr9a)

> Reply from rex1825
>
> GT5/Academy'13/GT6 will internally work with even more decrypt algo's for the file I'm looking at.
If you have worked with most files can you say which files are encrypted using this algorithm?
## Post #77
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-23T13:37:25+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from 0xqk
>
> hi folks, for a first time post, I'd like to offer something - instead of asking any crap questions...
rex1825 wrote:is there any table that states what is what car

Yes, there is. I've got it down for quite some months now. But, I don't like to get anything of that knwoledge into the wild public.
So "rex1825" - feel lucky as you've won a "gimme 10" voucher.

Name 10 Cars(either in game body ID or general ID or extracted folder modelcode)/COURSES NAMES while telling me what ID/NAME yout want (English Name, like the game would display them).
And I'll post their extracted counter part like exact name/body id/modelcode/whatnot in return..

I haven't automated their name extraction, as I'm not interested about that for like some months anymore.
I would have a "manual" look into a database for these car names/body id/modelcode/other relation/you name it.

And no, it's not a file that flatz's tool (btw, I bow down before his work for like a third time) would decrypt. GT5/Academy'13/GT6 will internally work with even more decrypt algo's for the file I'm looking at.

So, either take my offer or refuse it 

Regards, q-k

...thanks

These are 3 cars I'd really like to have:

Lamborghini Miura P400
Toyota 2000GT
Honda S2000

if anyone else wanna add some to the list of 10 fell free 

Cheers...
## Post #78
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-23T13:47:20+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from Ferrari formula 1
>
> Sorry for double posting 
I'm on my mobile phone now, so I can't post images here,I will return to my pc at sunday 

Just take a look here-theese are screenshots from the official polyphony digital presentation of gt6
http://www.google.com/search?q=gran+tur ... CAcQ_AUoAQ

I also want to mention, that adaptive tessellation works only on the one thing:when your rival is getting far away, the game may not change a lod of a car, but use a tesselation to make it look better.

I saw it 3 times, when lexus was leading in the race:rear window was jamming a little, just like if  I use a "reduce amoun of polygons" in cinema4d

All the details are must be hidden there

Please send me a lod0 model file from gt5.
## Post #79
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-23T14:04:22+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from EcheloCross
>
> Please send me a lod0 model file from gt5.

It is confirmed many times that GT5/6 have high lod models for premium cars, especially those that are used for photo mode.

[http://beyond3d.com/showthread.php?s=cb ... b2&t=43975](http://beyond3d.com/showthread.php?s=cb442d7b2f8e870e7da70023defd9db2&t=43975)

```
Cars - ~2,000-4,000 polygons

Gran Turismo 4, PS2, 2004
Cars - ~2,000-5,000 polygons

Gran Turismo 5: Prologue, PS3, 2007
Cars - 200,000 polygons (probably interior + exterior)

Gran Turismo 5
Cars ~500K photomode
```


So those thingies must be somewhere hidden...

No bad feeling, thanks for all your effort and work till now m8 

Cheers, you got a beer from me when we see us
## Post #80
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-23T16:07:56+00:00
- Post Title: Re: Gran Turismo 6 Models

Hmm, I'm seeing more data now

unsigned shorts


front of abarth 500 '09


So looking like this data I suspected to be 48bit floats is just unsigned shorts.  Now to find the faces.
## Post #81
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-23T16:47:23+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from EcheloCross
>
> Hmm, I'm seeing more data now

unsigned shorts


front of abarth 500 '09


So looking like this data I suspected to be 48bit floats is just unsigned shorts.  Now to find the faces.

I knew you'll make it  GJ
## Post #82
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-23T20:37:10+00:00
- Post Title: Re: Gran Turismo 6 Models

making progress..
still need to find faces, but now parsing all highest lod vertices from body_s automatically, I see the bounding box too, next step is to scale it according to the bounding box
## Post #83
- Username: 0xqk
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Aug 12, 2014 8:38 am
- Post datetime: 2014-08-23T20:39:06+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from flatz
>
> If you have worked with most files can you say which files are encrypted using this algorithm?

I'm grabbing all of my information that I'll attach to this posting from the specdb:

/specdb/GT6/DB0105.dat EDIT2 This file is not really being used. I guess it is a leftover as PD have planned to carry over GT5 savegames but abandoned that idea due to heavy savegeame modding at some point /EDIT2
/specdb/GT6/DB0106.dat

These files are encrypted by an algorithm that is not covered in your published source code. They are in fact sqlite3 databases as well.
I'm totally confident that you'll get the two way encryption algorithm of it down in minutes, no doubt. But I'd like to ask you not to make it public.
Although it is quite funny to have the game running with a modded specdb (as I've called it) and every car's price is 1cr, it will somehow allow real bad modding as well. This file is being used by the game to determine "in game" limits for the cars. For example, the boundaries for a custom suspension. like, how low can you set your ridehight.
All of that stuff may be modded right at the source and the game won't even know about bad modding.
Although I don't play the game anymore for quite some time now, I'm reasonable enough to not let my knowledge about the crypt algo go into public and let other unreasonable people go wild on modded specdb's..

The interesting fact about the algo is, I've only seen it being used on the specdb.
It is a static substitution algorithm. It will work for GT5/Academy 2013 and GT6 without changing anything at all.
I haven't checked GT5 Prologue yet, but I guess the seed will also be the name of a desert. Kalahari, Cholistan, Piscinas.. I do see a pattern here 

I couldn't get the Movie files you've mentioned to decrypt earlier. I haven't tried you new source on them yet. EDIT3: I don't know what went wrong on my side, but I can't see any .pam file in the extracted GT5 folder.. I also don't have a /movies folder in it.. can you provide the file number for that specific movie .pam? I'm then able to extract it from the PDIPFS folder  /EDIT3
EDIT I had a glimpse at the new crypt algorithm. I don't think I have seen it before, so this might be the 6th crypt algo they are using.
1 and 2: for savegames (and I'm not interested in making them public either)
3 and 4: the two you are using in your tool, where I've seen the one that is being used on the header (0x00 from file gt.vol) only being used on the header
5: the specdb algo
6: the new algo
/EDIT

All other files (except for specdb and movies), should just decrypt fine with your tool.
I wouldn't say I've looked into everything yet, but I still remember the specdb and movies using another crypt besides the first layer (which is covered in your tool).

> Reply from rex1825
>
> ...thanks

These are 3 cars I'd really like to have:

Lamborghini Miura P400
Toyota 2000GT
Honda S2000

if anyone else wanna add some to the list of 10 fell free

I've made up my mind about it. There's no harm in publically posting them..

I'm not an SQL expert, so bare with me 

ModelCodes:
select GC.ModelCode,CNA.LabelID,CNA.Name from GENERIC_CAR as GC, CAR_NAME_ALPHABET as CNA where CNA.LabelID = GC.ID;

Courses:
select CRS.ModelName,CRS.label,CRS.NameEng from COURSE as CRS where CRS.PWY = 0 and CRS.Scenery = 0 and CRS.Rail = 0;

You'll have to add leading zeros to the ModelCode until you have 8 digits. For Example:

```
2     | 10002     | 30      | Mazda Atenza Concept '01

```

ModelCode will need further 3 leading zeros: 00010002
Split it after 4 digits, you'll then have the folder names for /car/:

0001
0002

Which makes in total: /car/0001/0002

and that's the folder for your modelcode..

Courses should just read fine..

Have Fun with it 
[modelcode_and_modelname_mappings.7z](https://xentaxbackup.github.io/file/7712_modelcode_and_modelname_mappings.7z)
## Post #84
- Username: flatz
- Rank: advanced
- Number of posts: 58
- Joined date: Mon Nov 21, 2011 2:31 pm
- Post datetime: 2014-08-23T22:39:17+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from 0xqk
>
> I couldn't get the Movie files you've mentioned to decrypt earlier. I haven't tried you new source on them yet. EDIT3: I don't know what went wrong on my side, but I can't see any .pam file in the extracted GT5 folder.. I also don't have a /movies folder in it.. can you provide the file number for that specific movie .pam? I'm then able to extract it from the PDIPFS folder
They are not in GT.VOL, they are at USRDIR/movie, if I recall correctly.
## Post #85
- Username: 0xqk
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Aug 12, 2014 8:38 am
- Post datetime: 2014-08-23T22:44:52+00:00
- Post Title: Re: Gran Turismo 6 Models

ah ok. I've extracted GT5 prologue stuff some minutes ago. There's a TV.DAT file on the disc. I guess it will be the same for GT5 and thus provide further files I didn't know about until now. I've never looked into GT5 data that deep like I did for GT6
## Post #86
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-24T01:01:10+00:00
- Post Title: Re: Gran Turismo 6 Models

So far, ushort for highest lod is only working for some models, the vertices look like they can have different amounts of bits for different cars.

the following pictures are the (1132	 0140 0003	1932	Abarth 1500 Biposto Bertone B.A.T 1 '52)




the reason they're scaled/squished, is I'm not scaling to their bounding boxes yet, working on that now
## Post #87
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-24T12:22:34+00:00
- Post Title: Re: Gran Turismo 6 Models

@ EcheloCross, is it same for Tracks, or they are easily to extract?

Cheers...
## Post #88
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-24T15:14:09+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from rex1825
>
> @ EcheloCross, is it same for Tracks, or they are easily to extract?

Cheers...

As far as I can tell, the .rwy files are just the roadway of each track.  32bit floats for vertices and 24bit faces.  Also the edges of the roadway seem to be stored as a separate group of 32bit floats and ushort faces, but not nearly as detailed as the data with 24bit faces.

The cNNNx files contain multiple mdl3 and other data. (buildings + objects + etc..)  
When I finish the car/XXXX/YYYY/body + body_s I'll go for those.
## Post #89
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-24T15:31:37+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from EcheloCross
>
> rex1825 wrote:@ EcheloCross, is it same for Tracks, or they are easily to extract?

Cheers...

As far as I can tell, the .rwy files are just the roadway of each track.  32bit floats for vertices and 24bit faces.  Also the edges of the roadway seem to be stored as a separate group of 32bit floats and ushort faces, but not nearly as detailed as the data with 24bit faces.

The cNNNx files contain multiple mdl3 and other data. (buildings + objects + etc..)  
When I finish the car/XXXX/YYYY/body + body_s I'll go for those.

Thank you...
## Post #90
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-08-26T18:36:25+00:00
- Post Title: Re: Gran Turismo 6 Models

Hmmm...
That's very cool and amazing!  

But i can't really understand,why did they decrypted cars that much,so we can't locate meshes...  

As i understand,extracting standart cars is already totally done?)
Because i would like to start getting cars out...  

Premium cars have amazing detail,I really hope you can get meshes and textures,guys!  

Also,how about DLC cars,like amazing Vision GT cars?
I think they must be downloaded on PS3 harddrive separate from the game Blu-ray...
## Post #91
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-26T18:56:28+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from Ferrari formula 1
>
> Hmmm...
That's very cool and amazing!  

But i can't really understand,why did they decrypted cars that much,so we can't locate meshes...  

As i understand,extracting standart cars is already totally done?)
Because i would like to start getting cars out...  

Premium cars have amazing detail,I really hope you can get meshes and textures,guys!  

Also,how about DLC cars,like amazing Vision GT cars?
I think they must be downloaded on PS3 harddrive separate from the game Blu-ray...

I know that Mercedes-Benz VisionGT was 2055 and BMW M4 2074 ModelCode... for rest I don't know 

Cheers...
## Post #92
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-08-26T19:03:26+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from rex1825
>
> Ferrari formula 1 wrote:Hmmm...
That's very cool and amazing!  

But i can't really understand,why did they decrypted cars that much,so we can't locate meshes...  

As i understand,extracting standart cars is already totally done?)
Because i would like to start getting cars out...  

Premium cars have amazing detail,I really hope you can get meshes and textures,guys!  

Also,how about DLC cars,like amazing Vision GT cars?
I think they must be downloaded on PS3 harddrive separate from the game Blu-ray...

I know that Mercedes-Benz VisionGT was 2055 and BMW M4 2074 ModelCode... for rest I don't know 

Cheers...

I mean,that they are not actually inside GT.VOL file...
I think they are stired on PS3 hard drive,and there's should be a way to copy update\dlc files...

Nissan VGT is a dreeeaaam
## Post #93
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-26T19:08:06+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from Ferrari formula 1
>
> rex1825 wrote:Ferrari formula 1 wrote:Hmmm...
That's very cool and amazing!  

But i can't really understand,why did they decrypted cars that much,so we can't locate meshes...  

As i understand,extracting standart cars is already totally done?)
Because i would like to start getting cars out...  

Premium cars have amazing detail,I really hope you can get meshes and textures,guys!  

Also,how about DLC cars,like amazing Vision GT cars?
I think they must be downloaded on PS3 harddrive separate from the game Blu-ray...

I know that Mercedes-Benz VisionGT was 2055 and BMW M4 2074 ModelCode... for rest I don't know 

Cheers...

I mean,that they are not actually inside GT.VOL file...
I think they are stired on PS3 hard drive,and there's should be a way to copy update\dlc files...

Nissan VGT is a dreeeaaam

Yeap, they are separate download, will try to find files up to the last patch 

Edit: ...shouldn't be easier for someone that has GT6 with all updates to share files related to GT6 that are for patches related?

Cheers...
## Post #94
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-27T22:31:55+00:00
- Post Title: Re: Gran Turismo 6 Models

...any news? Some poly extracted
## Post #95
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-27T23:07:38+00:00
- Post Title: Re: Gran Turismo 6 Models

Taking a break from gt6 data.

Theres 2 data blocks left to parse for the highest lod meshes.  They must be at least faces and uv.  
They are a format I haven't seen yet though.  Will post some info about them soon.
## Post #96
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-09-07T16:33:33+00:00
- Post Title: Re: Gran Turismo 6 Models

...any extraction tutorial or tool on horizon?
## Post #97
- Username: MalagoliBR
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 14, 2014 11:00 pm
- Post datetime: 2014-09-14T15:10:19+00:00
- Post Title: Re: Gran Turismo 6 Models

Wow... those things looks like Laser Scan clouds. Amazing level of detail, looking forward for this tools....

Thank you mates!
## Post #98
- Username: MacedoSTI
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 11:57 pm
- Post datetime: 2014-09-23T15:09:26+00:00
- Post Title: Re: Gran Turismo 6 Models

i can use it on GT4.vol?
## Post #99
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-09-26T11:10:43+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from MacedoSTI
>
>  i can use it on GT4.vol?

...this is for GT5/6 only!

Any progress?

Cheers...
## Post #100
- Username: medwed
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Sep 03, 2010 3:45 pm
- Post datetime: 2014-09-27T11:24:45+00:00
- Post Title: Re: Gran Turismo 6 Models

Hello gentlemen.There is a chance for Gran Turismo 5 kubelwagen and Schwimmwagen 3D model ?  Big Thanks
## Post #101
- Username: Argonaut
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Sep 12, 2014 3:19 am
- Post datetime: 2014-09-27T15:46:02+00:00
- Post Title: Re: Gran Turismo 6 Models

To above person:

I'd wait until he's finalized the extraction method before asking, that's what I'm doing and most of my requests are standard cars too. Patience is a virtue.
## Post #102
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-10-16T19:58:50+00:00
- Post Title: Re: Gran Turismo 6 Models

...any news on this matter? Would be nice to see if there was some progress...
## Post #103
- Username: Voo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 20, 2014 6:26 am
- Post datetime: 2014-10-19T22:29:47+00:00
- Post Title: Re: Gran Turismo 6 Models

I've read every bit of this, and you all have done super excellent work on the research needed. Sounds like there isn't a full-proof way of extracting the meshes for cars. 

I'm curious as well if there has been any progress?

Thanks!
## Post #104
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-10-24T14:36:50+00:00
- Post Title: Re: Gran Turismo 6 Models

You guys did amazing job,and I beleive we should go further!

First of all,I see there's no problem for you,guys,to get meshes of the standart cars,so,please,can you explain the process?

There's one good thing with standart cars in GT6 : Some of them were upgraded,and they look pretty awesome!
So,with a little bit of work and polish they can look just like premium cars!

See the example:
*I do beleive,we can get them,because they are in standart section,not a premium one*
This is how the STANDART Nissan 2000 GT-R looks in GT5 and GT6.
It was updated,but it's still a standart car  



This is the same car i extracted from GT PSP
[](http://www.imagebam.com/image/f327b2359400073) 
[](http://www.imagebam.com/image/c89358359400067) 
[](http://www.imagebam.com/image/0fb3a7359400085) 
[](http://www.imagebam.com/image/ed2e4e359400079) 

So please,explain the process of getting meshes of standart cars 

Secondly,i saw Chpicao had made a small instrument to transfer all textures,but not the cars textures.
So,can we decrypt car textures?  

And the last part is that if we will get Premium cars - we will get the real treasure  
[](http://www.imagebam.com/image/9697fc339578561) 
[](http://www.imagebam.com/image/d33fdd339578551) 
[](http://www.imagebam.com/image/b89334339578587) 
[](http://www.imagebam.com/image/4b86a1339578596) 
[](http://www.imagebam.com/image/358085339578601) 
[](http://www.imagebam.com/image/613247339579253) 
Have a nice day,everybody!
## Post #105
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-10-24T18:48:47+00:00
- Post Title: Re: Gran Turismo 6 Models

Just forgot to mention:At the first launch,GT6 installs some data on PS3's HDD(and also updates) so mabye needed information is just right there?
## Post #106
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-10-24T23:14:44+00:00
- Post Title: Re: Gran Turismo 6 Models

Here is my code so far for handling the MDL3 files.  If you read through it you can either copy it to a c# program of your own, or re-write it in the language of your choice.

This code handles both the 2nd highest lod, and the vertices only of the highest lod.  The faces for the highest lod are edge compressed, I need to spend some more time with edge to get them figured out.  

```
public void extractMDL3_HIGHLOD(ref FileStream fs, ref FileInfo fi)
{
    //string extractedPath = fi.DirectoryName + "\\extracted_mdl3";
    //Directory.CreateDirectory(extractedPath);

    fs.Read(infoBuffer4, 0, 4); //magic
    fs.Read(infoBuffer4, 0, 4); //MDL3 Total Size
    mdl3Size = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);

    //Get meshInfoTable and sTable count
    fs.Seek(0x14, SeekOrigin.Begin);
    fs.Read(infoBuffer2, 0, 2);
    uint sTableCount = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0);

    //Enumerate Mesh Info Table
    List<List<uint>> meshInfoTable = new List<List<uint>>();
    fs.Seek(0x38, SeekOrigin.Begin);
    fs.Read(infoBuffer4, 0, 4);
    uint meshInfoTableAddress = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);
    fs.Seek(meshInfoTableAddress, SeekOrigin.Begin);
    for (int i = 0; i < sTableCount; i++)
    {
        List<uint> meshInfoEnum = new List<uint>();
        fs.Read(infoBuffer1, 0, 1); meshInfoEnum.Add(infoBuffer1[0]);   //unk flag 1
        fs.Read(infoBuffer1, 0, 1); meshInfoEnum.Add(infoBuffer1[0]);   //unk flag 2
        fs.Read(infoBuffer2, 0, 2); uint meshIndex = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0); meshInfoEnum.Add(meshIndex);
        fs.Read(infoBuffer2, 0, 2); uint unkIndex = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0); meshInfoEnum.Add(unkIndex);
        fs.Read(infoBuffer2, 0, 2); uint null_MIT1 = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0); meshInfoEnum.Add(null_MIT1);
        fs.Read(infoBuffer4, 0, 4); uint vertexCount = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0); meshInfoEnum.Add(vertexCount);
        fs.Read(infoBuffer4, 0, 4); uint null_MIT2 = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0); meshInfoEnum.Add(null_MIT2);
        fs.Read(infoBuffer4, 0, 4); uint null_MIT3 = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0); meshInfoEnum.Add(null_MIT3);
        fs.Read(infoBuffer4, 0, 4); uint faceIndexCount = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0); meshInfoEnum.Add(faceIndexCount);
        fs.Read(infoBuffer4, 0, 4); uint null_MIT4 = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0); meshInfoEnum.Add(null_MIT4);
        fs.Read(infoBuffer4, 0, 4); uint null_MIT5 = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0); meshInfoEnum.Add(null_MIT5);
        fs.Read(infoBuffer4, 0, 4); uint null_MIT6 = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0); meshInfoEnum.Add(null_MIT6);
        fs.Read(infoBuffer1, 0, 1); meshInfoEnum.Add(infoBuffer1[0]);   //unk flag 3
        fs.Read(infoBuffer1, 0, 1); meshInfoEnum.Add(infoBuffer1[0]);   //unk flag 4
        fs.Read(infoBuffer2, 0, 2); uint unkCount1 = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0); meshInfoEnum.Add(unkCount1);
        fs.Read(infoBuffer4, 0, 4); uint null_MIT7 = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0); meshInfoEnum.Add(null_MIT7);
        fs.Read(infoBuffer4, 0, 4); uint null_MIT8 = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0); meshInfoEnum.Add(null_MIT8);
        meshInfoTable.Add(meshInfoEnum);
    }

    //Get fvfTable Count
    fs.Seek(0x18, SeekOrigin.Begin);
    fs.Read(infoBuffer2, 0, 2);
    uint fvfTableCount = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0);

    //Enumerate fvfTable
    List<List<uint>> fvfTable = new List<List<uint>>();
    fs.Seek(0x40, SeekOrigin.Begin);
    fs.Read(infoBuffer4, 0, 4);
    uint fvfTableAddress = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);
    fs.Seek(fvfTableAddress, SeekOrigin.Begin);
    for (int i = 0; i < fvfTableCount; i++)
    {
        List<uint> fvfTableEnum = new List<uint>();
        //def loadfvf(self, bs):
        //#FVF Table
        //for a in range(0, self.fvfCount):
        fs.Seek((fvfTableAddress + (i * 0x78)), SeekOrigin.Begin);  //bs.seek(self.fvfOffst + (a * 0x78), NOESEEK_ABS)
        //print(bs.tell())
        //fvfData = bs.read(">" + "6I4B23I")
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer1, 0, 1); fvfTableEnum.Add(infoBuffer1[0]);
        fs.Read(infoBuffer1, 0, 1); fvfTableEnum.Add(infoBuffer1[0]);
        fs.Read(infoBuffer1, 0, 1); fvfTableEnum.Add(infoBuffer1[0]);
        fs.Read(infoBuffer1, 0, 1); fvfTableEnum.Add(infoBuffer1[0]);
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
        fs.Read(infoBuffer4, 0, 4); fvfTableEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));

        fs.Seek(fvfTableEnum[0], SeekOrigin.Begin);

        fvfTableEnum.Add((uint)fs.Position);

        fvfTable.Add(fvfTableEnum);
    }

    bp++;

    //Get PMSH Address
    fs.Seek(0xD0, SeekOrigin.Begin);
    fs.Read(infoBuffer4, 0, 4);
    pmshAddress = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);

    //Get zlibInfoAddress
    fs.Seek(0xDC, SeekOrigin.Begin);
    fs.Read(infoBuffer4, 0, 4);
    zlibInfoAddress = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);

    ushort pmshTable1Count = 0;
    ushort pmshTable2Count = 0;
    ushort pmshTable3Count = 0;
    ushort pmshTable4Count = 0;
    uint pmshTable1Address = 0;
    uint pmshTable2Address = 0;
    uint pmshTable3Address = 0;
    uint pmshTable4Address = 0;
    //Parse PMSH
    fs.Seek(pmshAddress, SeekOrigin.Begin);
    fs.Read(infoBuffer4, 0, 4); //PMSH Magic
    fs.Read(infoBuffer2, 0, 2);
    fs.Read(infoBuffer2, 0, 2);
    fs.Read(infoBuffer4, 0, 4); //PMSH Address from beginning of MDL3 file
    fs.Read(infoBuffer4, 0, 4); //padding?
    fs.Read(infoBuffer2, 0, 2);
    pmshTable1Count = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0);
    fs.Read(infoBuffer2, 0, 2);
    pmshTable2Count = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0);
    fs.Read(infoBuffer2, 0, 2);
    pmshTable3Count = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0);
    fs.Read(infoBuffer2, 0, 2);
    pmshTable4Count = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0);
    fs.Read(infoBuffer4, 0, 4);
    pmshTable1Address = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);
    fs.Read(infoBuffer4, 0, 4);
    pmshTable2Address = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);
    fs.Read(infoBuffer4, 0, 4);
    pmshTable3Address = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);
    fs.Read(infoBuffer4, 0, 4);
    pmshTable4Address = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);

    if (pmshTable1Count > 0)
    {
        fs.Seek(pmshTable1Address, SeekOrigin.Begin);

    }

    if (pmshTable2Count > 0)
    {
        fs.Seek(pmshTable2Address, SeekOrigin.Begin);
    }

    if (pmshTable3Count > 0)
    {
        fs.Seek(pmshTable3Address, SeekOrigin.Begin);
    }


    if (pmshTable4Count > 0)
    {
        List<uint> stringTableInfoPointers = new List<uint>();

        fs.Seek(pmshTable4Address, SeekOrigin.Begin);

        for (int i = 0; i < pmshTable4Count; i++)
        {
            fs.Read(infoBuffer1, 0, 1); //flag1
            fs.Read(infoBuffer1, 0, 1); //flag2
            fs.Read(infoBuffer1, 0, 1); //flag3
            fs.Read(infoBuffer1, 0, 1); //flag4
            fs.Read(infoBuffer4, 0, 4); //unk1
            fs.Read(infoBuffer4, 0, 4); //stringTableInfoPointer
            stringTableInfoPointers.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
            fs.Read(infoBuffer4, 0, 4); //unk2
        }

        for (int i = 0; i < pmshTable4Count; i++)
        {
            fs.Seek(stringTableInfoPointers[i], SeekOrigin.Begin);
            fs.Read(infoBuffer2, 0, 2); // ushort unk01;
            fs.Read(infoBuffer2, 0, 2); //ushort unk02;
            fs.Read(infoBuffer2, 0, 2); //ushort unk03;
            fs.Read(infoBuffer2, 0, 2); //ushort unk04;
            fs.Read(infoBuffer2, 0, 2); //ushort unk05;
            fs.Read(infoBuffer2, 0, 2); //ushort unk06;
            fs.Read(infoBuffer2, 0, 2); //ushort unk07;
            fs.Read(infoBuffer1, 0, 1); int entryType = infoBuffer1[0];
            fs.Read(infoBuffer1, 0, 1); //byte unk08;
            if (entryType == -2)
            {
                fs.Read(infoBuffer4, 0, 4); //ulong unkL01;
                fs.Read(infoBuffer4, 0, 4); //ulong unkL02;
                fs.Read(infoBuffer2, 0, 2); //ushort unkS03;
                fs.Read(infoBuffer2, 0, 2); //ushort unkS04;
                fs.Read(infoBuffer2, 0, 2); //ushort unkS05;
                fs.Read(infoBuffer2, 0, 2); //ushort unkS06;
            }
            if (entryType == -94)
            {
                fs.Read(infoBuffer4, 0, 4); //ulong unkL01;
                fs.Read(infoBuffer4, 0, 4); //ulong unkL02;
                fs.Read(infoBuffer2, 0, 2); //ushort unkS03;
                fs.Read(infoBuffer2, 0, 2); //ushort unkS04;
                fs.Read(infoBuffer2, 0, 2); //ushort unkS05;
                fs.Read(infoBuffer2, 0, 2); //ushort unkS06;
            }
            if (entryType == 2)
            {
                fs.Read(infoBuffer4, 0, 4); //ulong unkL01;
                fs.Read(infoBuffer4, 0, 4); //ulong unkL02;
                fs.Read(infoBuffer4, 0, 4); //ulong unkL03;
                fs.Read(infoBuffer4, 0, 4); //ulong unkL04;
            }
            if (entryType == 4)
            {
                fs.Read(infoBuffer2, 0, 2); //ushort unkS01;
                fs.Read(infoBuffer2, 0, 2); //ushort unkS02;
                fs.Read(infoBuffer4, 0, 4); //ulong unkL02;
                fs.Read(infoBuffer4, 0, 4); //ulong unkL03;
                fs.Read(infoBuffer4, 0, 4); //ulong unkL04;
                fs.Read(infoBuffer4, 0, 4); //ulong unkL05;
                fs.Read(infoBuffer4, 0, 4); //ulong unkL06;
                fs.Read(infoBuffer4, 0, 4); //ulong unkL07;
                fs.Read(infoBuffer4, 0, 4); //ulong unkL08;
            }
            if (i == (pmshTable4Count - 1))
            {
                bp++;
            }
        }

        //Read data info start
        fs.Seek(zlibInfoAddress, SeekOrigin.Begin);
        //FileStream zfs = new FileStream(fi.DirectoryName + "\\body_s.multiZlib", FileMode.Open, FileAccess.Read);
        FileStream zfs = new FileStream(fi.DirectoryName + "\\body_s", FileMode.Open, FileAccess.Read);
        FileStream dfs = new FileStream(fi.DirectoryName + "\\body_s.bin", FileMode.Create, FileAccess.Write);

        fs.Read(infoBuffer2, 0, 2); uint zlibInfo0 = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0);
        fs.Read(infoBuffer2, 0, 2); uint zlibInfo1 = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0);
        fs.Read(infoBuffer2, 0, 2); uint zlibInfo2 = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0);
        fs.Read(infoBuffer2, 0, 2); uint zlibInfo3 = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0);
        fs.Read(infoBuffer4, 0, 4); uint zlibInfo4 = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);
        fs.Read(infoBuffer4, 0, 4); uint zlibInfo5 = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);

        for (int i = 0; i < zlibInfo1; i++)
        {
            fs.Seek((zlibInfo4 + (0xC * i)), SeekOrigin.Begin);
            fs.Read(infoBuffer4, 0, 4); uint zlibHId = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);
            fs.Read(infoBuffer4, 0, 4); uint zlibHCount = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);
            fs.Read(infoBuffer4, 0, 4); uint zlibHoff = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);

            for (int j = 0; j < zlibHCount; j++)
            {
                fs.Seek((zlibHoff + (0x18 * j)), SeekOrigin.Begin);
                fs.Read(infoBuffer4, 0, 4); uint null00 = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);
                fs.Read(infoBuffer4, 0, 4); uint chunkStart = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);
                fs.Read(infoBuffer2, 0, 2); uint chunkCount00 = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0);
                fs.Read(infoBuffer2, 0, 2); uint chunkCount01 = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0);
                fs.Read(infoBuffer4, 0, 4); uint chunkInfoOff00 = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);
                fs.Read(infoBuffer2, 0, 2); uint chunkCount02 = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0);
                fs.Read(infoBuffer2, 0, 2); uint chunkCount03 = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0);
                fs.Read(infoBuffer4, 0, 4); uint chunkInfoOff01 = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);

                for (int k = 0; k < (chunkCount00 + chunkCount01); k++)
                {
                    fs.Seek((chunkInfoOff00 + (0x8 * k)), SeekOrigin.Begin);
                    fs.Read(infoBuffer2, 0, 2); uint zFlag = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0);
                    fs.Read(infoBuffer2, 0, 2); uint zSize = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0);
                    fs.Read(infoBuffer4, 0, 4); uint uSize = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);

                    zfs.Seek(chunkStart, SeekOrigin.Begin);
                    byte[] cmpData = new byte[zSize];
                    zfs.Read(cmpData, 0, cmpData.Length);
                    if (zFlag == 0)
                    {
                        dfs.Write(cmpData, 0, cmpData.Length);
                    }
                    else
                    {
                        byte[] dcmpData = DeflateStream.UncompressBuffer(cmpData);
                        dfs.Write(dcmpData, 0, dcmpData.Length);
                    }
                    chunkStart += zSize;
                }

                for (int k = 0; k < (chunkCount02 + chunkCount03); k++)
                {
                    fs.Seek((chunkInfoOff01 + (0x10 * k)), SeekOrigin.Begin);
                    fs.Read(infoBuffer4, 0, 4); uint null00a = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);
                    fs.Read(infoBuffer4, 0, 4); uint chunkStart2 = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);
                    fs.Read(infoBuffer2, 0, 2); uint chunkCount04 = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0);
                    fs.Read(infoBuffer2, 0, 2); uint chunkCount05 = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0);
                    fs.Read(infoBuffer4, 0, 4); uint zlibHoff2 = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);

                    for (int l = 0; l < (chunkCount04 + chunkCount05); l++)
                    {
                        fs.Seek((zlibHoff2 + (0x8 * l)), SeekOrigin.Begin);
                        fs.Read(infoBuffer2, 0, 2); uint zFlag = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0);
                        fs.Read(infoBuffer2, 0, 2); uint zSize = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0);
                        fs.Read(infoBuffer4, 0, 4); uint uSize = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);

                        zfs.Seek(chunkStart2, SeekOrigin.Begin);
                        byte[] cmpData = new byte[zSize];
                        zfs.Read(cmpData, 0, cmpData.Length);
                        if (zFlag == 0)
                        {
                            dfs.Write(cmpData, 0, cmpData.Length);
                        }
                        else
                        {
                            byte[] dcmpData = DeflateStream.UncompressBuffer(cmpData);
                            dfs.Write(dcmpData, 0, dcmpData.Length);
                        }
                        chunkStart2 += zSize;
                    }
                }
            }
        }

        zfs.Close();
        dfs.Close();

        //Enumerate body_s.bin header and main table
        FileStream bfs = new FileStream(fi.DirectoryName + "\\body_s.bin", FileMode.Open, FileAccess.Read);
        FileInfo bfi = new FileInfo(fi.DirectoryName + "\\body_s.bin");

        //Enumerate body_s.bin header
        bfs.Read(infoBuffer4, 0, 4); uint sNull00 = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);
        bfs.Read(infoBuffer4, 0, 4); uint sAddress1 = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0); //unknown data address
        bfs.Read(infoBuffer4, 0, 4); uint sAddress2 = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0); //data near end of file
        bfs.Read(infoBuffer4, 0, 4); uint sAddress3 = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0); //unknown data address or size
        bfs.Read(infoBuffer4, 0, 4); uint sNull01 = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);
        bfs.Read(infoBuffer2, 0, 2); uint sTable1Count = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0);
        bfs.Read(infoBuffer2, 0, 2); uint sCount2 = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0);
        bfs.Read(infoBuffer4, 0, 4); uint sCount3 = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0);
        bfs.Read(infoBuffer4, 0, 4); uint sAddress4 = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0); //pointer to another table

        List<List<uint>> sTable1 = new List<List<uint>>();
        for (int i = 0; i < sTable1Count; i++)
        {
            List<uint> sTable1Enum = new List<uint>();
            bfs.Read(infoBuffer4, 0, 4); uint dataId = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0); sTable1Enum.Add(dataId);
            bfs.Read(infoBuffer4, 0, 4); uint vAddress = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0); sTable1Enum.Add(vAddress);
            bfs.Read(infoBuffer4, 0, 4); uint fAddress = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0); sTable1Enum.Add(fAddress);
            bfs.Read(infoBuffer4, 0, 4); uint u1Address = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0); sTable1Enum.Add(u1Address);
            bfs.Read(infoBuffer4, 0, 4); uint u2Address = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0); sTable1Enum.Add(u2Address);
            bfs.Read(infoBuffer4, 0, 4); uint u3Address = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0); sTable1Enum.Add(u3Address);
            bfs.Read(infoBuffer4, 0, 4); uint u4Address = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0); sTable1Enum.Add(u4Address);
            bfs.Read(infoBuffer4, 0, 4); uint dataTypeFlag = BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0); sTable1Enum.Add(dataTypeFlag);
            sTable1.Add(sTable1Enum);
        }

        //Parse and extract sTable1[i][7] //SO FAR, (known as the mesh data signaling flag when its 0x00000000, 0x00000001, and 0x00000002)
        for (int i = 0; i < sTable1Count; i++)
        {
            if (sTable1[i][7] == 0) //standard lod
            {
                //Process known mesh data
                int meshInfoTableIndex = (int)sTable1[i][0];
                uint vCount = meshInfoTable[meshInfoTableIndex][5];
                uint fCount = meshInfoTable[meshInfoTableIndex][8];
                uint vAddress = sTable1[i][1];
                uint fAddress = sTable1[i][2];
                uint vStride = fvfTable[(int)meshInfoTable[(int)sTable1[i][0]][2]][7];

                //Enumerate vertices
                List<List<float>> verticesList = new List<List<float>>();
                bfs.Seek(vAddress, SeekOrigin.Begin);
                for (int j = 0; j < vCount; j++)
                {
                    List<float> vEnum = new List<float>();
                    if (vStride >= 12)
                    {
                        bfs.Read(infoBuffer4, 0, 4); vEnum.Add(-BitConverter.ToSingle(mh.ArrayReverse(infoBuffer4), 0));
                        bfs.Read(infoBuffer4, 0, 4); vEnum.Add(BitConverter.ToSingle(mh.ArrayReverse(infoBuffer4), 0));
                        bfs.Read(infoBuffer4, 0, 4); vEnum.Add(BitConverter.ToSingle(mh.ArrayReverse(infoBuffer4), 0));
                        bfs.Seek((vStride - 12), SeekOrigin.Current);
                        verticesList.Add(vEnum);
                    }
                    else
                    {

                    }
                }

                //Enumerate Faces
                List<List<ushort>> facesList = new List<List<ushort>>();
                bfs.Seek(fAddress, SeekOrigin.Begin);
                for (int j = 0; j < (fCount / 3); j++)
                {
                    List<ushort> fEnum = new List<ushort>();
                    if (vStride >= 12)
                    {
                        bfs.Read(infoBuffer2, 0, 2); fEnum.Add(BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0));
                        bfs.Read(infoBuffer2, 0, 2); fEnum.Add(BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0));
                        bfs.Read(infoBuffer2, 0, 2); fEnum.Add(BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0));
                        facesList.Add(fEnum);
                    }
                }

                //Write .obj file
                if (vStride >= 12)
                {
                    string outputPath = bfi.DirectoryName + "\\" + Path.GetFileNameWithoutExtension(bfi.Name) + "_extracted";
                    Directory.CreateDirectory(outputPath);
                    ow.writeSpecifiedObjFile(verticesList, facesList, null, ref bfi, ref bfi, 1, bfi.Name, "__" + mh.readString(ref fs, fvfTable[(int)meshInfoTable[(int)sTable1[i][0]][2]][0x21]) + "_" + meshInfoTableIndex.ToString("X"), 0);
                }
            }
            else //highest lod
            {
                //Read bounding box
                bfs.Seek(sTable1[i][3], SeekOrigin.Begin);
                List<List<float>> boundingBox = new List<List<float>>();
                for (int j = 0; j < 8; j++)
                {
                    List<float> bbEnum = new List<float>();
                    bfs.Read(infoBuffer4, 0, 4); bbEnum.Add(BitConverter.ToSingle(mh.ArrayReverse(infoBuffer4), 0));
                    bfs.Read(infoBuffer4, 0, 4); bbEnum.Add(BitConverter.ToSingle(mh.ArrayReverse(infoBuffer4), 0));
                    bfs.Read(infoBuffer4, 0, 4); bbEnum.Add(BitConverter.ToSingle(mh.ArrayReverse(infoBuffer4), 0));
                    boundingBox.Add(bbEnum);
                }

                string outputPathbb = bfi.DirectoryName + "\\" + Path.GetFileNameWithoutExtension(bfi.Name) + "_extracted";
                Directory.CreateDirectory(outputPathbb);
                ow.writeSpecifiedObjFile(boundingBox, ref bfi, ref bfi, 1, bfi.Name, "_" + "boundingBox_" + sTable1[i][0].ToString("X"));

                //Read info1
                bfs.Seek(sTable1[i][4], SeekOrigin.Begin);
                List<ushort> info1 = new List<ushort>();
                bfs.Read(infoBuffer2, 0, 2); info1.Add(BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0));
                bfs.Read(infoBuffer2, 0, 2); info1.Add(BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0));
                bfs.Read(infoBuffer2, 0, 2); info1.Add(BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0));
                bfs.Read(infoBuffer2, 0, 2); info1.Add(BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0));
                bfs.Read(infoBuffer2, 0, 2); info1.Add(BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0));
                bfs.Read(infoBuffer2, 0, 2); info1.Add(BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0));
                bfs.Read(infoBuffer2, 0, 2); info1.Add(BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0));
                bfs.Read(infoBuffer2, 0, 2); info1.Add(BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0));

                //Read info for mesh data
                bfs.Seek(sTable1[i][5], SeekOrigin.Begin);
                List<List<uint>> meshDataInfo = new List<List<uint>>();
                for (int j = 0; j < sTable1[i][7]; j++) //find this count if it exists
                {
                    List<uint> mdiEnum = new List<uint>();
                    bfs.Read(infoBuffer4, 0, 4); mdiEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
                    bfs.Read(infoBuffer4, 0, 4); mdiEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
                    bfs.Read(infoBuffer4, 0, 4); mdiEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
                    bfs.Read(infoBuffer4, 0, 4); mdiEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
                    bfs.Read(infoBuffer4, 0, 4); mdiEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
                    bfs.Read(infoBuffer4, 0, 4); mdiEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
                    bfs.Read(infoBuffer4, 0, 4); mdiEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
                    bfs.Read(infoBuffer4, 0, 4); mdiEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
                    bfs.Read(infoBuffer4, 0, 4); mdiEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
                    bfs.Read(infoBuffer4, 0, 4); mdiEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
                    bfs.Read(infoBuffer4, 0, 4); mdiEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
                    bfs.Read(infoBuffer4, 0, 4); mdiEnum.Add(BitConverter.ToUInt32(mh.ArrayReverse(infoBuffer4), 0));
                    meshDataInfo.Add(mdiEnum);
                }

                //Process HIGHLOD vertices
                for (int j = 0; j < sTable1[i][7]; j++)
                {
                    bfs.Seek(meshDataInfo[j][0], SeekOrigin.Begin);

                    //Enumerate ushort vertices as tris
                    List<List<float>> vList0 = new List<List<float>>();
                    for (int k = 0; k < meshDataInfo[j][8]; k++)
                    {
                        List<float> vEnum = new List<float>();
                        float vxF = 0; float vyF = 0; float vzF = 0;
                        bfs.Read(infoBuffer2, 0, 2); vxF = -BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0); vxF /= 0xFFFF; vEnum.Add(vxF);
                        bfs.Read(infoBuffer2, 0, 2); vyF = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0); vyF /= 0xFFFF; vEnum.Add(vyF);
                        bfs.Read(infoBuffer2, 0, 2); vzF = BitConverter.ToUInt16(mh.ArrayReverse(infoBuffer2), 0); vzF /= 0xFFFF; vEnum.Add(vzF);
                        vList0.Add(vEnum);
                    }
                    string outputPath = bfi.DirectoryName + "\\" + Path.GetFileNameWithoutExtension(bfi.Name) + "_extracted";
                    Directory.CreateDirectory(outputPath);
                    ow.writeSpecifiedObjFile(vList0, ref bfi, ref bfi, 1, bfi.Name, "_" + j.ToString() + "_" + sTable1[i][0].ToString("X"));
                }

            }
        }

        //USE FOR TEXTURE DATA MAYBE
        //bfs.Seek(sAddress4, SeekOrigin.Begin); //Texture Data

        bp++;

        bfs.Close();
    }
}

```
## Post #107
- Username: cornal
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Oct 25, 2014 10:31 am
- Post datetime: 2014-10-25T04:20:49+00:00
- Post Title: Re: Gran Turismo 6 Models

Hi, I'm new here only a question GTTools runs on Win8.1? because I can't run it.
And other thing I decompress some .pkg's from GT6 updates this shows directories similar to the game directory, but in a folder named USRDIR shows more folders containing files without extensions.
I like somebody can help with this. Thanks.
## Post #108
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-10-25T12:16:12+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from EcheloCross
>
> Here is my code so far for handling the MDL3 files.  If you read through it you can either copy it to a c# program of your own, or re-write it in the language of your choice.

This code handles both the 2nd highest lod, and the vertices only of the highest lod.  The faces for the highest lod are edge compressed, I need to spend some more time with edge to get them figured out.

So,as far as i understand,i use offzip to extract data from body_s,and then your script should do the job and make an .OBJ file of a car like this one?  
[](http://www.imagebam.com/image/363ca6360009622) 

If so,could you tell me please,in which programm should I run this C# script?

Also,I've been sucsessfully using offzip many times before,but right now I'm making a mistake,can you help me to slove it?  
[](http://www.imagebam.com/image/3492e2360009618) 
[](http://www.imagebam.com/image/de7ae5360009617)
## Post #109
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-10-25T16:39:38+00:00
- Post Title: Re: Gran Turismo 6 Models

No you do not use offzip.  You need to make a new c# program (with Visual Studio) and use that function in it.  It will not work right out of the box either, you must provide your own objWriter method, and add DotNetZip's compression namespace to your program as well. Also, make a public byte[] called ArrayReverse and make it return the reversed byte[] that is passed to it. (Just for endianness).

The body_s sections can be compressed, and can be raw.  The code will get all the compressed and raw chunks out and merge them to a body_s.bin file.  The offzip method will miss the raw chunks.

Here is the ArrayReverse method:

```
{
    Array.Reverse(array);
    return array;
}

```


Here are some of my objWriter methods: (the ones this code calls)

```
public void writeSpecifiedObjFile(
    List<List<float>> posList,
    List<List<ushort>> idxListUshort,
    List<List<ulong>> idxListUlong,
    ref FileInfo vfi,
    ref FileInfo ffi,
    int vertexOrderIndex,
    string outputName,
    string meshName,
    int facesMethod)
{
    StreamWriter objSw = new StreamWriter(
        vfi.DirectoryName + "\\" +
        Path.GetFileNameWithoutExtension(outputName) + "_extracted\\" +
        Path.GetFileNameWithoutExtension(outputName) + meshName +
        ".obj");
    foreach (List<float> lf in posList)
    {
        string x, y, z;
        if (lf[0].ToString().Contains("E") == true)
        {
            x = lf[0].ToString("F9");
        }
        else
        {
            x = lf[0].ToString();
        }
        if (lf[1].ToString().Contains("E"))
        {
            y = lf[1].ToString("F9");
        }
        else
        {
            y = lf[1].ToString();
        }
        if (lf[2].ToString().Contains("E"))
        {
            z = lf[2].ToString("F9");
        }
        else
        {
            z = lf[2].ToString();
        }
        if (vertexOrderIndex == 0)
        {
            objSw.WriteLine("v " + x + " " + y + " " + z);
        }
        if (vertexOrderIndex == 1)
        {
            objSw.WriteLine("v " + x + " " + z + " " + y);
        }
        if (vertexOrderIndex == 2)
        {
            objSw.WriteLine("v " + y + " " + x + " " + z);
        }
        if (vertexOrderIndex == 3)
        {
            objSw.WriteLine("v " + y + " " + z + " " + x);
        }
        if (vertexOrderIndex == 4)
        {
            objSw.WriteLine("v " + z + " " + x + " " + y);
        }
        if (vertexOrderIndex == 5)
        {
            objSw.WriteLine("v " + z + " " + y + " " + x);
        }
    }
    objSw.WriteLine("g " + ffi.Name);
    //objSw.WriteLine("usemtl " + matList[(int)objGeoSubCountCounter].ToString()); //Add .mtl generation in the future
    if (facesMethod == 0 || facesMethod == 2 || facesMethod == 3) //USHORT or TRI-STRIP or Generated faces
    {
        foreach (List<ushort> lS in idxListUshort)
        {
            objSw.WriteLine("f  " + (lS[0] + 1).ToString() + "/" + (lS[0] + 1).ToString() + "/" + (lS[0] + 1).ToString() + " "
                                  + (lS[1] + 1).ToString() + "/" + (lS[1] + 1).ToString() + "/" + (lS[1] + 1).ToString() + " "
                                  + (lS[2] + 1).ToString() + "/" + (lS[2] + 1).ToString() + "/" + (lS[2] + 1).ToString());
        }
    }
    if (facesMethod == 1 || facesMethod == 4) //ULONG or (24bit as ULONG)
    {
        foreach (List<ulong> lL in idxListUlong)
        {
            objSw.WriteLine("f  " + (lL[0] + 1).ToString() + "/" + (lL[0] + 1).ToString() + "/" + (lL[0] + 1).ToString() + " "
                                  + (lL[1] + 1).ToString() + "/" + (lL[1] + 1).ToString() + "/" + (lL[1] + 1).ToString() + " "
                                  + (lL[2] + 1).ToString() + "/" + (lL[2] + 1).ToString() + "/" + (lL[2] + 1).ToString());
        }
    }
    objSw.Close();
}


//generic no faces
public void writeSpecifiedObjFile(
    List<List<float>> posList,
    ref FileInfo vfi,
    ref FileInfo ffi,
    int vertexOrderIndex,
    string outputName,
    string meshName)
{
    StreamWriter objSw = new StreamWriter(
        vfi.DirectoryName + "\\" +
        Path.GetFileNameWithoutExtension(outputName) + "_extracted\\" +
        Path.GetFileNameWithoutExtension(outputName) + meshName +
        ".obj");
    foreach (List<float> lf in posList)
    {
        string x, y, z;
        if (lf[0].ToString().Contains("E") == true)
        {
            x = lf[0].ToString("F9");
        }
        else
        {
            x = lf[0].ToString();
        }
        if (lf[1].ToString().Contains("E"))
        {
            y = lf[1].ToString("F9");
        }
        else
        {
            y = lf[1].ToString();
        }
        if (lf[2].ToString().Contains("E"))
        {
            z = lf[2].ToString("F9");
        }
        else
        {
            z = lf[2].ToString();
        }
        if (vertexOrderIndex == 0)
        {
            objSw.WriteLine("v " + x + " " + y + " " + z);
        }
        if (vertexOrderIndex == 1)
        {
            objSw.WriteLine("v " + x + " " + z + " " + y);
        }
        if (vertexOrderIndex == 2)
        {
            objSw.WriteLine("v " + y + " " + x + " " + z);
        }
        if (vertexOrderIndex == 3)
        {
            objSw.WriteLine("v " + y + " " + z + " " + x);
        }
        if (vertexOrderIndex == 4)
        {
            objSw.WriteLine("v " + z + " " + x + " " + y);
        }
        if (vertexOrderIndex == 5)
        {
            objSw.WriteLine("v " + z + " " + y + " " + x);
        }
    }
    objSw.WriteLine("g " + ffi.Name);
    objSw.Close();
}

```


DotNetZip is open source and is easily addable to any c# program.  You can also use anything that supports Deflate.

Have fun.
## Post #110
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-10-25T18:15:17+00:00
- Post Title: Re: Gran Turismo 6 Models

Thanks, but what about the ReadString method?
## Post #111
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-10-25T18:31:49+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from barti
>
> Thanks, but what about the ReadString method?

```
public string readString(ref FileStream fs, uint specifiedAddress)
{
    string stringToBuild = String.Empty;
    bool endReached = false;
    fs.Seek(specifiedAddress, SeekOrigin.Begin);
    fs.Read(infoBuffer1, 0, 1);
    stringToBuild += Encoding.ASCII.GetString(infoBuffer1);
    while (endReached == false)
    {
        fs.Read(infoBuffer1, 0, 1);
        if (infoBuffer1[0] == 0)
        {
            endReached = true;
        }
        else
        {
            stringToBuild += Encoding.ASCII.GetString(infoBuffer1);
        }
    }
    return stringToBuild;
}

```
## Post #112
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-10-25T20:32:51+00:00
- Post Title: Re: Gran Turismo 6 Models

Thank you, it works now 




Here's a simple pre-built converter in case anyone needs it (requires .NET Framework 4.0):

```
http://speedy.sh/3hJvz/gt6.zip
```
## Post #113
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-10-26T09:46:07+00:00
- Post Title: Re: Gran Turismo 6 Models

Great progress,guys!  

Now,let's see if we can get semi-standart car out in highest lod! 

Standart:Cars ported to GT6 from GT3\4 (Low-poly,about 4000 polygons,poor detail nowadays,no interior)
Elite:Cars made for GT5\GT6 (High-poly,incredeble detail,Interior)

And in GT6 they have kinda semi-standart cars:Remastered cars from GT3\GT4(Mid-High poly,Very good detail,no interior,look at page 7)

As I can see,there's no problem with getting highest lod from a standart car(Mazda rx-8 from previous post) so I'm curious to see if It's the same for semi-standarts(Like Nissan gt-r from page 7)

So,can anybody try it out with this car?

```
230	      30109   836    Nissan       SKYLINE 2000GT-R (KPGC110) '73
```


There's a lot of remastered,semi-standart cars,I'll provide list soon
## Post #114
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-10-26T11:26:33+00:00
- Post Title: Re: Gran Turismo 6 Models

Hm that pre-built extractor doesn't work for me. What do I do wrong?



great progress and thanks to all for the hard work
## Post #115
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-10-26T12:04:46+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from TomWin
>
> Hm that pre-built extractor doesn't work for me. What do I do wrong?

great progress and thanks to all for the hard work

Load "body", not "body_s".
## Post #116
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-10-26T12:59:48+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from barti
>
> TomWin wrote:Hm that pre-built extractor doesn't work for me. What do I do wrong?

great progress and thanks to all for the hard work

Load "body", not "body_s".

Same happens to me,no matter if it's body or body_s   

[](http://www.imagebam.com/image/aba82d360244676)
## Post #117
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-10-26T13:11:01+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from Ferrari formula 1
>
> Same happens to me,no matter if it's body or body_s

Your error message is different. It says it can't open / find the "body_s" file. Are you sure it's there?
## Post #118
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-10-26T13:42:27+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from barti
>
> Ferrari formula 1 wrote:Same happens to me,no matter if it's body or body_s  

Your error message is different. It says it can't open / find the "body_s" file. Are you sure it's there?

Aaaahh,now I see the problem...
Well,it made up a bunch of obj files,but i can"t open them all together(at once)
I tried about 10 separated files,but they were blank or strange flat surfaces 
EDIT:
Still doesn't works for me,i have no parts of car in result.

Got only BIN (donno what to do with it) and a lot of OBJ(1-11 kb each,can't open in 3ds max,in cinema 4d it's strange surfaces or nothing at all.however,it tells me that data contains 240 polygons)
## Post #119
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-10-26T14:35:12+00:00
- Post Title: Re: Gran Turismo 6 Models

From what I understand, high LOD cars are stored in different format. So far only vertices can be extracted from them (no faces), and they're scaled incorrectly. I accidentally forgot to include the code for extracting them, but this may be the reason why there are only flat surfaces on some models. If you have a "hq" and "race" folder, try the "body" file from both of them.

I'll see how I can edit the OBJ Writer to reduce the number of .obj files.
## Post #120
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-10-26T14:51:25+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from barti
>
> From what I understand, high LOD cars are stored in different format. So far only vertices can be extracted from them (no faces), and they're scaled incorrectly. I accidentally forgot to include the code for extracting them, but this may be the reason why there are only flat surfaces on some models. If you have a "hq" and "race" folder, try the "body" file from both of them.

I'll see how I can edit the OBJ Writer to reduce the number of .obj files.

There's a problem with that:If I write to open body from hq\race folder,it extracts body_s anyway.
I can't open obj files in 3ds max.

This is what happens when I open body (not body_s)
None of extractet OBJ files can't be opened in 3ds max
[](http://www.imagebam.com/image/aaf059360263910)
## Post #121
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-10-26T16:10:17+00:00
- Post Title: Re: Gran Turismo 6 Models

I see now - Max won't load the models correctly for some reason. I'll try to fix this, but in the meantime use Blender instead.
## Post #122
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-10-26T16:52:00+00:00
- Post Title: Re: Gran Turismo 6 Models

Now it works!  
Downloading GT6 to test some things :3

[](http://www.imagebam.com/image/e8e111360282324)
## Post #123
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-10-26T20:35:53+00:00
- Post Title: Re: Gran Turismo 6 Models

Indeed all is flat and there are many tiny obj files
## Post #124
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-10-27T14:26:25+00:00
- Post Title: Re: Gran Turismo 6 Models

All right,well,I tried semi-standart car,but it gave me no result.(at least,not what's the game model is)
But right now I'm pretty sure that it's just a small piece of data we're looking for,because extracted meshes(of the car body) were called "Shadow" ,and it means that game uses this low-poly model to produce shadows(means this mesh is invisible in the game)

Here are shots of what I get - 3 absolutely same meshes called "Shasow" 2 from "HQ" and one from "race" for some reason.
[](http://www.imagebam.com/image/fedd96360518362) 

Here it is,take a look at this semi-standart car  

[http://www.mediafire.com/download/h99rx ... 0/30109.7z](http://www.mediafire.com/download/h99rx9m5a355fg0/30109.7z)
## Post #125
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-10-27T22:27:24+00:00
- Post Title: Re: Gran Turismo 6 Models

From what I see, this C# function can only import shadow mesh, bounding boxes, some planes and High LOD vertices.
High LOD are not only for premium cars, but they're the actual mesh of every car. So for now, the only fully extractable car mesh is the shadow.

High LOD vertices can be loaded into a point cloud, but then the model isn't scaled correctly and doesn't have faces or UVs.
Creating faces and UVs on your own would be a long and tedious (if not impossible) task.
So we can only hope that the way of storing High LOD faces and UVs will be decoded someday.
## Post #126
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-10-28T16:04:42+00:00
- Post Title: Re: Gran Turismo 6 Models

Open multiple .obj scripts

maxscript: (will use the settings from the last single .obj import)

```
    result = theDialog.showDialog() 
    result.ToString() 
    result.Equals result.OK 
    result.Equals result.Cancel 
	--theDialog.RootFolder = dotNetObject "System.Environment.SpecialFolder.Personal"
    objPath = theDialog.SelectedPath
	
files = getFiles (objPath + "\\*.obj")

for f in files do (
	
	importFile f #noprompt
	
) 

```


blender script:

```
import bpy

# put the location to the folder where the objs are located here in this fashion
# path_to_obj_dir = os.path.join('C:\\', 'Users', 'YOUR_NAME', 'Desktop', 'OBJS')
path_to_obj_dir = os.path.join('C:\\', 'gtvol', 'car', '0140', '0001', 'hq', 'body_s_extracted')

# get list of all files in directory
file_list = sorted(os.listdir(path_to_obj_dir))

# get a list of files ending in 'obj'
obj_list = [item for item in file_list if item[-3:] == 'obj']

# loop through the strings in obj_list and add the files to the scene
for item in obj_list:
    path_to_file = os.path.join(path_to_obj_dir, item)
    bpy.ops.import_scene.obj(filepath = path_to_file)

```
## Post #127
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-10-28T16:18:56+00:00
- Post Title: Re: Gran Turismo 6 Models

Highest LOD faces are edge compressed.

in 30109\hq\body_s.bin (the file provided above), examples can be seen at 0xE570, 0x12378, 0x14848, 0x166B0, 0x191C8, 0x19D90, 0x1CF58, 0x1F070, 0x1FC80, and many more...

Anyone willing to give them a whirl?
## Post #128
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-10-31T15:35:28+00:00
- Post Title: Re: Gran Turismo 6 Models

Polyphony Digital Official pictures from the announsment of GT6  
[](http://www.imagebam.com/image/fb0df8361329292) [](http://www.imagebam.com/image/1c2e85361329293) [](http://www.imagebam.com/image/ba2bf8361329301) [](http://www.imagebam.com/image/775eb2361329303) [](http://www.imagebam.com/image/4b0da4361329307) [](http://www.imagebam.com/image/13e794361329311)
## Post #129
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-31T16:05:56+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from EcheloCross
>
> Highest LOD faces are edge compressed.

in 30109\hq\body_s.bin (the file provided above), examples can be seen at 0xE570, 0x12378, 0x14848, 0x166B0, 0x191C8, 0x19D90, 0x1CF58, 0x1F070, 0x1FC80, and many more...

Anyone willing to give them a whirl?Only tool I know supporting edge decompression is Noesis (rapi.decompressEdgeIndices()) but I can't get decent face indices.
## Post #130
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-11-01T10:13:17+00:00
- Post Title: Re: Gran Turismo 6 Models

I found some shots taken from Polyphony Digital studio.  

Seems like they're using Maya 2012 to model their cars and prepare them for the game,because shaders look identical to the in-game one's

The name of the file on the picture is strange:
Z:\GTcar\Geheimnis\dsgwg79\Toyota_2011_FT86_HIRATSUKA_licenes\BRZ_sti_concept_\for_event_00.mb


[](http://www.imagebam.com/image/34dbf9361481428) [](http://www.imagebam.com/image/7e9fa2361481474) [](http://www.imagebam.com/image/bb7676361481480) [](http://www.imagebam.com/image/6d975d361481487) [](http://www.imagebam.com/image/bd7ffa361481493)[](http://www.imagebam.com/image/fc1945361486221)
## Post #131
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-11-01T18:51:14+00:00
- Post Title: Re: Gran Turismo 6 Models

Here's GT6Extract with the High LOD Vertices extraction I accidentally removed:
[https://www.sendspace.com/file/tt5zgo](https://www.sendspace.com/file/tt5zgo)

It seems to have problems on premium cars (at least some of them), so keep the old version.
## Post #132
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-11-02T12:47:48+00:00
- Post Title: Re: Gran Turismo 6 Models

hm, it doesn't work well with all models. no UV map yet.

Can I ask where to find cars textures?
## Post #133
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-11-03T19:13:16+00:00
- Post Title: Re: Gran Turismo 6 Models

Mabye we can extract UV's?  

I've got standart car and I can remap it by myself,because I ripped textures from GT4(PS2)
But scince it's a solid piece(I mean,body in GT4 consists of 50-60 parts,and here it has only 8 parts) I beleive they made new textures from the old ones and new UV'S  

Any ideas,gentelmen?  

[](http://www.imagebam.com/image/7c7ad6361995793) 

[](http://www.imagebam.com/image/0b359c361996463) 

Car:

[http://www.mediafire.com/download/kiaz6 ... %282%29.7z](http://www.mediafire.com/download/kiaz6mx4leh58b1/01640001%282%29.7z)
## Post #134
- Username: JimmyTheFox
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jan 30, 2011 10:33 pm
- Post datetime: 2014-11-07T23:41:24+00:00
- Post Title: Re: Gran Turismo 6 Models

Is it possible to extract the car thumbnails, course maps and logos? 

Any help would be appreciated, the course stuff are .img files and the car thumbnails have no extension, though the 15th anniversary cars are viewable .pngs, I've tried adding .png to the end of the others but no dice.
## Post #135
- Username: xfile
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 15, 2014 1:30 pm
- Post datetime: 2014-11-08T15:18:50+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from JimmyTheFox
>
> Is it possible to extract the car thumbnails, course maps and logos? 

Any help would be appreciated, the course stuff are .img files and the car thumbnails have no extension, though the 15th anniversary cars are viewable .pngs, I've tried adding .png to the end of the others but no dice.

Chipicao made TXS2DDS tool which can do it. It's on page 5. You could have found your answer with a bit of search
## Post #136
- Username: JimmyTheFox
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jan 30, 2011 10:33 pm
- Post datetime: 2014-11-13T16:27:53+00:00
- Post Title: Re: Gran Turismo 6 Models

I missed that 

Is it possible to access the same stuff in the game update files, it seems everything is split into smaller chunks and spread across different files?

The latest update for the game with Polyphony's file structure for game update install: 

9MB - [http://b0.ww.np.dl.playstation.net/tppk ... 100-PE.pkg](http://b0.ww.np.dl.playstation.net/tppkg/np/BCES01893/BCES01893_T183/7559e518addf0e37/EP9001-BCES01893_00-0000000000000000-A0113-V0100-PE.pkg)
## Post #137
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-11-26T21:17:10+00:00
- Post Title: Re: Gran Turismo 6 Models

...any news on track mesh extraction?

Cheers...
## Post #138
- Username: JimmyTheFox
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jan 30, 2011 10:33 pm
- Post datetime: 2015-01-12T19:14:28+00:00
- Post Title: Re: Gran Turismo 6 Models

Could somebody please advise how to use Flatz's GTtool to correctly unpack the cache system present in the game update packages?

> Also I've reversed their cache system with such weird naming system (K/H/A3 and so on), you can find all needed functions for them too.

> My tool can handle both things: HDD cache and specdb (and more). You just need to look carefully into original forum thread, I've released them too.
## Post #139
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2015-02-09T20:53:19+00:00
- Post Title: Re: Gran Turismo 6 Models

I don't want to annoy the people involved in this sweet project with the typical question, but I wonder if you guys have any news regarding the progress of the ripping process 

Cheers!
## Post #140
- Username: mus001
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Dec 12, 2011 2:28 am
- Post datetime: 2015-02-15T19:57:29+00:00
- Post Title: Re: Gran Turismo 6 Models

hey guys i'm trying to open gt6.vol but i have a problem the cmd window (gttool) closing please guys someone can to extract me the nismo 270r and nimo 400r models. there are 2 standard models please please
## Post #141
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2015-03-12T14:50:18+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from mus001
>
> hey guys i'm trying to open gt6.vol but i have a problem the cmd window (gttool) closing please guys someone can to extract me the nismo 270r and nimo 400r models. there are 2 standard models please please
are you just clicking the file and a cmd window opens then closes? or are you actually opening a proper cmd window. many people claim (not just for gt6 but for many different things) the window just opens then closes.  THEN you find out they didnt actually open a cmd window, they just let the app do its thing, which is the wrong way to do it..
## Post #142
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2015-03-30T14:54:57+00:00
- Post Title: Re: Gran Turismo 6 Models

How is going? i hope someday can rip models with some tool from GT5/6 like Forza Studio.
## Post #143
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2015-04-11T19:27:59+00:00
- Post Title: Re: Gran Turismo 6 Models

...any news in this field?

Just wondering if there was any progress regarding 3D models of cars and tracks?

Cheers...
## Post #144
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2015-04-19T16:37:32+00:00
- Post Title: Re: Gran Turismo 6 Models

I tried the gttool using a .cmd and write gttool GT.VOL GT6 E:\Descargas\JUEGOS PC\Gran Turismo 6\BCES01893\PS3_GAME\USRDIR but don't extract anything  

Edit: Fixed it need EXTRACT not something like a large location
## Post #145
- Username: JimmyTheFox
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jan 30, 2011 10:33 pm
- Post datetime: 2015-05-28T18:00:48+00:00
- Post Title: Re: Gran Turismo 6 Models

Somebody please help me with the PDIPFS folder and Flatz's tool
## Post #146
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2015-06-06T18:06:23+00:00
- Post Title: Re: Gran Turismo 6 Models

...any progress here?
## Post #147
- Username: nm69
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon May 03, 2010 5:12 pm
- Post datetime: 2015-06-27T07:32:47+00:00
- Post Title: Re: Gran Turismo 6 Models

Bump.  Any progress here?
## Post #148
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-07-12T17:16:27+00:00
- Post Title: Re: Gran Turismo 6 Models

Still waiting for more progress here. This shouldn't be dead, right?
## Post #149
- Username: cornal
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Oct 25, 2014 10:31 am
- Post datetime: 2015-07-20T05:40:57+00:00
- Post Title: Re: Gran Turismo 6 Models

For those that don't know how f..... works GTTOOL here's a tutorial:

1.- huge your pet.
2.- open cmd
3.- drag on cmd: gttool, gt.vol, write gt5 or gt6 depending the game that you extracting, and for last the output folder where the files can be stored. 

EXAMPLE:

C:\USERS\XXXXX\GTTOOL.EXE GT.VOL GT5 OUTPUT FOLDER


For each parameter you must give a space 
Example Style Matrix:  

C:\USERS\NEO\GTTOOL.EXE[space]GT.VOL[space]GT5orGT6[space]output folder

4.- press ENTER
5.- wait 30 minutes untill all be extracted (going out with your girlfriend, come out to see the birds fly, or prepare you a sandwich)  

6.- After what the time has passed, cmd put this message: "All files has been extracted"

WARNING: FOR THE EXTRACTION YOU MUST HAVE 30GBs OF SPACE IN YOUR HDD AND A LITTLE BIT OF PATIENCE  

And voala the gt.vol has been opened.

Hope too much people come to join us to the development of extraction tools for this game

BYE AND THANKS FOR READ!!!!!!
## Post #150
- Username: natsuki
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 23, 2012 2:19 am
- Post datetime: 2015-07-26T01:35:29+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from cornal
>
> For those that don't know how f..... works GTTOOL here's a tutorial:

1.- huge your pet.
2.- open cmd
3.- drag on cmd: gttool, gt.vol, write gt5 or gt6 depending the game that you extracting, and for last the output folder where the files can be stored. 

EXAMPLE:

C:\USERS\XXXXX\GTTOOL.EXE GT.VOL GT5 OUTPUT FOLDER


For each parameter you must give a space 
Example Style Matrix:  

C:\USERS\NEO\GTTOOL.EXE[space]GT.VOL[space]GT5orGT6[space]output folder

4.- press ENTER
5.- wait 30 minutes untill all be extracted (going out with your girlfriend, come out to see the birds fly, or prepare you a sandwich)  

6.- After what the time has passed, cmd put this message: "All files has been extracted"

WARNING: FOR THE EXTRACTION YOU MUST HAVE 30GBs OF SPACE IN YOUR HDD AND A LITTLE BIT OF PATIENCE  

And voala the gt.vol has been opened.

Hope too much people come to join us to the development of extraction tools for this game

BYE AND THANKS FOR READ!!!!!!
thanks cornal.
I'm successful ripping from body_s file.



gt6.jpg (34.25 KiB) Viewed 309 times


but,I wanna track mash data. 
but I don't know how to ripping of this.(Cxxx.shapestream?)
tell me about it??


.
## Post #151
- Username: nm69
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon May 03, 2010 5:12 pm
- Post datetime: 2015-09-11T05:37:55+00:00
- Post Title: Re: Gran Turismo 6 Models

Bump.  Any progress here?
## Post #152
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2015-11-14T15:41:35+00:00
- Post Title: Re: Gran Turismo 6 Models

Any updates? More than an year passed, what happened guys?
## Post #153
- Username: asylum
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 11, 2015 4:10 am
- Post datetime: 2016-02-10T12:36:35+00:00
- Post Title: Re: Gran Turismo 6 Models

Perhaps someone has unpacked DB0106.dat? or a table of sounds? It is very difficult to find the right set of sound from 619 files.
## Post #154
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2016-03-23T16:22:41+00:00
- Post Title: Re: Gran Turismo 6 Models

Oh god. Don't tell me that it stopped here. Please don't. Someone with the proper knowledge and experience, please come and make this project a reality!
## Post #155
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2016-03-24T23:55:32+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from REDZOEU
>
> Oh god. Don't tell me that it stopped here. Please don't. Someone with the proper knowledge and experience, please come and make this project a reality!

People involved looks like being apparently scared of doing something so massive and epic
## Post #156
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-03-25T05:42:11+00:00
- Post Title: Re: Gran Turismo 6 Models

From my experience a request like "any progress here?" leads to nothing. In any thread.
In short: no valuable input, no output.
## Post #157
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2016-03-25T13:18:38+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from shakotay2
>
> From my experience a request like "any progress here?" leads to nothing. In any thread.
In short: no valuable input, no output.
Can't argue with that. One hell of a strong point there.
## Post #158
- Username: mmtes
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 05, 2016 1:42 am
- Post datetime: 2017-02-17T12:52:22+00:00
- Post Title: Re: Gran Turismo 6 Models

I contacted with Flatz, and finally found TXS2DDS and Flatz GTTool.

TXS2DDS: [https://drive.google.com/file/d/0B6iBcy ... sp=sharing](https://drive.google.com/file/d/0B6iBcyr47y2UUkxpVHdIS2dPZGc/view?usp=sharing)
GTTools: [https://drive.google.com/file/d/0B6iBcy ... sp=sharing](https://drive.google.com/file/d/0B6iBcyr47y2UdzhtSGM0T1E4ZEU/view?usp=sharing)

I hope someone can make possible to convert 3d models from Gran Turismo 6....
## Post #159
- Username: oldman
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 19, 2017 2:54 am
- Post datetime: 2017-06-18T19:06:29+00:00
- Post Title: Re: Gran Turismo 6 Models

Hello dear fellow man.

I'm new to the forum

I'm looking for the GTTool

I searched this forum and found only the GT6extract tool
Gt6extract is worthless without GTtool to unpack the GT.VOL

I used Google and looked up and down. No useful infomation.

Then I hit my head on the keyboard. no help   

Can anyone help ???

Thanks for reading

Text is translated with Google. English is not my native language.
## Post #160
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-06-18T20:21:59+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from oldman
>
> I'm looking for the GTTool

I searched this forum and found onlyHello,
[viewtopic.php?f=16&t=11783&p=97169&hilit=gttool#p97169](http://forum.xentax.com/viewtopic.php?f=16&t=11783&p=97169&hilit=gttool#p97169)
The exe is in the bin\Release folder.
(If it doesn't run on your system you're required to compile the source.)
## Post #161
- Username: oldman
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 19, 2017 2:54 am
- Post datetime: 2017-06-18T22:07:25+00:00
- Post Title: Re: Gran Turismo 6 Models

Many thanks for your effort.

You are my hero   

I have very long time always read without account from the outside
And could not see the hidden file.   
That is why I abandoned the search because I thought Gttool does not exist anymore.

thank you again


Text is main with Google. English is not my native language.
## Post #162
- Username: SausageBoy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 08, 2017 4:32 am
- Post datetime: 2017-07-07T21:56:15+00:00
- Post Title: Re: Gran Turismo 6 Models

this is dead? i want to rip a Z31 Fairlady model from GT5 or GT6 someone can make me the favor or give me some tips to do it? i tryed with GT4 files but i cant get the .CAR and .PAT files i get just one Dat file and this one is broken in gran turismo viewer, tryed with a quick bms plugin but didnt recognize the file, any help in that? thanks
## Post #163
- Username: mmtes
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 05, 2016 1:42 am
- Post datetime: 2017-08-17T21:15:52+00:00
- Post Title: Re: Gran Turismo 6 Models

any progress?
## Post #164
- Username: medwed
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Sep 03, 2010 3:45 pm
- Post datetime: 2017-08-26T18:28:29+00:00
- Post Title: Re: Gran Turismo 6 Models

Hm ...  [https://plus.google.com/+%C3%81d%C3%A1m ... 9DsaRRznY3](https://plus.google.com/+%C3%81d%C3%A1mPajor/posts/c9DsaRRznY3)
## Post #165
- Username: Pix
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Nov 18, 2016 7:23 am
- Post datetime: 2017-12-20T05:52:02+00:00
- Post Title: Re: Gran Turismo 6 Models

could someone do a tutorial because i hardly understand anything.
i can't seem to find an ISO for gran turismo 5/6
thanks
## Post #166
- Username: johnwalter1044
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 20, 2018 12:21 am
- Post datetime: 2018-01-19T16:53:19+00:00
- Post Title: Re: Gran Turismo 6 Models

Hello, new on the forum.

So i got everything i need to extract the GT6.VOL.

So i typed this into CMD:

C:\Users\Korisnik>"D:\IVAN\Ivans\Games\GT6 Audio\gttool\bin\Release\gttool.exe" "D:\IVAN\Ivans\Games\GT6 Audio\volum\GT.VOL" "GT6" "D:\IVAN\Ivans\Games\GT6 Audio\volum\VOLUME 2"

And i get this:

"Unable to process volume file."

Please help.

EDIT: You know, the funny thing is, i only want to rip a song from the game. Which means it would probably be easier to ask if anyone has the files extracted already and if you can send me the song?

I want the Camo&Krooked - Aurora, GT6's Red Bull Main Menu Theme. Gt6 is the only media to have the song instrumental version.
## Post #167
- Username: johnwalter1044
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 20, 2018 12:21 am
- Post datetime: 2018-01-19T17:27:46+00:00
- Post Title: Re: Gran Turismo 6 Models

UPDATE: I managed to get a new message, this time Windows 10 popped a message saying:

This App wont run on your PC 

CMD:

Access is denied.

Tried opening cmd.exe by "Run as an Administrator"

Same as above:

Access is denied
## Post #168
- Username: medwed
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Sep 03, 2010 3:45 pm
- Post datetime: 2018-06-19T11:23:32+00:00
- Post Title: Re: Gran Turismo 6 Models

UModel now supports Playstation 3 and 4 game textures. More details here:[http://www.gildor.org/smf/index.php/top ... l#msg29005](http://www.gildor.org/smf/index.php/topic,2583.msg29005.html#msg29005)
## Post #169
- Username: solidpoke412
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 15, 2018 9:37 am
- Post datetime: 2018-09-18T14:28:59+00:00
- Post Title: Re: Gran Turismo 6 Models

BTW there is a new discord for GT Sport / other GT related research...
[watermark.png](https://xentaxbackup.github.io/file/14882_watermark.png)
## Post #170
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2018-09-19T11:05:20+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from solidpoke412
>
> medwed wrote:UModel now supports Playstation 3 and 4 game textures. More details here:http://www.gildor.org/smf/index.php/top ... l#msg29005

btw there is a new discord for GT Sport / other GT related research https://discord.gg/3jhrX7

 Says invite is invalid. I'd love to see what's going on with GT sport. Their models this time around would be fantastic to study or play around with in other games.
## Post #171
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2018-09-19T16:51:53+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from solidpoke412
>
> 
btw there is a new discord for GT Sport / other GT related research https://discord.gg/3jhrX7

Invite expired. Could you send another one?
## Post #172
- Username: solidpoke412
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 15, 2018 9:37 am
- Post datetime: 2018-09-22T10:55:39+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from REDZOEU
>
> solidpoke412 wrote:
btw there is a new discord for GT Sport / other GT related research https://discord.gg/3jhrX7

Invite expired. Could you send another one?
[https://discord.gg/c5ggHSq](https://discord.gg/c5ggHSq)
sorry i had forgotten to make it a forever link instead of 1 day expiry default...
it's a fairly new discord but we already have some good people who've been toying with various GT games for years..
keen as to get FLATZ on there too...
## Post #173
- Username: djibsone2
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Dec 21, 2016 10:15 am
- Post datetime: 2018-10-11T23:12:46+00:00
- Post Title: Re: Gran Turismo 6 Models

hello every body thank you for your big job 

please tried for extract the gran turismo psp models with jpcsp on obj .. the models is ready 
but the problem has that more than 1500 multy material object. and I do not know how to remove the objects the first layer uv black for the reflection of the car

I downloaded the models available on gamemodels ru and I contaste that the models and only 30/40 oibject after converting .please a tutorial for open the GT.vol PSP VERSION THANK YOU FOR YOUR HELP
## Post #174
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-11-24T17:25:32+00:00
- Post Title: Re: Gran Turismo 6 Models

I finally found some time to look at GT6 formats. Yes, they are non-standard indeed. This is an example.
## Post #175
- Username: medwed
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Sep 03, 2010 3:45 pm
- Post datetime: 2018-11-25T16:45:24+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from daemon1
>
> I finally found some time to look at GT6 formats. Yes, they are non-standard indeed. This is an example.

Wow! Kubelwagen and VW typ 166 Schwimmwagen from GT6 BIG Please  
 How do you do that ? THX !!!
## Post #176
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-11-26T06:34:23+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from medwed
>
>  How do you do that ? THX !!!
I'm making a tool to convert all GT6 cars.
## Post #177
- Username: medwed
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Sep 03, 2010 3:45 pm
- Post datetime: 2018-11-26T10:30:58+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from daemon1
>
> medwed wrote: How do you do that ? THX !!!
I'm making a tool to convert all GT6 cars.

Wow! Respect ! Unfortunately, I do not have this game.
Can you send me the files of these two models?
Kubelwagen and VW typ 166 Schwimmwagen.
Thank You for your time and help
## Post #178
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-11-27T11:01:41+00:00
- Post Title: Re: Gran Turismo 6 Models

No, I can't send you any files. Go to GT discord, people will be able to help you there.

Meanwhile I continue work on the format. The game is using 2 main formats for models: usual meshes (triangulated) and tesselation-ready meshes using quads. Here are some examples of WIP:









Total vert count for this car is about 130.000
## Post #179
- Username: jaimetal20
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 03, 2015 5:41 am
- Post datetime: 2018-11-30T22:22:44+00:00
- Post Title: Re: Gran Turismo 6 Models

Hey guys can you please provide a working link to the discord server?
## Post #180
- Username: verde57
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Sep 03, 2017 4:53 pm
- Post datetime: 2018-12-28T18:42:06+00:00
- Post Title: Re: Gran Turismo 6 Models

Can cars from GT6 be ripped with the tool daemon1 made?
how about GT5?
## Post #181
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-12-28T21:42:19+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from verde57
>
> Can cars from GT6 be ripped with the tool daemon1 made?
how about GT5?
Which tool, here is no specific tool for the GT6 game yet, and if there where one, GT5 would have not being supported since GT6 already has all cars from previous game, and before, thus would have been a waste of time in reversing it.
## Post #182
- Username: verde57
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Sep 03, 2017 4:53 pm
- Post datetime: 2018-12-29T07:59:28+00:00
- Post Title: Re: Gran Turismo 6 Models

at least GT5 does not have tesselation on its models, although it is an old game so maybe the models are  low poly count.
What is a good pkg ripper for GT6?
## Post #183
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-12-29T23:53:55+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from verde57
>
> What is a good pkg ripper for GT6?
You meant to say PS3 PKG extractor maybe? There are plenty options out there.
If that is what you meant then I recommend: [PkgView v1.3](https://foro.ifcaro.net/pkgview-v1-2-t193.html)
## Post #184
- Username: bmw30
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Feb 26, 2018 11:11 pm
- Post datetime: 2019-03-20T22:22:57+00:00
- Post Title: Re: Gran Turismo 6 Models

hello there al is there any news on the new tool is it stil in work progress ?
## Post #185
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-03-21T04:18:14+00:00
- Post Title: Re: Gran Turismo 6 Models

the work on GT6 tool is suspended indefinitely
because i had to work on other games
## Post #186
- Username: bmw30
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Feb 26, 2018 11:11 pm
- Post datetime: 2019-03-21T21:42:43+00:00
- Post Title: Re: Gran Turismo 6 Models

ok take your time and thanks again for your hard work 

cheers
## Post #187
- Username: bmw30
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Feb 26, 2018 11:11 pm
- Post datetime: 2019-03-23T19:45:46+00:00
- Post Title: Re: Gran Turismo 6 Models

can you maybe post a beta for it i need only the models textures are not need
## Post #188
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-03-31T15:52:48+00:00
- Post Title: Re: Gran Turismo 6 Models

GT6 (Gran Turismo 6) [PS3] tool will be posted here after some testing:

[https://forum.xentax.com/viewtopic.php?f=16&t=19919](https://forum.xentax.com/viewtopic.php?f=16&t=19919)
## Post #189
- Username: verde57
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Sep 03, 2017 4:53 pm
- Post datetime: 2019-04-01T11:08:07+00:00
- Post Title: Re: Gran Turismo 6 Models

GT SPORT 1.36 Update!! (5 New Cars!)
can we rip models from it?
## Post #190
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-04-01T18:01:06+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from verde57 ↑Mon Apr 01, 2019 7:08 pm at Mon Apr 01, 2019 7:08 pm
>
> 
GT SPORT 1.36 Update!! (5 New Cars!)
can we rip models from it?
No, it requires newer/latest PS4 firmware exploited, with out it no game can be reversed.
Currently supported only up to update 1.14 I think.
## Post #191
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2019-04-11T21:20:03+00:00
- Post Title: Re: Gran Turismo 6 Models

Is there a list of car folders? because all extracted files are 0000 etc and it's impossible to find anything
## Post #192
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2019-04-16T09:10:19+00:00
- Post Title: Re: Gran Turismo 6 Models

Does anyone have the Toyota Vitz model ripped from the game's archives?
## Post #193
- Username: oldman
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 19, 2017 2:54 am
- Post datetime: 2019-04-16T17:45:08+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from MarieRose1301 ↑Fri Apr 12, 2019 5:20 am at Fri Apr 12, 2019 5:20 am
>
> 
Is there a list of car folders? because all extracted files are 0000 etc and it's impossible to find anything

There is an easy way to find the names of the cars. Open the BODY file in the editor.
In the body file you can find the name of the cars.
Example:  
X: \ GT6 \ Car \ 0037 \ 0024 is the VW Golf R 2011
Scroll down in the open file, you found

// polyphony / dfs / GT / gt6 / src / car / 0037/0024 / maya / source images / GT / GT5 / VW_Golf_R_2011 /

At the moment I found the following folder
0037 = Volkswagen
0039 = Opel
0053 = Mercedes Benz
0058 = Vauxhall
0225 = Ferrari
## Post #194
- Username: Gta5KoRn
- Rank: beginner
- Number of posts: 23
- Joined date: Fri Jul 28, 2017 11:12 pm
- Post datetime: 2019-04-19T11:28:36+00:00
- Post Title: Re: Gran Turismo 6 Models

This was asked by somebody, but still not answered. 
When using the gttool the result is: "Unable to process volume file." Any fix for this?
## Post #195
- Username: oldman
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 19, 2017 2:54 am
- Post datetime: 2019-04-19T15:48:39+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from Gta5KoRn ↑Fri Apr 19, 2019 7:28 pm at Fri Apr 19, 2019 7:28 pm
>
> 
This was asked by somebody, but still not answered. 
When using the gttool the result is: "Unable to process volume file." Any fix for this?

My way for win 10. Make two new folders in the file explorer.
X: \ gt6_vol_file
X: \ gt6_extract_file
Copy the gttool and gt6.vol in the x: \ gt6_vol_file
Use the keys WIN + R. Type CMD, press Enter.

In the Command Prompt window, navigate to the X: \ gt6_vol_file folder.

Start the Gttool

gttool GT6.VOL GT6 X: \ gt6_extract_file

It is important to use the GT6 argument for the tool.Without the argument GT6 there is the error message "Unable to process volume file." Should the tool start now, patience you must have ... it takes some time to extrate.
## Post #196
- Username: Gta5KoRn
- Rank: beginner
- Number of posts: 23
- Joined date: Fri Jul 28, 2017 11:12 pm
- Post datetime: 2019-04-20T12:40:55+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from oldman ↑Fri Apr 19, 2019 11:48 pm at Fri Apr 19, 2019 11:48 pm
>
> 
Gta5KoRn wrote: ↑Fri Apr 19, 2019 7:28 pm
This was asked by somebody, but still not answered. 
When using the gttool the result is: "Unable to process volume file." Any fix for this?


My way for win 10. Make two new folders in the file explorer.
X: \ gt6_vol_file
X: \ gt6_extract_file
Copy the gttool and gt6.vol in the x: \ gt6_vol_file
Use the keys WIN + R. Type CMD, press Enter.

In the Command Prompt window, navigate to the X: \ gt6_vol_file folder.

Start the Gttool

gttool GT6.VOL GT6 X: \ gt6_extract_file

It is important to use the GT6 argument for the tool.Without the argument GT6 there is the error message "Unable to process volume file." Should the tool start now, patience you must have ... it takes some time to extrate.

still dont work 
what am i doing wrong? [https://imgur.com/a/UsNblJC](https://imgur.com/a/UsNblJC)
## Post #197
- Username: oldman
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 19, 2017 2:54 am
- Post datetime: 2019-04-20T13:50:51+00:00
- Post Title: Re: Gran Turismo 6 Models

What is wrong ??? Your command line ....

I wrote, navigate to the folder, inside. In your case H: \ gt6_vol_file
In this folder you can start the tool ... without H: \ ... blabla ...
you need only  gttool GT6.VOL GT6 H: \ gt6_extract_file
When executing executable files in a folder, the argument X: \ gttool blabla .... is not needed ....

Pay attention to the correct spelling of GT6.VOL or GT.VOL
## Post #198
- Username: Gta5KoRn
- Rank: beginner
- Number of posts: 23
- Joined date: Fri Jul 28, 2017 11:12 pm
- Post datetime: 2019-04-20T14:18:55+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from oldman ↑Sat Apr 20, 2019 9:50 pm at Sat Apr 20, 2019 9:50 pm
>
> 
What is wrong ??? Your command line ....

I wrote, navigate to the folder, inside. In your case H: \ gt6_vol_file
In this folder you can start the tool ... without H: \ ... blabla ...
you need only  gttool GT6.VOL GT6 H: \ gt6_extract_file
When executing executable files in a folder, the argument X: \ gttool blabla .... is not needed ....

Pay attention to the correct spelling of GT6.VOL or GT.VOL

i dont understand, it doesnt work. Command line is correct now, isnt it? [https://imgur.com/a/dpX9I7v](https://imgur.com/a/dpX9I7v)
## Post #199
- Username: oldman
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 19, 2017 2:54 am
- Post datetime: 2019-04-20T15:45:04+00:00
- Post Title: Re: Gran Turismo 6 Models

The commando line is correct and should work. 
I have tested twice now. Once Win 10 64Bit, the other Win 7 Home Premium 64Bit. 
No problem. I see you are using Win 8.1. Could it be possible that Win 8.1 is the problem? Missing share for folder ... 
I have no idea where the problem should be ...
## Post #200
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-04-20T17:07:41+00:00
- Post Title: Re: Gran Turismo 6 Models

in your folder where your VOL and exe files are create a new text file
open it in notepad and ad this

```
pause
```

now instead of new text document.txt rename it to something like extract.cmd
once renamed to extract.cmd double click it and let the archive extract
in mean time you'll see that in your H:\gt6_extract_file locations folders are being extracted, done
## Post #201
- Username: Gta5KoRn
- Rank: beginner
- Number of posts: 23
- Joined date: Fri Jul 28, 2017 11:12 pm
- Post datetime: 2019-04-20T18:04:21+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from mono24 ↑Sun Apr 21, 2019 1:07 am at Sun Apr 21, 2019 1:07 am
>
> 
in your folder where your VOL and exe files are create a new text file
open it in notepad and ad this
Code: Select allgttool.exe GT.VOL GT6 H:\gt6_extract_file
pause
now instead of new text document.txt rename it to something like extract.cmd
once renamed to extract.cmd double click it and let the archive extract
in mean time you'll see that in your H:\gt6_extract_file locations folders are being extracted, done
still the same error.. Tested on Win 8.1, Win7 and Win10
is that correct gt.vol file, right? [https://imgur.com/a/Qq2GRuO](https://imgur.com/a/Qq2GRuO)
## Post #202
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-04-21T06:51:09+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from Gta5KoRn ↑Sun Apr 21, 2019 2:04 am at Sun Apr 21, 2019 2:04 am
>
> still the same error..
you either have broken (corrupted, unfinished download) VOL file, or using wrong gttool
## Post #203
- Username: Gta5KoRn
- Rank: beginner
- Number of posts: 23
- Joined date: Fri Jul 28, 2017 11:12 pm
- Post datetime: 2019-04-21T08:44:53+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from daemon1 ↑Sun Apr 21, 2019 2:51 pm at Sun Apr 21, 2019 2:51 pm
>
> 
Gta5KoRn wrote: ↑Sun Apr 21, 2019 2:04 amstill the same error..
you either have broken (corrupted, unfinished download) VOL file, or using wrong gttool

well i extracted it 2 times from 1-BCES01893_00-0000000NPEB01893.pkg
gttool is from here [https://forum.xentax.com/viewtopic.php?p=97169#p97169](https://forum.xentax.com/viewtopic.php?p=97169#p97169)
## Post #204
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-04-21T09:10:55+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from Gta5KoRn ↑Sun Apr 21, 2019 4:44 pm at Sun Apr 21, 2019 4:44 pm
>
> 
well i extracted it 2 times from 1-BCES01893_00-0000000NPEB01893.pkg
gttool is from here https://forum.xentax.com/viewtopic.php?p=97169#p97169
pkg itself can be correpted
## Post #205
- Username: Gta5KoRn
- Rank: beginner
- Number of posts: 23
- Joined date: Fri Jul 28, 2017 11:12 pm
- Post datetime: 2019-04-21T11:15:36+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from daemon1 ↑Sun Apr 21, 2019 5:10 pm at Sun Apr 21, 2019 5:10 pm
>
> 
Gta5KoRn wrote: ↑Sun Apr 21, 2019 4:44 pm
well i extracted it 2 times from 1-BCES01893_00-0000000NPEB01893.pkg
gttool is from here https://forum.xentax.com/viewtopic.php?p=97169#p97169

pkg itself can be correpted
Solved. i downloaded GT.VOL from another place (Game version 1.00), now it seems to work.
Another question. GT.VOL from Gran Turismo 6 [EUR-RUS][BCES01893][OFW][PS3xploit Han] (1.22) game version doesn't include the cars from the 1.00-1.22 updates right?
Thanks to everyone who helped with that issue!
## Post #206
- Username: oldman
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 19, 2017 2:54 am
- Post datetime: 2019-04-21T15:07:16+00:00
- Post Title: Re: Gran Turismo 6 Models

Excellent that it worked.
It is sometimes a detective work after a long time finding the right file or tool.
Unfortunately, some creators do not document their tools. With which version the tools work correctly.
Another problem is finding the right GT.VOL. The WWW is big and so you can sometimes find a corrupt or a fake file.
As with Gran Turismo 6, it can be a matter of luck.
Personally, I'm happy about every little thing when it works.
## Post #207
- Username: StreetMode
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 17, 2018 4:45 am
- Post datetime: 2019-04-22T15:43:34+00:00
- Post Title: Re: Gran Turismo 6 Models

Thank you for this great job,
 I downloaded the full game, and extracted the gt.vol and I began to put the marks of cars on each folder, for those interested
## Post #208
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-04-22T16:53:47+00:00
- Post Title: Re: Gran Turismo 6 Models

Working on decrypting DLC cars
## Post #209
- Username: verde57
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Sep 03, 2017 4:53 pm
- Post datetime: 2019-04-23T06:50:10+00:00
- Post Title: Re: Gran Turismo 6 Models

In my GT6 game  files I am missing TVR Griffith and Aston Martin Vantage 1999, does anyone have have them?
## Post #210
- Username: Dennissaurus
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Aug 12, 2014 11:16 pm
- Post datetime: 2019-05-06T00:11:09+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from Gta5KoRn ↑Fri Apr 19, 2019 7:28 pm at Fri Apr 19, 2019 7:28 pm
>
> 
This was asked by somebody, but still not answered. 
When using the gttool the result is: "Unable to process volume file." Any fix for this?

Using explorer, navigate to GT.Vol folder (Example >> D:\torrents\PS3_GAME\USRDIR) 
extract or move the gttool64.exe to here also.

Now, click the address bar ONCE and type CMD, then press enter..
Command prompt will now open, Paste this when it does >>>        gttool64 -u -i gt.vol -o GT6 EXTRACT

then press enter and wait. Be sure you have 30Gb or more space, and good luck  

ToneBee
## Post #211
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-05-11T12:32:28+00:00
- Post Title: Re: Gran Turismo 6 Models

This updated tool will allow to extract GT6 packages that have no VOL file, but 1000's of small files in PDIPFS directory.
As a result, it can extract DLCs, updates or original game packaged in PDIPFS format. It will not extract VOL files anymore.

All original Flatz code, slightly modified by me.

Usage: same command line, just instead of VOL file, you give it your PDIPFS folder name, where your DLC files are extracted.

Note: there are 2 types of files in PDIPFS: "full" files and "partial" files. This version only supports full files.
[gttool_dlc.rar](https://xentaxbackup.github.io/file/16223_gttool_dlc.rar)
## Post #212
- Username: mclarenp20
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Apr 20, 2019 9:53 am
- Post datetime: 2019-05-19T07:24:28+00:00
- Post Title: Re: Gran Turismo 6 Models

Hello, everyone, who knows how to use TXS2DDS.exe converter? Please teach me, thank you!
## Post #213
- Username: juanmabraun
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 21, 2019 5:07 pm
- Post datetime: 2019-07-21T15:31:39+00:00
- Post Title: Re: Gran Turismo 6 Models

is there any guide o tutorial of the tool  ?
## Post #214
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2019-08-27T16:12:23+00:00
- Post Title: Re: Gran Turismo 6 Models

I am trying to extract the GT.VOL for Gran Turismo 5 (this is from the XL Edition) using gttools and all I get this error "Unable to process volume"....

This is the command I used: C:\Users\Owner>C:\Users\Owner\Downloads\gttool\bin\Release\gttool.exe "C:\Users\Owner\Documents\MEGAsync Downloads\Gran Turismo 5 XL Edition\Gran Turismo 5 XL Edition [BCUS98114]\PS3_GAME\USRDIR\GT.VOL" GT5 "C:\Users\Owner\Documents\MEGAsync Downloads\Gran Turismo 5 XL Edition\Gran Turismo 5 XL Edition [BCUS98114]\PS3_GAME\USRDIR\"

CAN SOMEBODY PLEASE HELP ME?! PLEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAASSSSSEEEE?!!??!!?!?

I'll give you a cookie if you do.
## Post #215
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-09-17T15:18:00+00:00
- Post Title: Re: Gran Turismo 6 Models

what progress do you expect? I think everything is done here
## Post #216
- Username: medwed
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Sep 03, 2010 3:45 pm
- Post datetime: 2019-09-17T17:34:24+00:00
- Post Title: Re: Gran Turismo 6 Models

The Link to Downloads the models
## Post #217
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-09-17T18:34:24+00:00
- Post Title: Re: Gran Turismo 6 Models

ah, that... this is not my mission
## Post #218
- Username: medwed
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Sep 03, 2010 3:45 pm
- Post datetime: 2019-09-17T20:47:27+00:00
- Post Title: Re: Gran Turismo 6 Models

GT6  (63 Cars Models) Login to Download   [http://gamemodels.ru/files/category/106 ... turismo-6/](http://gamemodels.ru/files/category/1066-gran-turismo-6/)

and All cars game files  [https://mega.nz/#!5RhW2AzQ!3h2s9ygaicT9 ... 1zdoc1FD0M](https://mega.nz/#!5RhW2AzQ!3h2s9ygaicT9jj6r2_VM9_5rnqboJUDpn1zdoc1FD0M)
## Post #219
- Username: Doc0
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Mar 02, 2017 3:56 pm
- Post datetime: 2019-10-03T09:22:19+00:00
- Post Title: Re: Gran Turismo 6 Models

Thanks for the file. With this "All car games file", what can i do? unzipped it's a 12gb folder called "crs"with 2420 files, is that the GT6 vol or i'm missing a step?
## Post #220
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-04T01:38:54+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from Doc0 ↑Thu Oct 03, 2019 5:22 pm at Thu Oct 03, 2019 5:22 pm
>
> ...unzipped it's a 12gb folder called "crs"with 2420 files
Those are the courses files, vehicle files are in a folder called car and subfolders are 0001, 0002 etc..
When you actually extract the main VOL archive you get a number of folders among which are crs and car, or carparts, tire etc etc etc
## Post #221
- Username: Doc0
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Mar 02, 2017 3:56 pm
- Post datetime: 2019-10-04T08:35:23+00:00
- Post Title: Re: Gran Turismo 6 Models

Thanx, i understand, i got fooled by the message saying all car game file, it was the courses files. I guess i have to found the VOL file now
## Post #222
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-04T17:38:56+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from Doc0 ↑Fri Oct 04, 2019 4:35 pm at Fri Oct 04, 2019 4:35 pm
>
> I guess i have to found the VOL file now
No need to, daemon1 went through all the trouble and did amazing job in supporting the downloadable PKGs as well of the WHOLE game, how about just use those instead hunting down a game disc version that has the VOL archive, plus its incomplete anyway, it doesn't have all the DLCs, you'll save yourself lots of headache.
## Post #223
- Username: Doc0
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Mar 02, 2017 3:56 pm
- Post datetime: 2019-10-08T08:54:24+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from mono24 ↑Sat Oct 05, 2019 1:38 am at Sat Oct 05, 2019 1:38 am
>
> 
Doc0 wrote: ↑Fri Oct 04, 2019 4:35 pmI guess i have to found the VOL file now 
No need to, daemon1 went through all the trouble and did amazing job in supporting the downloadable PKGs as well of the WHOLE game, how about just use those instead hunting down a game disc version that has the VOL archive, plus its incomplete anyway, it doesn't have all the DLCs, you'll save yourself lots of headache.

So i tried to read all the post but i don't understand the workflow. I thought it was: get the vol, extract it with GTTools and make models with GT6 frome daemon1.

Sorry i'm kind of slow for these things (i'm better with Blender if someboy want to exchange knowledge)
## Post #224
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-08T18:06:49+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from Doc0 ↑Tue Oct 08, 2019 4:54 pm at Tue Oct 08, 2019 4:54 pm
>
> So i tried to read all the post but i don't understand the workflow. I thought it was: get the vol, extract it with GTTools and make models with GT6 frome daemon1.
You sure you read it well enough, even on one page back is shown, because it has been explained multiple times, regardless if you choose to dump the VOL from a game disc or the PDIPFS folder structure form PKGs its all the same, as well using the tool to convert the meshes, where exactly are you stuck?
## Post #225
- Username: x86fanboy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 07, 2019 3:01 pm
- Post datetime: 2019-10-09T14:15:53+00:00
- Post Title: Re: Gran Turismo 6 Models

I've read through this discussion thread and was going to ask if there's a current link to the discord as I had a couple questions and the previously posted link had expired, however with the links posted above it seems as if the hard work has already been done. 
I was trying to extract the highest quality models available for the Toyota Aqua (aka Prius C), but for now I'll have a look through the provided links to see how much has already been done.
If the discord is still active then a link would be appreciated, but if not then I'll probably write a braindead-simple guide for future reference on how to extract and conform the models, along with how to find the desired files post-extraction, just as a point of future reference. 
Slightly easier than trying to find the most relevant/updated posts from a thread already spanning 15 pages.
## Post #226
- Username: markerfede
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Oct 15, 2019 9:19 pm
- Post datetime: 2019-10-15T13:24:06+00:00
- Post Title: Re: Gran Turismo 6 Models

Anyone a part of the Discord server that has the GT Sport 3d models? I've been trying to get access to the car models and tracks from latest updates?

Or if anyone could fill me in on how to do it myself, point me in the right direction!

Thanks!
## Post #227
- Username: medwed
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Sep 03, 2010 3:45 pm
- Post datetime: 2019-10-22T14:59:19+00:00
- Post Title: Re: Gran Turismo 6 Models

Gentlemen! I have already unpacked the game.In which files will I find textures of better quality and how to extract them ? BIG THANKS !
## Post #228
- Username: x86fanboy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 07, 2019 3:01 pm
- Post datetime: 2019-11-13T15:37:24+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from StreetMode ↑Mon Apr 22, 2019 11:43 pm at Mon Apr 22, 2019 11:43 pm
>
> 
Thank you for this great job,
 I downloaded the full game, and extracted the gt.vol and I began to put the marks of cars on each folder, for those interested

I'm just going through all the cars now to find what I want, I'm curious if you labeled them manually or if there is some more efficient way of looking up cars? Some database file somewhere? One other post mentioned opening files in an editor, but to manually open each body to see what car it is seems a little tedious, especially if you're just looking for one model of car.
I hope that I'm missing something important here, either that or my workflow is just slower because I'm doing this all in a virtual machine.
## Post #229
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2019-11-17T11:52:57+00:00
- Post Title: Re: Gran Turismo 6 Models

So been lately trying to research gt tracks, specially akasaka.... And found an interesting lead... For now i have tried to rip geometry by dumping the ram of pcsx3 while loaded the game, and though it seems that indeed the geometry gets outputted as part of the information the game stores, its not too clear to understand where it begins or ends, so i tried to do a little test, parse a .shapestream through offzip, and i actually got an unziped file that does actually have a clear mesh geometry with fis and verts, and the most interesting, it does resemble the vertex data i found in the ram dump(24-byte arrays); although, it only decompresses a 72 kbs out of a 12 mb file... So maybe the compression is right but dunno what else can be done for a proper unpacking...
[Captura.PNG](https://xentaxbackup.github.io/file/17078_Captura.PNG)
## Post #230
- Username: ryanjtm
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Apr 26, 2019 5:40 am
- Post datetime: 2019-12-03T23:38:54+00:00
- Post Title: Re: Gran Turismo 6 Models

Wow, I'm so happy to see someone taking a crack at the track geometry, I hope it's going well
## Post #231
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2019-12-04T13:16:14+00:00
- Post Title: Re: Gran Turismo 6 Models

Well, just here doing some testing aaaaaand i might have found another really interesting lead, using the comtype scan of quick bms did actually manage to unpack a whole .shapestream, both mcomp3 and mcomp4 algorithms manage to output exactly the same results that offzip got(but 1990 times repeated, it might be lacking a TOC and thus why repeating the first element to output, maybe vvl is the toc), plus another extra thanks to the dedication of a friend that checked some files, the scapes/foto travel are located in the folder called char, for gt6 those are the "bg0(number)", in GTS those are both in hd form in the char folder, or a preview mesh on scapes folder inside char folder..... have fun! (those arent even compressed, with simple knowledge of how the struct works its kinda easy to get mesh info out of it, so far havent done a propper extraction script for mrp, but its doable

also texts in the scapes/foto travel might be on the same files, for the .textstreams might aswell try the comtypes that worked with shapestream



Captura.JPG (146.12 KiB) Viewed 458 times
## Post #232
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2019-12-07T15:19:46+00:00
- Post Title: Re: Gran Turismo 6 Models

moar research, seems that for some reason the tracks either have a slob or a mcomp(3 or 4) compression, offzip and the scan tool basically throw the same result, the mesh i showed before.
the padding for the meshes seem to be a bit unconsistend and complicated to calculate... not sure if there is any hint on the listing on the header, but id say most likely bg file struct is the kind of 3d model struct that the tracks might also use. 
From what i have researched so far akasaka (c068) should be outputing a 200 mbs out of a 12 mbs xD kinda funky... here a preview of my research in bg014(valencia, now with texture and got uvs, names are also on the file, be it meshes or textures, you can basically see who did it from the texture path folder(project folders with modelers names), it was made in maya XDDDD
[agora.JPG](https://xentaxbackup.github.io/file/17158_agora.JPG)
## Post #233
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2019-12-08T19:22:12+00:00
- Post Title: Re: Gran Turismo 6 Models

Also a little update with no previews, by doing a bit of teating im getting the textures out by basically stripping the dxt raw info and triming to the desired size, its kinda time wasting, kinda lazy to try and program something to do it for me
## Post #234
- Username: ryanjtm
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Apr 26, 2019 5:40 am
- Post datetime: 2019-12-29T21:43:11+00:00
- Post Title: Re: Gran Turismo 6 Models

Great updates! Thanks for your hard work on this, I live in hope that one day we'll be able to extract track geometry.
## Post #235
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2019-12-31T12:26:52+00:00
- Post Title: Re: Gran Turismo 6 Models

Well, i have been already been able to.... precisely wanted to post an update, been working on akasaka and also on valencia, first of all, though i have been able to pull it out, its not easy, specially for tracks, the geometry is in various files, sky, road and simple stuff are with such names, that is the easy part, the scenery though, those are stored in the .shapestream files, but that is compressed, you can decompress with offzip, but wherever it finds a file it doesnt understand it stops suddenly, thus why i wasnt able to fully extract akasaka on the first try, i believe shapestream files use slob compression, that mcomp seems to have been an error or something, dunno much about compression methods, though there is a way to decompress, you have to check with offzip the working parts by using "offzip.exe -S -z -15 (here the name of the file).shapestream" it will scan the file and tell you the offsets in hexadecimal of the compressed streams, for akasaka, it seems the 2nd file gave some problem, so i did a script for mrp and stripped the files in all the compressed ones, decompressed them using offzip, 430 files, all the data for track parts... here an example 



1 is the mesh i already showed before, 2 is the new mesh, it lines up perfectly, here another mesh



now as explanation as why this is harder than it seems, the extracted models barely have headers, if there is more than one mesh per file you have to check yourself and get the offsets, the padding on the vertex blocks is variable, even the uvs seem to be kinda weird, im not quite sure if it uses Short_signed ones or even Half_floats, i believe it varies depending on the type of mesh(materials structure?) havent been able to automate the process...

on the other hand i have worked lots on valencia mesh... here a preview of all the meshes i was able to extract (1420ish)



though again uvs are a fuck and needs a lot of hand work to fix the problems, also one interesting thing, while this meshes do have already the textures embeded on the main file, in the track files the textures are in texstream as other users already said, most likely the extraction method using offzip will be the same, check for usable data and isolate it, if the textures are the same as the ones in valencia(bgs) those will be in raw format, you can use dxt programs to open them and generate the propper dds...

lastly, here a preview of doing testing porting valencia to AC
## Post #236
- Username: Pupsik
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 18, 2017 3:18 am
- Post datetime: 2020-02-22T06:02:09+00:00
- Post Title: Re: Gran Turismo 6 Models

Hi,
 Help please

I am trying to extract the GT.VOL for Gran Turismo 6 using gttools and all I get this error "Unable to process volume"....

This is the command I used: D:\gt6vol\gttool.exe "D:\gt6vol\" GT6 "D:\gt6vol\"

I have Windows 10, 64bit

CAN SOMEBODY PLEASE HELP ME?! PLEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAASSSSSEEEE?!!??!!?!?
## Post #237
- Username: Pupsik
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 18, 2017 3:18 am
- Post datetime: 2020-02-22T10:12:40+00:00
- Post Title: Re: Gran Turismo 6 Models

Hi again.

I tried using a different version  -  gttool_dlc.

Now an error is issued:
Unable to process volume file.
## Post #238
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-02-23T00:28:35+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from Pupsik ↑Sat Feb 22, 2020 2:02 pm at Sat Feb 22, 2020 2:02 pm
>
> ... I get this error "Unable to process volume"....
This is the command I used: D:\gt6vol\gttool.exe "D:\gt6vol\" GT6 "D:\gt6vol\"
So this method is if you have the VOL file from a disc version of the game.
Make sure to have at root folder a batch file, where the GT6.VOL file is alongside the gttool.exe, and where you want to dump the game, example:

```
gttool.exe GT6.VOL GT6 E:\GT6_extracted
```


> Reply from Pupsik ↑Sat Feb 22, 2020 6:12 pm at Sat Feb 22, 2020 6:12 pm
>
> 
...I tried using a different version  -  gttool_dlc.

Now an error is issued:
Unable to process volume file.
The dlc version is ONLY working if you have the retail PS3 PKG version of the game alongside all its DLCs to dump everything the game has, and it will NOT work with the GT6.VOL file from a disc version of the game.
As it was already explained here in its main thread of both tools: [viewtopic.php?p=152494#p152494](https://forum.xentax.com/viewtopic.php?p=152494#p152494)
## Post #239
- Username: Pupsik
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 18, 2017 3:18 am
- Post datetime: 2020-02-25T17:41:09+00:00
- Post Title: Re: Gran Turismo 6 Models

Oh, thank you very much! its now work
## Post #240
- Username: succha
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 12, 2019 6:55 pm
- Post datetime: 2020-04-29T10:14:16+00:00
- Post Title: Re: Gran Turismo 6 Models

Hi
so how can I extract GT6 tracks?
use gttool? any command?
## Post #241
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2020-05-24T08:00:33+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from succha ↑Wed Apr 29, 2020 6:14 pm at Wed Apr 29, 2020 6:14 pm
>
> 
Hi
so how can I extract GT6 tracks?
use gttool? any command?

Unless you know how to work with binary files, pretty much no, even doing a script its kinda hard cause the meshes have too many changes, it requires manual labour one way or another
## Post #242
- Username: succha
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 12, 2019 6:55 pm
- Post datetime: 2020-05-27T11:45:08+00:00
- Post Title: Re: Gran Turismo 6 Models

Ohh....
not so easy right now..
Thank you so much for your reply !
## Post #243
- Username: rekiem22
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 28, 2020 7:48 pm
- Post datetime: 2020-06-23T01:06:30+00:00
- Post Title: Re: Gran Turismo 6 Models

Thanks for all your information Machinedramon. I'm still learning hex2obj in order to "translate" the .dat files to objects. Will see if this come to a proper end. I'm also interested in taking some of the tracks to Asetto Corsa. It would be good if I can have a closer contact with you. ex: discord
## Post #244
- Username: frankalexandre
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Dec 02, 2020 10:01 pm
- Post datetime: 2020-12-07T13:14:58+00:00
- Post Title: Re: Gran Turismo 6 Models

After unpacking the PACK file i get 1400 textures, so its not what i need? Must uncompress TEX_STREAM too? How?
I think i am a bit lost, i loaded the Ascii files in max and can see all the meshes, uvs are in place too, only need to find the textures and identify the correct meshs lods.
## Post #245
- Username: CDTH06
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 16, 2021 3:00 am
- Post datetime: 2022-08-18T07:27:42+00:00
- Post Title: Re: Gran Turismo 6 Models

Guys. Can someone help me? I'm using GTToolSharp. When I'm trying to export GT.VOL from GT6, I got that error

Unhandled exception. System.UnauthorizedAccessException: Access to the path 'D:\gt6_vol_file\GT.VOL' is denied.
   at System.IO.FileStream.ValidateFileHandle(SafeFileHandle fileHandle)
   at System.IO.FileStream.CreateFileOpenHandle(FileMode mode, FileShare share, FileOptions options)
   at System.IO.FileStream..ctor(String path, FileMode mode, FileAccess access, FileShare share, Int32 bufferSize, FileOptions options)
   at System.IO.FileStream..ctor(String path, FileMode mode)
   at GTToolsSharp.Volumes.GTVolumePFS.Load(Keyset keyset, String path, Boolean isPatchVolume, Endian endianness) in C:\Users\nenkai\source\repos\GTToolsSharp\GTToolsSharp\Volumes\GTVolumePFS.cs:line 90
   at GTToolsSharp.Program.Unpack(UnpackVerbs options) in C:\Users\nenkai\source\repos\GTToolsSharp\GTToolsSharp\Program.cs:line 217
   at CommandLine.ParserResultExtensions.WithParsed[T](ParserResult`1 result, Action`1 action)
   at GTToolsSharp.Program.Main(String[] args) in C:\Users\nenkai\source\repos\GTToolsSharp\GTToolsSharp\Program.cs:line 41
   at GTToolsSharp.Program.<Main>(String[] args)
## Post #246
- Username: CDTH06
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 16, 2021 3:00 am
- Post datetime: 2022-08-19T14:17:21+00:00
- Post Title: Re: Gran Turismo 6 Models

> Reply from CDTH06 ↑Thu Aug 18, 2022 3:27 pm at Thu Aug 18, 2022 3:27 pm
>
> 
Guys. Can someone help me? I'm using GTToolSharp. When I'm trying to export GT.VOL from GT6, I got that error

Unhandled exception. System.UnauthorizedAccessException: Access to the path 'D:\gt6_vol_file\GT.VOL' is denied.
   at System.IO.FileStream.ValidateFileHandle(SafeFileHandle fileHandle)
   at System.IO.FileStream.CreateFileOpenHandle(FileMode mode, FileShare share, FileOptions options)
   at System.IO.FileStream..ctor(String path, FileMode mode, FileAccess access, FileShare share, Int32 bufferSize, FileOptions options)
   at System.IO.FileStream..ctor(String path, FileMode mode)
   at GTToolsSharp.Volumes.GTVolumePFS.Load(Keyset keyset, String path, Boolean isPatchVolume, Endian endianness) in C:\Users\nenkai\source\repos\GTToolsSharp\GTToolsSharp\Volumes\GTVolumePFS.cs:line 90
   at GTToolsSharp.Program.Unpack(UnpackVerbs options) in C:\Users\nenkai\source\repos\GTToolsSharp\GTToolsSharp\Program.cs:line 217
   at CommandLine.ParserResultExtensions.WithParsed[T](ParserResult`1 result, Action`1 action)
   at GTToolsSharp.Program.Main(String[] args) in C:\Users\nenkai\source\repos\GTToolsSharp\GTToolsSharp\Program.cs:line 41
   at GTToolsSharp.Program.<Main>(String[] args)

Ok. I solve my problem, now I have another question. How I can make files which extracted, useable?
