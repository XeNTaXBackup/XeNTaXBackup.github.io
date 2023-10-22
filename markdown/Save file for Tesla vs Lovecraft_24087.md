## Post #1
- Username: mortalis
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jun 27, 2020 3:50 am
- Post datetime: 2021-06-20T20:22:48+00:00
- Post Title: Save file for Tesla vs Lovecraft

Hi.
Could someone help me to determine the encryption type of the profile files in the game
Tesla vs Lovecraft v1.0.7 by 10tons (Windows version)?

There are 2 files in the AppData\Roaming\10tons\Tesla_vs_Lovecraft\profiles\ folder:
- 0.xml
- index.xml

As I investigated, the "index.xml" stores some settings
and the "0.xml" has all the levels info, some other settings, progress...

They have the "10TONS_SECRET" header and I tried to open them as ZIP files (with and without the "10TONS_SECRET" header)
with no result.

I think they should be real XML files but encoded in some manner.
Tried the Memory View of the Cheat Engine tool (searching for "index.xml" for example) but for me it's hard to figure out what XML entries could be stored in the file (maybe it's impossible since the RAM storage isn't sequential...).

The files I attach correspond to the Windowed mode 1366x768 (set in Options -> Display),
the last unlocked level is "Maw of Darkness" (18th from the start),
there are 9 crystals collected.

Thanks.
[profiles.zip](https://xentaxbackup.github.io/file/20342_profiles.zip)
## Post #2
- Username: mortalis
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-23T10:23:38+00:00
- Post Title: Save file for Tesla vs Lovecraft

Hi, you can use this tool to decrypt files
[https://github.com/bartlomiejduda/Tools ... ML_Tool.py](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/10tons%20games/10tons_XML_Tool.py)

Check also wiki article about this file format
[http://wiki.xentax.com/index.php/10tons_XML](http://wiki.xentax.com/index.php/10tons_XML)
