## Post #1
- Username: danielkarloskar1
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Aug 13, 2016 6:10 am
- Post datetime: 2019-08-14T01:15:56+00:00
- Post Title: Rebel Galaxy Outlaw PAK files

When progress is made im thankfull =) They will do official mod tolls later on
## Post #2
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2020-01-11T09:37:48+00:00
- Post Title: Rebel Galaxy Outlaw PAK files

[https://bitbucket.org/hhrhhr/lua-utils- ... axy-outlaw](https://bitbucket.org/hhrhhr/lua-utils-for-rebel-galaxy-outlaw)
## Post #3
- Username: cashgrany
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Feb 16, 2018 1:26 am
- Post datetime: 2020-12-18T15:19:30+00:00
- Post Title: Rebel Galaxy Outlaw PAK files

hi, i have a stupid question; but how do we execute these .LUA codes?
## Post #4
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2020-12-18T16:38:36+00:00
- Post Title: Rebel Galaxy Outlaw PAK files

```
    lua unpack.lua <INPUT.PAK> [OUTPUT_DIR [FILTER]]
```
## Post #5
- Username: cashgrany
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Feb 16, 2018 1:26 am
- Post datetime: 2020-12-18T17:27:25+00:00
- Post Title: Rebel Galaxy Outlaw PAK files

can you explain to me how to do it?
## Post #6
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2021-11-01T13:34:37+00:00
- Post Title: Rebel Galaxy Outlaw PAK files

hhrhhr,
I tried getting the LUA 5.3 binaries, that's fine.
But I could not find matching lua-zlib and lfs Windows binaries.
Any chance to share the binaries you used?
Thanks!
## Post #7
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2021-11-01T18:43:16+00:00
- Post Title: Rebel Galaxy Outlaw PAK files

lua_5.3.4_zlib_lfs_x64.zip [https://mega.nz/file/e4xmWCQZ#NmDjowuEx ... zvyhuFuHuM](https://mega.nz/file/e4xmWCQZ#NmDjowuExvA7NAV6ZO1CIXeFTzAisQiHUzvyhuFuHuM)
## Post #8
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2021-11-02T09:28:29+00:00
- Post Title: Rebel Galaxy Outlaw PAK files

Thanks, works great!
Note to self: destination directory must exist.
Here's a magic batch file 

Use this on the DAT files:

```
lua dat2lua.lua <infile> <outfile>
```

And covert back:

```
lua lua2dat.lua <infile> <outfile>
```



Great work hhrhhr!
[extractall.zip](https://xentaxbackup.github.io/file/21124_extractall.zip)
