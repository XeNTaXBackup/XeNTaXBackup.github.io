## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-10-05T16:25:17+00:00
- Post Title: RAGE .RESOURCES files

I am wondering if anyone knows how to extract these packages from the New ID tech 5?

[http://www.mediafire.com/?wlxdu366ew2p4el](http://www.mediafire.com/?wlxdu366ew2p4el)

I included the start and end cuts of the gameresources archive.

Thanks in advance.
## Post #2
- Username: oveja
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Feb 24, 2011 4:35 am
- Post datetime: 2011-10-06T11:52:40+00:00
- Post Title: RAGE .RESOURCES files

maybe zlib.
try offzip.
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-10-06T12:06:10+00:00
- Post Title: RAGE .RESOURCES files

Doesn't work.
## Post #4
- Username: vadim
- Rank: advanced
- Number of posts: 41
- Joined date: Fri Apr 09, 2010 11:15 pm
- Post datetime: 2011-10-06T12:35:38+00:00
- Post Title: RAGE .RESOURCES files

Gameresources_end.resources file without compression, there are resources localization in different languages
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-10-06T13:12:57+00:00
- Post Title: RAGE .RESOURCES files

Yes and also see music and sound strings which links to the streaming resource bank which is entirely uncompressed. with adpcm data. I would love to extract those with original filenames from the strings in gameresource bank.
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-10-06T16:06:34+00:00
- Post Title: RAGE .RESOURCES files

what is the filesize of gameresources.resources? 700mb+ ?

also, i heard rumors this game was 1 tb in size before it was optimized !?
## Post #7
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-10-06T16:17:21+00:00
- Post Title: RAGE .RESOURCES files

Gameresource is 1208179177 bytes (1.12GB)
## Post #8
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-10-06T17:04:12+00:00
- Post Title: RAGE .RESOURCES files

wip+untested. still parsing the filename directory (script should break at "sample" block header)

see next post
## Post #9
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-10-06T17:59:52+00:00
- Post Title: RAGE .RESOURCES files

It already broke at "get idstring" invalid argument just for your info.
## Post #10
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-10-06T18:51:30+00:00
- Post Title: RAGE .RESOURCES files

> Reply from WRS
>
> wip+untested. still parsing the filename directory (script should break at "sample" block header)
Code: Select allendian big
get DUMMY long
get FOFFSET long

goto FOFFSET

get FILES long
get DUMMY long

endian little

for i = 0 < FILES

  get STRLEN long
  getdstring BLOCKNAME STRLEN

# one of many (most are 40 bytes)
# "image" "renderParm" "table" "renderProg"
# "cm" "achievement" "damage" "entityDef" 
# "material" "anim" "baseModel" "md6Def"
# "flare" "atlas" "env" "particle"
# "ribbon" "fx" "sample" "voicetrack"

  get STRLEN long
  getdstring VALUE1 STRLEN  # filenames, data or options

  get STRLEN long
  getdstring VALUE2 STRLEN  # sometimes blank

  endian big

  get OFFSET long # starts from 16, some options take no filespace
  getdstring OTHER 36 # other

  endian little

  print "%BLOCKNAME% %OFFSET% %VALUE1%"

next i

edit fixed dstring error
Works right up to the first sample file as said! great job so far, looking forward to progress!
## Post #11
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-10-06T19:10:30+00:00
- Post Title: RAGE .RESOURCES files

The contents of this post was deleted because of possible forum rules violation.
## Post #12
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-10-06T20:12:39+00:00
- Post Title: RAGE .RESOURCES files

Tried to run on the original file but getting "the requested amount of bytes to allocate is negative" 1520366851

nvm forgot to comment the bottom section.

It didn't output any files. Strange. it shows the dumping process but no files were shown on my hard drive

Oh right needed to set my permissions.
## Post #13
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2011-10-06T20:56:25+00:00
- Post Title: RAGE .RESOURCES files

> Reply from OrangeC
>
> Tried to run on the original file but getting "the requested amount of bytes to allocate is negative" 1520366851
I get this error too.

What's wrong?

> endian big
>
> 
>
> #########################################
>
> ## uncomment to run on the entire file ##
>
> #########################################
>
> 
>
> get DUMMY long
>
> get FOFFSET long
>
> goto FOFFSET
>
> 
>
> ######################################
>
> 
>
> ######################################
>
> ## uncomment to run on the end cut ##
>
> ######################################
>
> 
>
> goto 7724419
>
> 
>
> ######################################
>
> 
>
> get FILES long # 74696, so this may take a while 
>
> 
>
> endian little
>
> 
>
> get DUMMY long # POSSIBLY THE FIRST BLOCKNAME??
>
> 
>
> 
>
> for i = 0 < FILES # 75000 #FILES
>
> 
>
>   get STRLEN long
>
> 
>
>   if STRLEN > 0
>
> 
>
>   getdstring BLOCKNAME STRLEN # data type names ("image", "material", ect)
>
> 
>
> 
>
>   get STRLEN long
>
>   getdstring VALUE1 STRLEN  # original names, or data
>
> 
>
> 
>
>   get STRLEN long
>
>   getdstring VALUE2 STRLEN  # filenames
>
> 
>
> 
>
>   endian big
>
> 
>
>   get OFFSET long # starts from 16, some options take no filespace
>
>   get DUMMY long
>
>   get FSIZE long
>
>   get LANGS long # not always languages
>
> 
>
>    #just skip it (24-bytes)
>
>   math LANGS *= 24
>
>   getdstring DUMMY LANGS
>
> 
>
>   endian little
>
> 
>
>   getdstring DUMMY 24
>
> 
>
> 
>
>   if FSIZE > 0
>
> 
>
>     if VALUE2 == ""
>
> 	  log "" OFFSET FSIZE
>
>     else
>
>       log VALUE2 OFFSET FSIZE
>
> 	endif
>
> 
>
>   endif
>
> 
>
>    ! debug only !
>
>   print "%OFFSET%\t%BLOCKNAME%\n  %VALUE1%\n  %VALUE2%"
>
> 
>
>   endif
>
> 
>
>   savepos POS
>
>   get SIZE asize
>
> 
>
>   if POS == SIZE
>
>     print "done -badly"
>
> 	cleanexit
>
>   endif
>
> 
>
> 
>
> next i
>
> 
>
> 
>
> 
>
> if POS != SIZE
>
>   print "!! other footer data here !!"
>
> endif
>
> 
>
> print "done"
## Post #14
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-10-06T21:03:36+00:00
- Post Title: RAGE .RESOURCES files

The contents of this post was deleted because of possible forum rules violation.
## Post #15
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2011-10-06T21:34:45+00:00
- Post Title: RAGE .RESOURCES files

Okey solved
Here is the modification:

> endian big
>
> 
>
> #########################################
>
> ## uncomment to run on the entire file ##
>
> #########################################
>
> 
>
> get DUMMY long
>
> get FOFFSET long
>
> goto FOFFSET
>
> 
>
> ######################################
>
> 
>
> ######################################
>
> ## uncomment to run on the end cut ##
>
> ######################################
>
> 
>
> #goto 7724419
>
> 
>
> ######################################
>
> 
>
> get FILES long # 74696, so this may take a while 
>
> 
>
> endian little
>
> 
>
> get DUMMY long # POSSIBLY THE FIRST BLOCKNAME??
>
> 
>
> 
>
> for i = 0 < FILES # 75000 #FILES
>
> 
>
>   get STRLEN long
>
> 
>
>   if STRLEN > 0
>
> 
>
>   getdstring BLOCKNAME STRLEN # data type names ("image", "material", ect)
>
> 
>
> 
>
>   get STRLEN long
>
>   getdstring VALUE1 STRLEN  # original names, or data
>
> 
>
> 
>
>   get STRLEN long
>
>   getdstring VALUE2 STRLEN  # filenames
>
> 
>
> 
>
>   endian big
>
> 
>
>   get OFFSET long # starts from 16, some options take no filespace
>
>   get DUMMY long
>
>   get FSIZE long
>
>   get LANGS long # not always languages
>
> 
>
>   # just skip it (24-bytes)
>
>   math LANGS *= 24
>
>   getdstring DUMMY LANGS
>
> 
>
>   endian little
>
> 
>
>   getdstring DUMMY 24
>
> 
>
> 
>
>   if FSIZE > 0
>
> 
>
>     if VALUE2 == ""
>
> 	  log "" OFFSET FSIZE
>
>     else
>
>       log VALUE2 OFFSET FSIZE
>
> 	endif
>
> 
>
>   endif
>
> 
>
>   # ! debug only !
>
>   #print "%OFFSET%\t%BLOCKNAME%\n  %VALUE1%\n  %VALUE2%"
>
> 
>
>   endif
>
> 
>
>   savepos POS
>
>   get SIZE asize
>
> 
>
>   if POS == SIZE
>
>     print "done -badly"
>
> 	cleanexit
>
>   endif
>
> 
>
> 
>
> next i
>
> 
>
> 
>
> 
>
> if POS != SIZE
>
>   print "!! other footer data here !!"
>
> endif
>
> 
>
> print "done"
## Post #16
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2011-10-06T21:38:12+00:00
- Post Title: Re: RAGE .RESOURCES files

> 473354e2 7582       generated/buildgame/game/wasteland2/sewer_level_09.mapreso
>
> urces
>
> 
>
> Error: incomplete input file number 0, can't read 4 bytes.
>
>        anyway don't worry, it's possible that the BMS script has been written
>
>        to exit in this way if it's reached the end of the archive so check it
>
>        or contact its author or verify that all the files have been extracted
## Post #17
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-10-06T22:09:50+00:00
- Post Title: Re: RAGE .RESOURCES files

That's Apparently suppose to happen according to WRS.
## Post #18
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-10-06T23:43:30+00:00
- Post Title: Re: RAGE .RESOURCES files

sorry about the script confusion - i should have enabled the script to work on the full .resource file   

i took a quick look at streaming.resource but have no idea of the audio (?) formats otherwise they could be ripped like that if there really are no offsets near the footer
## Post #19
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-10-07T00:06:06+00:00
- Post Title: Re: RAGE .RESOURCES files

Ahh so the current script didn't dump all files afterall?

What interests me is that the audio data is in another file and the actual names and pathways are in the main resource file.

Yes i got same error as well.
## Post #20
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-10-07T00:10:52+00:00
- Post Title: Re: RAGE .RESOURCES files

some of the file entries have extra data for different languages which could explain the audio thing:

> english, french, italian, german, spanish, russian, japanese
## Post #21
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-10-07T00:32:36+00:00
- Post Title: Re: RAGE .RESOURCES files

pretty sure he means how all the audio files are *edit*under*edit* 1kb, its a redirect to the streamed.resources or something
## Post #22
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-10-07T01:14:37+00:00
- Post Title: Re: RAGE .RESOURCES files

fixed the script error   

```
# QuickBMS script by WRS

endian big

get DUMMY long
get FOFFSET long
goto FOFFSET
get FILES long

for i = 0 < FILES

  endian little

  # file number (equal to i) - big endian
  get FILENUM long

  # data type names ("image", "material", ect)
  get STRLEN long
  getdstring BLOCKNAME STRLEN

  # source data or file
  get STRLEN long
  getdstring VALUE1 STRLEN

  # filename (could be blank)
  get STRLEN long
  getdstring VALUE2 STRLEN

  endian big

  # file entry data
  get OFFSET long # relative, from 16
  get DUMMY long
  get FSIZE long
  get EXTRA long
  math EXTRA *= 24 # sometimes language names
  getdstring DUMMY EXTRA

  getdstring DUMMY 20

  if FSIZE == 0
    print "'%BLOCKNAME%' type has no data (%VALUE1%)"
  else
    log VALUE2 OFFSET FSIZE
  endif

  # debug/filelist
  #print "%OFFSET%\t%BLOCKNAME%\n  %VALUE1%\n  %VALUE2%"

next i

get SIZE asize
savepos POS

if POS != SIZE
  print "!! other footer data here !!"
endif

print "Completed!!"

```
## Post #23
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-10-07T01:36:45+00:00
- Post Title: Re: RAGE .RESOURCES files

Thanks it worked!

Now just how to link these sound files from the compress folder to the audio in the streaming bank.
## Post #24
- Username: Zelex
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 07, 2011 9:16 am
- Post datetime: 2011-10-07T01:42:31+00:00
- Post Title: Re: RAGE .RESOURCES files

Still not extracting everything? generated dir is only 400mb or so.
## Post #25
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-10-07T01:48:59+00:00
- Post Title: Re: RAGE .RESOURCES files

It did extract everything in the bigfile, since now the folder reads 1gig in total.
## Post #26
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2011-10-07T04:37:35+00:00
- Post Title: Re: RAGE .RESOURCES files

The contents of this post was deleted because of possible forum rules violation.
## Post #27
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2011-10-07T06:50:06+00:00
- Post Title: Re: RAGE .RESOURCES files

> For textures Is it possible they use the same structure?
For me textures looks crypted (maybe im wrong)
And the audio looks xwb-raw
## Post #28
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-10-07T16:18:58+00:00
- Post Title: Re: RAGE .RESOURCES files

Audio is adpcm but i don;t think its xwb since theres no header indication that it is. unless the beginning part is a filetable of some sorts and its just missing the Beginning DWORD.

I looked at the strings in the game resource archive and it has the .idmsa extension which stands for ID Microsoft ADPCM. But i don't understand how the strings link to the files inside the streamed resources since i looked at the individual strings in hex and it showed really nothing useful.
## Post #29
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-10-07T18:55:24+00:00
- Post Title: Re: RAGE .RESOURCES files

Is there any chance to do a repacker please ?
## Post #30
- Username: Zelex
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 07, 2011 9:16 am
- Post datetime: 2011-10-07T19:50:28+00:00
- Post Title: Re: RAGE .RESOURCES files

> Reply from Savage
>
> 
For textures Is it possible they use the same structure?

For me textures looks crypted (maybe im wrong)
And the audio looks xwb-raw

The textures are HD-Photo compressed. Page lines probably contains an offset (8 bytes) and size (2-4 bytes?) for each page, however those files themselves look compressed as they are too small to hold all the data they actually need to hold. The wasteland likely contains a 128k by 128k texture, and with 128x128 pages that breaks down to 1m pages. 

Also, it looks like the decl files are compressed as well - likely huffman coded with a static dictionary.
## Post #31
- Username: LordRius
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Apr 01, 2011 5:48 pm
- Post datetime: 2011-10-08T10:55:41+00:00
- Post Title: Re: RAGE .RESOURCES files

Using the reimport command in QuickBMS you can repack files, but, you can't exceed the size of the original files or QuickBMS don't repack them. ¿There is any way to skip this and overwrite the files anyway?
## Post #32
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-10-09T13:25:54+00:00
- Post Title: Re: RAGE .RESOURCES files

anyone figured out how to open/decode streamed.resources yet?
## Post #33
- Username: Qartar
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Oct 10, 2011 12:12 pm
- Post datetime: 2011-10-10T04:25:11+00:00
- Post Title: Re: RAGE .RESOURCES files

I modified WRS's script to decompress any files that need it. I haven't started working on the model format in earnest but the output looks intelligible (as opposed to what was obviously compressed-gibberish). The long value preceding what WRS was using as the file size was the uncompressed file size, when this is different from the archived size the script decompresses it using deflate, otherwise extracting it as before. The total uncompressed size is approximately 1.84 GB.

```
# QuickBMS script by WRS, modified by Qartar

endian big

comtype deflate_noerror

get DUMMY long
get FOFFSET long
goto FOFFSET
get FILES long

for i = 0 < FILES

  endian little

  # file number (equal to i) - big endian
  get FILENUM long

  # data type names ("image", "material", ect)
  get STRLEN long
  getdstring BLOCKNAME STRLEN

  # source data or file
  get STRLEN long
  getdstring VALUE1 STRLEN

  # filename (could be blank)
  get STRLEN long
  getdstring VALUE2 STRLEN

  endian big

  # file entry data
  get OFFSET long	# relative, from 16
  get FSIZE long	# uncompressed size of file
  get CSIZE long	# size of file in archive (compressed size)
  get EXTRA long
  math EXTRA *= 24 # sometimes language names
  getdstring DUMMY EXTRA

  getdstring DUMMY 20

  if CSIZE == 0
    print "'%BLOCKNAME%' type has no data (%VALUE1%)"
  elif CSIZE != FSIZE
	clog VALUE2 OFFSET CSIZE FSIZE
  else
    log VALUE2 OFFSET CSIZE
  endif

  # debug/filelist
  #print "%OFFSET%\t%BLOCKNAME%\n  %VALUE1%\n  %VALUE2%"

next i

get SIZE asize
savepos POS

if POS != SIZE
  print "!! other footer data here !!"
endif

print "Completed!!"
```
## Post #34
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2011-10-10T17:10:57+00:00
- Post Title: Re: RAGE .RESOURCES files

Thanks, but I get the exact same error when I try to unpack streamed.resources.
## Post #35
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-10-10T20:23:06+00:00
- Post Title: Re: RAGE .RESOURCES files

As far as i can see the streaming resource bank doesn't have any info on the bottom like game resources archive. The headers of the  ms adpcm files are in game resources and can be already extracted as .idmsa files. But the actual data is the problem to extract and how to link them up with the header files.
## Post #36
- Username: LordRius
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Apr 01, 2011 5:48 pm
- Post datetime: 2011-10-11T22:19:44+00:00
- Post Title: Re: RAGE .RESOURCES files

Any idea of how repack any file avoiding the filesize control?
## Post #37
- Username: JPulowski
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 29, 2010 5:39 am
- Post datetime: 2011-10-16T08:21:39+00:00
- Post Title: Re: RAGE .RESOURCES files

Currently is there anyway to extract textures, models and audio files? There are several .swf flash files, which can be decompiled. But also there are .bswf files, I could not find any way to convert them to .swf files.
## Post #38
- Username: LordRius
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Apr 01, 2011 5:48 pm
- Post datetime: 2011-10-16T10:31:31+00:00
- Post Title: Re: RAGE .RESOURCES files

Anyone have the Change File Size tool?

Or anyway to override .resources and use extracted folders and files instead.
## Post #39
- Username: JPulowski
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Aug 29, 2010 5:39 am
- Post datetime: 2011-10-23T15:20:18+00:00
- Post Title: Re: RAGE .RESOURCES files

Bump.
## Post #40
- Username: LordRius
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Apr 01, 2011 5:48 pm
- Post datetime: 2011-10-26T20:17:49+00:00
- Post Title: Re: RAGE .RESOURCES files

Hi guys, any other tool for unpack repack .resources files??
## Post #41
- Username: Fallingwater
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Dec 12, 2011 9:39 am
- Post datetime: 2011-12-12T02:01:12+00:00
- Post Title: Re: RAGE .RESOURCES files

Hi, I happened on this thread while trying to find a way to modify Rage's stupid 999 ammo limit for all ammo types. I have downloaded the latest script and used quickbms to extract gameresources.resources; I then deleted everything I didn't need (which means everything but the 33 files I needed in "generated -> decls -> ammo -> ammo"). I then edited the files (they're standard text format) changing the ammo limit from 999 to 999999, and removing three indent (tab) characters for every file so as to maintain the same size.

I then ran quickbms reimport according to instructions:
quickbms -w -r rage.bms gameresources.resources <folder where I saved the resources file>

It reimported the files, but while doing so it complained that many other files had no data. Random example:

- SCRIPT's MESSAGE:
 'model' type has no data (vehicle/class2/c2buggy.md5)

Here's a complete dump of quickbms' output (for some reason, "SCRIPT's MESSAGE" isn't pasted in the dump): [http://pastebin.com/hUEwW6zH](http://pastebin.com/hUEwW6zH)

Running the game with the resulting gameresources.resources file caused it to crash after a bit of loading.

I also tried unpacking the original resources file and putting all the folders it created into rage\base, then deleting gameresources.resources, hoping to force it to run on unpacked resources (as it ignores them otherwise), but the game crashed again (and rather faster too). Apparently Rage's files must be in gameresources.resources, or it doesn't work at all. 

So what I'm looking for is either a way to let Rage load from unpacked resources, or reimporting the proper files in gameresources.resources in such a way that it'll work.

Any ideas?
## Post #42
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2011-12-16T06:30:57+00:00
- Post Title: Re: RAGE .RESOURCES files

-snip-
## Post #43
- Username: Fallingwater
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Dec 12, 2011 9:39 am
- Post datetime: 2011-12-19T03:15:04+00:00
- Post Title: Re: RAGE .RESOURCES files

If they're in gameresources.resources or in gameresources_patch(whatever), then you can extract them from the big file. Not sure how to handle them after that, I'm not interested in graphic modding.
If they're in streaming.resources, I haven't find a way to extract it so far - and I'm not likely to even if one exists (doubtful) because I don't really care about the contents of that file as what I need is in the other one.
Sorry I can't be of more help.
## Post #44
- Username: Fallingwater
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Dec 12, 2011 9:39 am
- Post datetime: 2011-12-20T23:54:00+00:00
- Post Title: Re: RAGE .RESOURCES files

Nobody? Has interest in this game already dropped to zero? Just by editing the weapon/enemy config files you could do nice things... I can't be the only one interested in getting it to see modified values...
## Post #45
- Username: Fallingwater
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Dec 12, 2011 9:39 am
- Post datetime: 2012-01-12T13:33:30+00:00
- Post Title: Re: RAGE .RESOURCES files

Desperate bump
## Post #46
- Username: rmezatang
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 21, 2010 10:32 am
- Post datetime: 2012-02-20T17:22:09+00:00
- Post Title: Re: RAGE .RESOURCES files

ditto, would like to see models and textures extracted from this.  Rage would have been a great game if they had a more open approach to modding like Bethesda or Rockstar.
## Post #47
- Username: Venushja
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 19, 2010 11:13 pm
- Post datetime: 2012-08-10T12:13:12+00:00
- Post Title: Re: RAGE .RESOURCES files

I find Unpacker/Packer to ResourceFiles ... Your have anyone? Please?
## Post #48
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2012-12-15T22:24:04+00:00
- Post Title: Re: RAGE .RESOURCES files

nothing happen when i use bms script i missing somethinks this game must get tool ? no
## Post #49
- Username: rmezatang
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 21, 2010 10:32 am
- Post datetime: 2012-12-23T13:10:54+00:00
- Post Title: Re: RAGE .RESOURCES files

Updated quickbms should unpack the gameresources.resources file.


I hope we will see an updated BMS Script for the Scorchers DLC, the current BMS script errors out before completing the unpack...

previous gameresources 1.12 GB unpacked around 800 MB

scorchers gameresources 261 MB unpacked only 33 MB

can someone look into this please ?
## Post #50
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2013-11-26T06:36:00+00:00
- Post Title: Re: RAGE .RESOURCES files

> Reply from rmezatang
>
> Updated quickbms should unpack the gameresources.resources file.


I hope we will see an updated BMS Script for the Scorchers DLC, the current BMS script errors out before completing the unpack...

previous gameresources 1.12 GB unpacked around 800 MB

scorchers gameresources 261 MB unpacked only 33 MB

can someone look into this please ?

There was just a play for free weekend for RAGE. I know this post is a little old but rmezatang's request for a BMS script that works for the scorchers dlc is still unfulfilled. I would also be very thankful to anyone who could update it.
## Post #51
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-11-26T19:37:13+00:00
- Post Title: Re: RAGE .RESOURCES files

I know most (if not all) of the scorchers DLC content comes in raw format with the modding toolkit. the nailgun mesh and texture and sounds (lightwave for model, ms adpcm for sounds, dds/tga for textures), and other bits of it. Not sure if this is dependent on owning the dlc on steam, but it might be since I have both the main game and dlc.
## Post #52
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2013-11-27T04:58:45+00:00
- Post Title: Re: RAGE .RESOURCES files

Pepper - I have the tool kit and therefore have the textures. However, the number of models is limited. There are some usable lwo files, but the majority of the models are unusable. If there were an import script for the md6mesh format found in the tool kit as there is for the bmd6model format that the BMS script produces, then that would be perfect too.
## Post #53
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-11-28T21:09:02+00:00
- Post Title: Re: RAGE .RESOURCES files

> Reply from dragbody
>
> Pepper - I have the tool kit and therefore have the textures. However, the number of models is limited. There are some usable lwo files, but the majority of the models are unusable. If there were an import script for the md6mesh format found in the tool kit as there is for the bmd6model format that the BMS script produces, then that would be perfect too.
I'm looking through the files extracted from gameresources, all I'm seeing with md6mesh in the name are folders that hold animations, can you point me towards a .md6mesh file?

It seems a majority of the models are unusable because they aren't models, just LOD states and animations. that's what I'm seeing atleast.

Edit: or dummy files. LOTS of dummy 1kb files that are worthless with .bmodel extension. and the legitimate bmodels work fine with the blender scripts.

Edit: I think I misunderstood you, the md6 mesh aren't in the extracted ones but in the toolkit. sorry.
## Post #54
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2014-05-10T05:31:22+00:00
- Post Title: Re: RAGE .RESOURCES files

As I understand, no one dont create extractor for another .resource and .streamed archives?
## Post #55
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-10T07:34:30+00:00
- Post Title: Re: RAGE .RESOURCES files

> Reply from Researchman
>
> As I understand, no one dont create extractor for another .resource and .streamed archives?
[viewtopic.php?p=60457#p60457](http://forum.xentax.com/viewtopic.php?p=60457#p60457)
## Post #56
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2014-05-10T08:11:02+00:00
- Post Title: Re: RAGE .RESOURCES files

Work with gameresources.resources only.

Dont work with gameresources_sp_01.patch, streamed.resources, english.streamed, russian.streamed.
## Post #57
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2014-07-26T13:21:21+00:00
- Post Title: Re: RAGE .RESOURCES files

I try to unpack streamed.resources,get some error:(
## Post #58
- Username: phill05
- Rank: beginner
- Number of posts: 37
- Joined date: Sun May 29, 2011 3:29 am
- Post datetime: 2015-05-01T14:34:08+00:00
- Post Title: Re: RAGE .RESOURCES files

I used the script from WRS for unpacking the gameresources.resources file, but only thing I get is the folder called "generated" which contains some .bimage files inside. I researched the file in hex and found ingame texts which I want to edit

Can anyone help me?

Thanks
## Post #59
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-02T11:58:19+00:00
- Post Title: Re: RAGE .RESOURCES files

Seems strange to me that there's only .bimage files extracted but I don't know about DLC resource files.

For gameresources_sp_01.patch dialogues to be found here:
strings\*.lang

or maybe here: generated\swf\dialog.bswf
## Post #60
- Username: phill05
- Rank: beginner
- Number of posts: 37
- Joined date: Sun May 29, 2011 3:29 am
- Post datetime: 2015-05-04T12:45:50+00:00
- Post Title: Re: RAGE .RESOURCES files

Actually the .lang file contains just a some basic text information, but not all. The rest of it is kept in .resource archives, which I'm not able to fully extract by this script. Bellow is the file with all ingame texts

[http://www.mediafire.com/?lj0lf836xt577yc](http://www.mediafire.com/?lj0lf836xt577yc)
