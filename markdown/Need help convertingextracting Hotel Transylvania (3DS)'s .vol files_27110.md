## Post #1
- Username: SimpleSymphony
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Dec 14, 2022 4:35 am
- Post datetime: 2023-08-16T21:31:25+00:00
- Post Title: Need help converting/extracting Hotel Transylvania (3DS)'s .vol files

Hello! I've recently extracted Hotel Transylvania's music so I could convert it into a listenable format, but they're .vol files (apparently connected to the game's EngineBlack engine), which I've never seen before! I've tried to use a Wayforward file tool ([https://github.com/meh2481/MSFHDEx](https://github.com/meh2481/MSFHDEx)), using both volEx and the quickbms script provided. volEx seems to extract a file, but the file has no bytes, no file extension, and both files I've tried extracting have this weird name: Ë2=µ. The quickbms method doesn't work at all, always saying that it can't read 4 bytes from a unique offset for each file. There aren't many online resources on this, so I'm pretty lost: If anyone could help me with this, that'd be great! Thanks in advance!

The .vol files I extracted: [https://www.mediafire.com/folder/dowuep ... .vol+files](https://www.mediafire.com/folder/dowuep39qumwl/Hotel+Transylvania+%283DS%29+-+.vol+files)
Wayforward file tool: [https://github.com/meh2481/MSFHDEx](https://github.com/meh2481/MSFHDEx)

music_ballroom offset: 002ca9b4
music_boss offset: 00249370
music_cellar offset: 0046fef2
music_finalboss offset: 0034b235
music_graveyard offset: 00412635
music_hall offset: 003eb2b0
music_lobby offset: 00475c71
music_tower offset:003e73f1
## Post #2
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2023-08-17T00:49:16+00:00
- Post Title: Need help converting/extracting Hotel Transylvania (3DS)'s .vol files

```
subfile_extension = wave
subfile_size = @0x30

```


Save the text above as ".vol.txth" and put it on the same directory as the vol files and then play/convert it with vgmstream.

There are [quickbms script](https://aluigi.altervista.org/bms/scooby_looney.bms) too for WF vol files however your files has an additional fields that the script doesn't cover yet though it should be easy to add. But the TXTH method is much easier and faster.
