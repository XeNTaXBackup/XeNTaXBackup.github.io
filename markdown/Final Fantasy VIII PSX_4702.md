## Post #1
- Username: Blyss
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 07, 2010 8:18 am
- Post datetime: 2010-07-03T21:15:32+00:00
- Post Title: Final Fantasy VIII PSX

Hello everyone. I am interested in extracting the data from the PSX version of Final Fantasy VIII. Specifically I am after the audio, but the way the archive is laid out I think it's pretty much going to be an all at once endeavor. I have been googling for about an hour and I only found one defunct attempt at this and unfortunately the executable and source for that attempted extractor is unavailable, so I guess it is starting from scratch. 

On any given disc from the game you will find three files: the system.cnf, the PSX executable and FF8DISCx.IMG where x is the disc number. So far from looking at the IMG in hex I have noticed that at least some of the files in it seemed to be indicated by a "SMN" header, of which I found 17000 ish occurrences of. There is also a "SMJ" that seems to mostly precede padding or something. Other than that I can find the text strings "SHUN_MORIYA" and "AKAO" at many locations within. As far as determining exactly what these strings are indicating, I am running into trouble. Looking at it again now, I wonder if "SMN" marks a beginning or end of a packed file. It wouldn't surprise me if some kind of compression is going on too. 

This would be my first major attempt at deciphering a large archive like this from scratch, and I would greatly appreciate the help of any like minded individuals. I have enough coding experience to hack up an extractor IF I knew what these headers and text strings were indicating.

~Blyss
## Post #2
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2010-07-04T18:53:36+00:00
- Post Title: Final Fantasy VIII PSX

I can only link you to the [qhimm forums](http://forums.qhimm.com/), this is THE place when it comes to hacking the FF games. They are mostly after the PC versions of the games but Im sure there are some guys with extensive knowledge about the FF8 PSX version. Just ask there.
Im sorry for just pointing to another forum instead of really helping out
## Post #3
- Username: Blyss
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 07, 2010 8:18 am
- Post datetime: 2010-07-05T04:21:34+00:00
- Post Title: Final Fantasy VIII PSX

Yeah, some of my Google searches landed me there and I noticed most of what they had was regarding the PC version. I noticed they had a MIDI extractor for the PC version but A - I don't own the PC version and B - I've heard the MIDI versions of the tracks in the PC demo. They suck. Anyway, I will probably ask around over there when I get some time, I just figured I'd post here first because I was already a member. Thanks for the reply though!
~Blyss
