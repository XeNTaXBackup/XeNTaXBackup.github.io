## Post #1
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2009-12-01T16:53:44+00:00
- Post Title: Star Wars The Force Unleashed pcd, pcp files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: joeyq
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 19, 2010 6:14 pm
- Post datetime: 2010-11-11T12:51:47+00:00
- Post Title: Star Wars The Force Unleashed pcd, pcp files

bump on extracting audio!
## Post #3
- Username: Tpiom
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Oct 08, 2011 7:37 pm
- Post datetime: 2011-10-08T11:42:07+00:00
- Post Title: Star Wars The Force Unleashed pcd, pcp files

Yes, checking out the .pcp files would be interesting... They are definitely audio and music.
I think the other files (.pcd) are scripts, they are only a few KBs each.

EDIT: Old thread... Have they figured these files already? 

Also, as the original file is down I give you two new ones:
[http://tpiom.webs.com/playertroopercomm ... .st.fr.pcp](http://tpiom.webs.com/playertroopercommander.actor.xml.st.fr.pcp)
[http://tpiom.webs.com/playerultimategoo ... .re.nv.pcd](http://tpiom.webs.com/playerultimategood.actor.xml.re.nv.pcd)
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-01-02T11:23:16+00:00
- Post Title: Star Wars The Force Unleashed pcd, pcp files

If anyone's interested, I just wrote two scripts that lets you access and play all sounds and music from those files.
First one is the plain extraction, pretty easy. Unquote the three indent lines to add the file name as a subfolder.

```
open FDDE pcp 1

get UNK long 0
get UNK long 0
get FILES long 0
get XML long 0
xmath NAMEOFF "(0x1c * FILES) + 0x10 + XML"
for i = 1 <= FILES
	get CRC long 0
	get OFFSET long 0
	get OFFSET2 long 0
	get SIZE long 0
	get FFFF long 0
	get UNK long 0
	get ZERO long 0
	savepos MYOFF 0
	goto NAMEOFF 0
	get NAMEL long 0
	getDstring NAME NAMEL 0
		#set NAME2 FOLDER
		#string NAME2 += NAME
		#set NAME NAME2
	savepos NAMEOFF 0
	log NAME OFFSET SIZE 1
	goto MYOFF 0
next i
```

Second one converts the resulting files without extension to correct MSADPCM or PCM wave files. I'm quite proud of that little script because the format is a real b****. The resulting files have a complete header so you can play them with the standard msadpcm codec, i.e. you can also import them to any audio editor. 

```
if CODE == 2
	callfunction msadpcm 1
elif CODE == 1
	callfunction pcm 1
else
	print "error: unknown codec"
endif
get SIZE asize MEMORY_FILE
get NAME basename
string NAME += ".wav"
log NAME 0 SIZE MEMORY_FILE

startfunction msadpcm
	set MEMORY_FILE binary "\x52\x49\x46\x46\x9C\xA8\x80\x00\x57\x41\x56\x45\x66\x6D\x74\x20\x32\x00\x00\xff"
	# note: byte at 0x13 has to be set to 0 later
	append
	log MEMORY_FILE 0 0x32
	append
	putVarChr MEMORY_FILE 0x46 0x61746164 long # "data"
	putVarChr MEMORY_FILE 0x4a 0xffffffff long # placeholder
	putVarChr MEMORY_FILE 0x13 0 byte
	set OFFSET 0x32
	get SIZE asize
	math SIZE -= OFFSET
	append
	log MEMORY_FILE OFFSET SIZE
	append
	putVarChr MEMORY_FILE 0x4a SIZE long # actual streamsize
	get RIFFSIZE asize MEMORY_FILE
	math RIFFSIZE -= 8
	putVarChr MEMORY_FILE 4 RIFFSIZE long
endfunction

startfunction pcm
	goto 2
	get CHANNELS short
	get FREQUENCY short
	set BITS 16
	set OFFSET 0x10
	get SIZE asize
	math SIZE -= OFFSET
	set MEMORY_FILE binary "\x52\x49\x46\x46\x00\x00\x00\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x64\x61\x74\x61\xff\xff\xff\xff"
	append
	log MEMORY_FILE OFFSET SIZE
	append

	set RIFFSIZE SIZE
	math RIFFSIZE += 36
	set BLOCKALIGN BITS
	set AVGBYTES FREQUENCY
	math BLOCKALIGN /= 8
	math BLOCKALIGN *= CHANNELS
	math AVGBYTES *= BLOCKALIGN

	putvarchr MEMORY_FILE 4 RIFFSIZE long
	putvarchr MEMORY_FILE 20 1 short          # wFormatTag: Microsoft PCM Format (0x0001)
	putvarchr MEMORY_FILE 22 CHANNELS short   # wChannels
	putvarchr MEMORY_FILE 24 FREQUENCY long   # dwSamplesPerSec
	putvarchr MEMORY_FILE 28 AVGBYTES long    # dwAvgBytesPerSec
	putvarchr MEMORY_FILE 32 BLOCKALIGN short # wBlockAlign
	putvarchr MEMORY_FILE 34 BITS short       # wBitsPerSample
	putvarchr MEMORY_FILE 40 SIZE long
endfunction
```


Tell me if it works!
## Post #5
- Username: WhiskeyBanger
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jul 23, 2015 1:09 pm
- Post datetime: 2015-07-23T16:37:43+00:00
- Post Title: Star Wars The Force Unleashed pcd, pcp files

Im interested in trying this out but im new to all this and need to know how to use it hahahaha
## Post #6
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2015-07-23T17:12:24+00:00
- Post Title: Star Wars The Force Unleashed pcd, pcp files

> Reply from WhiskeyBanger
>
> hahahaha
Laughing shows a lack of sincerity where I come from...
## Post #7
- Username: WhiskeyBanger
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jul 23, 2015 1:09 pm
- Post datetime: 2015-07-23T17:26:30+00:00
- Post Title: Star Wars The Force Unleashed pcd, pcp files

> Reply from AlphaTwentyThree
>
> WhiskeyBanger wrote:hahahaha
Laughing shows a lack of sincerity where I come from...

i didnt mean to show lack of interest so for that im sorry.. Im just very new to this and needed direction. I have Multiex Commander now and put your scripts into it but im guessing these are used for after i get the pak.lp files opened? Like i said, im new as of yesterday and watched some tutorials but am having trouble grasping it all. Have any pointers for me?
## Post #8
- Username: ARAJediMaster
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Jun 12, 2015 12:17 pm
- Post datetime: 2015-07-31T03:31:48+00:00
- Post Title: Star Wars The Force Unleashed pcd, pcp files

Excuse me, but which .pcd .pcp files are the sound files? There are so many in the Mac version of The Force Unleashed that I don’t know which one(s) it is.
## Post #9
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-08-04T17:52:05+00:00
- Post Title: Star Wars The Force Unleashed pcd, pcp files

AlphaTwentyThree

First of all thanks for your work. I've unpacked some files and found a little error in your script.

```
set NAMEOFF FILES
math NAMEOFF *= 0x1c
math NAMEOFF += 0x10

```


should be replaced to

```
set NAMEOFF FILES
math NAMEOFF *= 0x1c
math NAMEOFF += 0x10
math NAMEOFF += XML

```


Cause there are no any xml files on .pcp and it results incorrect names.
## Post #10
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2015-08-30T18:46:47+00:00
- Post Title: Star Wars The Force Unleashed pcd, pcp files

Thanks! Corrected.
## Post #11
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-10-08T18:56:08+00:00
- Post Title: Star Wars The Force Unleashed pcd, pcp files

Also i've found another mistake, some extra bytes (i think it's always 00 00 after "data" chunk) were in output .wav files. Here is script that extracts wav files without extra bytes and it extracts wav's directly, so no need to use second script

```
open FDDE pcp 1

get UNK long 0
get UNK long 0
get FILES long 0
get XML long 0
xmath NAMEOFF "(0x1c * FILES) + 0x10 + XML"
for i = 1 <= FILES
	get CRC long 0
	get OFFSET long 0
	get OFFSET2 long 0
	get SIZE long 0
	get FFFF long 0
	get UNK long 0
	get ZERO long 0
	savepos MYOFF 0
	goto NAMEOFF 0
	get NAMEL long 0
	getDstring NAME NAMEL 0
	string NAME += ".wav"
	savepos NAMEOFF 0
	xmath SIZE "SIZE - (OFFSET2 - OFFSET)"
	goto OFFSET 1
	get CODEC short 1
	if CODEC == 2
	   callfunction msadpcm 1
	elif CODEC == 1
	   callfunction pcm 1
	else
	   print "error: unknown codec"
	endif
	goto MYOFF 0
next i

startfunction msadpcm
	putVarChr MEMORY_FILE 78 0
	log MEMORY_FILE 0 0
	set MEMORY_FILE binary "\x52\x49\x46\x46\x00\x00\x00\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x32\x00\x00\x00\x02\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x64\x61\x74\x61\x00\x00\x00\x00"
   	append
   	log MEMORY_FILE OFFSET2 SIZE 1
	append
	get RIFFSIZE asize MEMORY_FILE
	math RIFFSIZE -= 8
	get CHANNELS short 1
	get FREQUENCY long 1
	get BPS long 1
	get ALIGN short 1
	get UNKNOWN1 long 1
	get UNKNOWN2 long 1
	get UNKNOWN3 long 1
	get UNKNOWN4 long 1
	get UNKNOWN5 long 1
	get UNKNOWN6 long 1
	get UNKNOWN7 long 1
	get UNKNOWN8 long 1
	get UNKNOWN9 long 1
	putVarChr MEMORY_FILE 4 RIFFSIZE long
	putVarChr MEMORY_FILE 22 CHANNELS short
	putVarChr MEMORY_FILE 24 FREQUENCY long
	putVarChr MEMORY_FILE 28 BPS long
	putVarChr MEMORY_FILE 32 ALIGN short
	putVarChr MEMORY_FILE 34 UNKNOWN1 long
	putVarChr MEMORY_FILE 38 UNKNOWN2 long
	putVarChr MEMORY_FILE 42 UNKNOWN3 long
	putVarChr MEMORY_FILE 46 UNKNOWN4 long
	putVarChr MEMORY_FILE 50 UNKNOWN5 long
	putVarChr MEMORY_FILE 54 UNKNOWN6 long
	putVarChr MEMORY_FILE 58 UNKNOWN7 long
	putVarChr MEMORY_FILE 62 UNKNOWN8 long
	putVarChr MEMORY_FILE 66 UNKNOWN9 long
	putVarChr MEMORY_FILE 74 SIZE long
	get FULLSIZE asize MEMORY_FILE
	log NAME 0 FULLSIZE MEMORY_FILE
endfunction

startfunction pcm
	putVarChr MEMORY_FILE 44 0
	log MEMORY_FILE 0 0
	set MEMORY_FILE binary "\x52\x49\x46\x46\x00\x00\x00\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x10\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x64\x61\x74\x61\x00\x00\x00\x00"
   	append
   	log MEMORY_FILE OFFSET2 SIZE 1
	append
	get RIFFSIZE asize MEMORY_FILE
	math RIFFSIZE -= 8
	get CHANNELS short 1
	get FREQUENCY long 1
	get BPS long 1
	get ALIGN short 1
	get BITS short 1
	putVarChr MEMORY_FILE 4 RIFFSIZE long
	putVarChr MEMORY_FILE 22 CHANNELS short
	putVarChr MEMORY_FILE 24 FREQUENCY long
	putVarChr MEMORY_FILE 28 BPS long
	putVarChr MEMORY_FILE 32 ALIGN short
	putVarChr MEMORY_FILE 34 BITS short
	putVarChr MEMORY_FILE 40 SIZE long
	get FULLSIZE asize MEMORY_FILE
	log NAME 0 FULLSIZE MEMORY_FILE
endfunction

```
## Post #12
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-10-09T04:16:02+00:00
- Post Title: Star Wars The Force Unleashed pcd, pcp files

> Reply from spider91
>
> Also i've found another mistake, some extra bytes (i think it's always 00 00 after "data" chunk) were in output .wav files. Here is script that extracts wav files without extra bytes and it extracts wav's directly, so no need to use second script
Code: Select allopen FDDE pcd 0
open FDDE pcp 1

