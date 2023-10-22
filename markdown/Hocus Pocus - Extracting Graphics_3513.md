## Post #1
- Username: MasterRipper
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 27, 2009 8:33 pm
- Post datetime: 2009-05-27T12:51:31+00:00
- Post Title: Hocus Pocus - Extracting Graphics

Hi guys.

I am new here and must say this is a great site - thank you very much.

I was wondering if someone can help with extracting the audio and graphics from a 1990's game called Hocus Pocus.

I have looked everywhere for the format / information with no luck.

Even some of the software from here doesn't work.

Many thanks in advance.

PS: I own the original, so not the shareware version.

Not sure if I am allowed to up the original game files or not , only about 1-2 MB...
## Post #2
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-27T14:36:06+00:00
- Post Title: Hocus Pocus - Extracting Graphics

Sure you can, it's abandonware:

[http://www.dosgamesarchive.com/download/hpocus.zip](http://www.dosgamesarchive.com/download/hpocus.zip)

It was a great game in it's time. At least, I played a lot in my DOS system hehe

I'll take a look. If I find something I'll tell.
## Post #3
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-27T17:41:51+00:00
- Post Title: Hocus Pocus - Extracting Graphics

This is the .dat file which contains the game resources (7zipped):

[http://www.fileden.com/getfile.php?file ... 3/HOCUS.7z](http://www.fileden.com/getfile.php?file_path=http://www.fileden.com/files/2006/12/25/553903/HOCUS.7z)

No header recognised, very strange header at least.

Some strings at the middle of the file, with texts about the game and apogee.

Will post if anything new discovered...
## Post #4
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-27T17:54:50+00:00
- Post Title: Hocus Pocus - Extracting Graphics

Recognised some headings inside the .DAT

Those of MIDIS and VOC files, so I think we have all the music/sound in the game.

I've attached the findings!
[HocusSound.zip](https://xentaxbackup.github.io/file/2067_HocusSound.zip)
## Post #5
- Username: MasterRipper
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 27, 2009 8:33 pm
- Post datetime: 2009-05-28T05:55:46+00:00
- Post Title: Hocus Pocus - Extracting Graphics

> Reply from Balder
>
> Recognised some headings inside the .DAT

Those of MIDIS and VOC files, so I think we have all the music/sound in the game.

I've attached the findings!

WOW ! Balder, thats great thanks very much ... would love to get the graphics as well but as you say, its some strange format.

Any chance you could post how you got the sounds, so we can all learn something new ?

Balder: I came across this website while browsing last night - maybe can help you ???
[http://www.shikadi.net/old/fileview/](http://www.shikadi.net/old/fileview/)

Another Edit - I managed to somehow get Wombat to read the .DAT file of the Registered Version.   It extracted the PCX graphics and these RAW files, that it labeled as sprites.   Is there a way to get the format ?   So I can convert them to BMP's ?
[SpritesRAW.zip](https://xentaxbackup.github.io/file/2071_SpritesRAW.zip)
## Post #6
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-28T07:51:37+00:00
- Post Title: Hocus Pocus - Extracting Graphics

> Reply from MasterRipper
>
> Any chance you could post how you got the sounds, so we can all learn something new ?

As I said, just used search in hex editor for midi headers and voc headers (among other standard like RIFF) and selected bytes until end bytes. I didn't discover ahything from the format as it's header-less. The need of the game's .exe to extract resources for that tool may confirm my theory: the format is hard-coded inside the game's .exe. I've also seen some offsets in the .exe with a dissasembler.

> Reply from Balder
>
> Another Edit - I managed to somehow get Wombat to read the .DAT file of the Registered Version. It extracted the PCX graphics and these RAW files, that it labeled as sprites. Is there a way to get the format ? So I can convert them to BMP's ?

Yes, I can give a try this evening. In a fast look I didn't see any recognised header (not standard pcx) but bytes doesn't seem to be coded, so I'll test with a tool what happens if we interpret them in groups of three as byte-colours. Let's see if we have luck.

Respect the main format and the tool... Reverse engineering would be necessary to know the offsets. So, if you need to know this dat format, I can get the offsets manually with the hex editor, now that we have both sound and images.  

I'll tell you the results later. see you!
## Post #7
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-28T13:02:52+00:00
- Post Title: Hocus Pocus - Extracting Graphics

Checked: not just raw.

Not all files are multiples or 3 o 4, and furthermore, my tool only produced "noise" when loading one of those. (If you want it or the source code just tell, it doesn't do much yet so I didn't attach)

So it will be very helpfull to have a screenshot of the ghost in Hocus Pocus (for example) in png. With that I can see what coding use this files (I'll have widht, height and colours, so I can start making my calculations).

See you!
## Post #8
- Username: MasterRipper
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 27, 2009 8:33 pm
- Post datetime: 2009-05-28T14:35:23+00:00
- Post Title: Hocus Pocus - Extracting Graphics

Just about it head off home soon.

Will take a few screen shots tonight and up in the morning.

Will do some of Hocus walking around and some of the enemies ( If i can still play the game    )
