## Post #1
- Username: Sajextryus
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Sep 04, 2012 8:07 am
- Post datetime: 2012-09-12T00:33:01+00:00
- Post Title: Custom Reader program needed for FEZ XNB files

(sorry that this is another thread in the same forum, but the main task in the first thread is over and irrelevant thanks to Vash and I have absolutely no clue if this could fit in any other forum)

Pretty much continuing off my other thread… [viewtopic.php?f=21&t=9596](http://forum.xentax.com/viewtopic.php?f=21&t=9596)

Click the link to read the full thread with some of my extra posts so you can read some notes I wrote about what I know of the programming of FEZ from the developers blog. I have absolutely no experience with programming yet, but from what I've read, it's certainly possible to do what I'm asking.




I'm trying to view the resource files for FEZ (text, images, audio and models) but all the XNB files seem to be written in a custom format that is included in the game engine files. I've already tried viewing it in GXView, but all it gives me is either "unexpected amount of data was read.", "Can't find type reader 'FezEngine.Readers.AnimatedTextureReader", or it will load up blank. As far as I know, it's written using XNA C#. I need help with figuring out how to read this files, probably with the help of the game engine files, and creating a program that can use these readers to read the contents of all the different resource XNB files.

Renaud Brédard, the programmer of FEZ, actually shared my previous thread on Twitter with positive interest in seeing people get it done, which led to it gaining a massive amount of views when Polytron retweeted it, as well as some little tidbits of information from other people interested with the game's programming. Just search @renaudbredard on Twitter and click All to view his responses and people responding from two days ago. Here's the main tweet: [https://twitter.com/renaudbedard/status ... 5128141825](https://twitter.com/renaudbedard/status/244938135128141825)

While at one point he said "Opening XNB files without the readers or the classes they represent is pretty much an impossible task though.", he received a reply from @feshz0r "‪@renaudbedard‬ XNBs are pretty easy ‪[http://imgur.com/badv7](http://imgur.com/badv7) ‬  as is getting hold of the reader classes, 360 FXOs suuuuuck though". Renaud replied "‪@fesh0r‬ Hah! Didn't consider you could reverse engineer the readers. Well then." so he's somewhat confident in people being able to do this. I replied "‪@renaudbedard‬ oh wow! Thanks for sharing my thread! That's totally awesome! You think you can help us out?" but he said "‪@samblye1‬ I... don't think I want to! It's cool to just watch these things happen but intervening kills the challenge. Plus it's not legal.". While he can't (and understandably doesn't want to) personally help, he has hinted enough for even me that it's clearly doable.

Here's the FEZ .pak decompiler to unpack the folders containing the resource XNB files if you want to try working with the files if you currently own the game, courtesy of Vash: [http://www.mediafire.com/download.php?0vuf47r2aq1w6fs](http://www.mediafire.com/download.php?0vuf47r2aq1w6fs)

So… anyone willing to help out or just plain interested?
## Post #2
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-09-12T11:23:42+00:00
- Post Title: Custom Reader program needed for FEZ XNB files

I'm onto decompression
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-09-12T18:57:53+00:00
- Post Title: Custom Reader program needed for FEZ XNB files

around this topic, his blog is really interesting - [http://theinstructionlimit.com/category/fez](http://theinstructionlimit.com/category/fez)
he was also interviewed for the indie game movie if you want to know more
## Post #4
- Username: Sajextryus
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Sep 04, 2012 8:07 am
- Post datetime: 2012-09-12T19:55:50+00:00
- Post Title: Custom Reader program needed for FEZ XNB files

> Reply from WRS
>
> around this topic, his blog is really interesting - http://theinstructionlimit.com/category/fez
he was also interviewed for the indie game movie if you want to know more
Ah, yes. I've read his blog quite thoroughly. I posted a couple things I found out about the programming of the game in the old thread. He's been talking a bit about Mono lately, so I'm guessing a PC/Mac/etc port is actually being made, which is awesome.
I've also seen IGTM and enjoyed it very much (It even inspired me to get started with my own game ideas and pull out an old dumbed down XNA  3.1 book from my shelf I never bothered to read, but that's another thing right now). There wasn't much said about the programming, but it was interesting to hear about the game being made from scratch four different times.

Thanks guys for all the positive responses! I had no idea if anyone even cared other than me, but this is real awesome! Keep us updated!
## Post #5
- Username: fesh0r
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Apr 24, 2012 3:33 pm
- Post datetime: 2012-09-12T22:30:54+00:00
- Post Title: Custom Reader program needed for FEZ XNB files

I was messing around with this back in june but got sidetracked as i tend to do.
I've got a generic XNB decompressor that I'll package up shortly, which makes reading the XNBs a bit less annoying.
also wrote a xnb template for 010 editor which is where the screenshot in my tweet came from.

Also, managed to pull out the .net assemblies which makes figuring out the XNB formats a lot easier as you can run them through reflector.

Been many months since i looked at this so will take a while to dig up everything and get back up to speed.

Wrote most of this stuff when pulling apart terraria and not sure how much they actually spread.

For a start, MS actually released some documentation of the XNB format which may help [http://xbox.create.msdn.com/en-US/sample/xnb_format](http://xbox.create.msdn.com/en-US/sample/xnb_format)
## Post #6
- Username: fesh0r
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Apr 24, 2012 3:33 pm
- Post datetime: 2012-09-13T03:22:16+00:00
- Post Title: Custom Reader program needed for FEZ XNB files

Ok cleaned up the initial stuff i did a bit.
[https://dl.dropbox.com/u/17271122/fez/fez_unpacker.zip](https://dl.dropbox.com/u/17271122/fez/fez_unpacker.zip) has a python pak file extractor, a xnb file decompressor, the 010 editor XNB template and a couple of bat files.

Couldn't get the unpacker that Vash posted in other thread to do anything other than crash so not sure where it outputs files, but if you put the pak files in Content, and run unpack.bat it will write them all into out, then decomp.bat will uncompress all the XNB files into out_u, which makes them much easier to work with.

One annoying thing with these XNBs is that the data in them is written out bigendian rather than little endian due to being intended for the 360 XNA runtime rather than PC so most of the PC XNB utils pack a sad when trying to read them.
## Post #7
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-09-13T08:32:02+00:00
- Post Title: Custom Reader program needed for FEZ XNB files

My unpacker is written in Visual Studio 2010, you might need the Redist VC++ 2010 (or update them). It puts the extracted files in a dir called like the file give (Other.pak creates the dir Other) and plus I only have that file, other paks might not have the same structure.

Anyway, I'm adding the decompression to the tool as we speak, then I'll see if in the xbox360 SDK there's something useful
## Post #8
- Username: Sajextryus
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Sep 04, 2012 8:07 am
- Post datetime: 2012-09-17T22:51:21+00:00
- Post Title: Custom Reader program needed for FEZ XNB files

Any progress? I've been able to read the gametext file, and even found some neat unused dialog. There's also some files that use the 2DTexture reader built in with XNA, but I have not been able to view them with GXView at all.
## Post #9
- Username: Sajextryus
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Sep 04, 2012 8:07 am
- Post datetime: 2012-09-23T09:39:44+00:00
- Post Title: Custom Reader program needed for FEZ XNB files

Has there been any success yet? Or has this just been forgotten amongst something else?
Just wondering since there hasn't been any posts or anything about any attempts or advancement in this project at all and I'm just itching to hear an update.
## Post #10
- Username: Sajextryus
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Sep 04, 2012 8:07 am
- Post datetime: 2012-09-26T17:53:03+00:00
- Post Title: Custom Reader program needed for FEZ XNB files

I've managed to view some of the textures using ICY Hexplorer's pixel view feature, and I've even found some unused (?) level designs and full 2D levels, as well as the fourth set of concentric circles which has yet to be found in the game (there's 8 sets in total, and they can be found on the floor of certain areas of the game when viewed in first person mode) so there may be a level in the level list we haven't seen (a level that no ones figured out how to access ingame but is accessible through some unknown puzzle possibly). While I'm able to match up most of the level names to maps and cutscenes, there are a few that I have no ideas about.

Is there any possibility of getting the reader files extracted and such and put then to use as a full level viewer and proper texture viewer?
## Post #11
- Username: Sajextryus
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Sep 04, 2012 8:07 am
- Post datetime: 2012-10-08T01:26:50+00:00
- Post Title: Custom Reader program needed for FEZ XNB files

Vash, fesh0r, are either of you still working on this?

I'm also wondering if it's possible to play some of the sound effect XNBs and possibly "Wave Bank.xwb" which has all the layers of the game's soundtrack.

The level files offer a bit of interesting info what what's being utilized from the engine and resource files, so I've started looking at those with a HEX viewer to see if there's something interesting that comes up.
## Post #12
- Username: fesh0r
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Apr 24, 2012 3:33 pm
- Post datetime: 2012-10-08T04:43:26+00:00
- Post Title: Custom Reader program needed for FEZ XNB files

yeah still poking away at it.
have implemented a full generic xnb parser in python including decompression support, and implemented parsers for all of the custom fez types
[https://gist.github.com/3831523](https://gist.github.com/3831523) is it parsing every byte of every xnb file
[https://gist.github.com/3831957](https://gist.github.com/3831957) is a full dump of a single level file

i've got writing pngs for uncompressed textures and animations done, still working on a dxt decoder to do the spritefonts and faraway_thumbs
[http://imgur.com/a/Ptdtw](http://imgur.com/a/Ptdtw)

also adding writing all the other type formats out to xml instead of the fairly raw python output above, along with a wav writer, which is a pain due to the wavformatheader being big-endian on the 360
had a xwb extractor around but it doesn't work either again due to bigendianess
## Post #13
- Username: fesh0r
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Apr 24, 2012 3:33 pm
- Post datetime: 2012-10-08T07:32:01+00:00
- Post Title: Custom Reader program needed for FEZ XNB files

checking twitter, renaud found another bunch of people ripping out the assets, over at gamefaqs
[http://www.gamefaqs.com/boards/961239-fez/64132270](http://www.gamefaqs.com/boards/961239-fez/64132270)
sounds like they are doing it all by hand though
## Post #14
- Username: fesh0r
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Apr 24, 2012 3:33 pm
- Post datetime: 2012-10-17T10:31:52+00:00
- Post Title: Custom Reader program needed for FEZ XNB files

Ok, got a reasonably releasable version of my xnb parser/exporter done

[https://dl.dropbox.com/u/17271122/fez/fez_parse_0.5.zip](https://dl.dropbox.com/u/17271122/fez/fez_parse_0.5.zip)

chuck Essentials.pak and Other.pak then run full_export.bat and it will unpack the pak pack files, decompress the resulting xnb files, and then export the contents as big xml files and pngs

will take a while to run due to generating said large xml files, decompressing the DXT compressed textures manually, and creating pngs manually

includes a copy of the portable python 2.7.3 install I did for the minecraft coder pack, with the python lxml module added also

umm, the xml files generated are basically the full contents of all the custom fez xnb file formats converted to xml, and i'm starting on a opengl viewer for the art objects, trilesets, and levels, but thats going to take a while as my 3d programming skills are currently a bit minimal, the files are a lot easier to understand in xml at least

didn't have much luck with the sound effects and xwb files but will go back to them eventually, feel free to buy the official soundtrack from disasterpiece as its pretty awesome anyway and was cheap when i grabbed it
## Post #15
- Username: Sajextryus
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Sep 04, 2012 8:07 am
- Post datetime: 2012-10-18T05:13:34+00:00
- Post Title: Custom Reader program needed for FEZ XNB files

Thanks for uploading that! I've been looking through the level files in XML format, and haven't found too much we haven't known yet. Code inputs specific to a level are usually included in the level files (at least this goes for the ritual monolith room). The 32 and 64 cube cutscenes are the only things that don't have level files, I believe (they're probably saved as some other kind of file possibly outside of these resource files and somewhere else in the game files, since they seem more like demoscenes rather than something done in level files, but really I have no idea). And CMY_Secret_Cave.png has everything but magenta as alpha, but then again it's something accidentally left in the game files so I'm not really concerned.


One odd and intriguing thing: I found one level file I can't match up to any sort of in game level or cutscene. It's titled 'octoheahedron' and the only art object file it seems to be using is NEW_HEXAO. It does look like there are triles set up, here, so it might actually contain something like a working level, which might be a final secret room which [Renaud somewhat hinted at (I think)!](http://www.formspring.me/renaudbedard/q/345199617618495104) He said that there are 157 levels and cutscenes total that are part of the normal game that have been discovered. There's 156 actual files (not counting the trial levels folder) in this file, and the two ending cutscenes add 2 more files, making it 158, which means that could be the one secret level not counted.

What I can find out so far is that the sky background is black and it uses the Zu trileset. It also doesn't show up in the game save files whereas most of the other levels are titled somewhere in the save files, so I guess it might not be possible to save here. I haven't found it mentioned in any level files yet, but I hope there's something more to this than just another left-over file!



Also in the way of Fractal, I haven't really found anything odd with that level file yet, so maybe there might not really be much to do with that level despite it having the fourth concentric square, but I haven't really checked that closely, so feel free to check yourselves.

There still might be something about those concentric circles, though. Maybe they might have something to do with that extra level! I think I may have really stumbled upon something awesome!
## Post #16
- Username: fesh0r
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Apr 24, 2012 3:33 pm
- Post datetime: 2012-10-29T10:50:04+00:00
- Post Title: Re: Custom Reader program needed for FEZ XNB files

Finally got around to added the promised sound and music exporting to the unpacker
[https://dl.dropbox.com/u/17271122/fez/fez_parse_0.6.zip](https://dl.dropbox.com/u/17271122/fez/fez_parse_0.6.zip)

You'll need to dig up a copy of either xmaencode.exe or xma2encode.exe to be able to convert the game soundeffects, and xwmaencode.exe for the music.

xwmaencode.exe is in the latest directx sdk download, while xmaencode.exe/xma2encode.exe are from the xbox 360 sdk
Though I'm sure a bit of googling or digging around on this forum will help with tracking down all three
## Post #17
- Username: fesh0r
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Apr 24, 2012 3:33 pm
- Post datetime: 2012-11-01T02:58:19+00:00
- Post Title: Re: Custom Reader program needed for FEZ XNB files

And another new version, this time with a barebones ArtObject viewer as shown at [http://imgur.com/a/xsFU0](http://imgur.com/a/xsFU0)

[https://dl.dropbox.com/u/17271122/fez/fez_parse_0.7.zip](https://dl.dropbox.com/u/17271122/fez/fez_parse_0.7.zip)

The viewer runs off the xnb files directly rather than the exported pngs and xml files, so you can either run full_export.bat to do a normal export of everything, or only unpack the xnbs with
fez_unpack.bat Content\Essentials.pak out
fez_unpack.bat Content\Other.pak out
then show_ao.bat "out\art objects\new_hexao.xnb" to view stuff
everything in the art objects directory that ends with ao is a viewable art object, while the files without the ao suffix are just the textures for each

In the viewer you can left click and drag to rotate, right click and drag to zoom in and out, hit L to toggle lighting, T to toggle texturing, W to toggle wireframe overlay, C to toggle backface culling, or ESC to exit

its a bit my very first opengl programish but seems to work ok on my machine at least
