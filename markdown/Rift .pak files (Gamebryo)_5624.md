## Post #1
- Username: Lavos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Dec 22, 2010 1:17 pm
- Post datetime: 2010-12-24T18:20:19+00:00
- Post Title: Rift .pak files (Gamebryo)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-12-24T20:52:15+00:00
- Post Title: Rift .pak files (Gamebryo)

```

get ONE long
get FILESIZE long
get PADDING long
get HSIZE long

math HEADERS = HSIZE
math HEADERS /= 60 # size of this structure:

for h = 1 to HEADERS
  getdstring UNKNOWN 20 # 5*4
  get ZSIZE long
  get SIZE long
  get UNKNOWN long
  get POINTER long
  getdstring UNKNOWN 24 # 6*4

  if ZSIZE == SIZE
    log "" POINTER ZSIZE
  else
    clog "" POINTER ZSIZE SIZE
  endif
next h

```


happy holidays
## Post #3
- Username: Lavos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Dec 22, 2010 1:17 pm
- Post datetime: 2010-12-24T21:02:12+00:00
- Post Title: Rift .pak files (Gamebryo)

Woohoo~ Works perfectly, thank you!
## Post #4
- Username: Auumar
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat May 29, 2010 12:56 pm
- Post datetime: 2010-12-24T23:48:42+00:00
- Post Title: Rift .pak files (Gamebryo)

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2010-12-26T13:18:19+00:00
- Post Title: Rift .pak files (Gamebryo)

Header suggests ms adpcm audio but header isn't exactly standard as usual codec info usually with ms adpcm header aint there and block size seems to be set to 72 which isnt standard i've seen used except xbox adpcm, either way it continues to play all wrong.
## Post #6
- Username: Naduron0
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 16, 2010 6:26 pm
- Post datetime: 2010-12-27T04:14:23+00:00
- Post Title: Rift .pak files (Gamebryo)

Awesome! Thanks a lot!   

Is there a way to compress it back?
## Post #7
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2011-01-13T20:01:07+00:00
- Post Title: Rift .pak files (Gamebryo)

sadly there are a few different hashes that need to be computed before we can put files back into the pak where the game will run them
## Post #8
- Username: Kritiker
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jan 18, 2009 8:30 pm
- Post datetime: 2011-01-13T23:04:30+00:00
- Post Title: Rift .pak files (Gamebryo)

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: nosferat
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 15, 2011 9:53 pm
- Post datetime: 2011-01-15T14:32:03+00:00
- Post Title: Rift .pak files (Gamebryo)

thank you for the information that works.

Now I find myself with different file extensions whose application is unknown.

I'm looking to have access to data contained in these files.

File Type: BKH SDB DAT VAP

