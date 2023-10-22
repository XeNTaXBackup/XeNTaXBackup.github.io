## Post #1
- Username: Dakilla
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 11, 2014 8:37 pm
- Post datetime: 2015-05-17T13:51:22+00:00
- Post Title: Help me figure out this J Stars STPZ compression

I've been looking on how I could uncompress these .pak files for a long, long time now...
I looked into many forum threads trying to figure out how to do it. While almost all of them have relevant information, none is actually 100% on point and leaves something to be worked upon.

Here are some of the threads I read: 
[http://zenhax.com/viewtopic.php?t=831](http://zenhax.com/viewtopic.php?t=831)
[viewtopic.php?f=10&t=11342&hilit=stpz](http://forum.xentax.com/viewtopic.php?f=10&t=11342&hilit=stpz)
[viewtopic.php?f=16&t=9129&hilit=stpz](http://forum.xentax.com/viewtopic.php?f=16&t=9129&hilit=stpz)

"Why am I starting a new thread about it then?" you might wonder. Well, it's simple, yesterday I was browsing the 
PS3 memory to get any clues and I found out the offsets for the uncompressed versions of the files...
So I'm attaching a file example of both the compressed and uncompressed versions with hopes that someone can figure out the compression algorithm that I cannot for the sake of me find out :S

Take into consideration that my goal isn't uncompressing and unpacking the files, but yet uncompress, edit and then compress it back!

Note: The uncompressed file is a memory dump from the idstring (STPK)  of the file, until the offset of the next file's idstring(STPK)... so, the filesize is likely correct but may be a few bytes off, i'm not sure
[example.rar](https://xentaxbackup.github.io/file/9208_example.rar)
