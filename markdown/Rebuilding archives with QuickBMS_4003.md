## Post #1
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-30T16:30:25+00:00
- Post Title: Rebuilding archives with QuickBMS

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-12-30T16:56:30+00:00
- Post Title: Rebuilding archives with QuickBMS

adding more rebuilding  functions to QuickBMS make it an acme tool ...
## Post #3
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-12-30T21:43:22+00:00
- Post Title: Rebuilding archives with QuickBMS

Yeah, I made a script to rebuild headers on pac files that the files are all the same size.  Came in handy for what I used it for.
## Post #4
- Username: ahon
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Dec 17, 2009 12:35 pm
- Post datetime: 2010-01-03T17:38:49+00:00
- Post Title: Rebuilding archives with QuickBMS

is there a script to rebuild Svr 2010 pac files with quickbms?
## Post #5
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2010-01-16T22:43:42+00:00
- Post Title: Rebuilding archives with QuickBMS

I would love to have a script that rebuilds zip files with different compression methods and zip signatures.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-16T23:01:26+00:00
- Post Title: Rebuilding archives with QuickBMS

I already tried to write that script just for my tests and was ok except for 2 things:

quickbms doesn't have a crc function and the zip archives need the crc of each archived file otherwise the extraction program doesn't extract them (yes I have already tried using the magic crc 0xdebb20e3)
you can only store the files because quickbms doesn't support recompression (it's an extractor)
except for the first point the zip file rebuilt with my script is perfect
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-07-28T16:58:16+00:00
- Post Title: Rebuilding archives with QuickBMS

first an update for my previous post: both the "exception" have been solved some versions ago, indeed quickbms supports a complete crc engine (plus tons of hashing algorithms) and supports also some recompression algorithms (zlib, xmem, lzo and so on).

instead now I want to talk about a feature I have implemented in version 0.4.6 for providing a solution for the current requests about endianess conversions.
I have implemented the -E option that costed me only 3 lines of code and automatically convert the endianess of any number read from a file.

imagine to have a file with the following format:

```
32bit size
16bit crc
```

the script for reading it would be:

```
get size long
get crc short
```

if you add the -E and -w options at the command-line of quickbms the SAME reading/extracting script will automatically change the endianess of those 3 values :)

it's also possible to avoid to add the -w option by loading the file into a memory file, like the following example:

```
log MEMORY_FILE 0 file_size
get signature long MEMORY_FILE
get size long MEMORY_FILE
get crc short MEMORY_FILE
log dump.dat 0 file_size MEMORY_FILE
```
cool :)
## Post #8
- Username: Jurko
- Rank: veteran
- Number of posts: 86
- Joined date: Fri Jan 22, 2010 9:35 pm
- Post datetime: 2011-03-04T08:53:51+00:00
- Post Title: Rebuilding archives with QuickBMS

Sorry for my bad English.
Can you create repacking script for Bad Company 2. For no gzip files. Please
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-06T10:17:02+00:00
- Post Title: Rebuilding archives with QuickBMS

I have just released version 0.4.9 of QuickBMS which contains a feature that will make happy a lot of people :)

from now it's possible to use QuickBMS also for reimporting files back in the archives without modifying the original script, so just an automatic inverted operation.

obviously there are some limitations, the first of which is the size of the imported files that must be equal or minor than the original one (that's why it's a reimported and not a real rebuilder).

the following is the detail I have added in the documentation of quickbms.txt:

```
less complex archives without touching a single line of the script,
yeah just reusing the same bms scripts that already exist!

The function is experimental and it must be used in the following way:

- make a backup copy of the original archive!

- extract the files you want to modify (-f option) or just all the
  files as you do normally via the GUI or by command-line:

    quickbms script.bms archive.pak output_folder

- do your modifications to the extracted files and delete the files
  that have not been modified so that the reimporting process will be
  faster

- reimport the files in the archive:

    quickbms -w -r script.bms archive.pak output_folder

- test the game with the modified archive

Obviously you can use the GUI also for the reimporting procedure
because it's enough to create a file.bat containing the following line
and then double clicking it when you need to do this job:
quickbms.exe -w -r
```
anyway keep in mind that this is not guarantee with all the file formats and you can find an exaustive list of "exceptions" in the relative section quickbms.txt

@jurko
maybe you can try with this new feature but the result could not work, in any case I can't help.
but probably exist tools that already do the rebuilding job for that specific format
## Post #10
- Username: cozy
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Dec 08, 2009 5:18 am
- Post datetime: 2011-03-09T20:25:33+00:00
- Post Title: Rebuilding archives with QuickBMS

Thanx for the new features in a great tool,but when i come to rebuild the files back in a .cpk file the files are the same ones,i tested by filling the files with 1 byte,and the result is the same - 1650 files reimported in 5 seconds
Im` using the bms script for cpk files in a line command:-

quickbms cpk.bms *.cpk extracted

and to reimport:-

quickbms -w -r cpk.bms *.cpk extracted

thanx cozy
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-09T21:37:05+00:00
- Post Title: Rebuilding archives with QuickBMS

oh finally a feedback about the new feature :)

can you check if you have the current version of quickbms?
it's 0.4.10, I have fixed various things lately after having implemented this feature

then the tool has reported that over 1600 files have been reimported so it seems correct, indeed the reimported files are counted only when each operation succeded at 100%.

are you sure the directory you selected contains the modified files?
if you have not modified all the 1600 files would be better to delete those that have not been modified.

as final test make a binary comparison between the original archive and the modified one.

I have verified the cpk.bms script and it uses a compression algorithm not supported in recompression mode so you can reimport in the archive ONLY the files that weren't compressed.
as far as I know doesn't exist code of the recompressor available publicly
## Post #12
- Username: cozy
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Dec 08, 2009 5:18 am
- Post datetime: 2011-03-10T17:05:00+00:00
- Post Title: Rebuilding archives with QuickBMS

> Reply from aluigi
>
> oh finally a feedback about the new feature 
I have verified the cpk.bms script and it uses a compression algorithm not supported in recompression mode so you can reimport in the archive ONLY the files that weren't compressed.
as far as I know doesn't exist code of the recompressor available publicly

I`ve got the new  0.4.10,and yes the files are compressed as i`ve looked at them using the CriPackedFileMaker.exe,so i guess thats why the files was not added,thanks for the reply,and keep up the good work!!!
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-10T19:47:39+00:00
- Post Title: Rebuilding archives with QuickBMS

quickbms reports an error if the recompression algorithm is not available, so if you didn't see the error then it's something else
## Post #14
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2011-03-23T06:30:04+00:00
- Post Title: Rebuilding archives with QuickBMS

thanks Luigi 
your tool is like a magic wand
## Post #15
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-30T09:55:58+00:00
- Post Title: Rebuilding archives with QuickBMS

I'm almost ready to release a new version of quickbms so if you have crazy ideas or suggestions, that's the moment to tell me :)
## Post #16
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-12-12T06:57:42+00:00
- Post Title: Re: Rebuilding archives with QuickBMS

Aluigi,

I was wonder, is it really complicated to also make quickbms do the pack part? Since you are able to unpack most of the archives, than it would make sence to me also make a possible to pack the archive back. I know we have re-import function and so on, but it is not same becasue you are limited filesize of replacing file. It is just an idea. But let me tell you 1 thing, if you would accomplish this and it would be working, than quickbms would become the best, most handy tool ever and ppl would not need anything else. 

This is just my input 

Regards
