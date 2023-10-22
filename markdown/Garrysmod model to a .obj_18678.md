## Post #1
- Username: Zaczac121
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Oct 05, 2017 3:19 am
- Post datetime: 2018-08-14T04:54:13+00:00
- Post Title: Garrysmod model to a .obj

Hi, I've been wondering how would I convert this garrysmod addon I got from the Gmod website to a .obj or atleast be able to obtain the models since I cannot seem to do it on my own...

If someone can help me that would be nice

Here is the zip file containing the addon


 VC4 tonks.zip
(66.63 KiB) Downloaded 24 times
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-08-14T12:44:15+00:00
- Post Title: Garrysmod model to a .obj

Decompress the txt file with the following BMS comands:

```
goto 0xB
getct STR string 0x1
string STR s "%d" Zsize
for i = 0 < 9
	getct STR string 0x1
next i
goto 0x7 0 SEEK_CUR
savepos Offset
comtype LZMA_86HEAD
goto 5 0 SEEK_CUR
get Size long
get Name basename
string Name + ".dcp"
clog Name Offset Zsize Size

```
## Post #3
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2018-08-14T12:51:21+00:00
- Post Title: Garrysmod model to a .obj

Where did you find this? These are not model files.
## Post #4
- Username: Zaczac121
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Oct 05, 2017 3:19 am
- Post datetime: 2018-08-14T21:41:12+00:00
- Post Title: Garrysmod model to a .obj

How would I decompress the txt...? Using what program is what I need since idk too much about BMS stuff

Also here is where I got it from [https://garrysmods.org/download/60775/a ... nicles-duo](https://garrysmods.org/download/60775/acf-valkyria-chronicles-duo)
## Post #5
- Username: Zaczac121
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Oct 05, 2017 3:19 am
- Post datetime: 2018-08-14T21:49:49+00:00
- Post Title: Garrysmod model to a .obj

Nvm I decompressed it but how do I open the .dcp in blender?
## Post #6
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2018-08-15T10:02:26+00:00
- Post Title: Garrysmod model to a .obj

These are not models. They are pseudo-models created using the Gmod building system. I do not know if you can translate this out of the engine.
