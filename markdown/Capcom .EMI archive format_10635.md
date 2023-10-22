## Post #1
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2013-07-27T10:21:07+00:00
- Post Title: Capcom .EMI archive format

Used in, as minimum, in Breath of Fire 3 and 4.

Views as container with not strong compression, which use table as MATH_TBL.

MrMouse write severals years ago MultiEx script for BoF4 ([http://wiki.xentax.com/index.php?title=EMI](http://wiki.xentax.com/index.php?title=EMI)) , but he doesn't supports by quickbms, and MultiEx(version 4.3.0) works bad in Win7(I, by my mistake, post about it in archive topic about BoF .EMI - [viewtopic.php?f=15&t=1984&p=86937#p86937](http://forum.xentax.com/viewtopic.php?f=15&t=1984&p=86937#p86937) ).

I will glad for tool or bms script(s) for .EMI formats of BoF3 and 4.

Files for researchs and tests can be sent throught PM.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-07-27T10:46:49+00:00
- Post Title: Capcom .EMI archive format

try that script in this way:

```
Get U1 Long 0
GetDString ID 8 0

Set Off Long FN
Math Off *= 16
Math Off += 16
Math Off /= 2048
Math Off *= 2048
Math Off += 2048

For T = 1 To FN
    Get FS Long 0
    Get U2 Long 0
    Get ID2 Long 0
    Get U3 Int 0
    Get END Int 0
    Log "" Off FS 0

    Math FS /= 2048
    Math FS *= 2048
    Math FS += 2048
    Math Off += FS
Next T
```
## Post #3
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2013-07-27T13:18:46+00:00
- Post Title: Capcom .EMI archive format

Thanks, aluigi.

I test script and he works great with simple archives of BoF 3 and 4(BGM aka music also). Graphic store archives unpacks not so good, but, I think, its fixable(or possible do any else - I found here - [http://www.vg-resource.com/archive/inde ... 715-9.html](http://www.vg-resource.com/archive/index.php?thread-7715-9.html) - two utils for graphic store .EMI archives, but they dont work on my OS or files from japanese versions).

Attach logs from command-line extraction process.
[bof34j.rar](https://xentaxbackup.github.io/file/6533_bof34j.rar)
