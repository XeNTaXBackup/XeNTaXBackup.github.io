## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-20T16:09:37+00:00
- Post Title: Sonic & SEGA All-Stars Racing (*.XPAC)

```
# 
# By Ekey (h4x0r)
# http://www.progamercity.net
#
# script for QuickBMS http://quickbms.aluigi.org

comtype unzip_dynamic

goto 0x8
get TABLESIZE long
goto 0xc
get FILES long
goto 0x18

for i = 0 < FILES
	get HASH long
	get OFFSET long
	get SIZE long
	get SIZED long
	get NULLS long
	string NAME p= "%08X" HASH
	clog NAME OFFSET SIZE SIZE
next i
```


FileNames hashed
[SASHasher.rar](https://xentaxbackup.github.io/file/5700_SASHasher.rar)
## Post #2
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-08-21T12:00:25+00:00
- Post Title: Sonic & SEGA All-Stars Racing (*.XPAC)

This for PC or X360? If PC, are you able to deal w/ X360 ver as well?

Any chances for repacking archives?
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-21T13:52:36+00:00
- Post Title: Sonic & SEGA All-Stars Racing (*.XPAC)

It's for PC. For Repack read section 3 in QuickBMS readme.
## Post #4
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-08-21T14:20:33+00:00
- Post Title: Sonic & SEGA All-Stars Racing (*.XPAC)

Will you be able to check out the X360 version of the format as well?

I can send you archives required if you do not have them.
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-21T14:35:39+00:00
- Post Title: Sonic & SEGA All-Stars Racing (*.XPAC)

Send me any small archive in pm.
## Post #6
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-08-21T14:37:59+00:00
- Post Title: Sonic & SEGA All-Stars Racing (*.XPAC)

OK, time to look for'em on my DVDs. Standby, please.
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-21T19:24:34+00:00
- Post Title: Sonic & SEGA All-Stars Racing (*.XPAC)

Same format. Just before 
```
comtype unzip_dynamic
```
 add 
```
endian big
```
## Post #8
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-08-22T02:14:32+00:00
- Post Title: Sonic & SEGA All-Stars Racing (*.XPAC)

I seem to have errors:

- invalid zlib compressed data (-3)
- there is an error with the decompression
   the returned output size is negative (-1)

Please advise!
## Post #9
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-25T13:50:13+00:00
- Post Title: Sonic & SEGA All-Stars Racing (*.XPAC)

What the pak you try unpack ?
## Post #10
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-08-25T21:28:42+00:00
- Post Title: Sonic & SEGA All-Stars Racing (*.XPAC)

The two I sent you, Sir.
## Post #11
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-25T22:48:34+00:00
- Post Title: Sonic & SEGA All-Stars Racing (*.XPAC)

Ok here updated script for Xbox

```
# 
# By Ekey (h4x0r)
# http://www.progamercity.net
#
# script for QuickBMS http://quickbms.aluigi.org

endian big
comtype unzip_dynamic

goto 0x8
get TABLESIZE long
goto 0xc
get FILES long
goto 0x18

for i = 0 < FILES
   get HASH long
   get OFFSET long
   get SIZE long
   get SIZED long
   get NULLS long
   string NAME p= "%08X" HASH
if ZSIZE == SIZE
   clog NAME OFFSET SIZE SIZE
else
   clog NAME OFFSET SIZED SIZE
 endif
next i
```
## Post #12
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-08-26T11:24:45+00:00
- Post Title: Sonic & SEGA All-Stars Racing (*.XPAC)

OK. Now is ther any way to get the filenames set properly, Sir?
## Post #13
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-26T11:27:56+00:00
- Post Title: Sonic & SEGA All-Stars Racing (*.XPAC)

I do not know how get filenames for Xbox. For PC need debugging.
## Post #14
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-08-26T14:14:49+00:00
- Post Title: Sonic & SEGA All-Stars Racing (*.XPAC)

Debugging of what -- the exe's process? Oh. That might be a problem. It is in NO WAY stored in the files, you are certain of that, Sir?
## Post #15
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-26T14:29:46+00:00
- Post Title: Sonic & SEGA All-Stars Racing (*.XPAC)

> Reply from Delacroix
>
> Debugging of what -- the exe's process?
Yep
