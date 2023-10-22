## Post #1
- Username: ProbPeriPlum
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 24, 2021 8:39 pm
- Post datetime: 2022-08-27T01:34:52+00:00
- Post Title: Neopets Mobile .pak File

This was an old Java phone game that gave access to Lutari Island which was only available throigh T Mobile.

These files store the .midis and bitmaps and such for the game and I wanted to recover them for preservation's sake. Since .pak files can vary I'm not sure if an existing method for this already exists or not, but help would be of great appreciation!

The original game (change the extension to zip to unpack): [https://cdn.discordapp.com/attachments/ ... 6uczoa.jar](https://cdn.discordapp.com/attachments/527605871107375119/1012751104473309224/neopetsmob_6x6uczoa.jar)

Just the .pak files: [https://cdn.discordapp.com/attachments/ ... _Files.zip](https://cdn.discordapp.com/attachments/569235314086772748/1012896622952337478/Neopets_Mobile_Pak_Files.zip)
## Post #2
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-08-28T21:13:08+00:00
- Post Title: Neopets Mobile .pak File

This is a pretty straight forward format that is built around loading files by their archive index. Each pak is named after the first file index they contain (e.g. r026.pak's first file is file number 26) with the pack.ifo storing this information in a binary format allowing for quick pak identification. When a file is needed, the game finds the closest previous pak, does some quick math to calculate the fileOffset index, and loads it.

Images are stored as stripped PNGs that the game rebuilds at runtime with only the important metadata and compressed data being stored with the paks. One thing to note; they've employed bit values (e.g. nibbles) instead of int8/16/32s for certain fields to squeeze out some extra space.

I've reimplemented the games code for file loading almost 1:1 in C# [here](https://gist.github.com/barncastle/fbab86d6a4d5a78333c73115d3ba9209) including the PNG conversion. There is a tool at the end of the page that will dump all files from these archives - just put it in a folder with the pack.ifo and *.pak files and run. I've added code to correctly set the file extensions for png and midi files however everything else is set to ".bin" as I couldn't identify them (likely custom formats). Unfortunately there are no file names so everything is dumped as it's file index.

```
   int16_BE count;
   int16_BE unused;
   byte archiveDeltas[count]; // difference between each pak's ordinal e.g. [r000, r014, r024] => [14, 10]
}

struct Pak {
   byte fileCount;
   int16_BE fileOffsets[fileCount]; // relative
   byte data[x];
}

```
