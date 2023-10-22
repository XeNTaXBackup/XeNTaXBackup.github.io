## Post #1
- Username: Matsilagi
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Aug 31, 2014 12:39 pm
- Post datetime: 2014-08-31T04:45:01+00:00
- Post Title: MegaRace 3 BFZ

Hi.
This is an old game, and theres something that pisses me off for 15 years, is the fact that i cant unlock the last ship from the game. And i think the awnser might be in extracting the game's files.
Last time i tried was with an offset zip extractor, i got scripts (apparently coded in LUA, used to define sprite points, ship names, levels and other stuff), sounds, 3d models and textures. However, i couldnt open half of them and it was really hard navigating trough those files.

I would like to know if someone here would be able to code a tool to open the BFZ files with ease (I think they are differently compressed zip files, but im not sure).

If anyone needs a file, i can upload it (otherwise you can download the game yourself).

Any help is appreciated.

EDIT:Here's the game's BFZ file: [https://mega.co.nz/#!0IUhHAxI!SFEr8VbGV ... TuKKniaFeo](https://mega.co.nz/#!0IUhHAxI!SFEr8VbGVfgGZOLOboNgUBGhlkE52ADh9TuKKniaFeo)
## Post #2
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2014-09-02T21:05:48+00:00
- Post Title: MegaRace 3 BFZ

I've tried to take a look at those unzipped files. All I can tell; impossible to look through it...
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-09-03T05:27:07+00:00
- Post Title: MegaRace 3 BFZ

Here script for unpack, but this archive don't contain filenames.

```
# 
# Written by Ekey (h4x0r)
# 
# script for QuickBMS http://quickbms.aluigi.org

get FILES long

for i = 0 < FILES
    get OFFSET long
    get ZSIZE long
    get SIZE long
    get HASH long
    get NULL long
	
    if SIZE == ZSIZE
        log "" OFFSET SIZE
    else
        clog "" OFFSET ZSIZE SIZE
    endif
next i
```
## Post #4
- Username: Matsilagi
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Aug 31, 2014 12:39 pm
- Post datetime: 2014-09-03T23:35:51+00:00
- Post Title: MegaRace 3 BFZ

Damn dude! Thanks a lot!
You managed to get the ship's textures!
Now only if i could rip the models.

Gonna explore trough the files. Thanks a lot! Really.
