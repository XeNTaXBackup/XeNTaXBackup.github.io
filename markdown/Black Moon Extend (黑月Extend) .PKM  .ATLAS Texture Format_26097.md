## Post #1
- Username: RokkuDayo
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Feb 21, 2018 8:59 pm
- Post datetime: 2022-12-18T17:44:05+00:00
- Post Title: Black Moon Extend (黑月Extend) .PKM / .ATLAS Texture Format

This is a 2D hack n' slash Chinese mobile game that can only be downloaded through TapTap ([https://www.taptap.cn/app/146956](https://www.taptap.cn/app/146956)) and I've been trying to convert the imagery in the game into something viewable.

Its files are all laid bare inside typical folders, with a good chunk of the game's assets being in common formats easy to crack open, however, its textures and sprites are stored in a set of 4 files: Two PKMs (one for the base image, another for the alpha channel), an ATLAS, and a JSON.

The PKM format is related to the Ericson Texture Compression technique and has been explored by other posts in the past, but the one in this game seems to be slightly different. I don't believe the data is compressed or encrypted differently than what is documented, but the header is unusual and doesn't match the 16-byte standard seen in other files of the same format, rendering these textures unreadable by every software I tried.

Most posts related to this format point to the Mali Texture Compression Tool, but I could only find its 2.2 version as its latest one, 4.3, hasn't been archived past the tool's discontinuation of service earlier this year, at least not that I'm aware of, so there could be a chance all that would be needed to open these is that version of the tool. I also tried a bunch of command line toolsets, both official and unofficial ones, that do the same thing but also to no avail.

The ATLAS and the JSON contain data mostly about screen positioning and scaling along with some other mundane definitions. They are somewhat readable with a text editor but they also look odd.

Full Game Assets: [https://mega.nz/file/cKJhCIRB#5wCMTuYQb ... 0r-qvXR-k8](https://mega.nz/file/cKJhCIRB#5wCMTuYQbgApXT15vI7q11_gefAOS-8CX0r-qvXR-k8)

If anyone could give me some help in figuring this out I would be more than grateful. I will be linking a sample in the post itself but here's a MEGA link to a ZIP with more of them: [https://mega.nz/file/ZKI1haYK#ZtQqOn5ev ... IecGlRCZm8](https://mega.nz/file/ZKI1haYK#ZtQqOn5evEv92uqX6vT0Ma9vEG82hTZLfIecGlRCZm8)

Thanks for your time.


 BME Samples.7z
(52.88 KiB) Downloaded 21 times
## Post #2
- Username: RokkuDayo
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Feb 21, 2018 8:59 pm
- Post datetime: 2022-12-18T20:06:12+00:00
- Post Title: Black Moon Extend (黑月Extend) .PKM / .ATLAS Texture Format

Might also add that I got one of the CGs in the game containing a scene inside a jail cell to show up in Texture Finder, albeit all messed up.

It also seems like the first 68 bytes of most files seem to be scrambled. There are a few PNG files in other folders and those have the same odd-looking bytes in the same region. Other files that aren't textures also exhibit this scrambled header.



 fy_login.7z
(38.04 KiB) Downloaded 13 times
## Post #3
- Username: RokkuDayo
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Feb 21, 2018 8:59 pm
- Post datetime: 2023-01-01T14:15:16+00:00
- Post Title: Black Moon Extend (黑月Extend) .PKM / .ATLAS Texture Format

While looking at another game, I noticed the PKM/ATLAS/JSONs in this one are Spine 3.4.01 files. They don't work with any viewer tool since those require the textures to be PNGs, plus the ATLAS and JSON also show the same weird padding I talked about. Below is a screenshot of an ATLAS and a JSON from BME (left) and a valid, fully working one from Punishing Gray Raven (right).
## Post #4
- Username: RokkuDayo
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Feb 21, 2018 8:59 pm
- Post datetime: 2023-01-03T15:44:29+00:00
- Post Title: Black Moon Extend (黑月Extend) .PKM / .ATLAS Texture Format

I've uploaded the entire game to MEGA in case it ever gets discontinued, and also because there are some Excel tables (list-v2.csv inside the "assets" folder) containing some data attached to each file in the game which could be related to the obfuscation on them. This could be just used while the game downloads its assets during the first boot as the files are all labeled as GZ, but I'm still not sure.
There is also a bunch of "SHA-256-Digest" entries in the MANIFEST.MF file, also with one "Digest" for each file.

< link deleted by moderator >
