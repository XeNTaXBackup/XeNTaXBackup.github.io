## Post #1
- Username: antoniu200
- Rank: n00b
- Number of posts: 17
- Joined date: Sun May 09, 2021 7:40 pm
- Post datetime: 2021-05-26T21:38:28+00:00
- Post Title: Gameloft voxpack and voxdata files

Hello!

I'm trying to extract the Asphalt 9 soundtrack from older versions of the game (0.4.3c and 1.5.3a).
After extracting the .obb archive, I can see 2 files of significance to me: music.voxpack and music.voxdata.

The music.voxpack file is openable with Game Extractor and can extract every file in there. The files are some kind of Musepack SV8 compression (possibly proprietary or a combination with VOX ADPCM?), but, when opened and played back, they sound very different compared to the game's audio. I believe the game applies some algorithms on these files in real-time or the Musepack algorithms have been slightly altered.

The music.voxdata file is not openable with Game Extractor and I cannot figure out what can open it. I'm hoping this music.voxdata file contains some information regarding the algorithms or maybe some equalizer the game is applying.

Here is the [music.voxpack](https://drive.google.com/file/d/1jKCJV-vskqjSGk57grXZ3oFL_h-2KJTl/view?usp=sharing) file and the [music.voxdata](https://drive.google.com/file/d/1zhVH9hdaGtCjXoI7niRP4vo0CBsdejRQ/view?usp=sharing) file, both on Google Drive.

If anybody can shed some light, it would be appreciated.
## Post #2
- Username: antoniu200
- Rank: n00b
- Number of posts: 17
- Joined date: Sun May 09, 2021 7:40 pm
- Post datetime: 2021-05-27T08:01:08+00:00
- Post Title: Gameloft voxpack and voxdata files

Disregard this.

The .mpc files are correctly opened by Foobar2000 using vgmstream plugin. From there, they can easily be converted to any format.
## Post #3
- Username: antoniu200
- Rank: n00b
- Number of posts: 17
- Joined date: Sun May 09, 2021 7:40 pm
- Post datetime: 2021-10-17T12:20:57+00:00
- Post Title: Gameloft voxpack and voxdata files

Sorry to revive this thread, but really I have nowhere else to ask.

All I would need to do with this game at this point is extract the 30", 60", 90" and 120" versions of all songs. It's a tedious process, if I were to record them from the game. And some removed songs can't be played back anymore. So, I would need help opening up the .voxdata file, which must contain all the playback information for these shorter music tracks.

No program that I know of opens up the .voxdata file correctly. I tried Game Extractor and foobar2000.
## Post #4
- Username: antoniu200
- Rank: n00b
- Number of posts: 17
- Joined date: Sun May 09, 2021 7:40 pm
- Post datetime: 2021-11-10T21:48:28+00:00
- Post Title: Gameloft voxpack and voxdata files

I'm going to give all the information I could gather on this archive, with the risk of repeating myself, in this reply:

> I've been looking into extracting the soundtrack from multiple Asphalt games, more specifically all versions of Asphalt 9. I'm looking to extract all exclusive tracks in the correct order along with their 30", 60", 90" and 120" versions.
>
> 
>
> Unfortunately, some tracks have been removed in later versions and older versions of the game cannot be launched anymore to be able to record the shorter versions of exclusive tracks. This means that those versions must be built using the game files - at least I don't see any other method.
>
> 
>
> Here we go with the technical stuff:
>
> After extracting the .obb archive using the Zip64Unpacker BMS script, in older versions, you'd get a music.voxpack archive. This archive has a "Voxarch1" header and is openable with Game Extractor. The Voxarch1 file contains all the audio data in .vxn and .mpc files, openable using foobar2000 and vgmscript.
>
> 
>
> VXN files have a header of type "VoxN" and contain multiple MP2 Musepack SV8 slices of varying lengths and bitrates. Some of these slices are ignored by the game in 30", 60" and possibly 90" and 120" track versions.
>
> 
>
> The Voxarch1 archive contains one more file that I cannot find any way to open: music.voxdata. Its header is "Voxpack1" and references all music files contained in the Voxarch1 archive. I believe this is the file that tells the game in what order the tracks should be played and which and when slices of audio from each .vxn track can be ignored. The reason I believe this is because I notice that the game has all the soundtrack information in this music.voxpack Voxarch1 file, nowhere else, so it must be specified in some file in the Voxarch1 file. The only file I cannot open is the voxdata Voxpack1 file.
>
> 
>
> Anyone have any ideas on opening this file up?

P.S.: This message is what I wrote on the XeNTaX Discord server regarding this file.
## Post #5
- Username: antoniu200
- Rank: n00b
- Number of posts: 17
- Joined date: Sun May 09, 2021 7:40 pm
- Post datetime: 2022-02-16T22:23:44+00:00
- Post Title: Gameloft voxpack and voxdata files

> Reply from DKDave
>
> First thing I noticed is that the music in your archive is different to what's on Youtube - plus the swearing is obfuscated in your version.  Having said that, it looks like the vxn files themselves have some sequence information - you can see in most files it shows "original", "medium" and "short" - those are the 3 different versions of the track.  Then you have a table starting with "Grpe" - this looks like the sequence data as it shows the order of each segment for each of the original, medium, short versions of the tracks.  It may be possible to use a .txtp file to generate these sequences for playback ...

> Reply from DKDave
>
> so using "bgm_ih_electro_01.vxn" as an example.  Each entry in the sequence table is 0x20 bytes.  I haven't filled in the colours for every single line ...  On this image, purple is the total number of sequence entries, light blue is the "song" number, red is the sequence number within that song, and green is the segment to play at that point.  So, for example, the last track, "short" is made up of segments 0, 2, 0xb, 0xc, 0xd

And this should be your .txtp file for that "short" song:
Code: Select allm_bgm_ih_electro_01.vxn #0
m_bgm_ih_electro_01.vxn #2
m_bgm_ih_electro_01.vxn #11
m_bgm_ih_electro_01.vxn #12
m_bgm_ih_electro_01.vxn #13

To simplify, the VXN files contain 3 rows of importance to us: one that contains values of 0 (original - 90", 120"), 1 (medium - 60") and 2 (short - 30"), another that contains (in hex) running numbers of the parts of the song and the last that contains (in hex) the actual part number.

To see these rows, you need to get a hex editor and set the number of Bytes per Row to 32. Then you will see something like this in the correct part of the file:

```
[b]00[/b]000000[b]01[/b]00000000000000[b]01[/b]00000001000000010000000100000001000000
[b]00[/b]000000[b]02[/b]00000000000000[b]02[/b]00000001000000010000000100000001000000
[b]00[/b]000000[b]03[/b]00000000000000[b]03[/b]00000001000000010000000100000001000000
[b]00[/b]000000[b]04[/b]00000000000000[b]04[/b]00000001000000010000000100000001000000
[b]00[/b]000000[b]05[/b]00000000000000[b]05[/b]00000001000000010000000100000001000000
[b]00[/b]000000[b]06[/b]00000000000000[b]06[/b]00000001000000010000000100000001000000
[b]00[/b]000000[b]07[/b]00000000000000[b]07[/b]00000001000000010000000100000001000000
[b]00[/b]000000[b]08[/b]00000000000000[b]08[/b]00000001000000010000000100000001000000
[b]00[/b]000000[b]09[/b]00000000000000[b]09[/b]00000001000000010000000100000001000000
[b]00[/b]000000[b]0A[/b]00000000000000[b]0A[/b]00000001000000010000000100000001000000
[b]00[/b]000000[b]0B[/b]00000000000000[b]0B[/b]00000001000000010000000100000001000000
[b]00[/b]000000[b]0C[/b]00000000000000[b]0C[/b]00000001000000010000000100000001000000
[b]00[/b]000000[b]0D[/b]00000000000000[b]0D[/b]00000001000000010000000100000001000000
[b]00[/b]000000[b]0E[/b]00000000000000[b]0E[/b]00000001000000010000000100000001000000
[b]00[/b]000000[b]0F[/b]00000000000000[b]0F[/b]00000001000000010000000100000001000000

```


What we have to focus on are these rows (bolded above):

```
00	01	01
00	02	02
00	03	03
00	04	04
00	05	05
00	06	06
00	07	07
00	08	08
00	09	09
00	0A	0A
00	0B	0B
00	0C	0C
00	0D	0D
00	0E	0E
00	0F	0F
00	10	10
00	11	11
00	12	12
00	13	13
00	14	14
01	00	00
01	01	01
01	02	02
01	03	03
01	04	04
01	05	05
01	06	06
01	07	0D
01	08	0E
01	09	0F
01	0A	10
01	0B	11
01	0C	12
01	0D	13
01	0E	14
02	00	01
02	01	02
02	02	03
02	03	06
02	04	07
02	05	08
02	06	11
02	07	13
02	08	14

```


For my example, I used m_ih_electro_dubei_ive_got_to_get_it.vxn. So, we can conclude that, for the 30" version of "I've Got to Get It", by Dubei, parts noted by Foobar2000 as 2 (hex 1 = 1 and add 1 more), 3, 4, 7, 8, 9, 18 (hex 11 = 17 and add 1 more), 20 and 21 are used for the 30" version.

To convert from hex to binary, the Windows Calculator can be used in Programmer mode. Or any other program.
[test1.png](https://xentaxbackup.github.io/file/21795_test1.png)
