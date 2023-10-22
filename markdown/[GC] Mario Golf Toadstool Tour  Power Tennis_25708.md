## Post #1
- Username: spakment
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Feb 11, 2021 9:44 pm
- Post datetime: 2022-08-17T14:29:12+00:00
- Post Title: [GC] Mario Golf Toadstool Tour / Power Tennis

I'm attempting to decypher the file formats used in Mario Golf Toadstool Tour for the Gamecube, created by Camelot Software Planning games.

Extracting the filesystem just gets a list of alphabetically named files (in alphabetical folders) with no extensions.

The developers also made Power Tennis which extratcs out similarly, it was re-released for the Wii and extracting that is succesfull with .stpl and .sbn files.

I'm guessing the .stpl files are textures (like standard Gamecube .tpl files) and the .sbn are the model files (character files can be found in /grp/mario.sbn ) 

I can reverse engineer the file extensions for the gamecube games with these:

SBN files have the hex: 0x06 0x01 0x48 at the 6th byte position
eg, this command line shows them up

```
grep -FHroab -m 1 $'\x{06}\x{01}\x{48}' | ggrep -b ':6:'
```


and similarly for STPL the hex: 0x20 0xAF 0x30 0x00 at the 4th byte position

```
ggrep -roab -m 1 $'\x{20}\x{af}\x{30}\x{00}' | ggrep -b ':6:'
```


These files seem to be some compressed / archive format though and none of the usual gamecube programs can open them as they seem to be "headerless" and are missing their magic numbers.

I'm attaching an example of dumps of the first 64 bytes from each file as an example incase anyone may know or have any suggestions as to how to attempt decompression.
[MGolf-sbn-64HexHeader.txt.zip](https://xentaxbackup.github.io/file/22657_MGolf-sbn-64HexHeader.txt.zip)
## Post #2
- Username: spakment
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Feb 11, 2021 9:44 pm
- Post datetime: 2022-08-17T14:30:04+00:00
- Post Title: [GC] Mario Golf Toadstool Tour / Power Tennis

And the STPL header dump
[MGolf-stpl-64HexHeader.txt.zip](https://xentaxbackup.github.io/file/22658_MGolf-stpl-64HexHeader.txt.zip)
## Post #3
- Username: Yoshimaster96
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Nov 24, 2014 12:57 am
- Post datetime: 2022-09-07T16:59:10+00:00
- Post Title: [GC] Mario Golf Toadstool Tour / Power Tennis

I actually figured out MGTT's filesystem and compression format not too long ago, so I thought I'd add to this.

As for the filesystem, they're accessed by a numerical ID value which is converted to a string using a sort of base-26 setup. See "cvt_id.c" for how to convert these.

As for the compression itself, it's a bit more complicated. It uses a combination of LZ77 compression, along with a relocation table at the end of the file (used to convert the pointers from file relative values to actual addresses). I haven't figured out the latter part entirely, so the code that handles it is incomplete. You can see what I have so far in "decomp.c".

The relocation stuff is also used for code as well, as you can imagine. In fact some of the model files I've come across so far actually have code in the header which returns pointers to various stuff in the file, which is rather strange but kinda interesting.

Haven't been working on this all that much though, but I hope what I do have is helpful to others.
[files.zip](https://xentaxbackup.github.io/file/22773_files.zip)
## Post #4
- Username: spakment
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Feb 11, 2021 9:44 pm
- Post datetime: 2022-09-08T14:30:09+00:00
- Post Title: [GC] Mario Golf Toadstool Tour / Power Tennis

Thanks Yoshimaster96, the above script was super useful as it allows access to the sprite and model files.
After decompressing using the "decomp" script, the standard tpl files can be converted using your favorite convertor (wiimms / everyexplorer / switch toolbox). You can find them now with the 0x0020AF30 at the start of the files.

The model files also have tpl textures embedded in them. 

To be able to extract these you need to cut the model "header bytes" off so the files start with the 0x0020AF30. Consistently the textures start 64 bytes into the model files, so I just used dd eg;

```
dd bs=64 skip=1 if=infilename of=outfile.tpl
```


and then you can run those files through your convertor.

After doing that I can see the intro skybox seems to be in the 
B/A/Q file. 

I tried regenerating the texture file to work out where it starts / stops within the file.
My guess is 0 - 64 bytes are the model header and then the texture from 64 - 349728

I dumped the geometry out of RenderDoc 


skybox-mesh.png (13.82 KiB) Viewed 63 times

 and I can see the models bounds as floats at 350472

```
-77.8983 -6.02128 -77.8982 77.8982  47.8919  77.8982
```


I can't spot any other obvious positions, possibly they're half precision, or some of my assumptions above are wrong. I'll report back if I discover any more useful info.
