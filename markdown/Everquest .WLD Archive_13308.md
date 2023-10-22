## Post #1
- Username: MajinCry
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jul 01, 2015 4:30 am
- Post datetime: 2015-09-10T20:45:06+00:00
- Post Title: Everquest .WLD Archive

Hullo lads.

For the past wee while, I've been dabbling with Everquest and EQEmulator, the server software for the game. Took me around three days to figure out all the kinks and get the thing working.

Good news, is that it plays just like the official server.

Bad news, is that I want to create swathes of custom content, as well as use pre-existing models, because why reinvent the wheel thousands of times?

As far as the custom content goes, I'm able to handle everything (or, uh, there are tools for everything) except for ripping the 3D models. Textures are easily obtained, models aren't.

Anyhow, onto the main part o' the post.


Everquest's mapsare designed by having an archive within an archive. The initial archive, that is provided with the client, is either an .s3d file, or an .eqg file. Inside these, are .dds, .bmp, .wld and .ani files. Luckily, a program named EQ-Zip can open .s3d and .eqg files, which provides immediate access to the .dds and .bmp textures. .Ani files aren't necessary at the moment; they're used for character animations, for which I have no intention of modifying.

.wld Files consist of multiple meshes (individual objects) placed together. These objects range from a single rock to a single tree, to a single barrel, to the terrain mesh. Evidence of this can be found due to the program GLModelViewer.exe (which I downloaded from the EQEmu wiki) being able to view the models used in the map, and even correctly name them.

The problem is, GLModelViewer does not export the files, applies a continuous rotation to the loaded mesh in the 3D preview, and does not use the object's textures. I attempted using 3DRipperDX on the program, but I had to use the QindieGL wrapper to make the program render in DirectX. The exported models had no UV mapping, as well as being distorted (due to GLModelViewer's constant rotation).


Naturally, as one would expect of a lad with no knowledge of reverse engineering, and only enough knowledge in programming to hack together a basic .pascal script, I'm not too confident in my abilities to extract the models.

However, I'm chronically ill which gives me plenty of time, and I have Visual Studio. I'm willin' and ready to learn, if there are lads willing to guide me through this perilous adventure.

In short: I've got textures and .wld file. .Wld file has meshes. How to extract meshes + UV mapping?

Here's an archive containing two .s3d archives, the extracted files from the .s3d archives, and GLModelViewer.exe: [https://www.mediafire.com/?m466t1n7mz7czda](https://www.mediafire.com/?m466t1n7mz7czda)
## Post #2
- Username: MajinCry
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jul 01, 2015 4:30 am
- Post datetime: 2015-09-11T21:08:06+00:00
- Post Title: Everquest .WLD Archive

Not much interest, eh? Well, err, would anybody be willing to at least provide resources that'll help a complete newb along his way? Only thing I could find was determining if an archive is compressed or not, by searching for text strings in a hex editor.

Of which, the .wld archive has none, so I'd wager it's safe to say that the .wld archives are compressed.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-09-11T23:13:42+00:00
- Post Title: Everquest .WLD Archive

did you have a look at wlddoc.pdf from this link: 
[http://sourceforge.net/projects/eqemu/f ... nce%201.1/](http://sourceforge.net/projects/eqemu/files/EQEMu%20Admin/WLD%20Reference%201.1/)
?
## Post #4
- Username: MajinCry
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jul 01, 2015 4:30 am
- Post datetime: 2015-09-12T20:59:04+00:00
- Post Title: Everquest .WLD Archive

> Reply from shakotay2
>
> did you have a look at wlddoc.pdf from this link: 
http://sourceforge.net/projects/eqemu/f ... nce%201.1/
?

Woops, forgot to check this thread.

Nice find, I do say. I'll go give it a read through when I'm less sleep-deprived.
## Post #5
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-08-10T05:25:48+00:00
- Post Title: Everquest .WLD Archive

*pulls out some tools to remove the dust*

After almost 4 years of sleep in this thread, I'm digging that one up again. This is 'cause I've found a game, which appearently uses the same file formatting as Everquest: League of Angels III from 2018. I start off with a .ba file, in which is a file without any extension (the file type simply says "File"). Then I went to take a look into the hex code of this simple file and there's the problem coming up - in the hex code is this written:
00 00 00 -> Flag
13 00 -> name size
00 D1 AA -> File size
72 6F 6C 65 5F 6D 5F 30 30 30 5F 68 65 61 64 2E 73 33 64 -> role_m_000_head.s3d

The last string is what keeps me sitting here puzzled: Is in this file without any extension yet another file packed? I'm asking 'cause I tried to open that file with 7z, but this diddy returned an error that the file can't be opened as an archive. Since this file format isn't supported by this board, the file's hosted [here](https://drive.google.com/open?id=1OmYj8Bu0CRgHzOcLp6yaaXvYpVwTYf73). How can I open this file to proceed with the ripping process?

If this is better placed in a seperated thread, the mods can feel free to move it.
## Post #6
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-08-10T10:17:33+00:00
- Post Title: Everquest .WLD Archive

The file you've provided - s3d_act1.s3d - is an archive containing various other files - there are 10 files contained within this archive.

The format is as follows - values are stored in big endian format:

DWORD - Size of filename text (e.g. 00 00 00 13)
DWORD - Size of file data (e.g. 00 00 D1 AA)
Text - Filename
File data

Each subsequent file follows in the same format until the end of the file is reached.

You can use this QuickBMS script to extract them.  I don't know anything about these individual files, so hopefully once you've extracted them you can make sense of them.


# S3D extractor

Endian big

Set OFFSET 0x0000
Get FILE_END asize

Do
	Goto OFFSET
	Get NAME_SIZE Long
	Get SIZE Long
	GetDString FILENAME NAME_SIZE
	XMath OFFSET "OFFSET + 8 + NAME_SIZE"

	Log FILENAME OFFSET SIZE

	Math OFFSET + SIZE

While OFFSET < FILE_END
