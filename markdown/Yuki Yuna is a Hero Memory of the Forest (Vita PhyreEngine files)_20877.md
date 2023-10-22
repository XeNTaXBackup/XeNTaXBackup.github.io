## Post #1
- Username: Silvris
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Jul 16, 2019 5:44 am
- Post datetime: 2019-07-30T08:12:02+00:00
- Post Title: Yuki Yuna is a Hero: Memory of the Forest (Vita PhyreEngine files)

Seeking to get the models from this game for a project I'm working on, and they seem to be regular PhyreEngine files (.pepd and .phyre). However, none of the tools I've found for these files have been able to work with them.

[https://drive.google.com/open?id=1LZKtc ... NbxiTP8s-z](https://drive.google.com/open?id=1LZKtcrvEWZXqBylUHU-BwHNbxiTP8s-z)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-07-31T07:18:29+00:00
- Post Title: Yuki Yuna is a Hero: Memory of the Forest (Vita PhyreEngine files)

format looks simple enough - using hex2obj (view links in my sig):
.



wpnmd_pc_02_001_01_lod1.dae.GXM.pepd.png (88.22 KiB) Viewed 162 times
## Post #3
- Username: Silvris
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Jul 16, 2019 5:44 am
- Post datetime: 2019-08-03T05:44:58+00:00
- Post Title: Yuki Yuna is a Hero: Memory of the Forest (Vita PhyreEngine files)

Ok, some updates. I used hex2obj to get the files I needed immediately, but I went and compared the files I had to other games using PhyreEngine. It seems like .pepd files are the same as other PhyreEngine models but with a unique header placed at the front. Removing this header let daemon's tool for Uta Kumi 575 export the files (both games are for Vita so I guess it makes sense). However doing this gets me the models without any UVs. Is it possible for me to extract the UVs separately, or does anyone know of a tool of some sort that would be able to get the mesh with UVs?
[scorpio.png](https://xentaxbackup.github.io/file/16561_scorpio.png)
