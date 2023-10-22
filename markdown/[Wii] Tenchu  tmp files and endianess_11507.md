## Post #1
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-05-14T20:22:53+00:00
- Post Title: [Wii] Tenchu : tmp files and endianess

Hi guys
I am exploring Tenchu:Shadow warrior files on the Wii. 
I managed to get into the main archive but my first problem was a container/compression file i found .tmp.

I am certain it is a container cos there are chunks of junk/padding followed by havok files ("WaaW" signature and every other thing in an havok file). My problem is i cant seem to find any form of file offset/size/pointer to help me effectively get past the chunks of unknown data. 

Secondly I am predominantly a Pc programmer and i have never come up against Big Endians even when I came up against PS2 files.
I am wondering if I should take any extra precaustions.  I am slightly confused cos the strings appear intact (I dont think they are ever affected by endian conversion).

The problems is that there were Havok files outside the tmp container that have turned out to be unreadable by every version of the havok sdk i tried. So even if i manually extract the  files from the tmp files i cant check if I got things right.

I wonder is there a way to mass convert a file's endianness?
[files.rar](https://xentaxbackup.github.io/file/7333_files.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-05-15T04:08:22+00:00
- Post Title: [Wii] Tenchu : tmp files and endianess

> Reply from JohnHudeski
>
> I am slightly confused cos the strings appear intact (I dont think they are ever affected by endian conversion).strings can be looked up as a sequence of bytes or a byte array. These are not affected by the endianness "by definition".

> The problems is that there were Havok files outside the tmp container that have turned out to be unreadable by every version of the havok sdk i tried.u did not try a Linux version I guess?

> I wonder is there a way to mass convert a file's endianness?Only if you knew the exact format of the file (where are WORDs, DWORDs, bytes?)
Easiest way imho would be to install Linux (or ubuntu?) on a VM and use Havok tools to save HKX as XML.
From wikipedia it reads: 

> Havok Version 2011.2, released in September 2011, is known to work on [...] Linux
(Maybe it's not related to Havok Standalone tools 'cause I couldn't find a free downloadable Linux version .)
## Post #3
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-05-15T10:37:13+00:00
- Post Title: [Wii] Tenchu : tmp files and endianess

Thanks a lot for the reply. It seems like its too much work. Considering it wasn't even my first choice game.

I dont know if i posted this in the wrong section also.
