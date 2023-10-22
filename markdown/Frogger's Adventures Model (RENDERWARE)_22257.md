## Post #1
- Username: Kneesnap
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 06, 2017 4:01 am
- Post datetime: 2020-06-08T07:34:41+00:00
- Post Title: Frogger's Adventures Model (RENDERWARE)

Hello again!

I was working on file formats for Frogger's Adventures: The Rescue, when I cracked the compression algorithm.
Unsurprisingly, the files I have decompressed are Renderware Stream files.
However, I'm completely unable to find any Renderware tool which is able to actually view these models.
RWAnalyze does load it, so it is a valid Renderware file.

I'm wondering if anyone has any tools which can view the model I've attached. Thanks!
[18-UNPACKED.zip](https://xentaxbackup.github.io/file/18290_18-UNPACKED.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-06-08T07:45:22+00:00
- Post Title: Frogger's Adventures Model (RENDERWARE)

I thought you were the one who's coding Frogger-tools?  
.



18-UNPACKED-dff.png (70.93 KiB) Viewed 100 times

(first submesh only)
## Post #3
- Username: Kneesnap
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 06, 2017 4:01 am
- Post datetime: 2020-06-08T21:53:46+00:00
- Post Title: Frogger's Adventures Model (RENDERWARE)

Thanks! I wasn't entirely looking for hex2obj, but that information is still useful.

> Reply from shakotay2 ↑Mon Jun 08, 2020 3:45 pm at Mon Jun 08, 2020 3:45 pm
>
> 
I thought you were the one who's coding Frogger-tools?

I'm not sure what you mean by this. Yup, that's me, I make the Frogger modding tools 
I'm checking out a new Frogger game (there are a lot, this is the third one I'm taking a look at), and it uses Renderware. Since that was such a popular engine, used in games like GTA, I was hoping I could find a tool out there which was already made to at least start previewing the files with.

If there isn't, it isn't the end of the world, there's loads of documentation on this file format by the looks of it, and I'll likely end up making a parser for this format anyways.
## Post #4
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-06-09T01:33:11+00:00
- Post Title: Frogger's Adventures Model (RENDERWARE)

It is possible to extract this dff with this [script](https://zenhax.com/download/file.php?id=2683%20url).
If you rename the larger .unk file to .dff, you can open it with the 3D Object Converter, but you will need to make some edits to the model.



Image.png (62.45 KiB) Viewed 81 times
## Post #5
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-06-09T01:37:52+00:00
- Post Title: Frogger's Adventures Model (RENDERWARE)

The second largest file is the texture, the texture I got with TextureFinder, I don't know if it's the best way to get it.



Textura.png (35.91 KiB) Viewed 81 times
## Post #6
- Username: Kneesnap
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 06, 2017 4:01 am
- Post datetime: 2020-06-09T04:57:34+00:00
- Post Title: Frogger's Adventures Model (RENDERWARE)

Perfect, this was exactly what I was hoping for. I'm still a little confused how to select a texture for a material in this program, but other that that this is great.
