## Post #1
- Username: spakment
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Feb 11, 2021 9:44 pm
- Post datetime: 2021-02-16T14:58:03+00:00
- Post Title: Crazy Taxi .bin files (Dreamcast / PC)

Has anyone any experience with the Crazy Taxi .bin file format? (or any other Dreamcast / Naomi SEGA formats)

I've seen a few other posts about Dreamcast games from around the same era (House of the Dead / Sonic Adventure) and none of the tools seem to help extracting the data from the .bin files.

I initially tried running decrytion / decompression from quickbms. I didn't find any of the standard types created usable files. 
The file headers / signatures don't appear (to me) to have any suggestions about whats contained in them, I've dumped out the first and last few bytes of the headers of the files (text file is attached).

There are 3 OBJDC* bin files each 64k, whihc I think may have the "header info" for the files - possibly, file, identifier, offset, length - but I'm assuming A LOT for that to be true...
There are some COLDC* files which I'm guessing are all the colliders, MOTDC the models? SPR* likely the sprites and TEXDC* surely the textures...

The bin files are availbale at [google drive](https://drive.google.com/drive/folders/1RIyCbjybk3ivo_9vzJe0pVkOaJKmSyd0) 



Any help would be really appreciated!

==== BIN files ====
SIZE	      NAME		
1477040  1ST_READ.BIN
3205672  COLDC1.BIN
3268952  COLDC2.BIN
1821220  COLDC3.BIN
2854020  MOTDC.BIN
  65536  OBJDC1.BIN
  65536  OBJDC2.BIN
  65536  OBJDC3.BIN
2358960  POLDC0.BIN
 369816  POLDC1.BIN
 151640  POLDC2.BIN
  22152  POLDC3.BIN
[crazy-taxi-hex-headfoot-bins.txt.zip](https://xentaxbackup.github.io/file/19546_crazy-taxi-hex-headfoot-bins.txt.zip)
## Post #2
- Username: spakment
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Feb 11, 2021 9:44 pm
- Post datetime: 2021-02-22T13:02:42+00:00
- Post Title: Crazy Taxi .bin files (Dreamcast / PC)

Adding a small progress report. I grabbed some of the game data using ninja ripper and the PC version and the skybox seemed to come out without any translations.
Taking one of the vertex data (3283.27 => 0x 52 34 4D 45) and searching through the files, found in 3 files
BINC2.AFS, COLDC2.BIN, POLDC0.BIN

None of them look like they're encoded, just wrapper archives. 
I think the POLDC0.BIN has the sections split by this header, which seems consistent with the *.AFS files.

```
0x 0100 0000   0100 0000
```


The segments of the archive files with this in are in this drive folder:
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1IS4nD-TPrP7gdWOEZ6KYgDGaLx5xk0gB?usp=sharing)

I think these are both model files - there are sections with what look like float co-ordinates and some with what look like 0 - 1 UV data to me.

```
0x0000 0000   0x0000 803F
```


Anyone here with some experianece able to take a look and tell me if I'm barking up the wrong tree?
## Post #3
- Username: spakment
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Feb 11, 2021 9:44 pm
- Post datetime: 2021-03-09T13:33:07+00:00
- Post Title: Crazy Taxi .bin files (Dreamcast / PC)

Another small progress report, I've created a BMS script to extract the POL DC bin file, attached to this post. These archives (POL) hold the model / polygon data.

Here's a link to the split up files
[https://drive.google.com/drive/folders/ ... BMlpj6faaY](https://drive.google.com/drive/folders/158Pn1SAVKj-YpyCm_P87U5BMlpj6faaY)

File POLDC0979.dat is the skybox, its easier to decipher than a lot of the files as the vertex co-ordinates are large floats upto 4,000 so its easier to distingush them from UV / other data.  

The files hold the vertex data along with UV and possibly vertex color data. Data seems to be mostly 8 (4byte) words wide usually with x,y,z at the start, occassionally its 10 words wide - I can't find any signiture though that marks this out, it obvious in a hex inspector but nothing obvious in the data. Each vertex block gets split by 0x"F2000000 ??000000" and 0x"72000000 ??000000" blocks. 

I believe the Dreamcast supported 14 types of polygon data, likely these are a mix of them, with 16 bit packed UVs, various color and texture intensity modifiers - I'm looking into how these were controlled as I'd guess the data for it must be in the files somewhere...

I'd appreciate any help or suggestions if anyone with experience could take a look and see if there's something obvious that might allow these files to be properly parsed.
[crazytaxi.pol.bms.zip](https://xentaxbackup.github.io/file/19684_crazytaxi.pol.bms.zip)
## Post #4
- Username: spakment
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Feb 11, 2021 9:44 pm
- Post datetime: 2021-03-09T17:13:33+00:00
- Post Title: Crazy Taxi .bin files (Dreamcast / PC)

Incase anyone stumbles on this and wants to examine the files, I found this very helpful - this is the skybox captured using Ninja Ripper and then exported from blender as an obj so it's easily readable, the vertices etc... all seem to match with file POLDC 0979.
[crazy-taxi-skybox.obj.zip](https://xentaxbackup.github.io/file/19685_crazy-taxi-skybox.obj.zip)
## Post #5
- Username: spakment
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Feb 11, 2021 9:44 pm
- Post datetime: 2021-03-10T11:44:06+00:00
- Post Title: Crazy Taxi .bin files (Dreamcast / PC)

And here's a view of the skybox data. Does anyone have any ideas as to where the indices are being packed away into?

[https://docs.google.com/document/d/1Fmq ... sp=sharing](https://docs.google.com/document/d/1Fmqn1R2zAdM6by3WtYYAmtTtYs3FriaOLK2hy2ZF50k/edit?usp=sharing)
