## Post #1
- Username: windfury
- Rank: beginner
- Number of posts: 23
- Joined date: Sun May 23, 2010 2:54 pm
- Post datetime: 2013-06-17T16:41:53+00:00
- Post Title: 300 Heroes .jmp file

It's a Chinese League of Legends clone/rip-off which pretty much takes everything from just about everywhere.
Website: [http://300.zqgame.com/](http://300.zqgame.com/)
Client Link: [http://download01.jumpwgame.com/client/300_v0.2.194.zip](http://download01.jumpwgame.com/client/300_v0.2.194.zip)
[http://download.17173.com/11903/10/63478/](http://download.17173.com/11903/10/63478/)

Plenty of stuff came from LoL, I'd say even the engine. They even have variables with LoL in it.
Characters were taken from different games, anime, movies, etc...

Anyway, I used offzip to extract the files from Data.jmp, it works for the most part.
Was able to see some textures and audio files.

I'd love to get the proper file names though.
## Post #2
- Username: windfury
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-17T18:31:42+00:00
- Post Title: 300 Heroes .jmp file

Quickbms script

```
#by chrrox
#http://aluigi.altervista.org/quickbms.htm
idstring "DATA"
goto 0x32
get files long
goto 0x38
for i = 0 < files
getdstring name 0x102
get offset long
get zsize long
get size long
getdstring null 0x22
clog name offset zsize size
next i

```
## Post #3
- Username: windfury
- Rank: beginner
- Number of posts: 23
- Joined date: Sun May 23, 2010 2:54 pm
- Post datetime: 2013-06-17T21:54:28+00:00
- Post Title: 300 Heroes .jmp file

Thanks chrrox!

It seems that the models are stored in another archive (.x files).
Although I'm not sure yet, I was assuming that they'd be using the same .skn format for their models as well.
Not sure if I should start another topic in 3D/2D models for this.
## Post #4
- Username: Brilleas
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Oct 22, 2014 8:50 pm
- Post datetime: 2015-03-20T13:09:29+00:00
- Post Title: 300 Heroes .jmp file

Ah.How to open .x file.I can't open it
## Post #5
- Username: AdmiralTraun
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Nov 01, 2020 3:46 pm
- Post datetime: 2023-08-09T07:23:07+00:00
- Post Title: 300 Heroes .jmp file

Hello hrox, you can update the script for 300 heroes, a new patch has been released and new resources that are added to the patch cannot be extracted
## Post #6
- Username: AdmiralTraun
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Nov 01, 2020 3:46 pm
- Post datetime: 2023-08-09T08:18:06+00:00
- Post Title: 300 Heroes .jmp file

i tried changing goto offset 0x32 to 0x0 it extracted a couple of files


image.png (5.79 KiB) Viewed 73 times
## Post #7
- Username: AdmiralTraun
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Nov 01, 2020 3:46 pm
- Post datetime: 2023-08-09T08:18:25+00:00
- Post Title: 300 Heroes .jmp file

image (1).png (12.87 KiB) Viewed 72 times
