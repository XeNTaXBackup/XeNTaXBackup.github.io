## Post #1
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2012-10-13T22:40:02+00:00
- Post Title: Sol Trigger for PSP, *.TPK files

I'm actually not especially interested in the game, but I did do some digging because I was curious and thought I'd at least have it documented somewhere.

Folder structure is visible in the user folder.
Most TPK files (at least the ones that start with ZZZ0) are compressed with zlib.
First word contains the magic number ZZZ0, the second word is the size of the decompressed file and the third word seems to be always 4. You can use normal zlib inflation from byte 0xC onward to decompress the file.

I haven't played too much with recompression levels, but level 1 seems to work fine.

Text files (in the, well, TEXT folder) are encoded in UTF-8 and are seemingly structured by having a line ID (4 bytes) and the corresponding offset in the file.

Sadly (for potential translations), the font is monospaced and looks pretty unpleasing:
[http://imgur.com/NgC0D](http://imgur.com/NgC0D)
## Post #2
- Username: Romored
- Rank: beginner
- Number of posts: 20
- Joined date: Fri May 14, 2010 7:52 pm
- Post datetime: 2013-02-01T14:46:10+00:00
- Post Title: Sol Trigger for PSP, *.TPK files

Hello there! I'll bump this topic as the subject is very similar.

I found this kind of files in another PSP game: Criminal Girls. Same "ZZZ0" header and same structure. I tried to find an utility to extract their content but I couldn't find absolutely anything. The only thing I know is what Forte said up here, that zlib can be used. The problem is that I've no idea how to do it. I have little experience in file manipulation and C++ programming in general, I don't think I could create an application from scratch. Can someone please help me? I think it could be useful for many people, as the format seems rather standard for most of the latest PSP games.

One of the files I wanted to extract is this one. It should contain sprites and/or textures.

[http://www.mediafire.com/?faiqqy18qc8zrfk](http://www.mediafire.com/?faiqqy18qc8zrfk)

Almost all the files of that game are .tpk.
## Post #3
- Username: Dazz
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Mar 17, 2011 7:10 pm
- Post datetime: 2013-04-22T10:49:50+00:00
- Post Title: Sol Trigger for PSP, *.TPK files

//tpk extraction bms script

idstring "ZZZ0"
get size long
get null long
savepos offset
get zsize asize
math zsize -= offset
get name basename
string name += .UTK
comtype zlib
clog name offset zsize size 


This is about as much as I think I can do; I can't for the life of me figure out the palettes for the files that come out of these though. This worked for Criminal Girls, not tried with the others.
## Post #4
- Username: sprayer
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Sep 10, 2010 2:09 pm
- Post datetime: 2017-08-13T15:55:43+00:00
- Post Title: Sol Trigger for PSP, *.TPK files

any news?
