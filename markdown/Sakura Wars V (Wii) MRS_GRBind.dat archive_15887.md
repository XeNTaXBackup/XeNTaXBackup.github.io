## Post #1
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2017-02-17T13:25:23+00:00
- Post Title: Sakura Wars V (Wii) MRS_GRBind.dat archive

I found a file called MRS_GRBind.DAT And i was thinking that this could be the file that has the models. I took a look at it through a hex editor and saw that there are HMDL (model), and HTSF (Texture) strings. Are there any tools to decrypt this archive, and extract files from it.

Link to file - [https://mega.nz/#!epoxEbzS!EdQePDco0aiI ... mjoG-aUO4M](https://mega.nz/#!epoxEbzS!EdQePDco0aiI6jmDv5MWzRG3dsj4Pzf_8mjoG-aUO4M)
## Post #2
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-02-17T15:13:02+00:00
- Post Title: Sakura Wars V (Wii) MRS_GRBind.dat archive

There should be Header File with file names/hashes and its offsets. Also some files looks compressed.
## Post #3
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2017-02-17T16:09:19+00:00
- Post Title: Sakura Wars V (Wii) MRS_GRBind.dat archive

I see that some of the files are compressed, but  how can I decompress this .dat archive? THis file has a MPLN header.
## Post #4
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-02-17T16:14:02+00:00
- Post Title: Sakura Wars V (Wii) MRS_GRBind.dat archive

Try looking in some different files for filenames/offsets/hashes, or try find file with same name as dat, but with different extensoin.
## Post #5
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2017-02-17T16:48:25+00:00
- Post Title: Sakura Wars V (Wii) MRS_GRBind.dat archive

When I was looking through the iso, I could find some amf archives that have AMPP headers, but have the same strings (HMDL, HTSF, PVRT, HTEX) as seen in the dat archive.

[https://mega.nz/#!L5gxQRKL!kVEfbyTzYdhr ... gtqY4iQ-XQ](https://mega.nz/#!L5gxQRKL!kVEfbyTzYdhr-HMGA7emU9dEQVZwbiM9rgtqY4iQ-XQ)
