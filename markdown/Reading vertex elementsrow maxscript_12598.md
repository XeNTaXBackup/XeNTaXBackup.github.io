## Post #1
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2015-02-13T03:00:00+00:00
- Post Title: Reading vertex elements/row maxscript

Hi guys, I`m currently rebuilding my Battlefield 3 mesh script. I`m hitting a wall when I come to reading elements from vertex row

So say I have vertex stride of 48 bytes, I have element positions ie 
```
(0,6,12,16,20,26,32,40)
```
, and usage map 
```
(pos,bisign,normal,tangent,texcoord0,texcoord1,boneindex, boneweights)
```
. Only "pos" is static and the rest of elements change positions from model to model. What would be a common approach to reading and storing the data?


Thanks guys
