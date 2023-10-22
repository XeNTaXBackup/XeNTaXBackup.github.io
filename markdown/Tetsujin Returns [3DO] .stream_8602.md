## Post #1
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-03-21T06:37:33+00:00
- Post Title: Tetsujin Returns [3DO] .stream

Tetsujin Returns (JP) - aka Iron Angel of the Apocalypse: The Return (US) for 3DO platform from 1995.

So we have some ancient file types which no one ever heard of, or at least I couldn't find any helpful info.
I'm really not expecting much help in this case due to rather limited research done on certain 3DO files, but would be nice to find a solution here cause I appreciate this game for its pure dark sci-fi setting and atmospheric ambient/techno soundtrack.

Both audio and video (pre-rendered FMVs) have a ".stream" extension.

There are 12 tracks (~56mb).

A couple things that I came across while doing the research that might be worth to mention: 

1) [http://sourceforge.net/news/?group_id=43499](http://sourceforge.net/news/?group_id=43499)
In 2002 MPlayer claims to have support for 3DO stream files. Well, I downloaded the most recent version and nothing happens, "unable to play media".

2) [http://www.squareenixmusic.com/composer ... ndex.shtml](http://www.squareenixmusic.com/composers/miura/index.shtml)

> He subsequently exploited streaming technology to create an atmospheric music and sound effects soundtrack for the 3DO's Iron Angel of the Apocalypse titles.
The guy mentions streaming technology for 3DO, hence the ".stream" file extension I guess, which maybe/might ring the bell for someone... I just thought to throw it in here as well.

. . . 

Here's a sample music file (3mb) and video (19mb) if anyone wants to take a look. 

[http://www.mediafire.com/?ll6yu1liwwm9x6b](http://www.mediafire.com/?ll6yu1liwwm9x6b)

[http://www.mediafire.com/?qfybvy55861xb2n](http://www.mediafire.com/?qfybvy55861xb2n)
## Post #2
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2012-03-22T02:35:56+00:00
- Post Title: Tetsujin Returns [3DO] .stream

The audio is 3DO SDX2.  Change the extension to .STR and try this [updated vgmstream plugin](http://www.mediafire.com/?hxj1d2x3e1392rt).  When available, I recommend the official vgmstream builds since they contain some additional codecs.
## Post #3
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-03-22T06:30:59+00:00
- Post Title: Tetsujin Returns [3DO] .stream

Thank you, but after using this latest Winamp plugin and renaming extension to .STR the files are still un-playable. 
Maybe I'm not doing something right?
After putting in_vgmstream.dll inside Plugins folder (or even the main Winamp folder) it just doesn't show up on the list of plugins when going to Options > Preferences > Plug-ins. 
Strange... I've got the registered version of the player and running it 'As administrator'.
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2012-03-22T08:48:02+00:00
- Post Title: Tetsujin Returns [3DO] .stream

The official build for r975 is up [here](http://hcs64.com/files/vgmstream/) now.  Check the readme for installation instructions if you haven't used in_vgmstream before.
## Post #5
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-03-22T17:03:21+00:00
- Post Title: Tetsujin Returns [3DO] .stream

OMG it worked!
The external dlls were essential for it to run and that's what I was missing. 
I used vgmstream before but only with f2k, where installation is a bit more straightforward (at least for me).
Great thanks to both of you! HCS your plugin is a lifesaver 

EDIT: Surprisingly this method didn't work for the first Tetsujin (Iron Angel of the Apocalypse).

Not 3DO SDX2 anymore?

Sample file:

[http://www.mediafire.com/?tuw9fi4xe37j279](http://www.mediafire.com/?tuw9fi4xe37j279)
## Post #6
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-08-28T03:30:54+00:00
- Post Title: Tetsujin Returns [3DO] .stream

Just a quick update that the problem with the videos is solved. In a work-around way.

I wanted to have them in any viewable format and it became possible with Windows-95 jap version of Tetsujin Returns. All videos are in AVI format here. 

Apparently it's a pretty rare version and mobygames didn't have it listed as one of the platforms for which the game was released. 

Got it from here: [http://www.suruga-ya.jp/database/145000160001.html](http://www.suruga-ya.jp/database/145000160001.html)
## Post #7
- Username: Herf
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Mar 02, 2012 2:47 pm
- Post datetime: 2017-02-02T01:41:22+00:00
- Post Title: Tetsujin Returns [3DO] .stream

I know this is an old thread, but eh:

1. Analyze and extract chunks from .stream files using ZStream Reader.
2. Import .sound files into Audacity using Import Raw function (Little-endian, Mono, 22.050 khz).
3. Save in whatever format you want.
4. Enjoy.

This applies to original Tetsujin. For Tetsujin Returns I'd recommend dealing with the PC version for now unless I find a better solution.
