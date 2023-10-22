## Post #1
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-02-08T03:00:05+00:00
- Post Title: Help with AdvUtil.exe in Art of Murder 2

I found a tool AdvUtil.exe  in Art of Murder 2 demo.
I can unpack .vbf with gobread and i think AdvUtil.exe is a pack tool which developed by game team .
Anyone can find out how to use this tool?

Art of Murder 2 demo is here.
[http://www.city-interactive2.home.pl/AO ... OM2_PL.zip](http://www.city-interactive2.home.pl/AOM/demo_AOM2_PL.zip)
[AdvUtil.rar](https://xentaxbackup.github.io/file/1863_AdvUtil.rar)
## Post #2
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-06-04T16:42:06+00:00
- Post Title: Help with AdvUtil.exe in Art of Murder 2

I tried the advutil.exe.
First of all, that needs three .dll files, that can be found in the game demo's "player" folder:
CK2.dll, CKZlib.dll and VxMath.dll.


Updated:
Here is a tiny .VBF maker/extractor/updater proggy.
(Originally I made it for the Syberia2 game, which uses the same archive format, without the Hash calculations.)
## Post #3
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-06-05T02:39:38+00:00
- Post Title: Help with AdvUtil.exe in Art of Murder 2

> Reply from bacter
>
> I tried the advutil.exe.
First of all, that needs three .dll files, that can be found in the game demo's "player" folder:
CK2.dll, CKZlib.dll and VxMath.dll.


Updated:
Here is a tiny .VBF maker/extractor/updater proggy.
(Originally I made it for the Syberia2 game, which uses the same archive format, without the Hash calculations.)

Very thanks!
## Post #4
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-06-05T03:36:35+00:00
- Post Title: Help with AdvUtil.exe in Art of Murder 2

Some unimportant information:

The game, and the AdvUtil uses the SHA1 Hash calculation to store the filenames.
(The SHA1 hash is 40 hexadecimal chars, but the game uses only the first 24 chars)
Before the calculation, always convert the filenames to low case letters.

ca82098eb099526814ea0632b178a82335d55e50.cmo => the original name was: game.cmo
c518ea690e5a100db13e143d.ogg => original name:  resources\music\ogg\danger_01.ogg
c4198040b69d49cb5b53e48f.png => original name: data\locations\l00_system\l00_0005_hurry\hurry.png
## Post #5
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-06-05T08:22:56+00:00
- Post Title: Help with AdvUtil.exe in Art of Murder 2

Some advice , i think a command line tool is more useful ,because if i made some language patch ,i must release the unpacker/packer too, if the tools is command line,the player just need to execute some .bat file.

Thanks again.
## Post #6
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-06-05T18:30:48+00:00
- Post Title: Help with AdvUtil.exe in Art of Murder 2

O.K. Here is the command line version of the program!
## Post #7
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-06-07T00:00:23+00:00
- Post Title: Help with AdvUtil.exe in Art of Murder 2

> Reply from bacter
>
> O.K. Here is the command line version of the program! 

Updated:
I discovered, that the game can handle the patch files, so you don't need to replace the lots of files singly!
The solution is to make new .vbf files with _p1 on the end of their names. For example:
data_p1.vbf for the data.vbf, resources_p1.vbf for the resources.vbf and so on.

Wow! Very thanks, also for your useful information!
Continue your good work , please.
## Post #8
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-03T00:46:29+00:00
- Post Title: Help with AdvUtil.exe in Art of Murder 2

> Reply from bacter
>
> Some unimportant information:

The game, and the AdvUtil uses the SHA1 Hash calculation to store the filenames.
(The SHA1 hash is 40 hexadecimal chars, but the game uses only the first 24 chars)
Before the calculation, always convert the filenames to low case letters.

ca82098eb099526814ea0632b178a82335d55e50.cmo => the original name was: game.cmo
c518ea690e5a100db13e143d.ogg => original name:  resources\music\ogg\danger_01.ogg
c4198040b69d49cb5b53e48f.png => original name: data\locations\l00_system\l00_0005_hurry\hurry.png
Sorry to necro-post but I find this information very interesting as none of the posted programs retrieves the original filenames! How can I rename the files with QuickBMS? Thanks in advance!
## Post #9
- Username: mikehood
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Jun 20, 2006 1:45 pm
- Post datetime: 2010-10-18T10:40:03+00:00
- Post Title: Help with AdvUtil.exe in Art of Murder 2

convert hash(sha1) to text is almost impossible and i don't know "bacter" how discovered it with 3 examples.
please explain and\or say examples for a dlg file 

thanks
