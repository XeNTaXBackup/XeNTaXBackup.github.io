## Post #1
- Username: ponaromixxx
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Jul 17, 2014 11:52 am
- Post datetime: 2017-03-27T10:37:13+00:00
- Post Title: encrypted FSB

Help please encrypted FSB

[fdp_vm30.zip](https://mega.nz/#!AgoxgLSJ!dlnlYerU4UVWv1HsmeNry6HTX8nJTbo5ECF9tUQr_YM)
## Post #2
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2017-03-27T13:54:07+00:00
- Post Title: encrypted FSB

> Reply from ponaromixxx
>
> Help please encrypted FSB

fdp_vm30.zip
Looks like you are trying to decrypt soundbank file from Dark Souls III.
After update 1.12 they change algoritm, so exctractor doesn't work now.

Maybe someone have the latest versions of fmodL.dll and fmodex.dll?
## Post #3
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2017-03-27T15:55:10+00:00
- Post Title: encrypted FSB

Password is FDPrVuT4fAFvdHJYAgyMzRF4EcBAnKg
## Post #4
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2017-03-28T16:00:44+00:00
- Post Title: encrypted FSB

> Reply from spider91
>
> Password is FDPrVuT4fAFvdHJYAgyMzRF4EcBAnKg
Thanks you for the password. Now it is possible to further extracting sounds of Dark Souls III using [fsbext](http://aluigi.altervista.org/search.php?src=fsbext) and a simple batch script like this:

```
md "%%~NA"
copy fsbext.exe "%%~NA"
copy "%%A" "%%~NA"
cd "%%~NA"
fsbext.exe -p FDPrVuT4fAFvdHJYAgyMzRF4EcBAnKg "%%A"
cd ..
)
pause
```
## Post #5
- Username: dead vii
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 21, 2017 12:27 am
- Post datetime: 2017-07-20T16:32:58+00:00
- Post Title: encrypted FSB

> Reply from fullinu
>
> spider91 wrote:Password is FDPrVuT4fAFvdHJYAgyMzRF4EcBAnKg
Thanks you for the password. Now it is possible to further extracting sounds of Dark Souls III using fsbext and a simple batch script like this:
Code: Select allfor %%A in (*.fsb) do (
md "%%~NA"
copy fsbext.exe "%%~NA"
copy "%%A" "%%~NA"
cd "%%~NA"
fsbext.exe -p FDPrVuT4fAFvdHJYAgyMzRF4EcBAnKg "%%A"
cd ..
)
pause

using this password with fsbext I get a couple ogg files however I cant seem to play them on vlc, could someone help me with this? i'm a complete noob
## Post #6
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2017-07-21T05:40:13+00:00
- Post Title: encrypted FSB

FSBExt cannot properly extract FSB vorbis encoded files. They come out as headerless OGG files which is why they won't play.

The easiest way to extract them is to download the linked tools and do the following:

[Download Dark Souls III Audio Ripping Tools](https://mega.nz/#!1CJkUYhD!cJxWUDWJPCMwQHY8EbCBV6HPftg5N6zYoj93Cp9V2dQ)


1. Copy your FSBs into the "1. FSBExt" folder and run the "FSBExt (Decrypt FSB).bat"

2. Copy the newly decrypted FSB files (they should have the _crypt.fsb in their name) into the "2. FSB Splitter" folder

3. Run the "Batch.bat" Every FSB file you want to split will have a folder created for it and its contents is placed in them.

4. Copy the newly created FSB files from each output folder into "3. FSB Audio Extractor"

5. Run the "FSB Audio Extractor.bat"


And there you go
## Post #7
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2020-10-21T09:53:32+00:00
- Post Title: encrypted FSB

- probably the file uses encryption, insert the needed keyword:
  type ? for viewing the hex dump of the first 176 bytes of the file because
  it's possible to see part of the plain-text password in the encrypted file!

look need pass here too
[fsbmod.zip](https://xentaxbackup.github.io/file/18872_fsbmod.zip)
