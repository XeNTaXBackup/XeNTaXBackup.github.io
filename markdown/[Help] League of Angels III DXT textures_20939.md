## Post #1
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-08-10T12:20:19+00:00
- Post Title: [Help] League of Angels III DXT textures?

This is the other half of the challenge League of Angels III has to offer: The textures. They come in the .dxt format, for which I found out that it is an ATF Texture. That would make it some kind of Adobe-based texture - here's the result of the TrIDNET analysis:
Match: 100,0%
Ext: ATF
Type: ATF Texture
Pts: 3000/1
The files in question are [these two](https://drive.google.com/open?id=1nu5fjKoB5iPNnPusbXpmudFH5UhLECKr) (I lead to the archived file!)

Is there any program which can open these files? If they're archived files - which I can't think of - what kind of archived files are those?
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-08-17T07:10:47+00:00
- Post Title: [Help] League of Angels III DXT textures?

there is some tools here to work on atf files.   
[https://github.com/hajimeku/atf-test-tool](https://github.com/hajimeku/atf-test-tool)
or more specifically here:
[https://github.com/hajimeku/atf-test-to ... TF/atftool](https://github.com/hajimeku/atf-test-tool/tree/master/atftools/batchConvert2ATF/atftool)
ATFViewer.exe is a GUI tool that will open your 2 samples for viewing and some info,
and atf2pvr.exe is a commandline tool that can only seem to convert your dxt1 sample,
but the pvr header created by the program looks strange to me.
## Post #3
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-08-18T03:26:34+00:00
- Post Title: [Help] League of Angels III DXT textures?

I found part of the solution, but now it cries for Android platform tools... League of Angels III runs - as far as I know - only on PC, so:
Is there any chance to get PC platform tools?
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-08-18T06:23:30+00:00
- Post Title: [Help] League of Angels III DXT textures?

what part of solution did you find, any good source code?   
it looks like each mip is lzma compressed though.
## Post #5
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-08-18T06:29:47+00:00
- Post Title: [Help] League of Angels III DXT textures?

I need Adobe Flex SDK to run it - that comes up when trying to run the tool and that additional program isn't installed at all.

What are the mip's you're talking about? Do I still have an archive in an archive? I'm wondering 'cause when I try to open them with 7z, it throws out an error saying that the file can't be opened as an archive...

Btw: If you want to shorten the way of discussing that with me, I'm also on the official Discord (display name there's my username here) 

EDIT wants to note:
I found out some more stuff about those .dxt files from the opening post - it seems this format is pretty common in the games business and they get used as a container file for textures, which in turn allows bigger textures at a smaller video memory usage. How could help this transferred to the textures from this game? And how did you manage to get the tool to open the files?
## Post #6
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-11-06T08:41:48+00:00
- Post Title: [Help] League of Angels III DXT textures?

Files are back up again - need a helping hand with converting them into a useful format (like .png)...

Working in shift prevents me from working full-time on that stuff...
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-11-08T13:08:32+00:00
- Post Title: [Help] League of Angels III DXT textures?

install Adobe Air
[https://www.adobe.com/products/air.html](https://www.adobe.com/products/air.html)
then install this ATF plugin
[https://vamapaull.com/atf-to-png-converter-tool/](https://vamapaull.com/atf-to-png-converter-tool/)

rename the extension of your samples from dxt to atf then open
them with the converter and they will convert to png immediately
and write to a folder named "PNG" in the same location as samples.
## Post #8
- Username: douchi
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 29, 2019 10:24 pm
- Post datetime: 2019-11-09T15:12:17+00:00
- Post Title: [Help] League of Angels III DXT textures?

> Reply from Acewell ↑Fri Nov 08, 2019 9:08 pm at Fri Nov 08, 2019 9:08 pm
>
> 
install Adobe Air
https://www.adobe.com/products/air.html
then install this ATF plugin
https://vamapaull.com/atf-to-png-converter-tool/

rename the extension of your samples from dxt to atf then open
them with the converter and they will convert to png immediately
and write to a folder named "PNG" in the same location as samples.

Hello, acewell, I heard from bigchildghost that you have a special research on mapping. I want you to help me see if this encrypted TGA map can be converted into a normal TGA image. I hope to get your help.
This is my post:
[viewtopic.php?f=18&t=21363&p=157607#p157607](https://forum.xentax.com/viewtopic.php?f=18&t=21363&p=157607#p157607)
Hope to get your help。
