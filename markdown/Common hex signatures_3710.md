## Post #1
- Username: Loculi
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 15, 2009 10:40 pm
- Post datetime: 2009-09-11T16:21:58+00:00
- Post Title: Common hex signatures

I was wondering if anyone knows of a good source for identifying common file signatures in hex.

For instance, from chrrox's tutorials and the Xentax wiki I learned that:

TGA - ends with "TRUEVISION-XFILE"
ZIP - hex signature is 0x04034b50
ZLIB - compression header sig. 789C

Looking a bit deeper, I was able to find a very similar resource to what I mean here: 

[http://www.garykessler.net/library/file_sigs.html](http://www.garykessler.net/library/file_sigs.html) 

But, I would love to find a more targeted list that covers the common files found in game archives. (e.g. jpeg, dds, mat, ogg, wav, etc.)  Does such a thing exist, or maybe I'm just looking in the wrong place and someone can guide me.

Cheers
## Post #2
- Username: nneonneo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 24, 2010 7:29 am
- Post datetime: 2010-11-24T13:19:21+00:00
- Post Title: Common hex signatures

It's sometimes useful to save out the unknown file and use the `file' utility (pre-installed on most modern operating systems except Windows, for which you can get a binary [here](http://gnuwin32.sourceforge.net/packages/file.htm)). `file' has a large, programmable database of file signatures.

Of course, this isn't a substitute for the simple ability to "see" a file's format just by looking at the hexdump.
## Post #3
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2010-12-17T03:57:20+00:00
- Post Title: Common hex signatures

Here are the ones I run into the most and then file types you mentioned. 


Textures

"DDS " : 0x44 0x44 0x53 0x20 : Direct3D Texture
"TIM2" : 0x54 0x49 0x4D 0x32 : Playstation 2 Texture // May not always be at the start of the file


Images

"JFIF" : 0x4A 0x46 0x49 0x46 : JPEG image // The JTIF appears 6 bytes into the file
"‰PNG" : 0x89 0x50 0x4E 0x47 : PNG image
"GIF" : 0x47 0x49 0x46 : GIF image
"8BPS" : 0x38 0x42 0x50 0x53 : PSD image  // photoshop document


Audio

"ID3"   : 0x49 0x44 0x33 0x?? : .MP3 audio file // The 4th byte inicates the version of the header and its either 0x01 or 0x02
"RIFF" : 0x52 0x49 0x46 0x46 : .WAV audio file // Also has tell-tale "WAVEfmt " 8 bytes into the file
