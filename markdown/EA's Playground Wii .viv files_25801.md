## Post #1
- Username: ampharos2pt0
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 05, 2019 9:04 am
- Post datetime: 2022-09-13T05:00:09+00:00
- Post Title: EA's Playground Wii .viv files

For EA Playground, all of the files are compressed in viv(no surprise there, its EA's fav format), which are unpacked just fine initially.
However, inside, there are more viv archives, containing stuff like maps/audio/characters.
I've tried all the viv extractors I could find, but these internal files are slightly different from other viv files and never decompress.
(It appears that it has the BIGF header just like others)

Internal file in question is linked below:
[https://mega.nz/file/8IQ3RaiI#YEp8MnUOq ... XLjTUVyN0k](https://mega.nz/file/8IQ3RaiI#YEp8MnUOqhPK6ed4MW-scH6T6SrkTjg_xXLjTUVyN0k)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-09-16T20:57:56+00:00
- Post Title: EA's Playground Wii .viv files

This VIV archive is compressed with Refpack.
You can use C&C3 file decompressor to decompress [https://cncguild.net/item-133](https://cncguild.net/item-133)

More info here [http://wiki.xentax.com/index.php/List_o ... algorithms](http://wiki.xentax.com/index.php/List_of_compression_algorithms)
and here [http://wiki.xentax.com/index.php/EA_BIG_BIGF_Archive](http://wiki.xentax.com/index.php/EA_BIG_BIGF_Archive)


Then you can unpack it with this script I made
[https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/EA%27s%20Playground/EA_Playground_Wii_BIG_VIV_script.bms)

and quickbms [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)


This file format seems to be different than BIGF archives I've seen before. It has mixed up big endian and litte endian threebyte fields,
so it's hard to fully support it without more samples...
## Post #3
- Username: ampharos2pt0
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 05, 2019 9:04 am
- Post datetime: 2022-10-05T03:40:55+00:00
- Post Title: EA's Playground Wii .viv files

Yup, I've been using the Refpack bms script to decompress some of the files.
I've linked below the characters archive(where the above file came from), minigame maps/objects, and the hub world map file, which can be extracted with aptly named "BIG File Extractor".
It seems the world data is a mix of csv and .o files, not sure what to make of that. Hopefully it's more content to sample...

[https://mega.nz/folder/8MRiEBiI#MIaZdvdJRhClpfWjC6QI4w](https://mega.nz/folder/8MRiEBiI#MIaZdvdJRhClpfWjC6QI4w)
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-10-06T19:48:26+00:00
- Post Title: EA's Playground Wii .viv files

Yes, those new samples were very helpful. It appears that main issue was that I was using C&C3 file decompressor, which was not a very good choice. Files were decompressed in a wrong way, so I was analyzing file format of corrupted files...   

Anyway, here is updated script
[https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/EA%27s%20Playground/EA_Playground_Wii_BIG_VIV_script.bms)
I've tested it with all samples from "characters.viv" and it worked with all of them.


So here is what you should do to achieve the same result:
1. Download BigGUI [https://forums.nba-live.com/downloads.p ... l&df_id=14](https://forums.nba-live.com/downloads.php?view=detail&df_id=14)
2. Open characters.viv in BigGUI and extract all VIV archives to separate directory 
3. Use my updated script to extract data from VIV archives (you can also use BigGUI once again)
There should by only two unpacked files per VIV archive in the output folder:



screenshot000159.png (3.42 KiB) Viewed 41 times



By the way, those *.o files seems to be ELF executable files [http://wiki.xentax.com/index.php/ELF_Executable](http://wiki.xentax.com/index.php/ELF_Executable)
while *.gsh files are EA Images [http://wiki.xentax.com/index.php/EA_SSH_FSH_Image](http://wiki.xentax.com/index.php/EA_SSH_FSH_Image)
## Post #5
- Username: ampharos2pt0
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 05, 2019 9:04 am
- Post datetime: 2022-10-08T00:50:02+00:00
- Post Title: EA's Playground Wii .viv files

What are your thoughts on the world files?
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-10-08T12:41:56+00:00
- Post Title: EA's Playground Wii .viv files

What do you mean?

World.big is a BIGF archive. You can open it in BigGUI.

It contains only *.CSV and *.O files. 
*.CSV can be opened with Notepad++ or Microsoft Excel.
*.O file is an ELF executable (more info on the wiki, I've already linked the article in my previous post).
