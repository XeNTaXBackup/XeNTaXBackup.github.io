## Post #1
- Username: pioneer
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Jan 25, 2010 10:28 pm
- Post datetime: 2011-10-22T19:09:33+00:00
- Post Title: Ninja storm 2 .bnsf/.xma sound files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-10-23T08:15:47+00:00
- Post Title: Ninja storm 2 .bnsf/.xma sound files

The PS3 version seems to work fine for me in vgmstream as far back as r931, make sure you're getting a recent version from [http://hcs64.com/files/vgmstream/](http://hcs64.com/files/vgmstream/)

The XMA starts at 0x100, you can extract this either with
```
xma_test infile.xma -o 0x100 -r outfile.xma
```
 (xma_test is in xma_parse at [http://hcs64.com/vgm_ripping.html](http://hcs64.com/vgm_ripping.html)) or just cutting off the first 0x100 bytes.  Then prepend a mono header (such as [http://hcs64.com/files/xma_header_mono.zip](http://hcs64.com/files/xma_header_mono.zip)) and it should covert ok with towav.


I AM INVINCIBLE!
## Post #3
- Username: pioneer
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Jan 25, 2010 10:28 pm
- Post datetime: 2011-10-23T13:23:23+00:00
- Post Title: Ninja storm 2 .bnsf/.xma sound files

Trying test.exe did convert them into playable .wav. Strange that the winamp plugin wouldn't work for me

Thanks for the answer on how to convert both
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-10-23T22:51:47+00:00
- Post Title: Ninja storm 2 .bnsf/.xma sound files

It's probably just that these sounds are all very short, and the output plugin (or maybe the vgmstream plugin's interface with the output plugin?) didn't handle < 1 second files very well.
