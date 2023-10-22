## Post #1
- Username: stetel
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jul 27, 2004 2:16 am
- Post datetime: 2004-07-26T18:22:10+00:00
- Post Title: How the hell   D:

Hi,

first of all, my appreciation for this great program (multiex commander).
Now to my main question: How does this reverse engineering work? I mean,
if theres a new game and some new fileformat and u want to extract it, then is it like: "*opens file wiv hexeditor* ,*looks at the first bytes* "oh yeah they remind me of (e.g.) the duke nukem 3d filesystem!!!" *changes some bytes* "TADA! now u can open and extract it =D""

i dont think it can be like this. i mean nobody can remember like 500 game titles and all the file format bytes and stuff (or can somebody @.@).

or how does this work? id really like to know...whats going on... 

thx in advance and keep going!
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-07-27T12:04:31+00:00
- Post Title: How the hell   D:

Hi there,

I have done some hacking of file formats in the past. If the game is an older game, say 6 months old or more, I usually try to find some documentation on the internet about the format, or even some open-source code that is easy to read. Within this time, and if the game is popular, someone has usually figured it out for you, which makes the job much easier.

If I can't find anything, or the game is new, it means I have to discover it myself. I use a little program I wrote myself to hack apart the file formats, but it basically functions similarly to a hex editor. Firstly I take a look at the first 4-ish bytes of the archive - usually it contains a header string that helps to identify the archive. For example, the Quake PAK archives have the word PACK at the beginning of each archive - knowing this I try to match the header to any previous archive I have decoded.

Most archives are of 2 different formats - either directory-based or chunk-based. Chunk-based archives are easy because they usually have a repeated segment that goes right through the file, something like...

4 Bytes - File Type
4 Bytes - File Size
X Bytes - The File Data

However, these are not very common in modern games. Most modern games use the directory-based structure, which involves locating a directory somewhere in the archive, which lists all the files. Usually it is at the beginning of the archive, in which case it is easy to work out, alternatively it may be located at the very end. However, if the directory is somewhere else in the archive, one of the 4-byte or 2-byte fields at the start of the file will point to the directory location. Finally, some archives actually store the directory in a separate file with the same name - for example, archive.arc and archive.idx - where the idx file contains the directory, and the arc file is the file data.

Once you find the directory, you need to work out the structure. In most archives, the fields for each entry in the directory will be 4-byte (or sometimes 2-byte) numbers. At the start of the directory, the offset to the files will be small, so you will look for 4-byte numbers where the last few bytes are null or zero. You are mainly looking for patterns in the directory here, so move through the directory until you find another 4-bytes with a few null bytes at the end. If the second 4-byte number is bigger than the first, it usually indicates the offset to the file. 

At this stage, you should also know approximately the size of each entry in the directory. For example, if the first file offset stored at position 8 in the archive, and the next at position 24 in the archive, then each directory entry is 16 bytes in size, or 4x4-byte numbers. Knowing this, you can then try to discover the meaning of the other bytes in each file entry. Common fields will be the compressed size of the file, a decompressed size of the file, and a file ID number. The file size is easy to confirm - just subtract the 2 offsets you found in the step above, and if it matches a field in file entry, then you found the file size.

Make sure, however, to choose an archive which is likely to contain files you will recognise. For example, I usually try to choose an audio archive, or sound archive, because it is easy to confirm whether your field guesses are correct. Many games store their audio as WAV files, which all have the header RIFF. Knowing this, you can then go to the offset of the first file in the archive. If you can see an RIFF at the offset, you can be sure your offset field guess is correct. You could also try using Text archives, or image archives, but normally image archives are alittle difficult because most game companies use unusual and proprietry image formats.

Naturally, as with anything, it gets much easier with practice. Once you decode about 50 archives, you are well on your way there. All archives follow a similar structure, and contain similar fields, so once you recognise what you are looking for, you can instantly pick up a file and tell whether it is likely to be an archive or not.

The difficult parts come when you are faced with archives that contain compression or encryption. The best thing to do, if you expect compression, is to extract a file from the archive (once you know the offset and size of the file from the directory) and run it through some standard decompressors (such as ZLIB and GZIP) to see if they work. If not, then you are pretty much stuck.


