## Post #1
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-01-26T20:51:29+00:00
- Post Title: VALIANT and ARGO

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-26T21:54:51+00:00
- Post Title: VALIANT and ARGO

file103.data2 and file104.data2 are a sequence of zlib compressed blocks (no header or file structure/informations), so stuff for offzip and similar tools

while the xbin file is not much clear, it's chaotic
## Post #3
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-01-26T21:57:34+00:00
- Post Title: VALIANT and ARGO

ok, havent used offzip much but will see what I can find, thanks. I will let you know if I need more guidance
## Post #4
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-01-26T22:18:30+00:00
- Post Title: VALIANT and ARGO

Ok, I used the command:

offzip -s file000.data2 extracted 0 and got:

0x000B5A68

1 valid zip block found

On the second file file000.data2 i get:

0x0018438a

Should this say something?  I have no clue what to do next
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-26T23:01:22+00:00
- Post Title: VALIANT and ARGO

offzip -a file000.data2 c:\folder 0

as already said the files have no header/name so you must watch their content.
maybe the header is in the other (index) files, anyway that's the max I can do in this moment
