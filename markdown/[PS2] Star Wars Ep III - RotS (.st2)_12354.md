## Post #1
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2014-12-08T20:07:19+00:00
- Post Title: [PS2] Star Wars: Ep III - RotS (*.st2)

Hi, i need help with this *.st2 texture format and if possible a method for converting them to usable images.

You can almost make out some images in TextureFinder. 
In a hex editor they look identical to these:
[viewtopic.php?f=18&t=10545](http://forum.xentax.com/viewtopic.php?f=18&t=10545)
Both games were developed by The Collective.

Are they encrypted, compressed, swizzled, twittled ... ?
Any help is appreciated, thanks!  


 samples.zip
(52.69 KiB) Downloaded 29 times



edit
the Xbox version of this game uses *.stx textures which are just *.dds with a custom header.  

the Xbox *.pak files contain a bunch of *.stx textures and they usually follow the model (msh) they belong to.
i can't unpack the *.pak files for the Xbox version, but the files are uncompressed and can be pulled out by hand. 
the PS2 version *.pak files can be unpacked using offzip but no one knows how to convert those models and the xbox textures are higher res anyway so it is rather pointless.
