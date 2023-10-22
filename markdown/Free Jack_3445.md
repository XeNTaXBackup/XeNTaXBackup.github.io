## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-26T20:13:34+00:00
- Post Title: Free Jack

This game has me stumped as to what kind of compression is being used. I know it is zlib but I have never seen an archive like this. There are 2 files 1 file table (FreeJack.wh)and then the container for the actual files. (FreeJack.wa)
The file table starts off with a list of all the folder locations of the files that corresponds to the order of the files.
then about half way down it starts listing the files. so the first folder location corresponds with the first file name.
Now ill describe the file locations the best I can. the file location size compression etc is 0x16 bytes before the name of the file. Here is 2 examples.
00 78 CB 14 E6 00 AA CC 35 00 00 00 00 00 18 00 BB 23 25 08 15 00
00 5E 67 50 08 01 B4 07 00 00 66 02 00 00 17 00 A1 1E D3 07 0F 00
1. All of these start and end with 0x00
2. followed by 0x4 unkown bytes (in these 2 it would be 78 CB 14 E6, and 5E 67 50 08)
3. The next byte is either a 0 or 1 to indicate compression
4. the next 4 bytes are the compressed file size (AA CC 35 00, and B4 07 00 00) (only indicates compressed size if compression bit is on)
5. The next 4 bytes are the uncompressed size (00 00 00 00, and 66 02 00 00) (only has a value if compression bit is set)
6. I believe the next to bytes indicate file type (17 00, and 18 00) (always has last byte 00)
7. the next 4 bytes are the file offset/start (BB 23 25 08, and A1 1E D3 07) (if the file is compressed you add 0x2 to the value) (example A1 1E D3 07 = A1 1E D3 09)
8.The next byte is is the file name length +1 (15, and 0F) which means it is actually (14, and 0E) (this may have the extra +1 on it to account for the ending 00 after the file name) (and lastly this is followed bye 0x00 and then the file name)

I have successfully extracted all un compressed data no problem I am just stumped on the compression part. any help would be great  This game uses nif files so the models will be viewable once they are extracted.

Here are the files for this game I included all the exe, dll's and the file table and the first and last 20mb of the big file.
screen shot and video
[](http://xs.to/xs.php?h=xs138&d=09176&f=freejack1352.jpg)
[http://www.youtube.com/watch?v=9bugIpZ1G9E](http://www.youtube.com/watch?v=9bugIpZ1G9E)

Client download if anyone wants the full game.
Here is the client link [http://60.170.241.2/FTP/FreeJack/200903 ... _Setup.exe](http://60.170.241.2/FTP/FreeJack/20090320/1/FreeJack_Setup.exe)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-04-27T14:54:27+00:00
- Post Title: Free Jack

the compression is lzo1x.
the script for handling the archive is [here](http://aluigi.org/papers/bms/freejack.bms)
(note you must update QuickBMS since I fixed some things needed to extract this file format!)
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-04-27T17:11:02+00:00
- Post Title: Free Jack

Thanks so much the script works perfectly  The program you wrote is amazing.
I found this model and I just had to render the animation out.
[http://www.youtube.com/watch?v=u-YF9V7hLjg](http://www.youtube.com/watch?v=u-YF9V7hLjg)
I can see someone using this as their avatar pic somewhere lol.
