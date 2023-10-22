## Post #1
- Username: Xendz
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Sep 03, 2011 3:25 am
- Post datetime: 2011-09-03T11:30:21+00:00
- Post Title: Bounty Hounds Online

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-09-03T23:06:25+00:00
- Post Title: Bounty Hounds Online

at a glance, each filename record is 64-bytes
clog will not work as the data is not the default compression type (deflate)

and the data has a header too (see dumps)

```
get DUMMY long
get FILES long
for i = 0 < FILES
    getdstring NAME 52 # gets 52 characters, not the ascii
    get OFFSET long
    get SIZE long
    get ZSIZE long
    log NAME OFFSET SIZE # not uncompressing
next i

```
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-09-04T00:55:40+00:00
- Post Title: Bounty Hounds Online

> clog will not work as the data is not the default compression type (deflate)

Can just change the compression type to something else using comType and then use clog.
I tried the comtype_scan2.bms on a dds file but nothing that looked like a dds file came out =/
## Post #4
- Username: Xendz
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Sep 03, 2011 3:25 am
- Post datetime: 2011-09-04T09:37:51+00:00
- Post Title: Bounty Hounds Online

Sadly I did not have any luck with that script it couldnt find any of the files? I dont really understand the compression but if anyone can explain this better that would help, or can code up a  script that works. Thanks.
## Post #5
- Username: Xendz
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Sep 03, 2011 3:25 am
- Post datetime: 2011-09-04T10:13:36+00:00
- Post Title: Bounty Hounds Online

After looking into abit more I do understand that its not working because it has a header, and i cant figure out how to get it to read the header, ive tried get HEADERSZ long .
## Post #6
- Username: Xendz
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Sep 03, 2011 3:25 am
- Post datetime: 2011-09-04T10:26:50+00:00
- Post Title: Bounty Hounds Online

still looking for a possible solution. Help is REALLY appreciated, this has been on my shoulders for awhile and would really like to get this extractor working.