get UNK long 0
get UNK long 0
get FILES long 0
get XML long 0
xmath NAMEOFF "(0x1c * FILES) + 0x10 + XML"
for i = 1 <= FILES
	get CRC long 0
	get OFFSET long 0
	get OFFSET2 long 0
	get SIZE long 0
	get FFFF long 0
	get UNK long 0
	get ZERO long 0
	savepos MYOFF 0
	goto NAMEOFF 0
	get NAMEL long 0
	getDstring NAME NAMEL 0
	string NAME += ".wav"
	savepos NAMEOFF 0
	xmath SIZE "SIZE - (OFFSET2 - OFFSET)"
	goto OFFSET 1
	get CODEC short 1
	if CODEC == 2
	   callfunction msadpcm 1
	elif CODEC == 1
	   callfunction pcm 1
	else
	   print "error: unknown codec"
	endif
	goto MYOFF 0
next i

startfunction msadpcm
	putVarChr MEMORY_FILE 78 0
	log MEMORY_FILE 0 0
	set MEMORY_FILE binary "\x52\x49\x46\x46\x00\x00\x00\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x32\x00\x00\x00\x02\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x64\x61\x74\x61\x00\x00\x00\x00"
   	append
   	log MEMORY_FILE OFFSET2 SIZE 1
	append
	get RIFFSIZE asize MEMORY_FILE
	math RIFFSIZE -= 8
	get CHANNELS short 1
	get FREQUENCY long 1
	get BPS long 1
	get ALIGN short 1
	get UNKNOWN1 long 1
	get UNKNOWN2 long 1
	get UNKNOWN3 long 1
	get UNKNOWN4 long 1
	get UNKNOWN5 long 1
	get UNKNOWN6 long 1
	get UNKNOWN7 long 1
	get UNKNOWN8 long 1
	get UNKNOWN9 long 1
	putVarChr MEMORY_FILE 4 RIFFSIZE long
	putVarChr MEMORY_FILE 22 CHANNELS short
	putVarChr MEMORY_FILE 24 FREQUENCY long
	putVarChr MEMORY_FILE 28 BPS long
	putVarChr MEMORY_FILE 32 ALIGN short
	putVarChr MEMORY_FILE 34 UNKNOWN1 long
	putVarChr MEMORY_FILE 38 UNKNOWN2 long
	putVarChr MEMORY_FILE 42 UNKNOWN3 long
	putVarChr MEMORY_FILE 46 UNKNOWN4 long
	putVarChr MEMORY_FILE 50 UNKNOWN5 long
	putVarChr MEMORY_FILE 54 UNKNOWN6 long
	putVarChr MEMORY_FILE 58 UNKNOWN7 long
	putVarChr MEMORY_FILE 62 UNKNOWN8 long
	putVarChr MEMORY_FILE 66 UNKNOWN9 long
	putVarChr MEMORY_FILE 74 SIZE long
	get FULLSIZE asize MEMORY_FILE
	log NAME 0 FULLSIZE MEMORY_FILE
