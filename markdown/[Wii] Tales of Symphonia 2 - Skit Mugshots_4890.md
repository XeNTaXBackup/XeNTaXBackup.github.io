## Post #1
- Username: Romored
- Rank: beginner
- Number of posts: 20
- Joined date: Fri May 14, 2010 7:52 pm
- Post datetime: 2010-08-16T13:47:49+00:00
- Post Title: [Wii] Tales of Symphonia 2 - Skit Mugshots

The files in this game are mostly Microsoft CABs renamed as general ".bin" files. After I finally understood this, I succeeded in extracting pretty much all of the game models in the disc (it's scary, how poorly protected is this game). There's just one thing I don't understand how to extract: pictures and menu textures (which are all in the same format, I guess). I'm particularly interested in the mugshots that appear during the skit events.
Each skit has its own file, which is supposed to contain all the mugshots needed for that skit (along with the texts, in the final part of the file). I'm not totally certain about it, but I tried to see into them with a GGD tool and glimpsed their shapes, but [they were heavily messed up.](http://img442.imageshack.us/img442/2548/62843411.png) I think they're compressed in some way, so I've been searching for some particular Wii picture format. I didn't find anything, until now.
I can append a file for example, maybe someone here can find something more.
Thanks!
[ar.zip](https://xentaxbackup.github.io/file/3334_ar.zip)
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2010-08-16T15:13:31+00:00
- Post Title: [Wii] Tales of Symphonia 2 - Skit Mugshots

Best results ive had so far was slapping a DXT1 header over the image at resolution X=336, (Y doesnt matter at the moment)
and byteflipping the whole texture data by 16 bit. (So that A B becomes B A).
thats when it actually starts too look like something.

Edit: I would assume this is either a DDS variation, or actually one of the Wii formats that has blocks of graphics instead of pixel per pixel. (pretty much the same as with DDS, which could be why the image is actually almost readable when read as an DDS image).
[ar4test.jpg](https://xentaxbackup.github.io/file/3335_ar4test.jpg)
## Post #3
- Username: Romored
- Rank: beginner
- Number of posts: 20
- Joined date: Fri May 14, 2010 7:52 pm
- Post datetime: 2010-08-18T11:02:39+00:00
- Post Title: [Wii] Tales of Symphonia 2 - Skit Mugshots

Thank you for your answer, Strobe!!
Mmmh... So there's nothing that allows to understand how exactly decode this kind of images, into those files.
I'm searching for something helpful among the other files in the disc, but until now I can't find anything >_<
It's strange, because many files in the disc are like this... There must be something...
## Post #4
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2010-08-21T08:30:41+00:00
- Post Title: [Wii] Tales of Symphonia 2 - Skit Mugshots

Maybe someone will examine these files further and find something out but till then you could try to dump textures with an emulator ([Dolphin](http://www.dolphin-emu.com/news.php)). That worked quite well for [me](http://forum.xentax.com/viewtopic.php?f=18&t=4893) but its not the real deal.
## Post #5
- Username: Romored
- Rank: beginner
- Number of posts: 20
- Joined date: Fri May 14, 2010 7:52 pm
- Post datetime: 2010-08-22T09:59:46+00:00
- Post Title: [Wii] Tales of Symphonia 2 - Skit Mugshots

Yes, I tried it... It works quite well (and if you already have the Skits Gallery you can rip all the portraits of the characters in about half an hour), but the problem is that Dolphin randomly "discards" the movements of the mouth and of the eyes, and I need all of them... You don't have this problem? If not, can you tell me how can I solve it? Now that I think about it, this is the only problem I have with the game... On my pc it works perfectly, with exception of the skits. Maybe I've to change some options.
## Post #6
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2010-08-22T13:08:56+00:00
- Post Title: [Wii] Tales of Symphonia 2 - Skit Mugshots

I only tried to play ARF with the emulator so I cant say anything about ToS. Besides that my pc is too low-end to play at a constant framerate (never over 15FPS).
I hope you used the "dump textures" option under graphics->advanced to rip the portraits. Using it for ARF I got many useless images for almost every frame but the real textures were also dumped e.g. uvmaps of weapons, enviroment and portraits too. (took MUCH diskspace, since I never turned the option off again...)
## Post #7
- Username: Romored
- Rank: beginner
- Number of posts: 20
- Joined date: Fri May 14, 2010 7:52 pm
- Post datetime: 2010-08-24T07:57:19+00:00
- Post Title: [Wii] Tales of Symphonia 2 - Skit Mugshots

Oh, I see >_< Well, it doesn't matter, then. Thank you anyway! Yes, I used the "Dump Textures" feature (doing all the work by hand would be a mess), but the problem is that maybe the skits are drawn in a particular way which Dolphin can't recreate perfectly. Because on the Wii the lips and eyes movements work well, while if you try them on Dolphin they don't.. As I said, it discards some pictures: the character who is talking in that moment should move his mouth, but in Dolphin it just remains either with shut mouth or with open mouth (even if he/she's finished talking)... this isn't good. I don't think that's a problem of frame rate, because ToS2 is maybe the only Wii game that outperforms on my pc (if you don't put a frame limit, it can go two or three times faster than it should go normally!).
## Post #8
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2011-03-24T08:16:26+00:00
- Post Title: [Wii] Tales of Symphonia 2 - Skit Mugshots

I was browsing the web for infos about imageformats of the wii and stumbled upon this: [https://bitbucket.org/delroth/tos2-tools/overview](https://bitbucket.org/delroth/tos2-tools/overview)

> A temporary repository containing tools and documentation about Tales of Symphonia: Dawn of the New World, a Wii game released by Namco at the end of 2008.
If you dont get the information to encode the images from the repositorie you could try to ask the owner about the images.
## Post #9
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2011-06-20T20:30:47+00:00
- Post Title: [Wii] Tales of Symphonia 2 - Skit Mugshots

With the information I got from [delroth](http://blog.delroth.net/2011/06/reverse-engineering-a-wii-game-script-interpreter-part-2/) I was able to write a quickbms-script to extract the ar.dat. The format of the extracted images is the standard wii tpl one ([http://hitmen.c02.at/files/yagcd/yagcd/ ... l#sec15.35](http://hitmen.c02.at/files/yagcd/yagcd/chap15.html#sec15.35)).

Since I don't have much experience with writing such scripts it would be nice if someone could check the script and maybe give some recommendations about it. The format of the archive is as follows:

> Reply from delroth
>
> The format is the following (in a C-like language):

struct header {
uint32_t nfiles;
uint32_t data_offset[nfiles];
};

And here is my first bmsscript

```
#All the real work was done by delroth. I only used his extractor to make this.
#Tales of Symphonia ar.dat extraction

endian big
get nfiles long
for i = 1 to nfiles
	get fileoffset long
	savepos currentpos
	get filesize long
	if filesize > 0
		math filesize -= fileoffset
		log i fileoffset filesize
	else
		get realfsize asize
		math realfsize -= fileoffset
		log i fileoffset realfsize
	endif
	goto currentpos
next i
```
