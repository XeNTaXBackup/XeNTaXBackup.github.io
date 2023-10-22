## Post #1
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2015-01-04T07:37:27+00:00
- Post Title: Need help with extract .pak achives from Battle vs. Chess

hi everybody,
i want mods game .
Do you have any idea how we could unpack/repack .pak Archive from " Battle vs. Chess "
and can't be extract by 7zip, winzip....
.pak file are protected.

A little bit more info (and guesswork) about the format:

Code:

> char magic[4];
>
> int versionNum;
>
> int unknown2;
>
> unsigned int numFiles;
>
> int unknown3;
>
> unsigned int realSizeOfFilelist;
>
> unsigned int compressedSizeOfFilelist;

After that is the compressed list of files (which would include filenames and offsets I assume). And after that are the actual files, where many (if not all) are uncompressed.

I have no which type of compression is used for that file list. I tried aluigi's quickbms script which tries every bms compression on a file list, and I only got gibberish.

The game is released with the name Check vs Mate in USA by the way. 

Help me?
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-01-04T23:26:45+00:00
- Post Title: Need help with extract .pak achives from Battle vs. Chess

edit
see below

also - the demo uses lua and the config.pak macros can make calls to it
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-01-04T23:39:12+00:00
- Post Title: Need help with extract .pak achives from Battle vs. Chess

[http://aluigi.altervista.org/papers/bms/clutch.bms](http://aluigi.altervista.org/papers/bms/clutch.bms)
## Post #4
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2015-01-07T03:02:20+00:00
- Post Title: Need help with extract .pak achives from Battle vs. Chess

thank you very much. Now, i needing a tool extract  .pak file in game Battle vs. Chess. Help me?
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-01-07T09:15:07+00:00
- Post Title: Need help with extract .pak achives from Battle vs. Chess

> Reply from namquang93
>
> thank you very much. Now, i needing a tool extract  .pak file in game Battle vs. Chess. Help me?
[http://quickbms.aluigi.org](http://quickbms.aluigi.org)
## Post #6
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2015-01-07T17:26:51+00:00
- Post Title: Need help with extract .pak achives from Battle vs. Chess

Try it on but i can't.  i had upload a .pak file. anyone extract out to it. After, tutorial for me. Thank you very much. 

[http://www.mediafire.com/download/9gd3d ... torial.pak](http://www.mediafire.com/download/9gd3dff391cyd4q/tutorial.pak)
## Post #7
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-01-08T22:08:41+00:00
- Post Title: Need help with extract .pak achives from Battle vs. Chess

the script needs updating for v6.

the first 4 bytes of the name table are xored with the file count before being decompressed :

```
	log MEMORY_FILE 0 0
	putvarchr MEMORY_FILE 0 0x78
	putvarchr MEMORY_FILE 1 0x9c
	append
	log MEMORY_FILE OFFSET NAMETABLESZZ
	append
	
	# (wrs): but there is a pretty lame xor on the first data:
	getvarchr FILE_SIZE_XOR MEMORY_FILE 2 long
    math FILE_SIZE_XOR ^= FILES
    putvarchr MEMORY_FILE 2 FILE_SIZE_XOR
    
    math NAMETABLE_REALSIZE = NAMETABLESZZ
    math NAMETABLE_REALSIZE += 2
    
    clog MEMORY_FILE2 0 NAMETABLE_REALSIZE NAMETABLESZ MEMORY_FILE

```


and other things (wip)
## Post #8
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2015-01-12T01:49:36+00:00
- Post Title: Need help with extract .pak achives from Battle vs. Chess

> Reply from WRS
>
> the script needs updating for v6.

the first 4 bytes of the name table are xored with the file count before being decompressed :
Code: Select all	# (wrs): this version doesn't override the first 2 bytes
	log MEMORY_FILE 0 0
	putvarchr MEMORY_FILE 0 0x78
	putvarchr MEMORY_FILE 1 0x9c
	append
	log MEMORY_FILE OFFSET NAMETABLESZZ
	append
	
	# (wrs): but there is a pretty lame xor on the first data:
	getvarchr FILE_SIZE_XOR MEMORY_FILE 2 long
    math FILE_SIZE_XOR ^= FILES
    putvarchr MEMORY_FILE 2 FILE_SIZE_XOR
    
    math NAMETABLE_REALSIZE = NAMETABLESZZ
    math NAMETABLE_REALSIZE += 2
    
    clog MEMORY_FILE2 0 NAMETABLE_REALSIZE NAMETABLESZ MEMORY_FILE


and other things (wip)
i don't understand. can you support to me? you can step by step. Thank you very much
