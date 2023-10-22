## Post #1
- Username: Molt
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 19, 2013 10:57 pm
- Post datetime: 2013-08-20T18:27:51+00:00
- Post Title: Cultures 2 file formats

Hello everyone

A bit more than two years ago I started looking into the resources and file formats used by the Cultures 2 engine (Games like "Northland" and "8th Wonder of the World"). I managed to extract the data0001.lib on my own and found the method to decode .cif file in [this](http://forum.xentax.com/viewtopic.php?f=21&t=3711) thread soon after. Since then I worked on the remaining files every now and then and I think I got somewhere, but I need help now.

So first, if you don't have a game from the Cultures series, you can download a demo of Northland [here](http://www.wikinger-tommy.de/NoM/NordlandDemo.exe).
All the resources are stored in datax/libs/data0001.lib which can be opened using game extractor.

There are 4 file formats left:
(Info: numbers are little-endian)

Edit: I managed to decode bmd and fnt by now, below is the original text and an updated file format description.

> .bmd - The models. I've tried model editors/viewers for Mario Sunshine and Mu Online which use the same suffix, but it's either a different file format or I'm too dumb to use these editors.
>
> I get results in the right direction:
>
> 
>
> Sometimes though:
>
> 
>
> Looking at a single row of pixels, where there are currently single transparent pixels there has to be a gap, but I can't figure out how to determine its length.
>
> 
>
> .fnt - The fonts. Nothing else than bmd files with an additional 16-byte header.

 format.pdf
(44.05 KiB) Downloaded 57 times


map.dat - Map core files. Contains the terrain and landscape information. (Inside the lib, look in data/maps, every folder there contains a map.dat)
I figured out every file has 40 sections, each containing an 32-byte header starting with "hoix" and 4 more letters. Sections 28 (I start counting at 0), 31 and 36 are palettes containing the names of terrain patterns, transitions and landscapes.
I didn't find out how to read all the other sections, but almost every one of them contains "kcpX6elr" or "kcpX8elr".
The 12th to 15th bytes in the section header give the length of the section excluding the initial 32 bytes.
The "palettes" look like this:

```
    u4 number_of_entries;
    entries[number_of_entries]{
        u1 length_of_entry;
        char[length_of_entry] string;
        u1 nullbyte; // just a 0x00
    }
}
```

.sav - The savegame. Seems to have the same format as the map.dat, but different sections as it also has to contain player data, figures, buildings, etc.


If you'd like to see the utilities I built myself, just ask.
Any help would be greatly appreciated.

Kind regards
Molt
## Post #2
- Username: Molt
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 19, 2013 10:57 pm
- Post datetime: 2013-08-24T16:18:25+00:00
- Post Title: Cultures 2 file formats

Ok, I managed to decode the .bmd/.fnt file format(s) and I updated the format.pdf file above.
Left are the map and the save formats.
Here's a bundle containing two maps I created, two saves and the tool I'm currently working with (written in PHP).

[ Download ] (Sorry for doing it this way, file is too big to be attached)

Again, any help on those would be greatly appreciated.

Kind regards
Molt
