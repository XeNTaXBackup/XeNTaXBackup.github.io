## Post #1
- Username: danu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 06, 2009 12:00 pm
- Post datetime: 2009-01-09T20:01:01+00:00
- Post Title: utx file from lineage 2

Hello everyone, this is my first post. I am asking for help to decript a utx file from lineage 2. Normally we can just patch it using utx fixer released by dstuff

CT2 utxfixer
[http://www.l2wh.com/down](http://www.l2wh.com/down)
and after we patch we can see using unreal editor

utx file  killerpanda.utx (1.33 MB) 

Download Link: [http://www.filesend.net/download.php?f= ... ed34baa186](http://www.filesend.net/download.php?f=ca08b8feb1746b0209d135ed34baa186)

but this file said its not in lineage 2 format.
Any help to see this file and to redo the special encription will be appriciated 

thx,
danu
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-02-09T16:28:03+00:00
- Post Title: utx file from lineage 2

take a hex editor and substituite the first 16 bytes with the following:

```
4c 00 69 00 6e 00 65 00 61 00 67 00 65 00 32 00   L.i.n.e.a.g.e.2.
```
it will be decrypted BUT I think that the encryption key is changed from the original one of Lineage 2 so this is useless.
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2009-07-05T13:18:04+00:00
- Post Title: utx file from lineage 2

> Reply from Bugtest
>
> take a hex editor and substituite the first 16 bytes with the following:
Code: Select all4c 00 69 00 6e 00 65 00 61 00 67 00 65 00 32 00   L.i.n.e.a.g.e.2.it will be decrypted BUT I think that the encryption key is changed from the original one of Lineage 2 so this is useless.
well i think is not good used L2UTX fixer is a nice tool but you can do it with other tool name L2VIEW UTX hope help you 

PD: file pandakiller is protected for avoid ppl get work of server make good work i think need modify code for work good but im not sure need investigate more about this i want protect my work too but only have a tool for my .dat files
## Post #4
- Username: potemkis
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Mar 01, 2009 2:11 pm
- Post datetime: 2009-10-03T06:58:19+00:00
- Post Title: utx file from lineage 2

You can actually use some of the tools that can edit UT2k3/UT2k4 texture files to convert them to .tga/.dds. From there, you need to open them in Photoshop in order to use them in 3ds max.
