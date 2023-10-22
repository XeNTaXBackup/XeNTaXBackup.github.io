## Post #1
- Username: Golubowski
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 15, 2015 11:32 pm
- Post datetime: 2016-09-09T16:11:42+00:00
- Post Title: One Piece Burning Blood

I'd like to extract the 3d models of the game One Piece Burning Blood. When i extract the .cpk files i get a bunch of .scz files and i don't know how to open them...    I'd appreciate any help.

Here's a link for a sample file: [http://www.mediafire.com/download/u61ew ... sample.rar](http://www.mediafire.com/download/u61ewjr755dqaj8/sample.rar)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-12-25T18:24:47+00:00
- Post Title: One Piece Burning Blood

They can be dumped from ram.
## Post #3
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2016-12-28T15:14:36+00:00
- Post Title: One Piece Burning Blood

> Reply from chrrox
>
> They can be dumped from ram.
...

Can you release the plugin/converter you used?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-12-28T22:19:39+00:00
- Post Title: One Piece Burning Blood

If someone finds the decompression code for these games ill clean up the code and post it.
## Post #5
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2016-12-29T08:15:25+00:00
- Post Title: One Piece Burning Blood

The game .cpk archives can be decompressed using the same tools as Xenoverse, that gives a lot of .scz files.
I haven't tried but it seems that these .scz can be processed with this quickBMS script: [http://forum.17907.n7.nabble.com/file/n1422/OPBB.txt](http://forum.17907.n7.nabble.com/file/n1422/OPBB.txt)
Now I think your script is needed to load the npk and similar files.
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-12-29T10:11:38+00:00
- Post Title: One Piece Burning Blood

no the .scz files can not be extracted.
that script does not work.
[http://zenhax.com/viewtopic.php?t=3053](http://zenhax.com/viewtopic.php?t=3053)
## Post #7
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2016-12-29T10:45:01+00:00
- Post Title: One Piece Burning Blood

> Reply from chrrox
>
> no the .scz files can not be extracted.
that script does not work.
http://zenhax.com/viewtopic.php?t=3053

Ook, so the remaining problem is to unpack the .scz files.

Sorry for the question, but what did you do to dump the models from ram on the PC version?
If it's possible to get them using your way we can avoid to decrypt the .scz
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-12-29T13:24:33+00:00
- Post Title: One Piece Burning Blood

you need to find them using a hex editor.
I use process hacker [http://processhacker.sourceforge.net/](http://processhacker.sourceforge.net/)
to dump the memory to disk then search using a hex editor for the files.
## Post #9
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2016-12-29T13:34:56+00:00
- Post Title: One Piece Burning Blood

I'll try!
The only thing I ask is what do I have to search for using the Hex editor?
I don't think they are saved as .fbx files!

How do I know I found a 3D model?

EDIT
From what I looked at, it's possible to obtain unpacked (npk, npki...) files using the dump, isn't it right?
I still haven't understood how to do but I only did a fast check!

After that you script loads these files into Noesis, am I correct?

EDIT2
From what you load here [https://i.snag.gy/HCmj5s.jpg](https://i.snag.gy/HCmj5s.jpg) , it seems that npak is what you are searching for, and I think I even understood how to extract them from the dump.
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-12-29T22:05:18+00:00
- Post Title: One Piece Burning Blood

You need 3 files.
npak(npk), npki, npkv
## Post #11
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2018-12-27T09:35:50+00:00
- Post Title: One Piece Burning Blood

Are there any news about this game extraction?

I've seen that some progresses on the game compression were made some time ago, but nothing more after that.
## Post #12
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2019-01-05T23:03:31+00:00
- Post Title: One Piece Burning Blood

For God,  please share the script for this game
## Post #13
- Username: asdzx34
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Apr 16, 2019 6:52 pm
- Post datetime: 2019-04-18T15:36:07+00:00
- Post Title: One Piece Burning Blood

Does anyone have a scz extract file?
## Post #14
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2019-06-27T17:17:43+00:00
- Post Title: One Piece Burning Blood

> Reply from chrrox ↑Thu Dec 29, 2016 6:19 am at Thu Dec 29, 2016 6:19 am
>
> 
If someone finds the decompression code for these games ill clean up the code and post it.

The cmp_scz script decompress the files perfectly  [http://aluigi.altervista.org/bms/cmp_scz.bms](http://aluigi.altervista.org/bms/cmp_scz.bms)
Please share the script, please this game has the best One Piece models, yes I know about the mobile dance game, but those are low poly.
## Post #15
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2020-04-21T21:53:09+00:00
- Post Title: One Piece Burning Blood

I too would like this script. There's a select number of characters who only appear in this game and I would like to acquire their models.
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-04-22T07:51:29+00:00
- Post Title: Re: One Piece Burning Blood

People like scripts, yeah.  The unpacking script is available since about a year now. Why not check the resulting npki?
.



character_052-npki.png (120.9 KiB) Viewed 86 times
## Post #17
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-04-22T07:59:12+00:00
- Post Title: Re: One Piece Burning Blood

Hi there, Andy 97/Hiroshi and I made a Noesis plugin for this format. [viewtopic.php?f=16&t=21863#p160926](https://forum.xentax.com/viewtopic.php?f=16&t=21863#p160926)
Thanks for your tutos shakotay and chrrox.
