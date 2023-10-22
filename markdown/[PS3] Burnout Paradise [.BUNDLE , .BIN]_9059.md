## Post #1
- Username: MaDetho
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 15, 2012 7:09 am
- Post datetime: 2012-06-10T11:26:33+00:00
- Post Title: [PS3] Burnout Paradise [.BUNDLE , .BIN]

hey there.

i'm currently trying my luck on Burnout Paradise .BUNDLE and .BIN files which r same as far as i could see yet.

i got this far yet, and now im actually stuck getting the ZSIZE :S.. 
I found another Burnout Paradise .bms here but seems like it didnt work for ps3.

```
goto 0x10
get FILES long
get DUMMY long
get OFFSET long
goto 0x30
for i = 0 < FILES
    getdstring DUMMY 1C
    get SIZE long
next i
```


i would like giving an example file, but im not allowed to so.

Still hope anyone can help me.
## Post #2
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2012-06-12T12:15:20+00:00
- Post Title: [PS3] Burnout Paradise [.BUNDLE , .BIN]

Though at first glance it doesn't seem very similar, you can check out format of NFS HP 2010 bundles (also done by Criterion Games):

[Need For Speed: Hot Pursuit bundle files (*.BNDL, *.BUNDLE, *.BIN) format](https://docs.google.com/document/d/1bRvVZZkmXBrdDthmYQ_Vcyk8048JGKCtAAnVDBLh4nw/edit?authkey=CNGf2JIK&pli=1) [GoogleDocs]
## Post #3
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-11-17T10:32:10+00:00
- Post Title: [PS3] Burnout Paradise [.BUNDLE , .BIN]

I'm with the files bnd2 the PS3, can someone help with this?
[LANGUAGE.rar](https://xentaxbackup.github.io/file/6003_LANGUAGE.rar)
