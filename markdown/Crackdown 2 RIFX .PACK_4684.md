## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-06-29T18:20:00+00:00
- Post Title: Crackdown 2 RIFX .PACK

Can someone write a bms script that splits the RIFX segments out of this PACk file seeing at it has no headers/filetable ect. just has RIFX files inside them.

Heres a cut from the 300MB file

[http://www.megaupload.com/?d=D4WO6MTT](http://www.megaupload.com/?d=D4WO6MTT)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-06-30T19:20:00+00:00
- Post Title: Crackdown 2 RIFX .PACK

```
for
    findloc OFFSET string "RIFX"
    goto OFFSET
    getdstring SIGN 4
    get SIZE long
    math TMP = PCK_SIZE
    math TMP -= OFFSET
    if SIZE u> TMP
        reverselong SIZE
    endif
    log "" OFFSET SIZE
    math OFFSET += SIZE
    goto OFFSET
next
```
*edit* updated
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-07-01T17:59:54+00:00
- Post Title: Crackdown 2 RIFX .PACK

THX luigi, But im getting an "Out Of space" Error mid way through extraction.
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-07-02T09:19:49+00:00
- Post Title: Crackdown 2 RIFX .PACK

Maybe your HD is full?
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-07-02T20:31:04+00:00
- Post Title: Crackdown 2 RIFX .PACK

[http://www.megaupload.com/?d=NPLQX690](http://www.megaupload.com/?d=NPLQX690)

No the hard drive is fine but maybe the full file can weed out some problem somewhere.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-07-02T22:43:06+00:00
- Post Title: Crackdown 2 RIFX .PACK

the problem was in the RIFX files that are mixed in both little and big endian.
I have added a work-around to the script to make the work
## Post #7
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-07-02T23:44:12+00:00
- Post Title: Crackdown 2 RIFX .PACK

Thanks aluigi that did it!
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-07-03T20:23:22+00:00
- Post Title: Crackdown 2 RIFX .PACK

> Reply from OrangeC
>
> Can someone write a bms script that splits the RIFX segments out of this PACk file seeing at it has no headers/filetable ect. just has RIFX files inside them.

Heres a cut from the 300MB file

Is that from the full game or a demo?
## Post #9
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-07-03T20:27:23+00:00
- Post Title: Crackdown 2 RIFX .PACK

From the demo.
