## Post #1
- Username: shinzef
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 30, 2021 12:03 pm
- Post datetime: 2021-11-02T03:54:56+00:00
- Post Title: Age Of Empires 4 / IV ( .rrtex )

Relic Chunky
Essence Engine 5.0

i don't know any importer / converter for it 

File samples: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1ttbFluoLzsD_EeeyyVW9d4n9V9USkndj?usp=sharing)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-11-02T10:32:55+00:00
- Post Title: Age Of Empires 4 / IV ( .rrtex )

> i don't know any importer / converter for it
You don't know any tools, bacause this game had a world premiere few days ago and noone has created any modding program yet. 
But AoE is a popular series, so something should appear soon.


Anyway, this RRTEX file is chunk based. All image data is in "DATATDAT" sub-chunk and it's compressed with ZLIB.
So easiest way to get textures is to use offzip [http://aluigi.altervista.org/mytoolz/offzip.zip](http://aluigi.altervista.org/mytoolz/offzip.zip)
and then view textures in rawtex [https://i.imgur.com/DqPOr4l.png](https://i.imgur.com/DqPOr4l.png)
## Post #3
- Username: shinzef
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 30, 2021 12:03 pm
- Post datetime: 2021-11-03T03:55:59+00:00
- Post Title: Age Of Empires 4 / IV ( .rrtex )

Thanks for this, but it doesnt work maybe im using the wrong command

i did "offzip -a (input.dir) (output.dir)"

then i copied the exact same setting for the raw texture based on ur imgur.

This is the result i got:
[Screenshot 2021-11-03 115333.png](https://xentaxbackup.github.io/file/21131_Screenshot 2021-11-03 115333.png)
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-11-03T10:24:40+00:00
- Post Title: Age Of Empires 4 / IV ( .rrtex )

> i did "offzip -a (input.dir) (output.dir)"
This command seems to be OK.

> then i copied the exact same setting for the raw texture
But did you use raw texture cooker for this? [viewtopic.php?t=16461](https://forum.xentax.com/viewtopic.php?t=16461)


Also, try to test it on some other samples like buildings textures etc.
And later try also some other settings, not every texture has to be BC3.
## Post #5
- Username: shinzef
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 30, 2021 12:03 pm
- Post datetime: 2021-11-04T00:09:39+00:00
- Post Title: Age Of Empires 4 / IV ( .rrtex )

yes i used that raw texture cooker

will try other settings
## Post #6
- Username: lordoftheroaches
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 11, 2021 6:41 am
- Post datetime: 2021-11-10T22:43:26+00:00
- Post Title: Age Of Empires 4 / IV ( .rrtex )

I've been having the most success with a BC7 format.

I've been working with icons mostly. Both backgrounds and badges are 96x96 with a 10 offset.

Also, remember you need to have microsoft's texconv on the same folder as Rawtex to see previews. You should see a graphical red "x" typical of image error within the GUI of Rawtex if you are having issues with texconv.
