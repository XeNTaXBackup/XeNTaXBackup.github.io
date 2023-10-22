## Post #1
- Username: 0xdeadbeef
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Feb 01, 2016 7:34 am
- Post datetime: 2018-08-04T23:07:07+00:00
- Post Title: Spellforce: The Order of Dawn / BoW / SotP Expansions

Hi

I am sharing some old but newly updated Python tools for exploring the data in Spellforce: The Order of Dawn.  The Breath of Winter and Shadow of the Phoenix expansions are also supported.  These tools were not made for editing, but instead to speed up the process of reverse-engineering.  The focus is on showing as much of the data as possible.  Therefore the user interface is quite simplistic.

As I have recently returned to this project for fun, I will be uploading updated versions here quite frequently for a while.  One of the members here expressed interest in the tools, so I decided to share them with everyone else too.

Dependencies are PyQt5, including Data Visualization for extremely simplistic 3D terrain visualization, and PIL for DDS textures:

```
pip3 install PyQtDataVisualization
pip3 install Pillow

```


Edit common.py to point to your Spellforce installation, then simply execute python main.py

Let me know in this thread if you find bugs or solve any unknown data. Thanks!  Note that the sound player is crashy on Windows (QMediaPlayer... sigh), and the backend for mesh preview only works for The Order of Dawn meshes at the moment.

History:
8 Aug 18: Second upload, forgot to include shaders
8 Aug 18: Initial upload
[Spellforce050818_2.7z](https://xentaxbackup.github.io/file/14707_Spellforce050818_2.7z)
