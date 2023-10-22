## Post #1
- Username: QISE
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 25, 2009 3:35 pm
- Post datetime: 2009-12-27T14:37:30+00:00
- Post Title: DBC.FILES

OK the file is XDB.VIV now its not same as dbf,file like PC version.

This for nba live 2003 ps2 version.


here a list of files in the XDB.VIV.
xdbcoch0-1.dbc
xdbcoch0.dbc
xdbdlyn0-1.dbc
xdbdlyn0.dbc
xdbinju0-1.dbc
xdbinju0.dbc
xdbloc0-1.dbc
xdbloc0.dbc
xdbplyr0-1.dbc
xdbplyr0.dbc
xdbplys0-1.dbc
xdbplys0.dbc
xdbschd0-1.dbc
xdbschd0.dbc
xdbschdl-1.dbc
xdbteam0-1.dbc
xdbteam0.dbc
xdbtmcr0-1.dbc
xdbtmcr0.dbc
xdbtmgr0-1.dbc
xdbtmgr0.dbc
xdbtmin0-1.dbc
xdbtmin0.dbc
xdbuser0-1.dbc
xdbuser0.dbc
[XDB.rar](https://xentaxbackup.github.io/file/2663_XDB.rar)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-27T16:40:43+00:00
- Post Title: DBC.FILES

```

endian big
idstring BIGF
get FULL_SIZE long
get FILES long
get DUMMY long
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    get NAME string
    log NAME OFFSET SIZE
next i
```
## Post #3
- Username: QISE
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 25, 2009 3:35 pm
- Post datetime: 2009-12-30T16:20:07+00:00
- Post Title: DBC.FILES

What i don't understand is the files DBC works with Visual FoxPro but these DBC.Files don't maybe there not really dbc.files?
[DBC.FILES.rar](https://xentaxbackup.github.io/file/2683_DBC.FILES.rar)
## Post #4
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2009-12-30T19:25:30+00:00
- Post Title: DBC.FILES

> Reply from QISE
>
> What i don't understand is the files DBC works with Visual FoxPro but these DBC.Files don't maybe there not really dbc.files?

Files can have any Extension, the creators decide what to set it to.
Just because some program says it can open X File Format does not mean that it will work for the file format your trying to open.
## Post #5
- Username: QISE
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 25, 2009 3:35 pm
- Post datetime: 2010-01-01T01:22:38+00:00
- Post Title: DBC.FILES

> Reply from Uli
>
> QISE wrote:What i don't understand is the files DBC works with Visual FoxPro but these DBC.Files don't maybe there not really dbc.files?

Files can have any Extension, the creators decide what to set it to.
Just because some program says it can open X File Format does not mean that it will work for the file format your trying to open.
Well you do have a good point i just need to figure out what file type it really is then.
## Post #6
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2010-01-01T14:48:18+00:00
- Post Title: DBC.FILES

> Reply from QISE
>
> Uli wrote:QISE wrote:What i don't understand is the files DBC works with Visual FoxPro but these DBC.Files don't maybe there not really dbc.files?

Files can have any Extension, the creators decide what to set it to.
Just because some program says it can open X File Format does not mean that it will work for the file format your trying to open.
Well you do have a good point i just need to figure out what file type it really is then.

Look up a program called TRID, it sometimes help when your checking out a fileformat.

Edit: It will tell you who the creators are and what can open it if its a known fileformat, if its not then its going to need a special program to open it (so you or someone will have to make a program which can open it)
## Post #7
- Username: QISE
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Mar 25, 2009 3:35 pm
- Post datetime: 2010-01-05T18:12:35+00:00
- Post Title: DBC.FILES

Files can have any Extension, the creators decide what to set it to.
Just because some program says it can open X File Format does not mean that it will work for the file format your trying to open.[/quote]
Well you do have a good point i just need to figure out what file type it really is then.[/quote]

Look up a program called TRID, it sometimes help when your checking out a fileformat.

Edit: It will tell you who the creators are and what can open it if its a known fileformat, if its not then its going to need a special program to open it (so you or someone will have to make a program which can open it)[/quote]

How do you get this to work i really cant get it to.