If you are looking at attempting file format hacking, I would firstly congratulate you. I would recommend you get a good hex editor, or a byte viewer if you can't read hex ( just as I can't read hex easily! ) The best ones are those that can display 2 files at once, because then you can load up 2 archives from the game, or even the same archive twice, and make comparisons between them. Then get hold of an archive and have a look at it. I would recommend you look at some archives that are already known well by most people, such as the Quake archives, and see if you can understand it - maybe even compare it to the code used by Multiex Commander to open the archives - it will help in your understanding. If you want a copy of the program I wrote to help me out (written quickly in java) just send me a personal message over these boards.

Good luck, I hope this helps.

WATTO

PS - when you get better at it, it will usually only take a few minutes to discover the format of a game.
## Post #3
- Username: Acewell
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-07-27T13:18:37+00:00
- Post Title: How the hell   D:

> Reply from friendsofwatto
>
> 
I usually try to find some documentation on the internet about the format, or even some open-source code that is easy to read.

Always good advice. I can second that. But only after I have had a look at the archive first and I could not figure it out in a quarter of an hour.   

> Reply from friendsofwatto
>
> If I can't find anything, or the game is new, it means I have to discover it myself. I use a little program I wrote myself to hack apart the file formats, but it basically functions similarly to a hex editor.

The way forward is definitely using a good Hex Editor. I use Hex Workshop from Breakpoint software. To me, that's the best tool available for pure hex editing. It incorporates a Hex Calculator (to easily calculate back and forth from hex->dec), but more inportantly, it enables you to bookmark positions in the file you have open, colormap pieces etc. and it shows you the values at your current cursor position (e.g. viewed as byte, int. long, string etc.) all in one window.

I have written a tool in the past to help me figure out the formats. It was called MexScan and I could run it to scan a new putative archive. It ran on scripts that I could easily feed it. It would search for file identity tags, it would search for pieces of text to identify directory entries and it would pick up simple repeating patterns (e.g. set lengths of those entries) and point out the location of the start of a possible header or tail. 

I never used it.   Why? Because I had already become completely adept at spotting an archive format miles away, just by opening it in Hex Workshop. Using MexScan would just be a waste of time.   


> Reply from friendsofwatto
>
> 
Most archives are of 2 different formats - either directory-based or chunk-based....Finally, some archives actually store the directory in a separate file with the same name - for example, archive.arc and archive.idx - where the idx file contains the directory, and the arc file is the file data.

Well, I have come across some very weird formats in my time, and I wish things were always that easy. Unfortunately, although what you say is true, you will find a lot of different formats nonetheless. As an example, there's this PAK format from Painkiller. Although they used the tail-approach (stuffing the file information at the back), they had invented some kind of encoding for the filename strings. This really was quite a puzzle for me, hence the satisfaction when I cracked their code. Besides, they used Zlib compression for their resources, which I can spot from 10 miles away. 

Another example is the TRE structure from Star Wars Galaxies, that uses compressed tails, so spying eyes can't easily identify a record structure. Too bad for them that they still pointed to the beginning of the compressed tail from somewhere at the start of the file, and I cold easily spot the compression technique used. Thus, I could uncompress the tail and examine the actual information in there to write the TRE Archiver. 

Sometimes though, you will come across archive formats that are fully integrated in some game code, and only the game code will know what to expect from the archive (i.e. the archive has no "universal" structure that will always apply when new archives are created). If this is the case, the best bet is to try and identify identity tags, such as the mentioned "RIFF" etc and extract them with a resource ripper. 

> Reply from friendsofwatto
>
> 
At the start of the directory, the offset to the files will be small, so you will look for 4-byte numbers where the last few bytes are null or zero. You are mainly looking for patterns in the directory here, so move through the directory until you find another 4-bytes with a few null bytes at the end. If the second 4-byte number is bigger than the first, it usually indicates the offset to the file.

