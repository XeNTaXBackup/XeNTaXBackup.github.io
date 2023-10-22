## Post #1
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-03-25T15:01:25+00:00
- Post Title: Cave Story Wii Files.

All right, this should be the last one for a while. This one consists of various types of files contained in the internal data of Cave Story for Wii.
The files contained here are...
".pxa"
".pxe"
".pxm"
".tsc"
".pbm"
".bmp" (Mind you these are not standard BMPs, they are encrypted in some way.)
".ogg" (Included for sentiment purposes.)
".midi" (Also included for sentiment purposes.)
".xm" (Same as above.)
".org"

Now. Before you get all out of shape because of all the different file types, I'll tell you the only files I'm interested in are the ".pbm" and the ".bmp" files. If someone could quickly figure these out for me it'd be most helpful, and of course, I will make a note of possible reward for the future.

Below are the files in a folder in a zip file. Follow the download link and extract as usual.
[http://www.sendspace.com/file/kfu5sv](http://www.sendspace.com/file/kfu5sv)
## Post #2
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-03-25T20:18:41+00:00
- Post Title: Cave Story Wii Files.

Sorry to double post, but I had a few more files that could be experimented on if one wished to do so.
In the following ZIP file is all the ".bmp" and ".pbm" files in the game's directory, for those of you who would like to compare them with each other.

[http://www.sendspace.com/file/mgtx5x](http://www.sendspace.com/file/mgtx5x)

Once again these are the only ones that really interest me.
## Post #3
- Username: EldritchDecross
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 27, 2010 10:39 am
- Post datetime: 2010-03-29T00:29:49+00:00
- Post Title: Cave Story Wii Files.

Actually I'm looking for the 'solution' to these files as well. Is there anyone who can help us out?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-03-29T00:51:36+00:00
- Post Title: Cave Story Wii Files.

quickbms script

```
get name BASENAME
string name + "_ext."
get name1 extension
string name + name1
get size long
get zsize asize
math zsize -= 4
savepos offset
comtype lz77wii
clog name 0 zsize zsize


```


seems like the creators of the wii game used modding tools for it?
[http://www.miraigamer.net/cavestory/downloads_1.php](http://www.miraigamer.net/cavestory/downloads_1.php)
[NpcBallos_ext.bmp](https://xentaxbackup.github.io/file/2896_NpcBallos_ext.bmp)
## Post #5
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-03-29T12:45:41+00:00
- Post Title: Cave Story Wii Files.

Hum...seems the script has a few errors relating to the recent updated images.  One such example is the "NPCRavil_detail.bmp".
What I'm trying to do is extract the updated sprites.
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-03-29T21:00:25+00:00
- Post Title: Cave Story Wii Files.

problem fixed.

> get name BASENAME
>
> string name + "_ext."
>
> get name1 extension
>
> string name + name1
>
> get zsize asize
>
> comtype lz77wii
>
> clog name 0 zsize zsize
[NpcRavil_detail_ext.bmp](https://xentaxbackup.github.io/file/2899_NpcRavil_detail_ext.bmp)
