## Post #1
- Username: mouzerball1000
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Mar 01, 2011 1:00 pm
- Post datetime: 2015-12-26T11:04:25+00:00
- Post Title: Syphon Filter The Omega Strain (.BNK)

Hello, 

So you may have seen I'm also trying to decode textures in the other subforum, but there's only one other file type from the game Syphon Filter The Omega Strain I'd like to crack. I'd think it's fairly simple, but no tools I've seen will open it. I've tried all sorts of extractors, such as quickbms scripts, a BNK converter on lastbullet, binkextractor (from several sources), and they either fail or crash loading these files. They're supposed to contain some various sound effects like gunshots and whatnot and I'd love to have them as a resource. Considering how widespread I see this format being used, I assumed this was going to be a fairly straightforward conversion, since the other formats in this game (.VAG and .VPK) were very simple to convert and I thought .BNK was somewhat documented, but this one has me confused. Can anyone take a look at it and see how plausible this would be to convert?

I had to host the file offsite, since it's 1976kb and the maximum attachment size is 256kb. If that's an issue just let me know and I'll take off the link, of course. Here's a small clip of the header in a hex editor of one of the files (WEPS.BNK):



Finally, a mediafire link to the archive with a few of these BNKs, in case anyone wants to take a look. I'd be really grateful if someone could give me a hand with this format! Thank you for your time.

[https://www.mediafire.com/?6afc81p83wdnsn3](https://www.mediafire.com/?6afc81p83wdnsn3)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-26T11:24:15+00:00
- Post Title: Syphon Filter The Omega Strain (.BNK)

BNK is not some "widespread" format. It's just a word usually used to name sound banks. This one is yet another archive of files encoded with the same encoder as VAG files. Should be easily decoded, just someone have to spend some time to split the bank into small files.
## Post #3
- Username: mouzerball1000
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Mar 01, 2011 1:00 pm
- Post datetime: 2015-12-26T11:36:03+00:00
- Post Title: Syphon Filter The Omega Strain (.BNK)

> Reply from daemon1
>
> BNK is not some "widespread" format. It's just a word usually used to name sound banks. This one is yet another archive of files encoded with the same encoder as VAG files. Should be easily decoded, just someone have to spend some time to split the bank into small files.

You'll have to pardon my ignorance on the subject. I just saw the format show up several times throughout researching ways to crack them open and assumed it would be easy enough to decode considering it seems so common. But I'm glad to know the decoding should, in theory, not be particularly difficult. I can't speak for the difficulty for splitting the bank of files, whether it's something anyone can pick up and do without much experience (something you can just do in audacity? turn one lump audio file into smaller ones? not sure how it works honestly), but I do appreciate the insight!
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-27T12:35:02+00:00
- Post Title: Syphon Filter The Omega Strain (.BNK)

I'm not an expert on Playstations, so maybe VGMtoolbox have some features to do this automatically, split the files e.t.c, but there's a quick solution for this. You can just convert the whole file and then split the big WAV.

Download VGMtoolbox & VGMStream.

Open GENH option in VGMtoolbox. Choose VGMtoolbox, 1 channel, 22050 or other frequency. Scroll down and click "no loop". Then "create GENH". You'll get the file with a header.

Then use test.exe from VGMStream & you get WAV file. There will be garbage in the beginning, this is the bank data, just skip it.
## Post #5
- Username: mouzerball1000
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Mar 01, 2011 1:00 pm
- Post datetime: 2015-12-27T21:26:17+00:00
- Post Title: Syphon Filter The Omega Strain (.BNK)

> Reply from daemon1
>
> 
Open GENH option in VGMtoolbox. Choose VGMtoolbox, 1 channel, 22050 or other frequency. Scroll down and click "no loop". Then "create GENH". You'll get the file with a header.

Just tried this, and it gives me a .WAV with 1:08 of nothing but static. Only thing I can think of here is that I have to use a different Input File type in this step, in VGMtoolbox. Is there more to it than leaving it at the default setting, 4-bit IMA ADPCM?

EDIT: I didn't see the two Playstation options in the list... Well, trying those gives less "static", but it's still nothing but noise. Are there specific options I should try messing with in the toolbox to get it to sound right?
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-28T04:31:14+00:00
- Post Title: Syphon Filter The Omega Strain (.BNK)

Yes, that was copy/paste problem. I meant "Choose playstation adpcm".

In some files the sound is not aligned to 16 bytes. Try another file. For those not aligned you must also set "header skip" to something from 1 to 15, you can find the correct number by looking into the file with hex editor.
## Post #7
- Username: mouzerball1000
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Mar 01, 2011 1:00 pm
- Post datetime: 2015-12-30T03:58:35+00:00
- Post Title: Syphon Filter The Omega Strain (.BNK)

Well, I've tried a few different files now, and it doesn't seem to be fixed by anything I put in the header skip. The options for that were 0x10, 0x20, 0x40, 0x80, and so on, and I tried every single one of them. Not really sure what else I can try. The only other options are Interleave and Use Offset, but checking Use Offset and trying any of those values results in the file not being dumped at all by the VGMstream test.exe. I do really appreciate all the in-depth help you're doing for me though.
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-30T04:29:59+00:00
- Post Title: Syphon Filter The Omega Strain (.BNK)

I mean you must manually enter numbers from 1 to 15, not choose the values from the list.
## Post #9
- Username: mouzerball1000
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Mar 01, 2011 1:00 pm
- Post datetime: 2015-12-30T05:33:30+00:00
- Post Title: Syphon Filter The Omega Strain (.BNK)

> Reply from daemon1
>
> I mean you must manually enter numbers from 1 to 15, not choose the values from the list.

Oh! I didn't even know that was possible. 

So, setting it to a value of 8 worked! I'd have to split this .wav up manually, but that's no issue at all. Looks like this was resolved, and I appreciate the help! Now's the fun part of digging through all the sound effects then.