endfunction

startfunction pcm
	putVarChr MEMORY_FILE 44 0
	log MEMORY_FILE 0 0
	set MEMORY_FILE binary "\x52\x49\x46\x46\x00\x00\x00\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x10\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x64\x61\x74\x61\x00\x00\x00\x00"
   	append
   	log MEMORY_FILE OFFSET2 SIZE 1
	append
	get RIFFSIZE asize MEMORY_FILE
	math RIFFSIZE -= 8
	get CHANNELS short 1
	get FREQUENCY long 1
	get BPS long 1
	get ALIGN short 1
	get BITS short 1
	putVarChr MEMORY_FILE 4 RIFFSIZE long
	putVarChr MEMORY_FILE 22 CHANNELS short
	putVarChr MEMORY_FILE 24 FREQUENCY long
	putVarChr MEMORY_FILE 28 BPS long
	putVarChr MEMORY_FILE 32 ALIGN short
	putVarChr MEMORY_FILE 34 BITS short
	putVarChr MEMORY_FILE 40 SIZE long
	get FULLSIZE asize MEMORY_FILE
	log NAME 0 FULLSIZE MEMORY_FILE
endfunction

I have to ask cause i'm not sure but what program do i use this script with?
## Post #13
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-10-09T07:39:51+00:00
- Post Title: Star Wars The Force Unleashed pcd, pcp files

