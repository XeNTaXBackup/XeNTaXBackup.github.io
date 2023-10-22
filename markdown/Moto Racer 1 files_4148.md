## Post #1
- Username: kekko
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Nov 01, 2008 9:26 pm
- Post datetime: 2010-02-16T22:16:27+00:00
- Post Title: Moto Racer 1 files

Hi,

Moto racer is one of my favourite arcade games of all times, it was colorful and fast, and I really enjoyed it when it came out.
 

I would like to start studying its data files, for a project involving a simple 3d engine in OpenGL. 
There are two main kinds of files in the game:
- BKF, archive files, they contain audio/textures/meshes data (the contained files need to be reversed, too)
- TRK files, I guess they contain the 3d geometry of the tracks, not sure about the textures, I guess they're in the respective bkf file.

I was wondering if anyone has some specification on moto racer 1 data files, so I don't have to reinvent the wheel. 
That's the [link to the playable demo](http://games.softpedia.com/progDownload/Moto-Racer-Download-51677.html), just in case you need it.

Thank you!!!
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-02-20T12:28:16+00:00
- Post Title: Moto Racer 1 files

Check out the info at Game File Format Central 
[http://wiki.xentax.com/index.php/Motoracer](http://wiki.xentax.com/index.php/Motoracer)
## Post #3
- Username: kekko
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Nov 01, 2008 9:26 pm
- Post datetime: 2010-02-20T16:48:48+00:00
- Post Title: Moto Racer 1 files

Thank you Mr.Mouse.
actually the .bkf files were not a problem, I was more interested in the files contained in them. that's what I noticed up to now:
.lez: splash screens (look like targa images with modified header?)
.raw: track textures (raw image data, they open with PS)
.3df: meshes (seem just a raw vertex list followed by the face list)
.map: objects textures (one for every .3df ?)
.wav: sound files (NOT in the standard wave file format "RIFF wavefmt")
and many others. 
I need to decode the files above (raw and 3df were easy). 
Moreover, there are the .trk files, which appear to be a bit more complicated than the simple 3df meshes.
Here's a sample of [trk file](http://www.sendspace.com/file/03tywd) (136kb 7z file)

Any help would be appreciated 
bye!
## Post #4
- Username: qwertadf
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 22, 2020 12:46 am
- Post datetime: 2020-04-21T16:55:13+00:00
- Post Title: Moto Racer 1 files

Hi, I managed to convert these .3df files to .obj. There is link for my tool.
[https://github.com/filipalac/3df2obj](https://github.com/filipalac/3df2obj)
Sorry for reviving old thread but it shows up when you google for motoracer 1 files. Maybe it will help someone in future.
