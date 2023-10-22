## Post #1
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2013-04-02T20:30:56+00:00
- Post Title: Final Fantasy 4 Heroes of Light DS .nmdp format

Hey Guys.

I was wondering if anyone has ever looked at the .lz format for Final Fantasy 4 Heroes of Light.

The .lz format is pretty common in DS games, but I've tried various .lz decompressors on these files and gotten nothing out of it.

I'm going to guess (judging by most of the other FF games on DS) that the model and texture format used might be pretty similar to FF3, though probably not similar enough for the same Noesis script to work.

I'll attach a model and texture file below shortly, I'm at work right now so I'm unable to do so for another few hours, but perhaps someone else on the board has this game on their PC already.
[4 Heroes of Light.zip](https://xentaxbackup.github.io/file/6310_4 Heroes of Light.zip)
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2013-04-03T11:41:22+00:00
- Post Title: Final Fantasy 4 Heroes of Light DS .nmdp format

Original Post attachment updated, previous attachment was corrupt, probably from my bad connection yesterday.
## Post #3
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2013-04-04T23:13:08+00:00
- Post Title: Final Fantasy 4 Heroes of Light DS .nmdp format

Not a bump, but I've realised perhaps this is in the wrong section, its not an achive format its a 3d model within a compressed file, so this makes it a compressed 3d model(I believe).

So if anyone could please move this to the appropriate subforum it'd be much appreciated.

Sorry for the mistake.
## Post #4
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2013-04-13T17:49:24+00:00
- Post Title: Final Fantasy 4 Heroes of Light DS .nmdp format

I managed to extract  the nmdp model and ntxp texture files for a few using some tools I managed to find online.
The compression seemed to be lzss, though various lzss decompressors didn't work at first I was able to find one that does.

However now I'm looking at the files in the hex editor and not really having much luck, I'm following a tutorial by Chroxx (Noesis tutorial Basic Model) but I'm not really quite understanding this format at all, even following parts of that tutorial.

I've attached the uncompressed model and texture, the extension is still .zs as the extraction tools don't seem to rename the extracted file extension.

This is how it looks in the hex editor, I can see clearly it lists the naming for the individual body parts (or at least some).
[](http://s22.photobucket.com/user/squall789/media/example_zpsad39c0df.jpg.html)

If anyone has any advice or tips that'd be great, I haven't hexed anything in almost 5 years so I'm beyond rusty and even then I wasn't particularly good at it.
[nmdp and ntxp files.zip](https://xentaxbackup.github.io/file/6324_nmdp and ntxp files.zip)
