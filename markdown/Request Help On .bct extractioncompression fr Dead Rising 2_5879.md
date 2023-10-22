## Post #1
- Username: Spider3PO
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 01, 2010 6:43 am
- Post datetime: 2011-01-22T22:12:58+00:00
- Post Title: Request Help On .bct extraction/compression fr Dead Rising 2

Need help with .bct. What I'm hoping for, is .bct compressor/extractor. If it is, indeed an archive format. Which, I believe it is.

If it's not, and don't discount it yet. Then, I need a converter that can also handle the header files.

What I know about DR2's textures:
- uses S3 texture compression (DX1, DX2, etc. mipmaps)
- .bct is connected to this somehow, in some cases can be converted to .dds files using a script with quickbms. This is done by running some .tex files through it. Others, will only generate a .bct.
- texmod, can save textures the crappy way, but, putting them in this way is poor and sloppy. For a list of reasons. One of the main ones, you need to boot texmod up with the game to use your custom textures.

Notes on quickbms and using existing script methods:
However, while being the best way, this doesn't work for all .bct files. I suspect, cause there's more then 1 .dds file in some .bct files. 

For example, kinda like modifying the odd FMOD file by changing the format, getting lucky, and hear sound. But, do it to others and you get crap cause the resources weren't extracted (of course, I have no issue with FMOD, I can grab what I want from that - just an example). With this quickbms method, you also need to edit the header files with a hex editor if you succeed. Keyword, if. Some things, won't convert.

Link to the quickbms program with script. Note, I have no relation to the files, other then the use of quickbms, gibbend's tools, and wtv. Here's two links to the tools.

[http://deadrising2mods.proboards.com/in ... s&thread=4](http://deadrising2mods.proboards.com/index.cgi?action=display&board=dr2tools&thread=4)

[http://deadrising2mods.proboards.com/in ... thread=213](http://deadrising2mods.proboards.com/index.cgi?board=dr2tuts&action=display&thread=213)

They'll work for some textures. The car is one I tested, that works. However, some it will do nothing. Like the Safehouse .tex files. Creating, .bct's that didn't convert.  

Its possible, I may have missed details or gotten something wrong. But, as it stands right now, not every texture can be edited. And that's a fact. Please, help. I'll try to gain more information on the .bct format in the meantime. However, the net is scarce on info on this file type. And most of it, is inaccurate in relation to Dead Rising 2. No surprise there. I suspect, game developers and 3d artists in the game industry know exactly what this is though. Hopefully, someone here knows too and can make a better tool or script. Thank you for your time.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-02-08T21:43:50+00:00
- Post Title: Request Help On .bct extraction/compression fr Dead Rising 2

```
Get U1 Long 0 ;
Get HeaderSize Long 0 ;
Get ArchiveSize Long 0 ;
Get FNum Long 0 ;
Get ITableOffset Long 0 ;
Get ITableEnd Long 0 ;
For T = 1 To FNum ;
Get NameOffset Long 0;
Get U2 Long 0 ;
Get PackSize Long 0 ;
Get UnpackSize Long 0 ;
Get Offset Long 0 ;
Get PadSize Long 0 ;
Get Compressed Long 0 ;
SavePos POS 0 ;
GoTo NameOffset 0 ;
Get Name String 0 ;
Log Name Offset PackSize 0 0 ;
GoTo POS 0 ;
Next T ;


```
 

That's a MultiEx Commander script for *.big files. I'm looking into the DDS format as well.

.bct format looks like a simple DDS data file with custom header.
