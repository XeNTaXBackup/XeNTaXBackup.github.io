## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-14T02:57:55+00:00
- Post Title: Gensokyo Shiki

Original name: 幻想郷史紀

Hmm first, the archives are encrypted.
That's all I know from looking at the hex.

Exe: [http://www.mediafire.com/?rjh4jt4o4x7xt6j](http://www.mediafire.com/?rjh4jt4o4x7xt6j)

Sample archives attached
[content.7z](https://xentaxbackup.github.io/file/5659_content.7z)
## Post #2
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2012-08-14T15:46:25+00:00
- Post Title: Gensokyo Shiki

It's a "Wolf RPG Editor" Game,

the decrypt key is "ypcd121231", 
the function to calculate the key is (in ida pro) at: ".text:00588C00"
the calculated key is: "86 07 E9 B9 CE 9E CE B9 99 4E 41 BC"

it's a simple xor encryption, here the decrypted samples: [http://www.mediafire.com/download.php?vv4ubxfbslbmep5](http://www.mediafire.com/download.php?vv4ubxfbslbmep5)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-14T16:56:56+00:00
- Post Title: Gensokyo Shiki

LOL wow it really is a wolf archive.
I was playing the game and never thought it was made in wolf.

I tried to figure out how their file table is stored. Offset to file table at 0xC, followed by the size of the name table. A bunch of names followed by a bunch of file entries, where there is some number system to indicate which directory a file belongs in. But couldn't figure it out.
