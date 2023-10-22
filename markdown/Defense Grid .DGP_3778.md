## Post #1
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2009-10-13T14:35:02+00:00
- Post Title: Defense Grid *.DGP

Hi, one simple question - is there someone who tried to get info about game files? I tried but there is any CRC and every editation makes game crash with message about damaged data. I thout that it is SHA1 or just modified value from SHA1 hash, but not sure.

Check attached 2 simple files (index data inside) and take a look on it. I think that CRC value is on last 20 bytes.


 files.rar
(345 Bytes) Downloaded 42 times
## Post #2
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2009-10-14T19:48:17+00:00
- Post Title: Defense Grid *.DGP

Hmm, no one wanna try?
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-14T22:31:08+00:00
- Post Title: Defense Grid *.DGP

*updated tool*
[dgridhash.zip](https://xentaxbackup.github.io/file/2446_dgridhash.zip)
## Post #4
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2009-10-15T07:33:24+00:00
- Post Title: Defense Grid *.DGP

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-15T07:52:02+00:00
- Post Title: Defense Grid *.DGP

ops I just noticed that instead in the full game the hash is simply xored with that special sequence of bytes without modifications to the sha1 algorithm like happens on the demo.
I will update the tool but in any case it's only a xor operation so you can do it also manually
## Post #6
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2009-10-15T08:24:51+00:00
- Post Title: Defense Grid *.DGP

oh, simple, got it  thnx for help
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-15T08:26:59+00:00
- Post Title: Defense Grid *.DGP

tool updated, check my first post
## Post #8
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2009-10-19T14:27:36+00:00
- Post Title: Defense Grid *.DGP

> Reply from aluigi
>
> tool updated, check my first post
Well, I think it doesn't work  Hash is counted ok, but writing back to file doesn't work.
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-19T15:04:29+00:00
- Post Title: Defense Grid *.DGP

uhmmm what you mean with "doesn't work"?
do you receive an error from the tool?
the output file has something strange?

how was your input file?
I mean had it already an hash (correct or wrong) at its end or just nothing?

here everything works perfectly overwriting the input file (dgridhash -o input_file input_file), so check if you have specified the correct options in case your input file doesn't have an hash at the end.
## Post #10
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2009-10-20T08:29:05+00:00
- Post Title: Defense Grid *.DGP

> Reply from aluigi
>
> uhmmm what you mean with "doesn't work"?
do you receive an error from the tool?
the output file has something strange?

how was your input file?
I mean had it already an hash (correct or wrong) at its end or just nothing?

here everything works perfectly overwriting the input file (dgridhash -o input_file input_file), so check if you have specified the correct options in case your input file doesn't have an hash at the end.

-a and -r switches are not working. Hash is never writed to file. -o seems to be working
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-20T10:02:38+00:00
- Post Title: Defense Grid *.DGP

here everything works.

for example I took data0001.dgp and copied it in another folder then I removed the 20 bytes hash at its end and then I launched:
dgridhash -a -o Z:\data0001.dgp Z:\data0001.dgp

and now the file is exactly like the original.

remember that the -o is necessary to write the file because "dgridhash file" does NOT overwrite the same file but simply calculates and shows its hash. any write operation is performed with -o
## Post #12
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2009-10-20T10:59:54+00:00
- Post Title: Defense Grid *.DGP

> Reply from aluigi
>
> remember that the -o is necessary to write the file because "dgridhash file" does NOT overwrite the same file but simply calculates and shows its hash. any write operation is performed with -o
So that's the problem, there is no info that -o switch must be provided  I just tried -a and -r + filename
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-19T20:32:59+00:00
- Post Title: Defense Grid *.DGP

I have written a bms script for the dgp files:
[http://aluigi.org/papers/bms/defense_grid.bms](http://aluigi.org/papers/bms/defense_grid.bms)

you must select only the file contains the number 0000 like data0000.dgp or enus0000.dgp (so the first dgp of the collection) because that one is the index file
