## Post #1
- Username: Star Raider
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 11, 2012 1:04 am
- Post datetime: 2012-02-10T17:13:01+00:00
- Post Title: Star Killer KaminoTwo Model GTO to OBJ Request

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2012-02-10T18:00:26+00:00
- Post Title: Star Killer KaminoTwo Model GTO to OBJ Request

Just rename the file playerkaminotwo.gto to playerkaminotwo.rar and extract the file and you will be able
to open the model file with noesis (dont forget to rename agian to .gto).
## Post #3
- Username: Star Raider
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 11, 2012 1:04 am
- Post datetime: 2012-02-10T18:43:40+00:00
- Post Title: Star Killer KaminoTwo Model GTO to OBJ Request

I have the .OBJ, But every time I load it into 3ds Max I get this error, "ERROR - invalid normal index"

I have also made sure that my regional settings are all "." and not ","..

Any suggestions?
## Post #4
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-02-10T22:07:35+00:00
- Post Title: Star Killer KaminoTwo Model GTO to OBJ Request

> Reply from Star Raider
>
> I have the .OBJ, But every time I load it into 3ds Max I get this error, "ERROR - invalid normal index"

I have also made sure that my regional settings are all "." and not ","..

Any suggestions?

I found this problem of normals with max obj even me. Probably because not all the vertexs are jointed in  each 3d mesh, so this may case some normal problems in max. There a re some methods to fix it but it' too long to explain...and i prefer working with cinema4d, which have not this problems. Anyway u can export the model in .dae format instead of obj or another format u wish.
So u should solve the problem. ( dae support even the bones and weights ).
Remember to use collada import plugin for max to import correctly the .dae format ( not the default import plugin).
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-10T22:41:16+00:00
- Post Title: Star Killer KaminoTwo Model GTO to OBJ Request

Post your OBJ file that you're trying to load so we can see what problem you are having with it.

I don't know if the tool comes with source or anything, but I took a quick glance at the (uncompressed) gto file and it looks pretty simple to rewrite a mesh exporter. But I'll need more samples to compare in case there are different types (MU died so those links are gone)
## Post #6
- Username: Star Raider
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 11, 2012 1:04 am
- Post datetime: 2012-02-10T22:57:41+00:00
- Post Title: Star Killer KaminoTwo Model GTO to OBJ Request

I got it working!! , I just changed a setting in 3ds Max to Auto and it imported the model perfectly, exported to Maya and Textured with original textures... Works perfect!
## Post #7
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-02-11T10:49:38+00:00
- Post Title: Star Killer KaminoTwo Model GTO to OBJ Request

The contents of this post was deleted because of possible forum rules violation.
