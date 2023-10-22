## Post #1
- Username: PentyDeasFortyNine
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jan 04, 2022 3:47 am
- Post datetime: 2022-06-20T23:40:21+00:00
- Post Title: Knockout City Model Extraction?? (Velan Viper Engine)

I've been wondering this for a while, but would it ever be possible to extract assets from games using Velan Studio's Viper Engine? It's used in games like Mario Kart Live and the now free to play Knockout City.

I attempted to go through KOC's files for some asset ripping, but my investigation was cut short when I saw how the game files were kept.
[https://imgur.com/a/FqqcDkT](https://imgur.com/a/FqqcDkT) (game directory)
[https://imgur.com/a/JBAXFBw](https://imgur.com/a/JBAXFBw) (internals of one of the data.zip files)
This is about all the knowledge of anything I can give, since I am NOT a very tech savvy person in this regard   . If anyone else has any interest in this topic, maybe try and see what you can do? Knockout City is a free game now, so it wouldn't cost you anything to try and take a look (and it's pretty fun!).

Good luck!
## Post #2
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-06-21T13:09:31+00:00
- Post Title: Knockout City Model Extraction?? (Velan Viper Engine)

Samples
## Post #3
- Username: PentyDeasFortyNine
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jan 04, 2022 3:47 am
- Post datetime: 2022-06-21T15:54:56+00:00
- Post Title: Knockout City Model Extraction?? (Velan Viper Engine)

> Reply from Sharppy ↑Tue Jun 21, 2022 9:09 pm at Tue Jun 21, 2022 9:09 pm
>
> Samples

Oh, yes. samples. here you go. [https://www.mediafire.com/file/mjh2iznb ... s.zip/file](https://www.mediafire.com/file/mjh2iznbunzzjdp/Knockout_City_File_Samples.zip/file)
just a fair warning, i haven't the slightest idea what's in these files. but my working theory is that it's all encrypted.
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2022-06-21T17:49:12+00:00
- Post Title: Knockout City Model Extraction?? (Velan Viper Engine)

The files aren't encrypted.

I don't know the header structure for the "VIPR" files, but 3 of those contain textures.

The other file beginning with "BKHD" is a Wwise audio bank - you can rename it to *.bnk and it'll play in Foobar with vgmstream plugin.
## Post #5
- Username: PentyDeasFortyNine
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jan 04, 2022 3:47 am
- Post datetime: 2022-06-21T19:10:14+00:00
- Post Title: Knockout City Model Extraction?? (Velan Viper Engine)

I see! thank you for your knowledge. Seems like they use .tga for their image format. That's an interesting choice for sure.
Seems like the files I grabbed are...

- An asset for a jacket, presumably for the greaser outfit.
- A normal map for what i can only assume to be a female character because of the "_f_" and "_n" in the file name.
- Some texture for the Hideout, an "rmah" texture. must be a PBR thing.
- Some kind of audio data.

Good to know these aren't encrypted, just.... mysterious to probably ward off the curious. Which would definitely make sense, I suppose.
## Post #6
- Username: PentyDeasFortyNine
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jan 04, 2022 3:47 am
- Post datetime: 2022-07-10T03:36:52+00:00
- Post Title: Knockout City Model Extraction?? (Velan Viper Engine)

Mini update, kind of?
I found a large file (a little over 100MB) with an audio header.. turns out, it's filled with SFX! Just some general sounds, I think, some unique taunt noises, too.
In some other files, I also found out that brawler voices are all individually stored inside their own sound banks, and some line from the character Police Commissioner Chase.
And then I found one of the Deep Space Dispatch audio files from a season pass reward in both English AND German!! Turns out they have ALL the voice acted languages downloaded at once rather than having it be a separate download that depends on your region.

 I'm surprised that its so easy to listen into these just by adding an extension, wwwwwww.

Buuuut.. that's enough about audio. This is under the 3D model section! Hopefully some kind of new developments can be made in that department someday..
