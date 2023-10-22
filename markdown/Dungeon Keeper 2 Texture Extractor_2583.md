## Post #1
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-04-12T11:34:40+00:00
- Post Title: Dungeon Keeper 2 Texture Extractor

This tool extracts all of the textures out of EngineTextures.dat.
Put it into the same directory als EngineTextures.dir and run it, that's all.
I didn't include much error handling, so there might occur some problems, but it works fine on my machine.

Doesn't work on Win9x!
[DK2TexExtractor.rar](https://xentaxbackup.github.io/file/1121_DK2TexExtractor.rar)
## Post #2
- Username: IKSLM
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 14, 2007 7:17 pm
- Post datetime: 2008-02-18T10:40:40+00:00
- Post Title: Dungeon Keeper 2 Texture Extractor

i know this is rather old but anyway. do you know how can i open/edit this textures since they seem to be in an unknown file format?

thnx!
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-18T10:48:46+00:00
- Post Title: Dungeon Keeper 2 Texture Extractor

They are compressed with an unknown compression algorithm.
I already reversed a decompression routine used in DK2's archive files -> [viewtopic.php?f=21&t=2855](http://forum.xentax.com/viewtopic.php?f=21&t=2855)
But this seems to be yet another technique.
There's a topic about that in the graphics section: [viewtopic.php?f=18&t=2580](http://forum.xentax.com/viewtopic.php?f=18&t=2580)
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-04-02T19:51:29+00:00
- Post Title: Dungeon Keeper 2 Texture Extractor

```
#MultiEx Commander MexScript
#Use in Script Window
IDString 0 "DWFB" ;
Set D Long 72 ;
GoTo D 0 ;
Get FileNum Long 0 ;
Get StringStart Long 0 ;
Get U1 Long 0 ;
Get U2 Long 0 ;
For T = 1 To FileNum ;
Get U3 Long 0 ;
Get FNO Long 0 ;
Get FNS Long 0 ;
SavePos S 0 ;
GoTo FNO 0 ;
GetDString FName FNS 0 ;
GoTo S 0 ;
Get FO Long 0 ;
Get FS Long 0 ;
SavePos S 0 ;
Math S += 20 ;
GoTo S 0 ;
Log FName FO FS 0 0 ;
Next T ;

```
