## Post #1
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-03-05T06:01:23+00:00
- Post Title: MVP Baseball 2005

ast audio files close to the same format as Need for Speed


and if it makes any difference I bought the program already
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-03-06T10:56:13+00:00
- Post Title: MVP Baseball 2005

AST audio archives cannot be opened in MultiEx Commander because the files in the archive are split up into many small pieces. Here are the specs...

```
| Need For Speed: Underground *.ast |
+-----------------------------------+

// This format lists all files one after the other. Each file is split up
// into chunks, presumably to make for more efficient file buffering when
// playing audio.

// for each file
4 - Header (SCHI)
4 - Split Header Offset
X - Unknown
12 - Split Header (see below)
X - File Data Chunks (see below)
4 - File End Tag (SCEI)
4 - Unknown (8)
X - Padding (filled with null)

// Split Header Format
4 - Split Header (SCCI)
4 - Chunk Data Offset (12) (relative to the start of the split header)
4 - Number Of Chunks

// File Data Chunks Format
4 - Chunk Header (SCDI)
4 - Compressed Size (of the chunk)
4 - Uncompressed Size (of the chunk)
4 - Padding (filled with null)
X - Chunk Data
```


This is of course assuming that the format is the same as that in Need For Speed. The same format is also used in NFSU2 with the extension *.mus .

Sorry mate.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-03-06T10:59:49+00:00
- Post Title: MVP Baseball 2005

However, if you can send us one of the files, we may be able to check it out for you. If there is a file that will zip up to under 2MB, you can attach it to the forums here. Otherwise, you can email it to us if it is under 4MB - I am available at [watto@watto.org](mailto:watto@watto.org) and Mr Mouse has an email link at the bottom of [http://multiex.xentax.com](http://multiex.xentax.com)

Thanks mate, hope we can help.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #4
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-03-10T17:05:39+00:00
- Post Title: MVP Baseball 2005

2.1 meg

[http://www.mvplanet.com/batmini.rar](http://www.mvplanet.com/batmini.rar)
