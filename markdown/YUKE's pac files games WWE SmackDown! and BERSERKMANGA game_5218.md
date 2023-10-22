## Post #1
- Username: just to learn 25
- Rank: beginner
- Number of posts: 23
- Joined date: Sun May 09, 2010 10:55 pm
- Post datetime: 2010-10-16T18:33:54+00:00
- Post Title: YUKE's pac files games WWE SmackDown! and BERSERK/MANGA game

Does any body know how to view Yuske's pac files. The game I'm trying rip models fromm is Berserk: Millennium Falcon Hen Seima Senki no Shō, for the 

Playstation 2.They made lots of wrestling games. And UFC games
## Post #2
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2010-10-19T05:17:01+00:00
- Post Title: YUKE's pac files games WWE SmackDown! and BERSERK/MANGA game

> Reply from just to learn 25
>
> Does any body know how to view Yuske's pac files. The game I'm trying rip models fromm is Berserk: Millennium Falcon Hen Seima Senki no Shō, for the 

Playstation 2.They made lots of wrestling games. And UFC games

Bersrek Guts model 



guts.png (46.51 KiB) Viewed 617 times
## Post #3
- Username: just to learn 25
- Rank: beginner
- Number of posts: 23
- Joined date: Sun May 09, 2010 10:55 pm
- Post datetime: 2010-10-19T07:06:06+00:00
- Post Title: YUKE's pac files games WWE SmackDown! and BERSERK/MANGA game

> Reply from dj082502
>
> just to learn 25 wrote:Does any body know how to view Yuske's pac files. The game I'm trying rip models fromm is Berserk: Millennium Falcon Hen Seima Senki no Shō, for the 

Playstation 2.They made lots of wrestling games. And UFC games

Bersrek Guts model 
guts.png

how do you rip the models doe ?
## Post #4
- Username: just to learn 25
- Rank: beginner
- Number of posts: 23
- Joined date: Sun May 09, 2010 10:55 pm
- Post datetime: 2010-10-19T07:08:10+00:00
- Post Title: YUKE's pac files games WWE SmackDown! and BERSERK/MANGA game

> Reply from dj082502
>
> just to learn 25 wrote:Does any body know how to view Yuske's pac files. The game I'm trying rip models fromm is Berserk: Millennium Falcon Hen Seima Senki no Shō, for the 

Playstation 2.They made lots of wrestling games. And UFC games

Bersrek Guts model 
guts.png

can you explain how you rip the models please
## Post #5
- Username: just to learn 25
- Rank: beginner
- Number of posts: 23
- Joined date: Sun May 09, 2010 10:55 pm
- Post datetime: 2010-10-19T15:40:32+00:00
- Post Title: YUKE's pac files games WWE SmackDown! and BERSERK/MANGA game

can you give me the soft ware I look every for it and i haven't found yet.
## Post #6
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2010-11-24T04:32:24+00:00
- Post Title: YUKE's pac files games WWE SmackDown! and BERSERK/MANGA game

> Reply from just to learn 25
>
> can you give me the soft ware I look every for it and i haven't found yet.
Sorry. I'm just checking the post now.
Using RRUnpack(*.PAC) & RROExporter(*.yobj).
## Post #7
- Username: gintaxon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 04, 2011 7:37 pm
- Post datetime: 2011-03-05T06:45:57+00:00
- Post Title: YUKE's pac files games WWE SmackDown! and BERSERK/MANGA game

That looks like a good rip for the model. I think the game is good but I have not done with the last part yet. I just need some guidelines for playing it more accurately and skillful.
## Post #8
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2011-03-31T09:04:52+00:00
- Post Title: YUKE's pac files games WWE SmackDown! and BERSERK/MANGA game

Thanks "dj082502" for the info about the Berserk ps2 game but when i drag and drop model.pac only appear an empty folder... Anybody know what happened?, what ever I extracted the .yobj files manualy with the Hex editor but with out textures.
[dump.jpg](https://xentaxbackup.github.io/file/4141_dump.jpg)
## Post #9
- Username: phorks88
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 04, 2011 5:52 am
- Post datetime: 2011-04-09T15:04:30+00:00
- Post Title: YUKE's pac files games WWE SmackDown! and BERSERK/MANGA game

If anyone is interested, you can use Mike's RRunpacker since it supports the DPAC type.
Only when it checks the model PAC dir listing it looks for the number of files and dpac 00 type, but theres some other value I can't figure out.
However, if you open it up in a hex editor, at x804 it will say 36 01, change it to FF 00... and it will extract most of the files.
It shouldn't be hard to update the source code but I haven't been able to compile it, so I use this lazy method
## Post #10
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2011-04-11T17:40:12+00:00
- Post Title: YUKE's pac files games WWE SmackDown! and BERSERK/MANGA game

> Reply from FEATHER
>
> Thanks "dj082502" for the info about the Berserk ps2 game but when i drag and drop model.pac only appear an empty folder... Anybody know what happened?, what ever I extracted the .yobj files manualy with the Hex editor but with out textures.

I don't know how to edit mtpx file.
But, my friend said 
"テクスチャですがこれはSwizzleと言う形式で、あるバイト数ごとに縦横にデータが入れ替わっています。"
Try searching through Swizzle on the internet first.
## Post #11
- Username: Bagserk
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Oct 02, 2011 9:50 am
- Post datetime: 2012-03-03T15:34:16+00:00
- Post Title: YUKE's pac files games WWE SmackDown! and BERSERK/MANGA game

Sorry if this topic is old, but I was searching how to do this too.

I got to extract all the yobj files, and I'm trying to get them into MAX.

Thing is, when I import the OBJ files generated by RROExporter I just get pure black, square-ish models, like this:

[http://imageshack.us/photo/my-images/834/wots.jpg](http://imageshack.us/photo/my-images/834/wots.jpg)
## Post #12
- Username: Ragash
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 15, 2012 2:44 am
- Post datetime: 2013-01-10T17:57:45+00:00
- Post Title: YUKE's pac files games WWE SmackDown! and BERSERK/MANGA game

> Reply from Bagserk
>
> Sorry if this topic is old, but I was searching how to do this too.

I got to extract all the yobj files, and I'm trying to get them into MAX.

Thing is, when I import the OBJ files generated by RROExporter I just get pure black, square-ish models, like this:

http://imageshack.us/photo/my-images/834/wots.jpg

im so sorry for necroposting,

but im trying to figure this out from MONTHS
