## Post #1
- Username: Kharaxel
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Apr 29, 2008 8:56 pm
- Post datetime: 2008-04-29T13:12:06+00:00
- Post Title: Makai Kingdom sndpak.pak

Hi! I'm new here, and this my first post et cetera, et cetera.

I'm in desperate need of help.

I have problem with a file from a game called Makai Kingdom(it's from Nippon Ichi). The file is called sndpak.pak and from what I know this file contains sound files from the game.

So, the question is...how the hell do I extract this? Because I tried many different PAK files extractors and none of them worked.
I can upload the file to some uploading host(but it will take some time though), however I'm not sure if this isn't against the rules.
So...help?

Oh! I forgot to mention...the game is for PS2
## Post #2
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2008-04-29T23:47:49+00:00
- Post Title: Makai Kingdom sndpak.pak

Hello Kharaxel It appears the file is completely uncompressed  and is just a bunch of files
inside one big file.

the sound files seems like .vag inside and I did not found filenames.

file starts with what I beleive to be the number of files inside the file. this is an int32
then for each file:

struct 
{
 int32 offset(absolute)
 int32 file size
}

I cna not confirm or make an extractor ATM, maybe later
