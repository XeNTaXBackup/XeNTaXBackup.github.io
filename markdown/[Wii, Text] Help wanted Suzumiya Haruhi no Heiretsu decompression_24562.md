## Post #1
- Username: William278
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 27, 2021 3:50 am
- Post datetime: 2021-10-02T19:49:18+00:00
- Post Title: [Wii, Text] Help wanted: Suzumiya Haruhi no Heiretsu decompression

Hi all,
I've been recently researching the game Suzumiya Haruhi no Heiretsu, a 2009 Wii 3D adventure visual novel game by SEGA/Kadokawa/AQ Interactive.  Without going into too many details, It's an interesting game in a few ways, notably that [the plot was written by the author of the original novel series](http://www.sos-dan.ru/suzumiya-haruhi-no-heiretsu/) and that it seemingly contains the highest poly models of the characters ever made. Graphically, the game is pretty good especially when upscaled on Dolphin, making it look pretty convincingly like an anime, meaning the assets here would be great to use in other projects. My personal interest in investigating this game was to work towards being able to extract the text and translate it, which would open up doors for an english patch being made through a combination of DeepL and community touch ups and contributions, which would make the game playable in English - and I think it sort of deserves to be in a weird way given how from dumping my disk and playing it, the game seems to be very polished and interesting.

My goal, being to find the games text, started with extracting the iso and looking Haruhi's game files. Here's what they look like

Haruhi uses the mcb0 bln layout, used in a few games. What this means is that the game stores data in two places;
The mcb0.bln and mcb1.bln files. The mcb0.bln file acts as a sort of header/pointer to the latter, which contains the bulk of the data.
The scr.bin, evt.bin, dat.bin and grp.bin files.

This particular layout type of the mcb0 format is also used in Inazuma Strikers Eleven 2013 (and purportedly another game, [Mahou Sensei Negima!? Neo-Pactio Fight!](https://forum.xentax.com/viewtopic.php?t=7248&start=15), too), and that game has a hacking and fan translation scene of sorts. I enquired with Obluda, who wrote some tools to extract the similarly formatted files from that game and they pointed me towards Kuriimu, software used for creating fan patches of which they added support for the .bln and .bin files for Inazuma Strikers.

I was thus able to extract the compressed sub-bin folders from the scr, evt, dat & grp.bin files, and after performing some text string searches (in SHIFT-JIS, as that's the text format of this game) yielded what I was after - the game's dialogue scripts. Kuriimu even let me replace them- pertfect! Searching through the mcb1 directory, however, proved less fruitful as the files were compressed, but I figured I already found what I needed. Sadly, the kicker is that mcb  games seem to use logic to determine where they load their data from - the bins or bln - and Haruhi loads its text data from the mcb0.bln and mcb1.bln files. By examining Dolphin and looking through memory at runtime I was able to deduce that the mcb does indeed contain the data I am after. Unfortunately, then, I was back to where I started, as although Kuriimu let me examine and extract the mcb.bln files I was unable to decompress the sub-bln within that likely contained the text I wanted to modify.

That's when I stumbled upon this forum. Previously, a very kind user known as mariokart64n helped a user known as Zerks [extract model data from the game](https://forum.xentax.com/viewtopic.php?t=21840) (after much difficulty from the sound of things), by figuring out that the game uses RLE from another Kadokawa PSP game and extracting model data and from there helped write a 3dsmax importer. Unfortunately, this only worked with some of the character models and the rest of the stuff wasn't able to be extracted, among other issues and oddities. However, I gave it a shot and it did indeed decompress my mcb1.bln, although into a different raw file format that I wasn't able to use sadly:


I got in touch with Zerks, who showed me their previous progress efforts in decompressing Haruhi files for the model data and they did indeed manage to export mcb1 into .sge files and later convert these into models and textures:


...although I was unable to replicate this extraction on my own mcb1.bln with the C++ .NET programs provided in the folder. Additionally, in both the weirdly formatted extraction I did and Zerks/mariokart64n's model extraction, text was either still compressed or not included. Zerks tried to help get me in contact with this user but unfortunately I didn't have any luck with this as they left the xentax discord, even though they still seem active. 

So, that sort of leaves me where I am now in terms of asking for help as I'm at a bit of a loss. I need to extract the mcb and decompress the files such that I can identify where the text is within the mcb and then figure out a way of decompressing and recompressing it.
If anyone has any ideas, I've put the mcb.bln files in a shared folder.

[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1AhPG-H0t0BtDvhbunZTvlxo1HcnKx35l?usp=sharing)

Currently, only [Kuriimu2](https://github.com/FanTranslatorsInternational/Kuriimu2) and mariokart64n's executable (which can be found in [this folder, courtesy of Zerks](https://drive.google.com/drive/folders/12bsIV2ECMqAOJYJuxCg5D99xGj87bM-z?usp=sharing)) are capable of extracting these files, but the decompression as mentioned once extracted is the issue. Mariokart64n previously made use of [a tool](https://github.com/Bigpet/KatagawaBinParser) made by Bigpet for the preliminary model extraction which worked to decompress the run length encoding used on a PSP game known as [Toaru Kagaku no Railgun](https://forum.xentax.com/viewtopic.php?p=98099#p98099) which they adapted for the extraction of this game, though my own testing with this method was sadly fruitless and I simply lack experience and the skillset to work with raw hexadecimal files.

It's worth briefly mentioning that there's another Haruhi Wii game known as Suzumiya Haruhi no Gekidou, which this is not to be confused with. That game is a Rhythm game released earlier in 2009 and has lower resolution models and a completely different format as it was made by a different developer.

Thanks!   And if you'd like to get in touch, reply below or find my name (William # 5204) on the xentax discord.
## Post #2
- Username: William278
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 27, 2021 3:50 am
- Post datetime: 2021-11-29T13:19:02+00:00
- Post Title: [Wii, Text] Help wanted: Suzumiya Haruhi no Heiretsu decompression

Update on this for anyone searching google, I've made significant progress in cracking this and am working on [a tool](https://github.com/WiIIiam278/HaruhiHeiretsuTranslator) to easily edit the game text. I won't post any further updates on here since it's a bit out of scope for the forum, but do get in touch if you're interested in this sort of thing.