file_for_test
[http://www.megaupload.com/?d=7T5UQ6FC](http://www.megaupload.com/?d=7T5UQ6FC)


thank you in advance for those who can help me


PS: sorry for the mistakes I'm french.
## Post #10
- Username: hoffmeyr
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 19, 2011 3:21 am
- Post datetime: 2011-01-18T22:14:04+00:00
- Post Title: Rift .pak files (Gamebryo)

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-01-19T10:11:23+00:00
- Post Title: Rift .pak files (Gamebryo)

sorry for the confusion guys - i forgot to mention my script was written for quickbms ([http://aluigi.altervista.org/papers.htm#quickbms](http://aluigi.altervista.org/papers.htm#quickbms))
## Post #12
- Username: hoffmeyr
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 19, 2011 3:21 am
- Post datetime: 2011-01-19T16:21:42+00:00
- Post Title: Rift .pak files (Gamebryo)

The contents of this post was deleted because of possible forum rules violation.
## Post #13
- Username: Kritiker
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jan 18, 2009 8:30 pm
- Post datetime: 2011-01-19T22:26:50+00:00
- Post Title: Rift .pak files (Gamebryo)

now it works, thx. 

Too bd that file names aren't saved :/ i wonder where game stores those names
## Post #14
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2011-01-20T23:06:39+00:00
- Post Title: Rift .pak files (Gamebryo)

hoff:you can figure out the format from the post WRS made
## Post #15
- Username: hoffmeyr
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 19, 2011 3:21 am
- Post datetime: 2011-01-21T00:51:06+00:00
- Post Title: Rift .pak files (Gamebryo)

No, I can't.  If you read the post, I already used what he said to extract the .pak file.  Inside that .pak file was several other files that are also encoded in a format that I can't read.  They're not .paks and have a different structure.
## Post #16
- Username: harpseal
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Dec 08, 2010 8:48 am
- Post datetime: 2011-01-22T12:24:31+00:00
- Post Title: Re: Rift .pak files (Gamebryo)

Thank you for your effort. I am content.
## Post #17
- Username: Kritiker
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jan 18, 2009 8:30 pm
- Post datetime: 2011-01-24T11:29:41+00:00
- Post Title: Re: Rift .pak files (Gamebryo)

> Reply from WRS
>
> sorry for the confusion guys - i forgot to mention my script was written for quickbms (http://aluigi.altervista.org/papers.htm#quickbms)

may i ask how your program determine which extension unpacked files use? rift pak files are easy tu unpack, but i currently have 2 problems with them:

1st file extensions
2nd file names
## Post #18
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-01-24T13:26:36+00:00
- Post Title: Re: Rift .pak files (Gamebryo)

> Reply from Kritiker
>
> may i ask how your program determine which extension unpacked files use? rift pak files are easy tu unpack, but i currently have 2 problems with them:

1st file extensions
2nd file names

sure.

as there are no filenames in the PAK, quickbms handles the file naming:

```
snprintf(fname, PATHSZ, "%08x.dat", (i32)extracted_files);
```


so the filename is the extracted file index (0 to filecount-1) as a 4-byte hexadecimal number
and the extension is just .dat

just because they all have the same extension, they may still be different formats.
## Post #19
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2011-01-25T19:01:54+00:00
- Post Title: Re: Rift .pak files (Gamebryo)

the way i tell the format is by looking at the first few bytes of the data. The file formats i have found so far

.wav
.dds
.nif
.kfm
.bik
.xml
## Post #20
- Username: Pilgrim
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Dec 03, 2010 1:41 am
- Post datetime: 2011-01-25T22:33:47+00:00
- Post Title: Re: Rift .pak files (Gamebryo)

I tried this on a couple of the .pak files, and it worked fine.  However, when I tried the character.pak file, I got the error about line 8623: dumpa_direct_copy() in the source.  Says there is no such file or directory.
Can i fix this?

Thank you for this script.
## Post #21
- Username: Sumpfmolch
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 29, 2011 9:15 pm
- Post datetime: 2011-01-29T13:16:56+00:00
- Post Title: Re: Rift .pak files (Gamebryo)

Thank you for the Script. Anyone found out how to actually play those strange .wav files?
## Post #22
- Username: Windcape
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 14, 2011 1:39 pm
- Post datetime: 2011-02-14T05:46:00+00:00
- Post Title: Re: Rift .pak files (Gamebryo)

Based on the information from WRS in #2 I've started the work on a C# library for a unpacker, [http://code.google.com/p/rift-lib/](http://code.google.com/p/rift-lib/)
So far so good, the unpacking works well, and handles both uncompressed, and compressed files (standard DEFLATE).

In regards to the audio files, if you look at the [RIFF WAVE](http://www.sonicspot.com/guide/wavefiles.html) specification, 
you can see that the Compression Code is 2 (0x0002), which is the equivalent to Microsoft ADPCM.

However, I had no luck decompressing the file with Microsoft ADPCM yet. I tried using the ADPCM decompressor from the MPQ unpacker (for Blizzard games),
but I'm still having trouble with updating the header of the sound file.

Hopefully this information can help to solve the mystery of the sound files. Everything else seems easily decompressed.

Also, anyone managed to get the .nif files opened in [NifSkope](http://niftools.sourceforge.net/wiki/NifSkope) yet?
## Post #23
- Username: aritheory
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Mar 26, 2007 11:49 am
- Post datetime: 2011-02-15T00:23:13+00:00
- Post Title: Re: Rift .pak files (Gamebryo)

> Reply from Windcape
>
> Based on the information from WRS in #2 I've started the work on a C# library for a unpacker, http://code.google.com/p/rift-lib/
So far so good, the unpacking works well, and handles both uncompressed, and compressed files (standard DEFLATE).

In regards to the audio files, if you look at the RIFF WAVE specification, 
you can see that the Compression Code is 2 (0x0002), which is the equivalent to Microsoft ADPCM.

However, I had no luck decompressing the file with Microsoft ADPCM yet. I tried using the ADPCM decompressor from the MPQ unpacker (for Blizzard games),
but I'm still having trouble with updating the header of the sound file.

Hopefully this information can help to solve the mystery of the sound files. Everything else seems easily decompressed.

Also, anyone managed to get the .nif files opened in NifSkope yet?

Nice job Windcape!

I actually have a license for the Gamebryo engine so if you need any contributions, let me know
## Post #24
- Username: Naduron0
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 16, 2010 6:26 pm
- Post datetime: 2011-02-17T03:52:45+00:00
- Post Title: Re: Rift .pak files (Gamebryo)

Awesome!!

I'll be keeping an eye on your project. ^^
## Post #25
- Username: nezroy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 15, 2011 1:44 am
- Post datetime: 2011-03-14T17:49:51+00:00
- Post Title: Re: Rift .pak files (Gamebryo)

Has anyone been working on trying to figure out how the resources are mapped into these pak files? Specifically I'm looking at some of the nifs and they have the expected texture references with .dds texture names, but obviously this naming scheme is not being stored in the paks.

Is this being done through a lookup or are they hashing resource names/ids into the pak somehow?
## Post #26
- Username: divStar
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Sep 22, 2010 6:46 am
- Post datetime: 2011-03-22T12:26:55+00:00
- Post Title: Re: Rift .pak files (Gamebryo)

Hi ,

I've been following this thread and it's probably the only source of information about the RIFT .pak files on the whole web :/. I've successfully extracted soundfiles from audio_0.pak using quickBMS and the offered script. However: the music/sound(s) doesn't/don't play as it/they should. I've tried to import raw data in audacity at many different combinations - still: no success.

Maybe someone in here has figured out how to play the sounds? I don't want to "repack" the stuff .. and I don't care for the filenames.. I just want to find out what music is in there and maybe the sound effects too.

Thank you all in advance!
