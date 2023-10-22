## Post #1
- Username: ebokucaz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 08, 2021 2:41 am
- Post datetime: 2021-05-08T14:38:55+00:00
- Post Title: Wonderland Online - *.MMG Files

Hello everyone,

I'm currently looking into some of the files from this old MMO Game. There already has been an older thread on here for this game about unpacking some of its other files ([viewtopic.php?f=10&t=11690&p=96426](https://forum.xentax.com/viewtopic.php?f=10&t=11690&p=96426)). But I would like to look at some of the games map files, which seem to be inside the two .MMG files (Ground.MMG and Wem.MMG): [https://www.mediafire.com/file/3v38x7od ... s.rar/file](https://www.mediafire.com/file/3v38x7odspu1usw/MMG_Files.rar/file)

The Ground.MMG file seems to contain .map-Files and the Wem.MMG seems to contain .wem files (MapObjects). I would like to extract these, but as I'm very new to all of this I wasn't able to figure out how to write a script for these files yet.
Any help with this would be greatly appreciated. Or maybe someone could point me in the right direction of where to start.
## Post #2
- Username: ebokucaz
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-05-08T17:21:53+00:00
- Post Title: Wonderland Online - *.MMG Files

> Or maybe someone could point me in the right direction of where to start.
If you want to learn how to do some reverse engineering and extract data from archives,
you can start here [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)


I have created also specification for this file format on the wiki
[http://wiki.xentax.com/index.php/Wonderland_Online_MMG](http://wiki.xentax.com/index.php/Wonderland_Online_MMG)

You can use it to write working script/extractor.
Such program would need to:
1. Go to the end of the archive file and read "number of files" value
2. Calculate the offset of the info array and go to this offset
3. Read all the entries from the info array
4. Save data of the files
## Post #3
- Username: ebokucaz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 08, 2021 2:41 am
- Post datetime: 2021-05-08T17:55:30+00:00
- Post Title: Wonderland Online - *.MMG Files

Thank you very much for the quick reply and the specification.

I'll look into it and if I manage to create a working BMS script I'll add it to the wiki page, in case anyone else might be interested.
