## Post #1
- Username: bgbennyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Oct 15, 2005 6:41 pm
- Post datetime: 2006-03-27T15:26:12+00:00
- Post Title: Psychonauts PS2 .PAK Archive

Psychonauts PS2 version has only one resource file - a 3.26GB Resource.Pak file. I am the author of [Psychonauts Explorer](http://quick.mixnmojo.com/software.php#psychonautsexplorer) and have tried to decipher the file format on a number of occasions, I have failed at every attempt.

I'm posting an archive cutter zip and my notes in the hope that someone else will have more success. 

Things to note about the file:It contains every file in the game - in the xbox and pc versions - all the files are contained within 3 resource types:
Data.pkg - for general files
Level pack files (.ppf) - for level specific data
Isb audio files - for music and voice. (A wavebank in the xbox version).
I have found the Level pack files inside resource.pak, but not the other archive types.
I havent been able to find a name directory anywhere. Perhaps the filenames are compressed/encrypted? The level pack files dont contain information about their own filename so I would assume that the names for the level archives are stored somewhere.
The PS2 binary contains 'inflate 1.1.3 Copyright 1995-1998 Mark Adler' - so its a fairly good bet that GZIP/ZLIB is used somewhere.
The first file is at offset 393216 - an image file marked by the chunk 'PS2 ', followed by a number of other PS2 files - however I cant get the offsets to match up to those in the file records.
HEADER
4 bytes - ?
4 bytes (30681) - Number of Files/records
4 bytes - ?

File Records:
2 bytes - ?
2 bytes - ID ?
4 bytes - Offset? (relative to...something thats variable)
4 bytes - File Size?

The only thing that I'm sure of is the number of file records. There are 368172 bytes after the header - which looks like file records, so assuming that each record is 12 bytes: 
30681 * 12 + the 12 byte header = offset 368182 - which takes you neatly to the end of the file records.

[ArchiveCutter Zip](http://quick.mixnmojo.com/temp/ps2/RESOURCE.PAK.zip)
I know its not much of a file spec, but hopefully someone will be able to spot something that I haven't
## Post #2
- Username: baccello
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Sep 23, 2004 1:44 am
- Post datetime: 2007-01-30T12:09:33+00:00
- Post Title: Psychonauts PS2 .PAK Archive

Do you think that could help you to have the archive cutter of the pal version?

Let me know
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-01-30T15:09:54+00:00
- Post Title: Psychonauts PS2 .PAK Archive

> Reply from bgbennyboy
>
> I havent been able to find a name directory anywhere. Perhaps the filenames are compressed/encrypted? The level pack files dont contain information about their own filename so I would assume that the names for the level archives are stored somewhere.
They don't have to be saved in the file, a hash table is also possible.

> The PS2 binary contains 'inflate 1.1.3 Copyright 1995-1998 Mark Adler' - so its a fairly good bet that GZIP/ZLIB is used somewhere.
so go search something like 78h in the file. This normally is the header of a zlibbed file. At least the 8 is constant cause it identifies deflate.
