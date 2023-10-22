## Post #1
- Username: SillyWills
- Rank: n00b
- Number of posts: 11
- Joined date: Sun May 22, 2016 2:26 pm
- Post datetime: 2018-10-13T20:03:09+00:00
- Post Title: Battle Garegga Rev 2016 (PS4)

So, after obtaining the titular game, I found its data is contained in one file called "ps4data_body.bin", which is a little over 600MB in size. I'd like to know if there's a script or tool that could crack this baby open? Sadly, the few resources I tried failed to get the job done. Anyway, got the archive in question right here:

[ps4data_body.bin](https://drive.google.com/open?id=1NL_IDQhIl-5ZaffpcuLP-oJOhSvQpEVD)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-14T01:25:12+00:00
- Post Title: Battle Garegga Rev 2016 (PS4)

Are there any other files with similar name? This file seem to contain only raw data and you'll need a directory file containing offsets and size fields to unpack it.
## Post #3
- Username: SillyWills
- Rank: n00b
- Number of posts: 11
- Joined date: Sun May 22, 2016 2:26 pm
- Post datetime: 2018-10-17T19:43:28+00:00
- Post Title: Battle Garegga Rev 2016 (PS4)

> Reply from Bigchillghost
>
> Are there any other files with similar name? This file seem to contain only raw data and you'll need a directory file containing offsets and size fields to unpack it.

Sorry for the late response! Anyway, I checked, and.... perhaps this is the necessary file?
[ps4data_info.psb.rar](https://xentaxbackup.github.io/file/15044_ps4data_info.psb.rar)
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-18T04:27:14+00:00
- Post Title: Battle Garegga Rev 2016 (PS4)

> Reply from SillyWills
>
> perhaps this is the necessary file?
No idea. But it's using the same structure as the previous one:

```
long	UnzipSize // Probably?
byte	Data[?] // No fields about the actual size

```

Even if you manually cut off a piece of data based on the signature and scan the compression with comtype scaner, you can't actually find a match.
So chances are that the data are encrypted after the compression is performed, which can explain why there's only one mdf signature in this file, if it indeed is the only file recording all the necessary info.