True, yet not always the case. In some instances the offsets may vary (i.e. the resources in the archive are not listed in order of saving in the archive). Also, in many cases the archive will only list offsets, and not sizes. Especially if the resources are not compressed, and are saved in order of appearance in the header or tail, this saves the programmers some space. To calculate the sizes one only needs to substract the offset of the file of interest from the offset of the next file in the list. What happens when you reach the last file depends on where the resource information was saved (header or tail). You calculate the size of the last entry by either substracting the offset from the end of the archive (total size of the archive), or by the start of the tail (if it comes directly after the last file). 
There are many variations possible to this theme, however, and it will require logic to find ways to universally be able to open these variations. 

One variable you could also look for, is the Number of Resources. Usually somewhere in an archive you may find this variable. This is handy, both to identify the purpose of such a number in the file (because if you figured out the directory structure you can calculate the number of files and if that matches this unknown number you have succesfully identified it AND have good support for the putative structure), and it may also help to positively identify the number of entries to expect.
However, there are also a lot of cases where people have not used such a variable. In this case, you must use other logical techniques to calculate the number of entries in an archive. 

Furthermore, regarding strings that comprise the names of the resouces in an archive, there are a number of possibilities of which I will list some. 

First, a string may be null-terminated. That is, you will see a string of characters (e.g. "C:\sounds\arg.wav" that is immediately followed by a 0-byte. This way, entries in a header of an archive may vary in length, because of varying string entry lengths. No matter, just read null-terminated strings and continue processing the information that comes thereafter like a normal entry. 
Second, somewhere before the string you may find a number that actually is the length of the string that follows. So, you read that number prior to reading the string, so you know how long it is, and continue processing the stuff that comes after the string right after the last character of the string. 
Thirdly, strings have a fixed size. In Doom .wad files all strings are 8 bytes in length for instance, 8 bytes that all are characters of the filename. In SadCom's .SAD files strings have 256 bytes reserved for them, BUT are not always 256 in length, they are still null-terminated, but have space up to 256. Just read the 256 bytes and process normally thereafter. 

> Reply from friendsofwatto
>
> 
Make sure, however, to choose an archive which is likely to contain files you will recognise. For example, I usually try to choose an audio archive, or sound archive, because it is easy to confirm whether your field guesses are correct.

Yes, if your new to this, it's a good way to start off with. As you examine more files, you will remember more ID tags, so you can open just any file. Also, as you examine more files, the more easy you will pick up patterns and structures. I have examined hundreds at least. 

> Reply from friendsofwatto
>
> 
The difficult parts come when you are faced with archives that contain compression or encryption. The best thing to do, if you expect compression, is to extract a file from the archive (once you know the offset and size of the file from the directory) and run it through some standard decompressors (such as ZLIB and GZIP) to see if they work. If not, then you are pretty much stuck.

You can spot a ZLib archive by just looking for a "x" at the start of the compressed resource. If there's an 'x' as the first byte, then you have a good chance that it was ZLib compressed. 

The early Painkiller files just used an actual PKZip archive and altered the identity tags that the normal .ZIP format saves. (I.e. the "PK" at the beginning of the file and throughout the file was removed). Quake 3, Thief 2 andmany more just use standard .ZIP files, but with another file extension (e.g. .PK3 in the case of Quake 3). If you open a file and the first two characters are "PK" you bet you have a normal ZIP archive, just try renaming it to *.ZIP and open it with WinRAR or any other .ZIP archive handler. 

> Reply from friendsofwatto
>
> 
PS - when you get better at it, it will usually only take a few minutes to discover the format of a game.

Practice makes easy. As I have often said, there are only so many formats to make up a game resource archive. Although I am quite often still surprised at the new things these programmers come up with, the majority of the archives out there will become easy for you, once you have had the necessary practise. Look at it as a puzzle, a riddle. There are many easy riddles, but some are tough, even tough beyond unravelling. That's just bad luck then. But remember to check the internet often to see if someone has done the impossible. You could also try to reverse engineer impossible formats, by using disassemblers on the executable. You can also look at all the binaries that come with the game to see if there's some trace of the compression method the game uses (e.g. find company markers, look inside dll's to see "zlib" or something etc.). 

Good stuff from WATTO, and I hope my addition to this swift tutorial will explain things further to you.
## Post #4
- Username: stetel
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jul 27, 2004 2:16 am
- Post datetime: 2004-07-27T18:53:39+00:00
- Post Title: How the hell   D:

thx for ur replies. lots of interesting and helpful information inside. my problem just is, that ive for example opened some file wiv hexworkshop (yeah it rawks !) and also found some kinda pattern in there...BUT what to do now? im a bit lost...i lack the skills to program some decompression engine :S
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-07-28T07:14:50+00:00
- Post Title: How the hell   D:

Well, if you have figured out a pattern, you could try to implement it in MultiEx Commander using MexScriptor. Just let me know what you figured out and I could explain to you how to get that pattern into a script. That is, if the pattern/format is implementable by the script.
## Post #6
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-07-30T14:11:38+00:00
- Post Title: How the hell   D:

> Reply from Mr.Mouse
>
> 
friendsofwatto wrote:
Most archives are of 2 different formats - either directory-based or chunk-based....Finally, some archives actually store the directory in a separate file with the same name - for example, archive.arc and archive.idx - where the idx file contains the directory, and the arc file is the file data.

Well, I have come across some very weird formats in my time, and I wish things were always that easy. Unfortunately, although what you say is true, you will find a lot of different formats nonetheless. As an example, there's this PAK format from Painkiller. Although they used the tail-approach (stuffing the file information at the back), they had invented some kind of encoding for the filename strings. This really was quite a puzzle for me, hence the satisfaction when I cracked their code. Besides, they used Zlib compression for their resources, which I can spot from 10 miles away.

I will agree with this, there are some very unusual formats out there, but i would say that the majority are roughly of a similar structure, namely the directory structure. 

The ones that I still think are the most difficult to discover are the formats that put the whole directory structure in the archive - usually it involves jumping backwards and forwards in the archive to different sub-directories in order to build up the actual file name. I havn't come across many of these, thankfully, but they do exist.

> Reply from Mr.Mouse
>
> 
True, yet not always the case. In some instances the offsets may vary (i.e. the resources in the archive are not listed in order of saving in the archive). Also, in many cases the archive will only list offsets, and not sizes. Especially if the resources are not compressed, and are saved in order of appearance in the header or tail, this saves the programmers some space. To calculate the sizes one only needs to substract the offset of the file of interest from the offset of the next file in the list. What happens when you reach the last file depends on where the resource information was saved (header or tail). You calculate the size of the last entry by either substracting the offset from the end of the archive (total size of the archive), or by the start of the tail (if it comes directly after the last file). 
There are many variations possible to this theme, however, and it will require logic to find ways to universally be able to open these variations. 

One variable you could also look for, is the Number of Resources. Usually somewhere in an archive you may find this variable. This is handy, both to identify the purpose of such a number in the file (because if you figured out the directory structure you can calculate the number of files and if that matches this unknown number you have succesfully identified it AND have good support for the putative structure), and it may also help to positively identify the number of entries to expect.
However, there are also a lot of cases where people have not used such a variable. In this case, you must use other logical techniques to calculate the number of entries in an archive.

Quite right, the number of files is usually one of the most critical things I aim to discover, because it allows me to set up arrays in the least memory as possible. If you cannot find a field in the archive that lists the number of files, but you can find out the first file offset, and each file entry in the directory is a fixed size, you can simply divide the first file offset by the entry size - something like (firstFileOffset - headerInfo) / entrySize, where the headerInfo is anything which is not part of the directory (like a file tag, for example)

> Reply from Mr.Mouse
>
> 
Furthermore, regarding strings that comprise the names of the resouces in an archive, there are a number of possibilities of which I will list some. 

First, a string may be null-terminated. That is, you will see a string of characters (e.g. "C:\sounds\arg.wav" that is immediately followed by a 0-byte. This way, entries in a header of an archive may vary in length, because of varying string entry lengths. No matter, just read null-terminated strings and continue processing the information that comes thereafter like a normal entry. 
Second, somewhere before the string you may find a number that actually is the length of the string that follows. So, you read that number prior to reading the string, so you know how long it is, and continue processing the stuff that comes after the string right after the last character of the string. 
Thirdly, strings have a fixed size. In Doom .wad files all strings are 8 bytes in length for instance, 8 bytes that all are characters of the filename. In SadCom's .SAD files strings have 256 bytes reserved for them, BUT are not always 256 in length, they are still null-terminated, but have space up to 256. Just read the 256 bytes and process normally thereafter.

It is always nice to find a list of filenames somewhere in the archive, not only so you know what the files in the archive are supposed to be, but also as it can help determine the directory structure of the archive itself. However, game companies don't really like to store filenames in an archive because it takes up alot of space, and they slow down the reading time of a file because it has to skip over the data.

If filenames are used, they normally occur in each directory entry, however some archives have the filenames stored in a separate directory elsewhere in the archive. This allows the game to skip reading the filenames, thus loading the archive quicker. If this is the case, the filenames are usually null-terminated, as described by Mr Mouse.

> Reply from Mr.Mouse
>
> 
Practice makes easy. As I have often said, there are only so many formats to make up a game resource archive. Although I am quite often still surprised at the new things these programmers come up with, the majority of the archives out there will become easy for you, once you have had the necessary practise. Look at it as a puzzle, a riddle. There are many easy riddles, but some are tough, even tough beyond unravelling. That's just bad luck then. But remember to check the internet often to see if someone has done the impossible. You could also try to reverse engineer impossible formats, by using disassemblers on the executable. You can also look at all the binaries that come with the game to see if there's some trace of the compression method the game uses (e.g. find company markers, look inside dll's to see "zlib" or something etc.). 

Good stuff from WATTO, and I hope my addition to this swift tutorial will explain things further to you.

Thanks for completing the work Mr Mouse, I think we both covered it pretty well.

BTW, I wish to congratulate and thank you for your work on MultiEx Commander over the years, it has been a great help to so many people!

WATTO
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-01T21:38:24+00:00
- Post Title: How the hell   D:

Yes, we did cover it pretty good.
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-11-01T09:24:10+00:00
- Post Title: How the hell   D:

Check for our massive tutorial here :
[viewtopic.php?t=968](http://forum.xentax.com/viewtopic.php?t=968)
## Post #9
- Username: RevConfusmo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 24, 2005 6:44 am
- Post datetime: 2005-11-24T00:16:16+00:00
- Post Title: How the hell   D:

I've been looking at the Metalheart portion of the wiki since last night, and the actual .pkg files for nearly a week (amidst much head scratching and confusion). It's a pretty cool game and I'd like to try my hand at modding from the ground up. After reading the [DGTEFF](http://wiki.xentax.com/index.php/DGTEFF) this morning I began rooting around with Hex Workshop and was pleasantly surprised to find that I'd actually learned something for a change. My old buddy, on the other hand, is already experimenting with decompressing those fluffy little beasties. Did I mention that I'm a complete n00b?  

Thanks for helping a not-so-old old dog learn some new tricks.
## Post #10
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-11-24T00:34:47+00:00
- Post Title: How the hell   D:

Hey, not a problem mate. I'm sure both Mr Mouse and I are glad that someone is using it and has found it benificial - I know I am. Thanks for the complements, and good luck with your exploration!

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #11
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-11-24T08:58:43+00:00
- Post Title: How the hell   D:

Ta very much, the DGTEFF was written to help out others who were new to this field, and I'm pleased to see it helped you out indeed!
## Post #12
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-08-25T19:16:32+00:00
- Post Title: How the hell   D:

> Reply from Mr.Mouse
>
> Ta very much, the DGTEFF was written to help out others who were new to this field, and I'm pleased to see it helped you out indeed!
Any tips on how to Extract from PS2 games.
Ie: metal Gear SOlid 3: Snake EATER or Breath Of Fire Dragon Quarter?
PS2 games contians TONS of compression and sometimes even compressed USELESS files, just to fool anyone clever enough to hack them.
Any ideas what the BEST program to create an EXTRACTION program in is?
I hear that Turfster uses DELPHI.
