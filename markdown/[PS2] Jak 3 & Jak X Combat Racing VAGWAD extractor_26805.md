## Post #1
- Username: Edness
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Feb 11, 2018 7:26 pm
- Post datetime: 2023-05-31T11:06:02+00:00
- Post Title: [PS2] Jak 3 & Jak X: Combat Racing VAGWAD extractor

While extracting Jak & Daxter: The Precursor Legacy and Jak II: Renegade VAGWAD audio is fairly trivial, Jak 3 and Jak X: Combat Racing has custom compressed file table entries, and I couldn't find any other tool at the time of writing this that fully supported it.

Below is a command line Python 3 script that supports both Jak 3 and Jak X's VAGWAD audio files with filenames and all:
[https://github.com/EdnessP/scripts/blob/main/jak-daxter/jak3-Xvagwad.py](https://github.com/EdnessP/scripts/blob/main/jak-daxter/jak3-Xvagwad.py)

To use it, simply run the script with the path to a VAGWAD file as the argument.  It'll expect to find the VAGDIR.AYB file table in the same directory, where it normally should be.

```
python  script_name.py "X:\PATH\TO\VAGWAD.ENG"
```

By default it'll create a folder named VAGWAD in the same directory and extract everything there.  An optional -o / --output argument can be used to specify a different output path if the input file is, say, still on the disc which would be read-only.

```
python  script_name.py "X:\PATH\TO\VAGWAD.INT"  -o "Y:\path\to\output\folder"
```


When it's extracted, use your favorite Sony PS-ADPCM .VAG player of choice, there's plenty of them out there  My personal choice is vgmstream, which has a plugin for foobar2000.  The stereo tracks in these games use two .VAG files interleaved with the headers of both streams intact, which vgmstream has no issue detecting and automatically adjusting.  Can't speak for other tools, I just remember many years ago some tools I used back then couldn't handle that properly.  Putting that out there just in case.
