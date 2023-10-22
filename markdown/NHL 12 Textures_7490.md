## Post #1
- Username: Vampiretea
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 12, 2011 4:52 am
- Post datetime: 2011-10-11T21:02:13+00:00
- Post Title: NHL 12 Textures

Hello, XeNTaX. I've been looking a forum for long time now that can answer a few questions and finally I've found you!

I think this is the place where I can get some answers for some major issues when it comes to opening texture files from NHL 12. Before I register here, I visited this forum and checked out "FIFA 12 Textures" - thread. It seems like some of you are able to open FIFA 12 XBOX 360 texture files which are in *.rx3 - format. I'm wondering if you can do the same thing with NHL 12 texture files which are in *.rx2 -format? So far I haven't seen a single editor that can open these kind of files and trust me, I've been searching for a long time now.

What I found that NHL 12 files are constructed similiar way compared to FIFA. Texture files are in *.big files and I'm able to extract the *.rx2 - files with QuickBMS. However, that's all I can do. File headers are in "RW4xb2" - format, the same format NBA Live 06 uses for texture files. In FIFA 12, the file headers are "chunklzx."

Here's few files from NHL 12: [http://www.mediafire.com/?cozvkpwukuj23dz](http://www.mediafire.com/?cozvkpwukuj23dz)

Whoever finds a solution for this, I owe him a big favour. This has been tried to do now for almost 3 years without any bigger result. 

Best regards, Vampiretea
## Post #2
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-10-12T07:06:16+00:00
- Post Title: NHL 12 Textures

In files with names ending with _dm, _tm and _cm, I see textures. They are easy to spot - FF FF 00 00 | FF FF 00 00. Or 00 00 00 86 | 00 1F E0 FF.

