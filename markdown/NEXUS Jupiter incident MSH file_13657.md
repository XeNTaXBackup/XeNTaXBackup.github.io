## Post #1
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2015-12-11T18:35:39+00:00
- Post Title: NEXUS Jupiter incident MSH file

Let theese be revealed.  

A maxscript to import everything but the animations from msh file.

What does this little thingy do?

    Import mesh with LODs and layer them
    Import material colors
    It also create some sort of summary mesh (the ones named *_unkmesh), they seem to have UVs as well.
    Import parameters like attachments for guns, docking lines, boosters (More info in "NEXUS Modding Documentation" chapter 2.7.1) as points and splines. Theese are stored in "Parameters" Layer and are hidden by default.

On some models tool may create artifacted meshes, these seems to have no impact on data or mesh loss.

Since I wrote it in maxscript, loading some large files (1MB+) may take a few seconds to load. But your CPUs are surely better than mine.   

Sample Image:

[NEXUS (MSH).zip](https://xentaxbackup.github.io/file/10139_NEXUS (MSH).zip)
