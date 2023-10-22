## Post #1
- Username: Pigixir
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 30, 2021 2:04 am
- Post datetime: 2021-07-29T18:20:50+00:00
- Post Title: Requesting Help with Rosenkreuzstilette decryption

Hello. I have been searching around web archives to find the music files from the game Rosenkreuzstilette. All traces of files or decryptions of the game files have been lost, but information about that is available on the wiki page here: [https://rks.fandom.com/wiki/Rosenkreuzs ... tion_Tools](https://rks.fandom.com/wiki/Rosenkreuzstilette_Extraction_Tools)

I must have to decrypt the files, which are in .dat format. The only tool I was able to discover was DXextract, which should work considering  Rosenkreuzstilette was built with DXlibrary. Unfortunately, I require a decryption key for the game which I've been unable to find; although a decryption key of the game's sequel, Rosenkreuzstilette Freudenstachel does exist. If you have interest in helping, I have uploaded the game's data files to mediafire here: [https://www.mediafire.com/file/pbycfaln ... t.zip/file](https://www.mediafire.com/file/pbycfalnfojiiao/rozenkreuzdat.zip/file).
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-08-01T14:09:19+00:00
- Post Title: Requesting Help with Rosenkreuzstilette decryption

Hi, try to use DXADecodeW with key "AC36E2889ADE96323B36E18F".
Here you can download this tool [https://attachments.f95zone.to/2018/08/ ... ecodeW.zip](https://attachments.f95zone.to/2018/08/147613_DXADecodeW.zip)

And here is the usage:

```
DXADecode.exe -K:AC36E2889ADE96323B36E18F "script.dat"
```


Check also this article [http://wiki.xentax.com/index.php/DX_Archive](http://wiki.xentax.com/index.php/DX_Archive)
