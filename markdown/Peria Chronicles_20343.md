## Post #1
- Username: Mrtest
- Rank: advanced
- Number of posts: 43
- Joined date: Wed Aug 24, 2011 3:11 am
- Post datetime: 2019-05-07T23:09:40+00:00
- Post Title: Peria Chronicles

Need help to extracting all meshes. 3D Model Researcher working fine, but need batch script. 
Sample: [https://yadi.sk/d/o7MxUJnr0xKaPQ](https://yadi.sk/d/o7MxUJnr0xKaPQ)
## Post #2
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-05-08T10:52:24+00:00
- Post Title: Peria Chronicles

I will take a look when I get back tonight. Currently working on another project, but I can do this after that.

In the meantime can you post some model researcher screenshots, if you have extracted anything? At least it would save some time on research.
## Post #3
- Username: Mrtest
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-05-08T22:15:16+00:00
- Post Title: Peria Chronicles

```
#http://aluigi.altervista.org/quickbms.htm
#by chrrox
get TPK basename
string TPK R ".tpk" ""
set TBL TPK
set REP TPK
string TPK + ".tpk"
string TBL + ".tpk.table"
open FDSE TBL
open FDSE TPK 1 
get FILES long
get NULL long
for i = 0 < files
get NSIZE long
getdstring NULL 6
math NSIZE - 1
getdstring NAME NSIZE
string NAME R "cache" REP
string NAME + ".TARC"
get OFFSET long
get SIZE long
log NAME OFFSET SIZE 1
next i
```
## Post #4
- Username: Mrtest
- Rank: advanced
- Number of posts: 43
- Joined date: Wed Aug 24, 2011 3:11 am
- Post datetime: 2019-05-08T23:42:32+00:00
- Post Title: Peria Chronicles

> Reply from akderebur ↑Wed May 08, 2019 6:52 pm at Wed May 08, 2019 6:52 pm
>
> 
I will take a look when I get back tonight. Currently working on another project, but I can do this after that.

In the meantime can you post some model researcher screenshots, if you have extracted anything? At least it would save some time on research.
[https://imgur.com/a/Z8g9oVw](https://imgur.com/a/Z8g9oVw)
file: [https://yadi.sk/d/B4xJCF8AMRjg8A](https://yadi.sk/d/B4xJCF8AMRjg8A)
(full client downloader: [https://yadi.sk/d/e-xXMnP9GF12kQ](https://yadi.sk/d/e-xXMnP9GF12kQ))

> Reply from chrrox ↑Thu May 09, 2019 6:15 am at Thu May 09, 2019 6:15 am
>
> 
Code: Select all#Peria Chronicles quickbms script
#http://aluigi.altervista.org/quickbms.htm
#by chrrox
get TPK basename
string TPK R ".tpk" ""
set TBL TPK
set REP TPK
string TPK + ".tpk"
string TBL + ".tpk.table"
open FDSE TBL
open FDSE TPK 1 
get FILES long
get NULL long
for i = 0 < files
get NSIZE long
getdstring NULL 6
math NSIZE - 1
getdstring NAME NSIZE
string NAME R "cache" REP
string NAME + ".TARC"
get OFFSET long
get SIZE long
log NAME OFFSET SIZE 1
next i
thx!
## Post #5
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-05-09T08:27:53+00:00
- Post Title: Peria Chronicles

Weird format, especially faces. You first need to reorder the vertices with an index list, then there is another index list for actual triangles. I don't really get the point of that. Here is a face mesh extracted.



I can probably make a tool, but need to investigate a bit more. I will start with extracting static meshes, and will continue with skinned if I I have the time.
