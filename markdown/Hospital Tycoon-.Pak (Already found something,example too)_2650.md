## Post #1
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2007-06-09T14:40:18+00:00
- Post Title: Hospital Tycoon-.Pak (Already found something,example too)

Hello everybody 

Hospital Tycoon using .pak archives,they are not packed or encrypted and I managed to found out some important information.

GameExtractor is able to extract them but game wont work without archives so after modding,its need to packed again.


Header - 32 bytes length (probably less)
4 - Magic
4 - Files Count
4 - Unknown
4 - Unknown
4 - Offset to Tail
4 - Unknown
4 - Unknown
4 - Unknown

Animations,pak:

6AF6 FD34 0D05 0000 0EC3 3806 9C3C 0000 
AAFF 3806 1C04 0100 2000 0000 EEC2 3806

After archive header (32 bytes) starting data of first file in archive.

In tail is saved filenames (only) with different length (detelimer i 0x00).

Please any help ??? thank you so much

Example:
Textures.pak (2MB,Cutted):

```
http://www.badongo.com/file/3365950
```
## Post #2
- Username: SparedLife
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Mar 07, 2004 1:37 pm
- Post datetime: 2007-06-09T19:18:27+00:00
- Post Title: Hospital Tycoon-.Pak (Already found something,example too)

From the example you gave they appear to be complete DDS files with a separate unique header on top of the DDS header. Try using one of my DDS extraction tool. Maybe this one:

[http://www.spared-life.com/SparedLifeFi ... S-1.02.zip](http://www.spared-life.com/SparedLifeFiles/SLConverter-DDS-1.02.zip)

 It's fairly easy to use. 

 Create a folder, drop the DDS tool into that folder, drop the files to extract into that folder, and run the program. The program extracts the complete DDS files minus any mips but does give the needed info for saving and reinserting the textures. The edited file must be exactly as the extracted file including filename.
## Post #3
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2007-06-09T19:58:18+00:00
- Post Title: Hospital Tycoon-.Pak (Already found something,example too)

Did you read what I wrote ?:D I"m able to open archive and extract via GameExtractor ... but i need to find out the header information of that pak archive to create my own too which will be able to create that archives (archives are required for plaing game)
## Post #4
- Username: SparedLife
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Mar 07, 2004 1:37 pm
- Post datetime: 2007-06-11T04:32:22+00:00
- Post Title: Hospital Tycoon-.Pak (Already found something,example too)

hmm well yes I read your post. The game does not work unless the textures are in the archive. If what you posted is a sample from said archive then the textures are not archived but only stored in the library.
 If you want to edit the textures (skin the game) and what you posted is a valid part of the game library then the link I gave you will extract the texture from the library and reinsert the texture back into the library.
 I did however miss the part in your post where you said you wanted to create "your own" tool. All I read was something about "any help"
## Post #5
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2007-06-11T11:49:03+00:00
- Post Title: Hospital Tycoon-.Pak (Already found something,example too)

Yes,I"m able to create my own unpacker and injector,anyway thank you for your help/answers
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-06-11T17:50:34+00:00
- Post Title: Hospital Tycoon-.Pak (Already found something,example too)

PM friendsofwatto. He can probably help you.
## Post #7
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2007-06-11T20:33:29+00:00
- Post Title: Hospital Tycoon-.Pak (Already found something,example too)

I think that if somebody wants help me that he will write here,I wont disturbing someone via PM 

But anyway thank you for your answer.
## Post #8
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-06-11T20:41:49+00:00
- Post Title: Hospital Tycoon-.Pak (Already found something,example too)

friendsofwatto is the developer of GameExtractor afaik.
## Post #9
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2007-06-11T21:31:19+00:00
- Post Title: Hospital Tycoon-.Pak (Already found something,example too)

Heh  Its Watto,right ? lol ... thank you.
## Post #10
- Username: itg
- Rank: beginner
- Number of posts: 31
- Joined date: Sat May 12, 2007 10:11 pm
- Post datetime: 2007-06-13T07:42:29+00:00
- Post Title: Hospital Tycoon-.Pak (Already found something,example too)

[http://int0thegame.blogspot.com/2007/06 ... ycoon.html](http://int0thegame.blogspot.com/2007/06/hospital-tycoon.html)

File format is simplest.
## Post #11
- Username: Demander
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Jun 06, 2007 4:59 am
- Post datetime: 2007-06-13T10:12:11+00:00
- Post Title: Hospital Tycoon-.Pak (Already found something,example too)

Thank you so much
## Post #12
- Username: cobainfish
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 15, 2007 1:25 am
- Post datetime: 2007-06-15T07:10:52+00:00
- Post Title: Hospital Tycoon-.Pak (Already found something,example too)

The contents of this post was deleted because of possible forum rules violation.
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-06-16T06:53:31+00:00
- Post Title: Hospital Tycoon-.Pak (Already found something,example too)

What game are you talking about? Hospital Tycoon?
