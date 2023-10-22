## Post #1
- Username: MateSMC
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Mar 02, 2011 1:14 am
- Post datetime: 2013-11-06T08:02:21+00:00
- Post Title: Gran Turismo 3 and 4 cars ripping?

Hi,
here's the files of one of cars from GT4. In my opinion .car file is 3d model and .pat file is texture.
Someone know how to rip these files?

[http://www.4shared.com/rar/j-GKqDFx/pk156.html](http://www.4shared.com/rar/j-GKqDFx/pk156.html) or [http://www.uploadmb.com/dw.php?id=1383728549](http://www.uploadmb.com/dw.php?id=1383728549)

1. Extraction tool for GT3/GT4.vol = extract compressed files of cars (pk0156 etc):
GT3FSExtract: [http://www.4shared.com/zip/BP5EV8np/GT3FSExtract.html](http://www.4shared.com/zip/BP5EV8np/GT3FSExtract.html) or [http://www.uploadmb.com/dw.php?id=1383728470](http://www.uploadmb.com/dw.php?id=1383728470)
GT3vol: [http://www.4shared.com/zip/OalSltb2/gt3vol.html](http://www.4shared.com/zip/OalSltb2/gt3vol.html) or [http://www.uploadmb.com/dw.php?id=1383728411](http://www.uploadmb.com/dw.php?id=1383728411)

2. Extraction tool for compressed car files (like pk0156) = it gives you files .car and .pat etc.:
OFFZIP: [http://www.4shared.com/zip/o4BqbvQt/offzip.html](http://www.4shared.com/zip/o4BqbvQt/offzip.html) or [http://www.uploadmb.com/dw.php?id=1383728504](http://www.uploadmb.com/dw.php?id=1383728504)

3. And one man do that quickBMS script (export .car to .3ds format), but it not work's for me correctly:
GT4 BMS script: [http://www.4shared.com/file/PC6_hmgf/GT ... to3ds.html](http://www.4shared.com/file/PC6_hmgf/GT4eememoryto3ds.html) or [http://www.uploadmb.com/dw.php?id=1383728591](http://www.uploadmb.com/dw.php?id=1383728591)


And original (compressed) car files form GT4.vol
GT4 car files: PM only
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-06T08:26:29+00:00
- Post Title: Gran Turismo 3 and 4 cars ripping?

Is there a way to download from 4shared other than using facebook/twitter/google+?

For facebook it says: "4shared gets the following infos: your profil, email address etc."

That's not funny, imho.
On 'cancel' it redirects me back to 4shared trying to connect to twitter or something else.
So sorry, can't help you.
## Post #3
- Username: MateSMC
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Mar 02, 2011 1:14 am
- Post datetime: 2013-11-06T08:41:22+00:00
- Post Title: Gran Turismo 3 and 4 cars ripping?

Oh, sorry. I have account (free) on this site.
On 4shared is possible to create account without using social networks. 
Click on Sign up under social networks buttons (in pop-up menu), or on the header of site is Sign Up.

But If you have upload server without Signing up, i can reupload files.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-06T08:59:46+00:00
- Post Title: Gran Turismo 3 and 4 cars ripping?

I use http://www.uploadmb.com/ for example.

(Disadvantage is that files are erased after 30 days without a download.)
## Post #5
- Username: MateSMC
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Mar 02, 2011 1:14 am
- Post datetime: 2013-11-06T09:17:15+00:00
- Post Title: Gran Turismo 3 and 4 cars ripping?

Ok, reuploaded... =)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-06T10:08:15+00:00
- Post Title: Gran Turismo 3 and 4 cars ripping?

Thx.

> Extraction tool for extracted car files (like pk0156):What does that mean?
Does it mean offzip to be used on pk0156? If so could you post the command line, please?

So 0001d008.car is one of the extracted files? There's some floats (IEEE754 format, 4 bytes) but I don't see face indices so far.

From 0x49F80 seems to be some texture data: [](http://www.pic-upload.de/view-21249765/0001d008.car.jpg.html)
## Post #7
- Username: MateSMC
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Mar 02, 2011 1:14 am
- Post datetime: 2013-11-06T12:32:24+00:00
- Post Title: Gran Turismo 3 and 4 cars ripping?

Command line in CMD like this:
G:\offzip\offzip.exe -a -z -15 G:\GT4\cars\pk0156 G:\GT4\cars -0
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-06T13:28:31+00:00
- Post Title: Gran Turismo 3 and 4 cars ripping?

thx! (not seeing -z is a "sub option" only so I forgot the main option -a  )

Anyway the prob with the face indices remains.
It could help if you had another small *.car file. Or another object, since the uncompressed size should be <100 kB if possible.

edit: your last uploaded file is too big to download for me. Just as a hint: it also might violate forum rules.
If so maybe better delete it before the whole post is.
## Post #9
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2013-11-06T14:27:17+00:00
- Post Title: Gran Turismo 3 and 4 cars ripping?

Looking forward this thread.   

If you want to upload something, do it on MEDIAFIRE, it's the best upload site with MEGA right now.
## Post #10
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2014-02-10T05:47:34+00:00
- Post Title: Gran Turismo 3 and 4 cars ripping?

Found some useful information [here](http://ps23dformat.wikispaces.com/Gran+Turismo+3).
Looks very promising, but sample model has many intersected polygons inside.
[](http://fastpic.ru/view/33/2014/0210/f5dd2e8b776b560a288d0bcfd953b099.png.html)
## Post #11
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2014-08-21T21:09:16+00:00
- Post Title: Gran Turismo 3 and 4 cars ripping?

...did you manage to extract tracks from GT3?

Cheers...
## Post #12
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-08-26T18:29:50+00:00
- Post Title: Gran Turismo 3 and 4 cars ripping?

> Reply from Andrakann
>
> Found some useful information here.
Looks very promising, but sample model has many intersected polygons inside.

I did everything by theese instructions,but got only 3 panels(literally,3 flat faces) and absolutely messed up wheel.


Of course,you can hardly rip cars from GTPSP,they are the same,sometimes even a little better,But GT3 and GT4 has some great cars like nike one or Auto union,Ford T...

Also,extracting tracks would be amazing too,they are very detailed and unique

As a proof,here are the cars i extracted from GTPSP
[](http://www.imagebam.com/image/fac791347521352) 
[](http://www.imagebam.com/image/4c95b7347521329) 
[](http://www.imagebam.com/image/ab8c67334991198) 
[](http://www.imagebam.com/image/f915ef334991221) 
[](http://www.imagebam.com/image/a57cb6337296542) 
[](http://www.imagebam.com/image/aabb5d337296491) 
[](http://www.imagebam.com/image/5b44f8347521335) 
[](http://www.imagebam.com/image/8c1625347521311) 

But cars have some serious problems...

For some reason(I think because of PlayStation Platform):
1)textures don't have actual alpha layers
2)UV's are sometimes absolutely strange and not right...
3)No Normals with my ripping method
4)thousands of parts with my method

[](http://www.imagebam.com/image/9a1bcd327673720) 
[](http://www.imagebam.com/image/2bc646327673753) 
[](http://www.imagebam.com/image/b8aec5327673785) 
[](http://www.imagebam.com/image/d5c91d334804888) 
[](http://www.imagebam.com/image/17d85c334804892) 
[](http://www.imagebam.com/image/a96ba1347521320) 
[](http://www.imagebam.com/image/54ecfb347521341) 
[](http://www.imagebam.com/image/9967ab347521348) 

Also,I can't rip tracks by my method...
[](http://www.imagebam.com/image/255e05335109132) 


So please,can anyone help to decrypt original game files to rip meshes and extract textures...automatically  
That would be absolutely amazing!
## Post #13
- Username: nosfornos
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Dec 21, 2011 4:16 pm
- Post datetime: 2014-09-06T02:44:12+00:00
- Post Title: Gran Turismo 3 and 4 cars ripping?

Long for cerbera.
## Post #14
- Username: mike1234
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 15, 2016 4:23 pm
- Post datetime: 2016-03-15T08:35:30+00:00
- Post Title: Gran Turismo 3 and 4 cars ripping?

> Reply from MateSMC
>
> Hi,
here's the files of one of cars from GT4. In my opinion .car file is 3d model and .pat file is texture.
Someone know how to rip these files?
Luxury Car Hire New Zealand
http://www.4shared.com/rar/j-GKqDFx/pk156.html or http://www.uploadmb.com/dw.php?id=1383728549

1. Extraction tool for GT3/GT4.vol = extract compressed files of cars (pk0156 etc):
GT3FSExtract: http://www.4shared.com/zip/BP5EV8np/GT3FSExtract.html or http://www.uploadmb.com/dw.php?id=1383728470
GT3vol: http://www.4shared.com/zip/OalSltb2/gt3vol.html or http://www.uploadmb.com/dw.php?id=1383728411

2. Extraction tool for compressed car files (like pk0156) = it gives you files .car and .pat etc.:
OFFZIP: http://www.4shared.com/zip/o4BqbvQt/offzip.html or http://www.uploadmb.com/dw.php?id=1383728504

3. And one man do that quickBMS script (export .car to .3ds format), but it not work's for me correctly:
GT4 BMS script: http://www.4shared.com/file/PC6_hmgf/GT ... to3ds.html or http://www.uploadmb.com/dw.php?id=1383728591


And original (compressed) car files form GT4.vol
GT4 car files: PM only

View this topic may be this will help you: [viewtopic.php?f=16&t=12805](http://forum.xentax.com/viewtopic.php?f=16&t=12805)
## Post #15
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2016-06-14T00:16:22+00:00
- Post Title: Gran Turismo 3 and 4 cars ripping?

...didn't want to start a new thread, just wondering if it is possible to get track models?
Was looking at the SS Route 11, would like to get my hands on it... thanks
## Post #16
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2016-06-14T13:33:42+00:00
- Post Title: Re: Gran Turismo 3 and 4 cars ripping?

I personally ripped Tsukuba from Gran Turismo PSP, piece by piece, so that means that if someone wants to collapse it to port it into another game that would take a huge amount of time. A proper 3D export tool or script would make things way better and obviously will also preserve the original quality of the meshes.
## Post #17
- Username: steddy96
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 09, 2017 4:22 am
- Post datetime: 2017-10-08T20:25:04+00:00
- Post Title: Re: Gran Turismo 3 and 4 cars ripping?

Is this thread still active? Because I'd need help to understand how to make work the .bat file, because it keeps to give me error, and I'd need help
## Post #18
- Username: Pix
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Nov 18, 2016 7:23 am
- Post datetime: 2017-12-20T17:29:25+00:00
- Post Title: Re: Gran Turismo 3 and 4 cars ripping?

I don't really understand the offzip part. whenever i open it it closes automatically
## Post #19
- Username: gcr27
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Jul 31, 2017 8:19 am
- Post datetime: 2019-03-09T03:58:35+00:00
- Post Title: Re: Gran Turismo 3 and 4 cars ripping?

How do extract raybrig jgtc 00 and toyota supra denso sard and takata nsx dome Jgtc 03 models from psp using a psp jcpsp emulator me use blender and 3ds max me have much dificult to editing scale opening the export folder obj with textures me talking this forum i love gtpsp its prosess me not notions the tutoriais very compliqued
