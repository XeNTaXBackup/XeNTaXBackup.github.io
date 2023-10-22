## Post #1
- Username: Spira1&He1ix
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Jun 24, 2012 11:44 pm
- Post datetime: 2012-11-01T11:58:36+00:00
- Post Title: WarFrame close beta link,anyone help me rip 3d model?

Here:[http://www.mediafire.com/download.php?c52ugaboxrd4234](http://www.mediafire.com/download.php?c52ugaboxrd4234)
Sorry i'm not at home so there aren't a sample just the link.Thank a lot
## Post #2
- Username: Spira1&He1ix
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Jun 24, 2012 11:44 pm
- Post datetime: 2012-11-05T04:16:50+00:00
- Post Title: WarFrame close beta link,anyone help me rip 3d model?

Anyone? Here's game information: [https://warframe.com](https://warframe.com)
## Post #3
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2013-01-14T14:00:18+00:00
- Post Title: WarFrame close beta link,anyone help me rip 3d model?

downloaded it on lunch, will post packages later. I can see that there is a archive file and a .loc file together that specifies a filelist. There are .fbx, .wav, .dds and other stuff showing in there
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-01-15T12:50:53+00:00
- Post Title: WarFrame close beta link,anyone help me rip 3d model?

the archives look like it might be a custom compression of lzss
the compressions that come close in quickbms are
229  *
160  *
230  *
the archive format is
8 bytes header
loop till end of file (
offset long long
hash long long
zip size long
size long
null long
path depth long
0x40 - name / path
)
if data is ff then its directory
## Post #5
- Username: Maxunit
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 28, 2010 7:49 am
- Post datetime: 2013-01-16T03:07:46+00:00
- Post Title: WarFrame close beta link,anyone help me rip 3d model?

I'm no expert on digging into the files, figuring out encryption methods etc pp, but my guess is:

The files are LZMA Encrypted. A custom compression of lzma maybe as well?
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-01-16T11:43:40+00:00
- Post Title: WarFrame close beta link,anyone help me rip 3d model?

I do not think its encrypted a lot of files have plain readable text.
it reminds me of lzss or lz01x
## Post #7
- Username: Maxunit
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 28, 2010 7:49 am
- Post datetime: 2013-01-16T12:25:06+00:00
- Post Title: WarFrame close beta link,anyone help me rip 3d model?

I'm sniffing around in the actual client files now, but I'm not sure, how much info I can post or not without getting into trouble :/ Closed Beta, EULA and stuff...
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-01-16T18:27:22+00:00
- Post Title: WarFrame close beta link,anyone help me rip 3d model?

The only thing unknown is the compression routine.
once that Is posted the format is done.
I am not really interesting in the game just looked at the files to help out.
Just post what you feel you can if you think it will move the thread forward.
## Post #9
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2013-01-27T23:28:18+00:00
- Post Title: WarFrame close beta link,anyone help me rip 3d model?

seem to have some decent models inside and I think I saw .fbx and .x when snooping in hex
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-20T16:11:38+00:00
- Post Title: WarFrame close beta link,anyone help me rip 3d model?

Script for unpack archives [here](http://forum.xentax.com/viewtopic.php?p=65826#p65826)
## Post #11
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2013-02-23T13:01:46+00:00
- Post Title: WarFrame close beta link,anyone help me rip 3d model?

> Reply from Ekey
>
> Script for unpack archives here

This game uses evolution engine like darkness 2 and dark serctor, unfortunately the script doesent work properly for this game. 
I'm mainly interested to extract the textures but the extracted ones are not valid. Probably they changed something.
I used quickbms 0.5.6 and the latest version with the same result.

EDIT: i read the the all post , it seems there is the same problem with darkness 2 tex.
