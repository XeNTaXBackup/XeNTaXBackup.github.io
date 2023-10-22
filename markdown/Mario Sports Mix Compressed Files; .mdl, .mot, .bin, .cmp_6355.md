## Post #1
- Username: mnsg
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Apr 05, 2011 1:36 am
- Post datetime: 2011-04-04T18:08:05+00:00
- Post Title: Mario Sports Mix Compressed Files; .mdl, .mot, .bin, .cmp

Hello, and this is my very first post on these forums.

My full user name is Mario & Sonic Guy, but my user name is often abbreviated M&SG or MnSG.  My specialty is texture hacks, which I've done for three different Wii titles; Super Smash Bros. Brawl, Mario Kart Wii, and New Super Mario Bros. Wii.

Anyway, I came here in an attempt to get help on some files that I'm working with.

The game, Mario Sports Mix, has been out in my area for nearly two months, while it has been out in Japan for over 4 months.  However, I haven't seen any discussions involving that game's files.  For weeks, I've been trying to get some answers for reading the files, but I haven't gotten anywhere by any means.

You see, the contents of the Mario Sports Mix ISO use an unknown kind of compression, which hasn't been figured out yet.  What I do know is that the game does contain MDL0, TEX0, BRRES, and BRSTM files; all of them being present on the three Wii titles that I've mentioned above.

The file extensions that I've seen in the Mario Sports Mix ISO include...

1: .mdl - Character model files.
2: .mot - Character animation data files.
3: .bin - Frequently used for various files, including stages and sports objects.
4: .cmp - Used on a few files, such as the strap loader.

There are also some files that end with .bnr and .arc.

I was hoping that someone out there can take his/her time to work with those files and figure out this unknown compression.  I'm hoping that if this request gets pulled off, it'll be possible to hack the game itself.

The download link below will contain one of each of the four file types that I've mentioned above; .mdl, .mot, .bin, .cmp.

[http://www.megaupload.com/?d=4U3KXGJM](http://www.megaupload.com/?d=4U3KXGJM)
## Post #2
- Username: mnsg
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Apr 05, 2011 1:36 am
- Post datetime: 2011-05-01T15:12:53+00:00
- Post Title: Mario Sports Mix Compressed Files; .mdl, .mot, .bin, .cmp

It'll soon be a full month since I've posted this thread, and I'm pretty surprised by the lack of replies.  Anyway, during the last set of weeks, I did come into contact with RVLution member, Treeki, who told me the issue about Mario Sports Mix's compression method.  He also gave me an incomplete decompressor (incomplete, because it crashes with certain files), which enabled me to look at a decent amount of the compressed files.

Now, from what I've seen, the compression that Mario Sports Mix uses is quite unique, since the file size of the compressed files is always divisible by 32 bytes.

Regarding the decompressing results...

.mdl: A lot of the .mdl files are actually BRRES files, with the exception of Menu.mdl and Tour.mdl, which are ARC files containing BRRES archives.

.mot: Same as with .mdl, with the exception of Menu.mot and Tour.mot.

.bin: The stage BIN files are actually BRRES files.  I also looked at the contents inside the lyt folder (which is in the root of the ISO).  The BIN files in that folder are actually ARC files which contain TPL contents.

.cmp: I did try to look into those files, but with no luck.

The good news is that when the .mdl, .mot, and .bin files are decompressed, they can be viewed with the SZS Modifier, along with BrawlBox.

Sadly, I wish that I could post more file examples, but it's illegal to distribute ISOs.

Anyway, the main challenge is being able to decompress every file in the Mario Sports Mix ISO, along with being able to recreate this unusual compression method.  For those who are still doing this requested objective, keep up the good work.
## Post #3
- Username: mnsg
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Apr 05, 2011 1:36 am
- Post datetime: 2011-06-01T11:44:37+00:00
- Post Title: Mario Sports Mix Compressed Files; .mdl, .mot, .bin, .cmp

Thread bump.  Just letting people know that I'm still following this post.

By the way, if any progress does get made with cracking this compression, be sure to input the information here.
## Post #4
- Username: mnsg
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Apr 05, 2011 1:36 am
- Post datetime: 2011-09-01T18:53:32+00:00
- Post Title: Mario Sports Mix Compressed Files; .mdl, .mot, .bin, .cmp

With the summer ending, I'll pretty much bump this thread again.  Hopefully something might come up during this time.
## Post #5
- Username: ashleyjames222
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 01, 2011 3:01 pm
- Post datetime: 2011-12-01T07:28:42+00:00
- Post Title: Mario Sports Mix Compressed Files; .mdl, .mot, .bin, .cmp


## Post #6
- Username: Misawa Hajime
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Aug 23, 2014 3:23 pm
- Post datetime: 2014-08-23T07:29:11+00:00
- Post Title: Mario Sports Mix Compressed Files; .mdl, .mot, .bin, .cmp

> Reply from mnsg
>
> It'll soon be a full month since I've posted this thread, and I'm pretty surprised by the lack of replies.  Anyway, during the last set of weeks, I did come into contact with RVLution member, Treeki, who told me the issue about Mario Sports Mix's compression method.  He also gave me an incomplete decompressor (incomplete, because it crashes with certain files), which enabled me to look at a decent amount of the compressed files.

Now, from what I've seen, the compression that Mario Sports Mix uses is quite unique, since the file size of the compressed files is always divisible by 32 bytes.

Regarding the decompressing results...

.mdl: A lot of the .mdl files are actually BRRES files, with the exception of Menu.mdl and Tour.mdl, which are ARC files containing BRRES archives.

.mot: Same as with .mdl, with the exception of Menu.mot and Tour.mot.

.bin: The stage BIN files are actually BRRES files.  I also looked at the contents inside the lyt folder (which is in the root of the ISO).  The BIN files in that folder are actually ARC files which contain TPL contents.

.cmp: I did try to look into those files, but with no luck.

The good news is that when the .mdl, .mot, and .bin files are decompressed, they can be viewed with the SZS Modifier, along with BrawlBox.

Sadly, I wish that I could post more file examples, but it's illegal to distribute ISOs.

Anyway, the main challenge is being able to decompress every file in the Mario Sports Mix ISO, along with being able to recreate this unusual compression method.  For those who are still doing this requested objective, keep up the good work.
But I still can not open my mot file....
