## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-29T17:57:37+00:00
- Post Title: Fatal Action Zero

Textured meshes only.
Some of the textures are wrong too (not sure how it is stored, I assumed first entry is diffuse tex and second entry is normal...)


Unpacker

```

idstring "LARC"
get FILES long
for i = 0 < FILES
  get len short
  getdstring NAME len
  get SIZE long
  get OFFSET long
  
  putarray 0 i NAME
  putarray 1 i SIZE
  putarray 2 i OFFSET
next i

savepos DAT_START
for i = 0 < FILES
  getarray NAME 0 i
  getarray SIZE 1 i
  getarray OFFSET 2 i
  
  math OFFSET += DAT_START
  log NAME OFFSET SIZE
next i

```
## Post #2
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-08-30T01:15:22+00:00
- Post Title: Fatal Action Zero

Amazing Finale good work really.
