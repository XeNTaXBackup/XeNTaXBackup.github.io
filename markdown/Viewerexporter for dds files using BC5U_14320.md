## Post #1
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2016-05-07T16:18:25+00:00
- Post Title: Viewer/exporter for dds files using BC5U

Hi all, could anyone suggest a suitable viewer/exporter for normal maps in dds format using BC5U? I've tried Photoshop, NVIDIA tools and even Noesis (unless there was an update these past few weeks) nothing could open the image properly.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-05-07T17:46:19+00:00
- Post Title: Viewer/exporter for dds files using BC5U

You got any samples?  
BC5U is just ATI2 from what i understand reading this post 
[http://niftools.sourceforge.net/forum/v ... 316#p31956](http://niftools.sourceforge.net/forum/viewtopic.php?f=31&t=6316#p31956)

there is some brief discussion here too
[viewtopic.php?p=112390#p112390](http://forum.xentax.com/viewtopic.php?p=112390#p112390)
Noesis supports it and i tried to write a script that works with the samples from that thread but the native dds reader overrides my script and type check unless you change the extension and magic of the file which kind of defeats the purpose of using the script. i would rather the user not have to edit anything.   

BCn app support
[https://github.com/GameTechDev/Intel-Te ... pp-Support](https://github.com/GameTechDev/Intel-Texture-Works-Plugin/wiki/BCn-App-Support)
## Post #3
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2016-05-07T21:24:47+00:00
- Post Title: Viewer/exporter for dds files using BC5U

> Reply from AceWell
>
> You got any samples?  
BC5U is just ATI2 from what i understand reading this post 
http://niftools.sourceforge.net/forum/v ... 316#p31956

there is some brief discussion here too
viewtopic.php?p=112390#p112390
Noesis supports it and i tried to write a script that works with the samples from that thread but the native dds reader overrides my script and type check unless you change the extension and magic of the file which kind of defeats the purpose of using the script. i would rather the user not have to edit anything.   

BCn app support
https://github.com/GameTechDev/Intel-Te ... pp-Support

Thanks! The dds file was actually output image when exported from openiv... I just found out the tool itself had the workaround I needed, export the image as png instead of dds and use Noesis to convert from png to editable tga.
