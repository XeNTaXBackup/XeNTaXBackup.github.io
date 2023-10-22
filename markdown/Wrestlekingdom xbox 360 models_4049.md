## Post #1
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2010-01-15T20:26:40+00:00
- Post Title: Wrestlekingdom xbox 360 models

Hers is an model for wrestle kingdom on the xbox 360. From looking at them in Hex workshop I believe them to be the same type of models used in SVR but in different container. Also instead of the model and the texture being in one file Here they are seperated. Can someone take a look at this and make a model/texture extractor? That would be huge because then we can remap the textures and build a pac file to be used in smackdown vs raw 2010. Thanks in advance for your time and effort
[wrestlekingdommodel.7z](https://xentaxbackup.github.io/file/2723_wrestlekingdommodel.7z)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-01-15T20:39:27+00:00
- Post Title: Wrestlekingdom xbox 360 models

the mesh file is a yobj file and my importer works fine on it if you rename it to .yobj
the dds file just has some extra bytes at the beginning.
## Post #3
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2010-01-15T21:30:04+00:00
- Post Title: Wrestlekingdom xbox 360 models

Chrrox youre the effin man. so what do i do to get rid of the extra bites?
## Post #4
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2010-01-16T15:23:45+00:00
- Post Title: Wrestlekingdom xbox 360 models

BMS Script for Wrestle Kingdom files that are packed

```
get FILES long
GoTo 0x010
for i = 0 < FILES
getdstring NAME 16 0
getdstring FILEEXT 4 0
get SIZE long 0
get OFFSET long 0
get DUMMY long 0
string NAME + . 0
string NAME + FILEEXT 0
log NAME OFFSET SIZE
next i
```
