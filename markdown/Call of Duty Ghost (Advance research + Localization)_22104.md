## Post #1
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2020-05-05T07:49:42+00:00
- Post Title: Call of Duty Ghost (Advance research + Localization)

Hello,
we have been little bit exploring the format of PC (Steam) Call of Duty: Ghosts .ff file in english folder to be able to make translation.
If we take only non _mp files, the content is non crypted and stored inside zlibbed containers.

Inside, localized strings were easy to find, but we have also found out, that there is inner comprimation/reduction involved as well.
Out of 4 usuall types of files inside (video subtitle, .csv file, zlib import and sound), three of them are no big trouble to reconstruct (.csv, zlib import and video subtitles).

The problem comes with one type which we guess is wav or flac sound container without header.
If we were able to reconstruct the sound file at least to level, when no looking back/forward within file is required, the translation would be peace of cake.

So far what we know
0x........ 0xF3FDFDFD is offset specifier - which can be looking back or forward usually from start of raw data section or previous file (so far only one easy file with video subtitles and csv file was fully reconstructed).
0xFFFFFFFF 0xFFFDFDFD is telling reconstruct algorithm to use available data following after offset section (at least for .csv file and video subtitles)
0xFEFFFFFF 0xFFFDFDFD is also appearing in data, not sure what it is meaning

Sound files have also unusual pattern of offsets inside - most of them have offset data in pattern (8)-32-(8)-72-(24)-16-(8)-8-(8)-16, where numbers mean bytes and (offsets)-data.
The first offset of first sound file is targeting special header, which is probably telling, how to reconstruct header of sound file, but others we are not sure of.

We are including templates and files which we think are necessary to understand the problematics.
They are working properly on eng_patch_common.ff but others have sound included and they do not work there.
The reconstruction also requires, that previous files are reconstructed before continuing on next one, thus we cannot skip sound section
Another problem is strange computation of the main raw data size and main header size,
but that can be caused by not completed reconstruction of files.

One possible solution would be to snip ram and take a look, how reconstructed files look like and continue from there,
which we will try in few weeks when having some spare time. But we hope, that someone with better sound file knowledge can help as well.

```
https://mega.nz/file/C1ogiKaI#wWKwYwtM2sTVNAgqSuqUD_r0Y8pBCE4DPEc2ndJMuxI
```
## Post #2
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2020-05-16T19:25:39+00:00
- Post Title: Call of Duty Ghost (Advance research + Localization)

anyone ?? If someone help i will publish tools for all CODS we will make..
