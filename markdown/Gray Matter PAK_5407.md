## Post #1
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2010-11-17T15:16:49+00:00
- Post Title: Gray Matter PAK

Hi guys,

There is out one nice adventure Gra Matter, so it is available only in English and Deutch.

Here are localization files, looks like compressed somehow.
en.pak, 171 kb: [http://www.datafilehost.com/download-7c1ecb66.html](http://www.datafilehost.com/download-7c1ecb66.html)
Fonts.pak, 658 kb: [http://www.datafilehost.com/download-605ac977.html](http://www.datafilehost.com/download-605ac977.html)

Any help with extracting/decompressing and back, will be appreciated.

Thanks in advance my brothers! Love you!
## Post #2
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-11-17T16:12:02+00:00
- Post Title: Gray Matter PAK

Here's my .PAK extractor / packer / replacer program.

The attached file deleted. See my latest comment for the most recent version...
## Post #3
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2010-11-17T18:23:38+00:00
- Post Title: Gray Matter PAK

Great work done!  

Thank you brather!
## Post #4
- Username: alternati
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 26, 2010 3:57 am
- Post datetime: 2010-11-19T00:06:34+00:00
- Post Title: Gray Matter PAK

Hello, here the file spec, sorry but i don't know correct wiki-xentax file format or bms scripting.

File extension: .PAK
Endianness:   Little-endian

Format Specifications 

```

uint32 {4}		- Offset Base

byte {Offset Base - 8}	- Header (compressed in ZLIB)

byte {x}		- File 1 (compressed in ZLIB) (Located in Offset Base)       

byte {x}		- File 2 (compressed in ZLIB) (Located in Offset Base + Offset)

....

byte {x}		- File x (compressed in ZLIB) ...
```


Header Spec (unpacked)

```

FOR 0 to numsubdirectories - 1

	uint32 {4}	- Strlen Directory Name
	
	char {strlen}	- Directory Name
	
	uint32 {4} = 0	- NULL
	
	uint32 {4}	- Num Files

	FOR 0 to numfiles - 1

		uint32 {4} 	- Strlen Filename

		char {strlen}	- Filename

		uint32 {4}	- Offset (relative)

		uint32 {4}	- Zsize (compressed size)

		uint32 {4}	- Size (unpacket size)

 	FOREND
FOREND

uint32 {4} = 0		- NULL
```

In Depth *.LOC Spec (unpacked - Located in LOCALIZED\xx.pak)

```

FOR x = 0 to numstring

	uint32 {4}					- Relative offset String X

ENDFOR

char{offset1 - offset0} 				- String 1 (null terminated)

char{offset2 - offset1} 				- String 2 (null terminated)

...

char{sizefile - 4*(1 + numstring) - Last offset}	- Last String (null terminated)
```
## Post #5
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2010-11-19T10:25:30+00:00
- Post Title: Gray Matter PAK

Good work, just a small correction:

> Reply from alternati
>
> 
Header Spec (unpacked)
Code: Select alluint32 {4}		- Num Subdirectories

FOR 0 to numsubdirectories

	uint32 {4}	- Strlen Directory Name
	
	char {strlen}	- Directory Name
	
	uint32 {4} = 0	- NULL
The last zero value is presumably the number of subdirectories within the current directory. The whole structure is most probably recursive.

> Reply from alternati
>
> 
Code: Select all [...]
uint32 {4} = 0		- NULL
This last value should be the number of files in the current directory, otherwise you'll miss some files. Take a look at PAK archives that don't have subdirectories (fonts.pak?) and you'll see what I'm hinting at.

In the end, the basic structure should look like this:

```
  uint32 {4}     - number of subdirectories
  // for each subdirectory
    uint32 {4}     - subdirectory name length
    char {x}       - subdirectory name
    TPAKStruct {x} - recursive entry for subdirectory
  uint32 {4}     - number of files within this directory
  // for each file: just as you described
)

```


Best wishes,
Deniz
## Post #6
- Username: alternati
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 26, 2010 3:57 am
- Post datetime: 2010-11-19T12:06:31+00:00
- Post Title: Gray Matter PAK

> Reply from Deniz Oezmen
>
> Good work, just a small correction:
The last zero value is presumably the number of subdirectories within the current directory. The whole structure is most probably recursive.

mmm... great I had not thought about it	

> This last value should be the number of files in the current directory, otherwise you'll miss some files. Take a look at PAK archives that don't have subdirectories (fonts.pak?) and you'll see what I'm hinting at.

Yep, i missed add this note in file spec for files without directories. And another "bug" was For 0 to numfiles -> must be For 0 to numfiles - 1 ^_^

> In the end, the basic structure should look like this:
>
> Code: Select allTPAKStruct = (
>
>   uint32 {4}     - number of subdirectories
>
>   // for each subdirectory
>
>     uint32 {4}     - subdirectory name length
>
>     char {x}       - subdirectory name
>
>     TPAKStruct {x} - recursive entry for subdirectory
>
>   uint32 {4}     - number of files within this directory
>
>   // for each file: just as you described
>
> )

Better than mi looooooong file spec jajaja. I'll take note !!!

> Best wishes,
>
> Deniz

Thanks for your feedback. For people that are learning like me, these comment are very usefull
## Post #7
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2010-11-19T12:08:13+00:00
- Post Title: Gray Matter PAK

I almost finished my tools too, I'll post them in a few hours. Deniz Oezmen is right, it's recursive. I'm adding support for XBOX360 files and there is a little dumper/reinserter for the text files
## Post #8
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-11-21T15:24:53+00:00
- Post Title: Gray Matter PAK

Can anyone help me with the format of  .abc and .fnt files in fonts.pak?
A sample is here:
[Arial_10.rar](https://xentaxbackup.github.io/file/3630_Arial_10.rar)
## Post #9
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-12-02T16:34:21+00:00
- Post Title: Gray Matter PAK

Here's a simple commandline version of my PAK maker/extractor/updater.
## Post #10
- Username: sl4cker
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 29, 2010 6:06 pm
- Post datetime: 2010-12-03T00:21:39+00:00
- Post Title: Gray Matter PAK

> Reply from bacter
>
> Here's a simple commandline version of my PAK maker/extractor/updater.

Thanks again bacter. You just made my night xd
## Post #11
- Username: suszi
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jan 02, 2011 6:30 pm
- Post datetime: 2011-01-08T09:38:17+00:00
- Post Title: Gray Matter PAK

```

```


I wait for this program ! Unpack Gray Matter Xbox 360 file .pak ??
## Post #12
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2011-01-08T10:23:54+00:00
- Post Title: Gray Matter PAK

yeah, I had a little problem with the packer and I never continued since...the unpacker is ok if you just need that
## Post #13
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2011-01-08T11:17:11+00:00
- Post Title: Gray Matter PAK

Could someone post some XBOX sample .pak files?
It's possible that it's just the same structure as the PC version, with reversed Endianness.
## Post #14
- Username: suszi
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jan 02, 2011 6:30 pm
- Post datetime: 2011-01-08T13:53:21+00:00
- Post Title: Gray Matter PAK

Non problem this is lockalized xbox 360 en.pak file i need extract becose lockalized this game sorry 4 my language im from poland this is the file xbox 360 
```
http://www.megaupload.com/?d=RHZQ766Y
```
## Post #15
- Username: lordfrikk
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 10, 2011 12:07 am
- Post datetime: 2011-01-09T16:21:52+00:00
- Post Title: Gray Matter PAK

> Reply from stevenx
>
> Can anyone help me with the format of  .abc and .fnt files in fonts.pak?
A sample is here:

Quoting this in case there's someone here who can help. I ready to start translating the game but need to add some of the characters typical to our language.
## Post #16
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2011-01-28T15:14:40+00:00
- Post Title: Re: Gray Matter PAK

Niether of these tools (the GUI or the command line version) seem to work on the (360)full games PAK files..only the (PC)demo?
## Post #17
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2011-01-29T07:48:17+00:00
- Post Title: Re: Gray Matter PAK

If I'll have some time, I will update my utils.

The XBOX version uses just the same formats, but with reversed Endianness,
so I'll have to update my program's .PAK and .LOC file handling parts.
## Post #18
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2011-01-29T14:25:59+00:00
- Post Title: Re: Gray Matter PAK

> Reply from bacter
>
> If I'll have some time, I will update my utils.

The XBOX version uses just the same formats, but with reversed Endianness,
so I'll have to update my program's .PAK and .LOC file handling parts.

Thank you so much! Look forward to it
## Post #19
- Username: harpseal
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 08, 2010 8:48 am
- Post datetime: 2011-02-01T13:21:52+00:00
- Post Title: Re: Gray Matter PAK

Thank you.I tested it work's.
## Post #20
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2011-02-02T05:11:34+00:00
- Post Title: Re: Gray Matter PAK

Here's the updated version of my PAK util.
I hope this works with the XBOX version too.
(The Extract and Make functions)
## Post #21
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2011-02-02T14:34:09+00:00
- Post Title: Re: Gray Matter PAK

Indeed it does! Thank you!

 Sadly the grey Matter blender script fails but i've posted on that thread and hopefully a resolution might be found.
## Post #22
- Username: saidsrc
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Apr 18, 2011 10:38 pm
- Post datetime: 2011-05-09T12:06:27+00:00
- Post Title: Re: Gray Matter PAK

For fellows who want to edit font files: Edit only the DDS file with Photoshop DDS Plugin and you must edit both the RGB and the Alpha channels. After finishing save it with DXT5 and you are good to go.
## Post #23
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-05-23T09:07:09+00:00
- Post Title: Re: Gray Matter PAK

> Reply from bacter
>
> Here's the updated version of my PAK util.
I hope this works with the XBOX version too.
(The Extract and Make functions)

Thank you for the tool. But i have a problem with PC version where i'm able to unpack the texts but all files has only 1 kb. I guess it is caused by Special characters like ščřžýť. Please help

```
http://loadfiles.in/v8fkl2vugj50/cs.pak
```
## Post #24
- Username: forced2be
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 08, 2010 1:35 am
- Post datetime: 2011-06-27T07:41:12+00:00
- Post Title: Re: Gray Matter PAK

where's the link to download this unpacker?
## Post #25
- Username: 3pacalypse
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Jul 08, 2010 10:17 am
- Post datetime: 2013-01-16T20:25:19+00:00
- Post Title: Re: Gray Matter PAK

bacter removed all of his tools for some reason. Im looking for couple of his old tools, but there are nowhere to be found.
