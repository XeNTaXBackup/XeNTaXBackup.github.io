## Post #1
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2016-10-04T03:43:47+00:00
- Post Title: [PSVita] Trillion: God of Destruction .ism2 file help?

Hello! I've tried to open the ism2 file from Trillion with previous scripts for this file format, but none of them work. I guess Compile Heart decided to mess with the ism2 file again. lol. If anyone could help figure out this format it'd be great! The models seem to look a lot like the Mugen Souls games, and there are quite a few nice character designs. The TID files can be extracted using nr1_tidtool.exe

```
Sample: https://mega.nz/#!mo1DBTAL!5o82OBhUOB9lGP4UyAKct0ZNetiHBdrGO0pxv7ZRa4c
```
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-10-07T21:04:18+00:00
- Post Title: [PSVita] Trillion: God of Destruction .ism2 file help?

there's some bytes/floats between the face indices (FIs) to be skipped
so a script is useful here:



pc01-ism2.jpg (154.78 KiB) Viewed 149 times


(not sure about UV pos, there might be additional data between tx and ty; [viewtopic.php?f=16&t=12753&hilit=ism2](http://forum.xentax.com/viewtopic.php?f=16&t=12753&hilit=ism2))

At address 0x91C7C: FI count for 2nd submesh: 0x3B4= 948
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-10-07T21:51:58+00:00
- Post Title: [PSVita] Trillion: God of Destruction .ism2 file help?

using R.T.Bush's max script with a small change:



ism2_pc01.JPG (99.72 KiB) Viewed 145 times

(if vertexstuff1== 0x03 disabled by replacing the 03 by 13)
## Post #4
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2016-10-10T07:58:51+00:00
- Post Title: [PSVita] Trillion: God of Destruction .ism2 file help?

I've added proper support for the models from Trillion to my MaxScript now.
[https://mega.nz/#!nlQAAK4S!KtUqFVFcaJD0 ... nwsCDesAwU](https://mega.nz/#!nlQAAK4S!KtUqFVFcaJD0oV5g14o4PpeVwIkLIPVBqnwsCDesAwU)

What was causing the script to crash was because it had a different vertex buffer size instead for the rigging information (0x10 for half-floats instead of 0x20), which is what shakotay2 had essentially commented out in the post above. I added a check for that so now it imports those correctly, everything else for the model format was the same (thankfully).
## Post #5
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2016-10-11T22:12:22+00:00
- Post Title: [PSVita] Trillion: God of Destruction .ism2 file help?

Sweet! Thanks!
