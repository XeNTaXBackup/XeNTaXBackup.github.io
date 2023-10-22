## Post #1
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-10-27T16:26:22+00:00
- Post Title: PSP fac&fah files

Hi 
I need help  unpacking fac&fah files from PSP Sunday VS Magazine Shuuketsu! Choujou Daikessen.
Here is the sample cut file of sxm.fac & sxm.fah file.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-10-27T22:00:36+00:00
- Post Title: PSP fac&fah files

no filenames

```
open FDDE fac 1

idstring "FARC"
get DUMMY long # 256
get FILES long
get DUMMY long

for f = 0 < FILES
  get OFFSET long
  get SIZE long
  get DUMMY long
  get DUMMY long
  log "" OFFSET SIZE 1
next f

```
