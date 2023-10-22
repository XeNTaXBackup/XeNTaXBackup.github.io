## Post #1
- Username: Rear Wheel Drive
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 21, 2014 12:30 am
- Post datetime: 2014-04-20T18:09:57+00:00
- Post Title: SWTOR GR2 to OBJ Converter

Hi everyone, new to this forum so idk if this is the right place for this post but anyway...

I made a [very rough and dirty] converter for the GR2 files used by SWTOR. Some people may know that in the beta version of TOR they used standard GR2 files, which could with relative ease be converted to OBJ/whatever to be opened up in a modelling program. Since the retail versions however, they changed the format and I was unable to find any program that read this new format, so I made one.  

This is a simple console application, to use just drag a GR2 on in windows explorer and it will automatically convert.

PLEASE NOTE: This is as I said very rough and dirty, I made this in a day! As of right now, it only converts the mesh, so no UV maps, no bones, and no normals either  I of course intend to implement these in the future, but I thought I'd try and get this basic version out nice and quick. There also seems to be a problem with the scaling, which is probably to do with how I'm reading the coordinates of vertices. As such, there are two things you should do when importing the converted obj:
Set your modelling program to auto generate normals, this is easy to do in Max, although I haven't tried any other program. Just google it and it shouldn't be too hard
Scale up! You'll want to set the scale to somewhere in the order of between 100 and 1000, again very easy to do, just google it if you don't know how

Here's the download link: [http://www.mediafire.com/download/60v8k ... ecoder.zip](http://www.mediafire.com/download/60v8khxx6xuxu3l/gr2decoder.zip)

And a picture of a model in 3DS Max:



EDIT: Forgot to mention also, a very big thanks to the author of this wiki page, without whom I'd have had no idea where to start. [http://wiki.xentax.com/index.php?title= ... model_file](http://wiki.xentax.com/index.php?title=SWTOR:_.gr2_3D_model_file)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2014-04-20T23:10:13+00:00
- Post Title: SWTOR GR2 to OBJ Converter

Thanks for sharing! I'm having trouble with it when dragging a *.gr2 file on the 'GR2 Decoder.exe'. 
I get this error: "GR2 Decoder.exe is not a valid Win32 application" 
Is this a debug or release build? Is .NET Framework 4.5 required for it to work? Are there any other dependencies?
## Post #3
- Username: Rear Wheel Drive
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 21, 2014 12:30 am
- Post datetime: 2014-04-23T18:21:14+00:00
- Post Title: SWTOR GR2 to OBJ Converter

Yes sorry I accidentally released it targeted to .NET 4.5, I've changed it to 3.5 which is the lowest I could get it to work, at least at short notice. Just download the file again from the link in my first post and it should work, provided you have .NET 3.5 of course.
## Post #4
- Username: Misium
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 06, 2014 6:27 pm
- Post datetime: 2014-10-06T10:35:18+00:00
- Post Title: SWTOR GR2 to OBJ Converter

Has there been any progress on this? I've been trying to get the Fury Class Interceptor model all morning and most of yesterday. I've got the .gr2 model finally, but I'm stuck trying to get it into 3DS Max 2013. Everything I've found has been for older versions.

Your program here is the closest I've come.

When I import the resulting .obj, this is what I end up with:



interceptor broken.jpg (16.43 KiB) Viewed 408 times


Something is clearly not right, but I don't know what to do about it or if there's some alternate way I could get a working model of this ship. I'm about to the point of giving up.
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2014-10-07T01:04:50+00:00
- Post Title: SWTOR GR2 to OBJ Converter

Use [Noesis](http://forum.xentax.com/viewtopic.php?f=33&t=4582) and the [swtor plugin](http://forum.xentax.com/viewtopic.php?p=94880#p94880) to import the gr2 file, they provide better support at this time.
