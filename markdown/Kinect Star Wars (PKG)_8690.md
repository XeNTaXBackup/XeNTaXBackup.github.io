## Post #1
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2012-04-04T15:15:25+00:00
- Post Title: Kinect Star Wars (PKG)

Hello all,

I have been analyzing Star Wars Kinect to extract the 3D assests and have successfully unpacked the POD archives here:
[viewtopic.php?f=10&t=8687](http://forum.xentax.com/viewtopic.php?f=10&t=8687)

Now am almost certain that assets are in PODLZX. Must analyze for confirmation.

Can anyone help with researching this? 

Smaller sample : [http://www.sendspace.com/file/wya3ha](http://www.sendspace.com/file/wya3ha)

Larger sample : [http://www.sendspace.com/file/9nwv9p](http://www.sendspace.com/file/9nwv9p)

Edit: PKG files were null, have removed them. Uploaded PODLZX files.
## Post #2
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-04-05T03:27:45+00:00
- Post Title: Kinect Star Wars (PKG)

Nothing in those files - they only 90 bytes.......
Problem with uploading or is that what you uploaded?
## Post #3
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2012-04-05T03:56:06+00:00
- Post Title: Kinect Star Wars (PKG)

> Reply from Ninja
>
> Nothing in those files - they only 90 bytes.......
Problem with uploading or is that what you uploaded?
No, no problem with uploading those are the files. I found out this myself that the PKG files were only 1KB or less in size. They were in the POD archive with the corresponding sound files. Maybe file name listings for the archive or something. Now I know that the models are in the PODLZX archives.
Sorry my bad, must not put all eggs in one basket. (Except, unless eggs contain candy)
## Post #4
- Username: mazor
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-04-05T10:53:54+00:00
- Post Title: Kinect Star Wars (PKG)

upload the smallest podlzx file.
## Post #5
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2012-04-05T12:06:31+00:00
- Post Title: Kinect Star Wars (PKG)

> Reply from chrrox
>
> upload the smallest podlzx file.
Will do. Original post now updated with new links to PODLZX file.
## Post #6
- Username: mazor
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-04-05T13:39:48+00:00
- Post Title: Kinect Star Wars (PKG)

podlzx files are plain pod files compressed with xbcompress.exe from the sdk.
you can decompress them with xbdecompress.exe

here is a pkg extractor for the pkg files.

> for
>
> set MAGIC 0
>
> Do
>
> getdstring MAGIC 4
>
> While MAGIC != "adoY"
>
> getdstring MAGIC2 4
>
> if MAGIC2 == "oMoN"
>
> cleanexit
>
> endif
>
> get SIZE long
>
> getdstring NAME 0x54
>
> savepos OFFSET
>
> log NAME OFFSET SIZE
>
> math offset + size
>
> goto offset
>
> Padding 16
>
> next
## Post #7
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2012-04-05T19:51:10+00:00
- Post Title: Kinect Star Wars (PKG)

> Reply from chrrox
>
> podlzx files are plain pod files compressed with xbcompress.exe from the sdk.
you can decompress them with xbdecompress.exe

here is a pkg extractor for the pkg files.

for
set MAGIC 0
Do
getdstring MAGIC 4
While MAGIC != "adoY"
getdstring MAGIC2 4
if MAGIC2 == "oMoN"
cleanexit
endif
get SIZE long
getdstring NAME 0x54
savepos OFFSET
log NAME OFFSET SIZE
math offset + size
goto offset
Padding 16
next
Many thanks for the info and extractor. I assume you were able to decompress the sample PODLZX and unpacked the contents with the POD5 bms script, then having done so found PKG files inside? Then was able to write PKG extractor from unpacked files?

I now have the xbdecompressor.exe, how do I decompress properly?
## Post #8
- Username: mazor
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-04-05T20:19:24+00:00
- Post Title: Kinect Star Wars (PKG)

xbdecompress.exe c:\test.podlzx c:\test.pod

I am almost done with he 3d model format it is so bad its beyond words how cluttered and unoptimized it is.
## Post #9
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2012-04-05T21:38:03+00:00
- Post Title: Kinect Star Wars (PKG)

OK, PODLZX archives have been successfully decompressed and unpacked. Will you be making a bms script for model format conversion?

Excellent work and thanks again.
## Post #10
- Username: abdyla
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Mar 30, 2011 6:29 am
- Post datetime: 2012-04-07T11:59:30+00:00
- Post Title: Kinect Star Wars (PKG)

how you imported the *. dfm file 3Ds Max?
+ File *. TGA does not open.
/
как ты импортировал *.dfm файл  в 3Ds Max?
+  файл *.TGA ничем не открывается.

sample *. dfm file
[http://www.sendspace.com/file/7zghwe](http://www.sendspace.com/file/7zghwe)

sample *. TGA file
[http://www.sendspace.com/file/g3gghj](http://www.sendspace.com/file/g3gghj)
## Post #11
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2012-04-07T21:35:05+00:00
- Post Title: Kinect Star Wars (PKG)

where can i get the xbdecompress.exe cause i really wanna get these models in 3ds max
