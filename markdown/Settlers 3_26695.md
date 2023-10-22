## Post #1
- Username: Gerbert
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Aug 17, 2021 6:08 am
- Post datetime: 2023-04-25T21:37:01+00:00
- Post Title: Settlers 3

I'm trying to translate Settlers III into Spanish (at least the Mission CD and Quest of the Amazons expansion, both of them were never translated into Spanish), but I have to deal with some .dat files for that and I haven't found any tool to unpack these .dat files to .text and, after that, repacking them back to .dat format.

With a tool called "S3DatPacker" ([https://github.com/horkrux/S3DatPacker](https://github.com/horkrux/S3DatPacker)) I've found a way to unpack some .dat files that contain some mission texts. These files are "siedler3_07.f8007e01f.dat", "siedler3_08.f8007e01f.dat" and "siedler3_09.f8007e01f.dat". You can find them inside this Polish "Fan" Translator for this game: [https://drive.google.com/file/d/1a2EplG ... uI-_Qu0QRg](https://drive.google.com/file/d/1a2EplGLwRhu4tXrbmto0d5uI-_Qu0QRg) (you can unpack these .dat files inside this Polish installer using 7-zip).
These files are inside a folder called "GFX". but S3DatPacker can't repack them after that (there are a lot of unpacked .txt files inside some folders, and  S3DatPacker shows this error: "Couldn't load filelist". Curiously, the filelist is a XML file created by S3DatPacker when unpacking the .dat file).

On the other hand, S3DatPacker fails to unpack the .dat files that aren't inside GFX folder of the Game and there are two files ("Siedler3_00.dat" and "Siedler3_01.dat" inside a folder called "SND") that also contain some text dialogs (You can find the Spanish translation for the base game in [http://traducciones.clandlan.net/index. ... 3-tradu.7z](http://traducciones.clandlan.net/index.php?page=download&file=AS/Settlers3-tradu.7z) and that file contains these two .dat files -the Polish translator also contains the last of them inside the above installer-).

I've found some Fan translations for this game (russian or polish) but I don't know how they've been able to unpack and repack these DAT files. I have found a tool to translate Settlers IV but this tool doesn't recognize Settlers 3 .dat files.

Finally, I  have also found a topic for this game in this forum [viewtopic.php?p=57166&hilit=Settlers#p57166](https://forum.xentax.com/viewtopic.php?p=57166&hilit=Settlers#p57166)
But I don't know how to make the script to work with the above needed .dat files and It seems It's only for unpacking texts, not for repacking them back to .dat.

Any idea of how to unpack and repack these .dat files?
## Post #2
- Username: Arqwell
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 27, 2023 2:04 am
- Post datetime: 2023-05-26T18:44:01+00:00
- Post Title: Settlers 3

You have to keep the unpacked files structure. Then, in the texts directory, replace the modified .txt files (according to the language of the game) and then run the repack. Rename the created test.dat file according to the modified file.



S3DatPacker.jpg (111.49 KiB) Viewed 56 times
## Post #3
- Username: Gerbert
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Aug 17, 2021 6:08 am
- Post datetime: 2023-05-27T20:48:24+00:00
- Post Title: Settlers 3

Thanks for your answer. 
Any idea on how to unpack (and repack) "Siedler3_00.dat" and "Siedler3_01.dat"? Because S3DatPacker can´t handle them.
