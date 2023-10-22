## Post #1
- Username: AsparagusCute1467
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Mar 10, 2021 2:02 am
- Post datetime: 2021-03-09T20:46:35+00:00
- Post Title: Lego Legacy deobfuscate png files

Tried to get some png files from "Lego Legacy: Heroes Unboxed", but as usual with Gameloft they are obfuscated. The content of the files start with "GCBF", so I guess they are not compressed additionally. I tried the "gcbf_versus.bms" script from [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm) but it didn't work.

Anybody any idea what I'm missing? Or maybe even with a working solution?
## Post #2
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2021-03-10T05:10:00+00:00
- Post Title: Lego Legacy deobfuscate png files

Post a sample file.
## Post #3
- Username: AsparagusCute1467
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Mar 10, 2021 2:02 am
- Post datetime: 2021-03-10T06:32:12+00:00
- Post Title: Lego Legacy deobfuscate png files

Sure thing!

Within the zip is the original, obfuscated file from the APK.
[minifig_col170_decal.png.zip](https://xentaxbackup.github.io/file/19688_minifig_col170_decal.png.zip)
## Post #4
- Username: AsparagusCute1467
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Mar 10, 2021 2:02 am
- Post datetime: 2021-03-10T06:33:02+00:00
- Post Title: Lego Legacy deobfuscate png files

(Sorry for splitting this in two replies, could not add two files at once)

Deobfuscated it should look like this:



yeti.png (8.31 KiB) Viewed 55 times


(Got that image from another, uncomplete & outdated, source)
## Post #5
- Username: AsparagusCute1467
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Mar 10, 2021 2:02 am
- Post datetime: 2021-03-11T03:10:12+00:00
- Post Title: Lego Legacy deobfuscate png files

Forget that I ever asked!

QuickBMS with the mentioned script is working perfect! I just missed the part, that the resulting file is a ktx file and not a straight png. So with an additional step I've got the pictures.