[http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)
## Post #14
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-10-09T14:02:16+00:00
- Post Title: Star Wars The Force Unleashed pcd, pcp files

> Reply from spider91
>
> http://aluigi.altervista.org/quickbms.htm

Ah okay thanks, um for these scripts when one do i use first and then again to convert it to .WAV?
## Post #15
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-10-09T15:13:30+00:00
- Post Title: Star Wars The Force Unleashed pcd, pcp files

No need to use it two times, if you use my script, you should use it only once and it will output wav's.
## Post #16
- Username: iDu
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Feb 15, 2021 1:53 am
- Post datetime: 2021-02-14T17:59:43+00:00
- Post Title: Re: Star Wars The Force Unleashed pcd, pcp files

Just created an account to post this...

Mine's not working:



1wea.PNG (60.55 KiB) Viewed 34 times



Also, what about the LP files? And how do you convert the ogg files to something playable that come with force unleashed 2? I'm guessing the music and sound files are in one of the ogg files there but I can't play them....

Sample media info:
General
Complete name                            : G:\LucasArts\Star Wars The Force Unleashed 2\Game\Disc\Audio\External\English(US)\10\100416634.ogg
Format                                   : Wave
File size                                : 3.89 KiB
Duration                                 : 1 s 173 ms
Overall bit rate                         : 27.2 kb/s
FileExtension_Invalid                    : act at9 wav

Audio
Format                                   : In Development
Codec ID                                 : FFFF
Duration                                 : 1 s 173 ms
Bit rate                                 : 26.4 kb/s
Channel(s)                               : 1 channel
Sampling rate                            : 11.025 kHz
Stream size                              : 3.78 KiB (97%)
