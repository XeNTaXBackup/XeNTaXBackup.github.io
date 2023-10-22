## Post #1
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2012-07-04T18:02:01+00:00
- Post Title: REQUEST: Star Trek Online .mest file format

If this thread needs to be moved to an archive format request thread then so be it

As we know so far, the .mset file the MMO Star Trek Online uses is an archive format, containing 2 file, a .geo2 file and a .lodinfo file, now id like to start work with someone to bring into being a program or even a Noesis plugin that will alow us to extract these files from the .mset file, so that we may then start to study the .geo2 and .lodinfo files to then build a reliable 3d model viewer. The texture files (.wtex) are a simple modified .dds file, which can easily be extracted through the use of QuickBMS.

if anyone wants a .mset file to look at in full i will provide one. if you want to extract from the .hogg files yourself, looke up a program called "Gibbed.Champions.Bacon.exe" you should be able to fine it, if not leave a post and i will host a link to the program and the QuickBMS script which allows for texture conversions after extraction.

here is a screenshot of a .mset file open in hex workshop, i hope this is usefull


heres is a download of a .mset file from STO for people to look at in more detail: [http://www.mediafire.com/?rswxwae9o221x94](http://www.mediafire.com/?rswxwae9o221x94)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-05T11:26:01+00:00
- Post Title: REQUEST: Star Trek Online .mest file format

I think it's model file.
## Post #3
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2012-07-05T11:31:42+00:00
- Post Title: REQUEST: Star Trek Online .mest file format

> Reply from Ekey
>
> I think it's model file.
I just wonder, where the indices are stored...
## Post #4
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2012-07-05T11:41:58+00:00
- Post Title: REQUEST: Star Trek Online .mest file format

> Reply from pivke
>
> Ekey wrote:I think it's model file.
I just wonder, where the indices are stored...
The .mset format is a container file, as it lists 2 files inside of it in a hex editor, the .geo2 is the actual model file and the .lodinfo is, well the lod info for the model....
## Post #5
- Username: Carnaxus
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 17, 2011 9:00 am
- Post datetime: 2014-01-01T04:28:35+00:00
- Post Title: REQUEST: Star Trek Online .mest file format

Sorry for the necrobump, I won't bump this more than once.  I'm wondering if this has ever been resolved and, if so, where the answer is hiding.  Thanks for your time
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-01-01T09:23:05+00:00
- Post Title: REQUEST: Star Trek Online .mest file format

as from the mset sample, at address 0x1E0, there seems to be 3 floats but then I don't see any structure in the data. Maybe compressed, encoded, whatever. So guess noone will waste time on this.

But you might have a look into this thread,
[viewtopic.php?f=10&t=4225&p=85930&hilit=mset#p85930](http://forum.xentax.com/viewtopic.php?f=10&t=4225&p=85930&hilit=mset#p85930)
see flarespire's  post of Tue Jun 04, 2013 4:19 pm
