## Post #1
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2013-05-11T20:07:53+00:00
- Post Title: WildStar Data Mining

Greetings!

Anyone can help me to get the WildStar Client File extracted?

The File is called: ClientData.archive and there is an file: ClientData.index

The File contain some *.tex files and Folders etc. 

I attached the 2 MB Cuted File + Index File.

[http://www.multiupload.nl/07W6IOUBT4](http://www.multiupload.nl/07W6IOUBT4)
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2013-05-30T01:07:20+00:00
- Post Title: WildStar Data Mining

front-ClientData.archive consists of various files,
starting from 0x230 the container has the following structure:
8 bytes - size of previous file
8 bytes - size of next file
x bytes - file (zlib compressed if it starts with 78 9C)

For example:
from 0x713C0 to 0x130D7F (0xBF9C0 bytes) there's a zlib compressed file.
The uncompressed file is a 3d model, here you can download it (Cine_Aurin_Tree01.scn):
[http://www.mediafire.com/?p7bepdiirpjbk94](http://www.mediafire.com/?p7bepdiirpjbk94)
## Post #3
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2013-06-01T20:37:26+00:00
- Post Title: WildStar Data Mining

This is from [http://www.wildstar-online.com/](http://www.wildstar-online.com/) ?

If so, I want to crack this code 

Y.
## Post #4
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2013-06-02T03:22:56+00:00
- Post Title: WildStar Data Mining

Hey ehnoah, have you already checked out this thread?
[http://www.ownedcore.com/forums/mmo/wil ... lorer.html](http://www.ownedcore.com/forums/mmo/wildstar/413478-wildstar-beta-file-explorer.html)
I think you might like it
## Post #5
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2013-06-05T19:57:20+00:00
- Post Title: WildStar Data Mining

thnx herbertt
## Post #6
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2013-10-10T08:04:23+00:00
- Post Title: WildStar Data Mining

Hi guys, been busy with this.

Once you extracted the textures from the game files, you can look at them with this little tool: just double click on the tex file and choose the Wildstar Tex Viewer. You can save the image as png file.

[http://www.ownedcore.com/forums/attachm ... viewer.zip](http://www.ownedcore.com/forums/attachments/mmo/wildstar/15688d1381270539-wildstar-beta-file-explorer-wildstartexviewer.zip)

Hope you like it.

Still need to break my brain on the m3 files, which, I think, contain the 3D model .

T.
## Post #7
- Username: jmgg
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Sep 16, 2013 4:20 am
- Post datetime: 2015-09-30T17:27:12+00:00
- Post Title: WildStar Data Mining

I download the game and the viewer
[http://www.ownedcore.com/forums/mmo/wil ... lorer.html](http://www.ownedcore.com/forums/mmo/wildstar/wildstar-bots-programs/448310-wildstar-studio-file-viewer-explorer.html)
I can't view the m3 model files. The program crashes. I've tried even with an old client version but nothing...
any ideas?
## Post #8
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-10-01T20:35:31+00:00
- Post Title: WildStar Data Mining

Same thing happens to me, I 'm looking at the code, but it is c++, which I know nothing of :/

So I need to convert it to somehign I can use, like extract all the files from the archive

...

Keep you posted.

T
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-02T09:46:29+00:00
- Post Title: WildStar Data Mining

> Reply from TaylorMouse
>
> Same thing happens to me, I 'm looking at the code, but it is c++there's sources for the Wildstar fileexplorer?
Could you give a dwonload link?
## Post #10
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-10-02T11:31:50+00:00
- Post Title: WildStar Data Mining

[https://bitbucket.org/mugadr_m/wildstar ... ?at=master](https://bitbucket.org/mugadr_m/wildstar-studio/src/d632411c59b0fbe5879f03018cc37e5353f2703d/WildstarStudio/?at=master)

source is in bitbucket, I got it through git

T.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-02T22:32:53+00:00
- Post Title: WildStar Data Mining

@T.: thx for the link - appreciated!
@jmgg: do you have an m3 sample for me that causes a crash?

Thank you for the sample, jmgg!

As for the the code the models seem to be handled here: 
```
	M3Model model(path, file);
	model.loadForExport();
	model.exportAsObj(true);
}
```
dunno, whether I'll find the time to care for it.

For now it's easier for me to use hex2obj (not sure about uvs, probably wrong):



Face_01_Aurin_F.jpg (152.07 KiB) Viewed 184 times
## Post #12
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-10-03T22:10:38+00:00
- Post Title: WildStar Data Mining

So I'm just interested in exporting all the objects from the archive / index file and getting my hands on the m3 and tex files ofcourse

So shakotay2, can you give me a push in the right direction, I used an earlier version which is called Wildstar browser, it allows me to browse the archive files, and export the files, one by one, but when I open them they are all starting with 
5D 00 00 00

I presume they are compressed?

Second thing, how did you find the start offset of the vertices and faces in that m3 sample file ?

T.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-05T10:42:37+00:00
- Post Title: WildStar Data Mining

> Reply from TaylorMouse
>
> So shakotay2, can you give me a push in the right direction, I used an earlier version which is called Wildstar browser, it allows me to browse the archive files, and export the files, one by one, but when I open them they are all starting with 
5D 00 00 00

I presume they are compressed?So you say the exported obj for example start with 5D 00 00 00? That would be strange.
Otherwise I'd guess the Wildstar browser needs ClientData.index from old client.

The WildstarStudio seems to extract from ClientData.index as follows:
.tex -> as Bitmap or PNG
.tbl -> .cs
.area -> ToObj 
.bin -> .cs
.m3 -> .obj

(but I need a working compiled WildstarStudio exe. There's some caveats.
edit: here's where it crashes (it exits the last thread on trying to create it):



WS_before_crash_.jpg (226.65 KiB) Viewed 162 times


Guess the problem is located in awesomium.dll so I need the SDK, but a version prior to 1.7.5.1)

> Second thing, how did you find the start offset of the vertices and faces in that m3 sample file ?using my fastest method: trial&error 

Now that I got them I'd say search for 740065007800  // that is 'tex'
then the vertices will follow about 1k after that finding.

Face indices start address to be found after vertexstart + vertexcount*48
maybe some bytes to scroll down past the last 808080FF 0000FF00.

Search for DA 03 00 00 to maybe find some sort of magic table containing the counts.
(My todays $100 tip?) From that the FIs count should be 4260 (instead of 4000).
