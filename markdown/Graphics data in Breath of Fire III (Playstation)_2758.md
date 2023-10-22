## Post #1
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-08-18T17:37:58+00:00
- Post Title: Graphics data in Breath of Fire III (Playstation)?

Hello, all!

I'm attempting to view graphics data from Breath of Fire 3 (Playstation). Virtually all the data on disc is contained in the .EMI archive format, which MultiEx Commander supports via the wiki (thanks to Mr. Mouse for that). 

However, upon opening/unpacking a .EMI file, all I can see are a series of "noname_" files. To illustrate, I'll use a series of screencaps:


Here I'm exploring the "Plchar" folder on the Breath of Fire III disc. I assume there's sprites and sounds for the main characters within this set of archives. Note the file size on PL026.EMI -- 329,728b (329kb?). There's got to be something in there.


This is what I get after unpacking PL026.EMI. The "noname_" file sizes vary widely, and as a matter of fact, they only add up to 323,060b (6668 short of this .EMI archive's total size). Could this be important? Nearly identical situations exist with all the .EMI files on the disc I unpack.


Turning on the preview, I find either nothing, some gibberish, or in this case, as with many of the "noname1" files I've investigated, the text "pBAVI." 


An example of the typical preview of "noname_" files on the Breath of Fire III disc.


A successfully extracted "noname4" file from the same archive. It's 286kb, so something's got to be in there.

Now my question is, is the production of "noname_" files by MultiEx Commander normal? Do users typically have to do some kind of post-processing on these files to mine for graphics data?

Or is MultiEx Commander supposed to pull actual images, sounds, etc., directly from the proprietary file archives, in which case it appears that support for .EMI archives is incomplete thus far?

Any advice anyone can provide is greatly appreciated. I'm aware that the .EMI script developed by Mr. Mouse was specifically meant to handle Breath of Fire IV, and not Breath of Fire III. Perhaps that's the cause? If so, I can provide .EMI archives from Breath of Fire III for the perusal of any gracious guru who happens upon this thread.
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-08-19T07:32:37+00:00
- Post Title: Graphics data in Breath of Fire III (Playstation)?

The graphics of Capcom games like BOF3 and so on have been a troubling issue that would be great if somebody could resolve them.

Also, it is possible a change was made between BOF3 and BOF4. And it could be possible that a compression is used. I have planned to seek a resolve for it by grapping some worthwhile examples.
## Post #3
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-08-19T15:47:24+00:00
- Post Title: Graphics data in Breath of Fire III (Playstation)?

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: Maelstrom
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Dec 23, 2007 4:38 am
- Post datetime: 2008-01-08T20:31:41+00:00
- Post Title: Graphics data in Breath of Fire III (Playstation)?

Graphic of BOF3 is basically a kind of strange tim...
You may view graphic data in raw format 2bpp with nana
32 tiles large... (not byte)

Other file may be viewed using PSicture...
An Italian Translator is secretly working to bring this game to italian and still has made some graphics hack and some tools...
## Post #5
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2008-03-21T18:01:13+00:00
- Post Title: Graphics data in Breath of Fire III (Playstation)?

Thanks Maelstrom! I'm knee-deep in altered-TIM format Chrono Cross textures right now, so BOFIII may be easier to work with than I thought once I'm done with my current project. I'll definitely check this out again!