Actually value 0x001FE0FF contains width and height of the texture. You can use my definition of [NFSHP2010 X360 textures](http://forum.xentax.com/viewtopic.php?p=60292#p60292) and fit it on NHL12 textures.
## Post #3
- Username: Quingo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Feb 25, 2010 7:45 pm
- Post datetime: 2011-10-12T10:23:29+00:00
- Post Title: NHL 12 Textures

Interesting you were able to make something out of it. Do you know how it would be possible to open them, or convert them into a readable format (I suppose they're somehow twisted DDS-files) and vice versa?
## Post #4
- Username: Vampiretea
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 12, 2011 4:52 am
- Post datetime: 2011-10-12T11:03:09+00:00
- Post Title: NHL 12 Textures

I'm wondering the same as Quingo. So tell us, mnn, how hard you think it's to convert them in to readable format?
Adn what should I do with that code you posted? Yes, I'm a noob in things like this.
## Post #5
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-10-12T14:11:15+00:00
- Post Title: NHL 12 Textures

Well, the format seems to be RGBA (0x86). Basically you need to extract all raw data, then you need to byte-swap because of the big endian on consoles and most likely untiling (and/or unswizzling) takes places.
## Post #6
- Username: Vampiretea
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 12, 2011 4:52 am
- Post datetime: 2011-10-12T14:18:53+00:00
- Post Title: NHL 12 Textures

> Reply from mnn
>
> Well, the format seems to be RGBA (0x86). Basically you need to extract all raw data, then you need to byte-swap because of the big endian on consoles and most likely untiling (and/or unswizzling) takes places.

In lightness? Any chance to link for a tutorial and what tools I need to get extract all the raw data from that? 
And of course, how I perorm a byte-swap? With HEX-editor?
I'm not asking you to do it, but are you able to do all this ?
## Post #7
- Username: Vampiretea
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 12, 2011 4:52 am
- Post datetime: 2011-10-12T16:12:37+00:00
- Post Title: NHL 12 Textures

Another weird thing. Here is the link for NHL 12 Texture file and FIFA 11 Texture file: [http://thegrafixer.com/nhl12/rw4xb2.zip](http://thegrafixer.com/nhl12/rw4xb2.zip). NHL 12 texture file have been renamed to .rx3 file using Windows Explorer (which doesn't help at all). The Fifa file is from PC-version and the NHL 12 file from XBOX 360.

However, no changes have been made in FIFA 11 file. If you compare these files with HEX Workshop, you can see that the files are identical, but  FIFA 11 texture file is still the only file that can be opened using "RX3 Master" with this result:

[](http://aijaa.com/v.php?i=007198863200.png)

Any help? Looks like we're so close with this but still so far away. It's getting pretty complicated since we tried to found an answer from FIFA 12 XBOX 360 - version, although it uses compeletly different file header, a header called "chunklzx".

E: I have spotted the difference between these two files with HEX-editor. In FIFA 11, on line 004080 (HEX Workshop), there's a also header named "rx3b" which cannot be found on NHL 12 texture file. So what we need now, is to somehow get that "rx3b" header in NHL 12 texture, am I right? Any ideas, mnn?
## Post #8
- Username: Vampiretea
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 12, 2011 4:52 am
- Post datetime: 2011-10-12T18:02:23+00:00
- Post Title: NHL 12 Textures

Okay, now I think I get it somehow and partly. Underneath there's a script I've been modified from you original script:

```
{
    int stuff1[8];
    int textureType; // mask  0x001FE0FF, 0x86 = DXT1, 0x87 = DX2/3, 0x88 = DXT4/5
    int size;   // 0-12 bits = height (+1), 13-25 = width (+1), 26-31 = flags
    int stuff2;
    int mipmaps; // bits 6-11
}
flag = size >> (13 * 2);
height = ((size >> 13) &  0x001FE0FF) + 1;
width = ((size << 19) >> 19 & 0x001FE0FFF) + 1;
mipmaps = (temp >> 6) &  0x001FE0FFFF;
```


Am I right and you will guarantee that this method will work? 

But I still don't get it. This script works with what tool? What program should I use to run this script? And the byte-swap thing. Is there a script for that also?

And then I need to untile the file using GTA IV Xbox 360 Texture Editor by Frosty (DXTDecoder.ConvertToLinearTexture) script? Should I run that script with GTA IV Xbox 360 Texture editor?
## Post #9
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-10-12T18:32:11+00:00
- Post Title: NHL 12 Textures

No, actually you've ruined that script 

0x001FE0FFF was just value where width & height of the texture is saved. You have to leave those hex values as they are, because they "extract" width & height from that "ugly" value (width & height are saved in 13-bits and not some pretty as 16 or 32-bit).

You need to modify it in terms of adding/removing fields, because NHL12 textures don't seem to be exactly the same [as NFSHP2010].

> Reply from Vampiretea
>
> But I still don't get it. This script works with what tool? What program should I use to run this script? And the byte-swap thing. Is there a script for that also?
That's just a quick overview of the header, it's not exactly written in any (scripting) language.

> Reply from Vampiretea
>
> And then I need to untile the file using GTA IV Xbox 360 Texture Editor by Frosty (DXTDecoder.ConvertToLinearTexture) script? Should I run that script with GTA IV Xbox 360 Texture editor?
That's not a script. That's C# code. Also you can't directly use that application - you need to write your own.

Generally, these things are not as easy as they seem. I strongly recommend to learn some programming (or scripting) language.
## Post #10
- Username: Vampiretea
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 12, 2011 4:52 am
- Post datetime: 2011-10-12T18:35:59+00:00
- Post Title: NHL 12 Textures

So you're saying that there's not an easier way? ffs... How can it be that FIFA files are much more easier, although they're almost same. God damn. So there's not a script that can add "Rx3b" headers in "Rw4xb2" -texture files?

Maybe we have to finally agree, after three years, that this is impossible to do with such a small group.
## Post #11
- Username: Vampiretea
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 12, 2011 4:52 am
- Post datetime: 2011-10-12T21:00:46+00:00
- Post Title: NHL 12 Textures

Shame that I can't do any scripts with C# and don't think there is anyone who'd like to do it just to test his limits... Looks like we just have to bury this idea =/
## Post #12
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-10-13T07:31:29+00:00
- Post Title: NHL 12 Textures

> Reply from Vampiretea
>
> So you're saying that there's not an easier way? ffs... How can it be that FIFA files are much more easier, although they're almost same. God damn. So there's not a script that can add "Rx3b" headers in "Rw4xb2" -texture files?
I have no idea. Maybe it is possible to use some stuff from FIFA...

> Reply from Vampiretea
>
> Shame that I can't do any scripts with C# and don't think there is anyone who'd like to do it just to test his limits... Looks like we just have to bury this idea =/
C# is a [url=[http://en.wikipedia.org/wiki/C_Sharp_%2 ... anguage%29](http://en.wikipedia.org/wiki/C_Sharp_%28programming_language%29)]programming language[/b], not scripting...
