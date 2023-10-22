## Post #1
- Username: ManKeyyeman
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 17, 2020 2:24 pm
- Post datetime: 2020-04-17T06:57:24+00:00
- Post Title: Plants vs. zombies (ps3) .pak files

Hi, I can't unpack .pak files of plants vs. zombies on ps3. Format pak on console is different pak from the pc version.It's pretty simple here, the files aren't compressed, but I can't find offsets and sizes. Sample files here:
[https://drive.google.com/file/d/1XJbF0n ... sp=sharing](https://drive.google.com/file/d/1XJbF0nOy2BYAePsVqmIF1gicnTzfR5Gi/view?usp=sharing)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-04-18T11:36:59+00:00
- Post Title: Plants vs. zombies (ps3) .pak files

It's a bit of a rubbish format, but it goes like this,

8-byte file header followed by each file entry as follows:

Byte - Flag (if 0x80 then there are no more file entries)
Byte - String length
Text - Filename
Long - File size
Long - Uncompressed file size
Long - ?
Long - ?

Each file starts on an 8-byte boundary.  Also, it doesn't store the initial offset to the start of the data or the number of files, so it seems like you have to go through the file table first to get the initial data offset, and then go through it again to process the actual files.
## Post #3
- Username: lizterzapzap
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 19, 2020 11:34 pm
- Post datetime: 2020-10-19T15:38:27+00:00
- Post Title: Plants vs. zombies (ps3) .pak files

But is it possible thou. I also do need the .pak unpacked.
## Post #4
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2020-10-23T12:38:41+00:00
- Post Title: Plants vs. zombies (ps3) .pak files

There is zlib compression. You can use offZip but it extract files without filenames.
