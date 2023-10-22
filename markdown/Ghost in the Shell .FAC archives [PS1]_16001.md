## Post #1
- Username: Triangle90
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Oct 29, 2013 4:32 pm
- Post datetime: 2017-03-15T10:03:59+00:00
- Post Title: Ghost in the Shell .FAC archives [PS1]

So I've been following some QuickBMS tutorials to get these .FAC archives extracted, but I haven't had any success so far due to not having enough information. They store .CLT, .VX1, .XS3, .GRD, .M01, .PM1, .LX2, .BCF, .EA3, .SO3 and .CB4 files despite the small size. Could someone please write a BMS script or at least provide me with some hints/ examples on how to write one for these archives? Sample files are attached.

[https://www.mediafire.com/?n16oxccwz9wfxwb](https://www.mediafire.com/?n16oxccwz9wfxwb)
[fac.zip](https://xentaxbackup.github.io/file/12625_fac.zip)
## Post #2
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2017-03-19T17:15:35+00:00
- Post Title: Ghost in the Shell .FAC archives [PS1]

Already solved this on VGR, but going to post here just in case anyone who manages not to find VGR finds this site instead . 

```
# Written By Anex For QuickBMS
# http://aluigi.altervista.org/quickbms.htm

#  Upon Extraction, will come out to an error,
#  but this is the way the script is supposed to exit!
for FILES = 0
    get NULL byte
    get FNAMELENGTH byte
    getdstring NAME FNAMELENGTH

    do
        get NULL byte
        while NULL == 0
        
    get SIZE long
    get OFFSET long
    log NAME OFFSET SIZE
next FILES

```
