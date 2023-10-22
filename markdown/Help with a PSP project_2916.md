## Post #1
- Username: Wyseman
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 02, 2008 3:24 am
- Post datetime: 2008-02-02T04:07:15+00:00
- Post Title: Help with a PSP project

I'm trying to get change the graphic UI menus in Daisenryaku Portable 1 and 2, to English.  This would not be to hard if i had access to all of the .gim graphic files in the games archives.  As it is now i only have access to a very small few that are not archived.  The archives i can find so far are .dat and .ofs.  I have never heard of .ofs but i have .dat and attempted to find a means to access them with no luck.  

Also if i'm able to access the graphic files I should be able to mod a great deal of this games appearence from map tiles to vehicles them selves.  I wish i new more when it comes to programming but i'm a graphic designer so.

If anyone can help i have attached the UI directories .dat and .ofs files for anyone to look at here.  [http://www.wisedesignz.net/dat/archives.rar](http://www.wisedesignz.net/dat/archives.rar)

Thanks this is that last place i can think of to ask for help.
## Post #2
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2008-02-03T07:09:00+00:00
- Post Title: Help with a PSP project

.ofs is a very simple archive format.

Beginning of file starts with a dword count, then there are three dwords * count, made up of: dword dataoffset, dword datasize, dword nameoffset

dataoffset is an absolute offset to the file data, then use datasize as normal, files are normal GIM images ('MIG' header), you can use gimconv to convert them easily. nameoffset points to near the end of the file, filename of the file, null terminated.

Those .dat looks more complicated though. Probably raw RGBA data with associated image data (width, height, etc), didn't look too hard.
## Post #3
- Username: Wyseman
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 02, 2008 3:24 am
- Post datetime: 2008-02-04T02:00:30+00:00
- Post Title: Help with a PSP project

thx for looking at them,  I'm still interested if anyone is able to create a plugin to unpack these files.,  and of course, I would share my finished game translations with the community if they so desired.
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-04T10:15:56+00:00
- Post Title: Help with a PSP project

```
Get numFiles Long 0 ;
Do ;
SavePos offsetOffset 0 ;
Get dataOffset Long 0 ;
SavePos ressourceSizeOffset 0 ;
Get dataSize Long 0 ;
Get nameOffset Long 0 ;
SavePos filePointer 0 ;
GoTo nameOffset 0 ;
Get filename String 0 ;
GoTo filePointer 0 ;

Log filename dataOffset dataSize offsetOffset ressourceSizeOffset 0 ;
Math counter += 1 ;
While counter <> numFiles ;
```

Haven't tested it though.
