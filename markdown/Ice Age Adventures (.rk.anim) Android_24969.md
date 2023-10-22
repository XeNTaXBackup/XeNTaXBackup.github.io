## Post #1
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-01-19T20:50:14+00:00
- Post Title: Ice Age Adventures (.rk/.anim) Android

I made a plugin for Noesis which opens (.rk) models.
Game archive (.ark) unpacked using this [qbms script](https://forum.xentax.com/viewtopic.php?f=10&t=21242&p=157564&hilit=ice+age#p157564).
now i want to add animation (.anim)

```
int ver1//(always 6)
int ver2//(always 3)
name 64 bytes
int bone_count
int frame_count
int unk//(always 4)
int framerate?
anim Data...

```


sizeData/frame_count/bone_count = 11bytes for bone in frame?
anim in game:

EDIT: update plugin [fmt_rk(Ice_Age).py](https://github.com/Durik256/Noesis-Plugins/blob/master/fmt_rk%28Ice_Age%29.py)
[file.zip](https://xentaxbackup.github.io/file/21671_file.zip)
