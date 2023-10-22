## Post #1
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-12-05T14:09:00+00:00
- Post Title: Fantasy Life [3DS] File Archive.bin

Hey Guys.

So I managed to decrypt and extract the files from Fantasy Life for the 3DS.

Outside of some smaller shader files theres a large 312mb _File_Archive.bin file.

This should contain all the games models and textures, probably other stuff too but i can't say.

I've used FileCutter and since its 1mb too large to attach to this post, I've placed it into my dropbox here:

[https://dl.dropboxusercontent.com/u/779 ... rchive.zip](https://dl.dropboxusercontent.com/u/7797280/FantasyLife_file_archive.zip)

I'm really interested in whats inside this file along with how some things were put together, I'm sure that whatever files are in here are probably going to be a weird compressed/encrypted format anyway, but won't know until this has been opened up.
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-12-08T16:33:30+00:00
- Post Title: Fantasy Life [3DS] File Archive.bin

Damn.

Was really hoping somebody might be interested in this too.
## Post #3
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2014-12-14T10:01:56+00:00
- Post Title: Fantasy Life [3DS] File Archive.bin

It's an easy format to unpack, but no filenames.

```
numFiles * 4 Byte = OffsetTable
```

Between OffsetTable[0] and the end of the table is an InfoTable, but it's not needed for unpacking and it does not contain any filenames.

Compression is Lz77, 0x10/0x11.
Number of Files is 58.095, but there are 0-byte files, the true count is 38.204.
Fileformats are ztex, zmdl, actmot, BPAK and other.

Here a quickbms script to unpack:

```

get numFiles long
get temp long

set lastfile numFiles
math lastfile -= 1

for x = 0 < numFiles

	get Offset long
	savepos temp

	if x == lastfile
		get Size asize
	else
		get Size long
	endif

	math Size -= Offset

	#note: offset table contains 0-byte files, we skip them
	if Size > 0
		goto Offset
		get Ident byte
		get USize threebyte

		if Ident == 0x10
			clog "" Offset Size USize
		elseif Ident == 0x11
			clog "" Offset Size USize
		else
			log "" Offset Size
		endif
	endif
	
	goto temp

next x
```
## Post #4
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-12-14T11:23:21+00:00
- Post Title: Fantasy Life [3DS] File Archive.bin

Thanks Falo.

Though I actually just ran this script from what you sent me over at GBAtemp, haha.

Now its just figuring out the formats within really.

.dat files contain, I've really no idea, areas, events, and possibly animations, zte are ztex files, it looks like they're a container for various .tga files.

the .bpa files are bpak, I can't really tell what they contain, lots of SOBJ fils and CNOD files though, looks like a container of sorts.

Same situation with the .zmd files, they're archives containing models, 99% header is zmdl, I see a fair few things in there, nothing I'd be able to do anything with due to my limited skills, but theres deffinitly some models in those.
