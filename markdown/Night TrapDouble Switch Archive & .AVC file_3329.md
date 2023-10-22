## Post #1
- Username: HarroSIN
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 26, 2009 1:56 pm
- Post datetime: 2009-01-28T23:54:24+00:00
- Post Title: Night Trap/Double Switch: Archive & .AVC file

Hello, just signed up here, but I'll get right to the point.

I've been trying (and failing) to understand this archive/video file type for sometime. It's from the Windows/MS-DOS PC version of the FMV action game, [Night Trap](http://en.wikipedia.org/wiki/Night_Trap). It's 'sequel,' [Double Switch](http://en.wikipedia.org/wiki/Double_Switch), also uses a similar container. The file in question ends with the extension .AVC (not related to the MPEG-4 or H.264 video codec, as these games were available around 1994). I've tried everything, and I can't seem to find any clue on where .AVC comes from: the file headers seem to have no rhyme or reason in relation to each other, so I'll break it down with some examples of what I've noticed so far:

Night Trap is a 16-bit DOS executeable. The videos are stored in three extension-less archives: NTMOVIE (the main game), CRMOVIE (the credits sequence), and LOGMOVIE (the developer logo sequence). These may or may not derive from the aforementioned .AVC, rather, these extension-less archives may contain many .AVC files (at least NTMOVIE). I have an example, CRMOVIE, [uploaded here](http://www.moccio.net/files/examples/CRMOVIE) (13.9 megabytes).

Double Switch is a 32-bit Windows executeable utilizing DirectX. Unlike Night Trap, everything but the actual in-game video sequences are found in various folders on the CD-ROMs. For the in-game video sequences, they reside in a huge archive called DSDISK1.GAM (or DSDISK2.GAM or 3 depending on which disk is in the drive). Some examples of this game's movie files: DPLOGO.AVC, which is the developer's logo, can be [downloaded here](http://www.moccio.net/files/examples/DPLOGO.AVC), and ALEXSTIL.AVC, which is most likely a single frame (acting as background artwork when the game is idle, I believe, as it is only 16K) can be [downloaded here](http://www.moccio.net/files/examples/ALEXSTIL.AVC).

I am more interested in the Night Trap archive files than I am the Double Switch ones, only mentioning the .AVC files because there may be a link. As for any real details, the only solid information I could find on the technical side is that the videos are compressed by a system called "DigiChrome," which may or may not be a gimmick for an actual video codec or just a sly name for use in marketing (DigiChrome is mentioned on the box as a 'revolutionary system').

I would really appreciate any details concerning either the NTMOVIE/CRMOVIE archives, or the .AVC file type.

Thanks!
## Post #2
- Username: HarroSIN
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 26, 2009 1:56 pm
- Post datetime: 2009-02-01T23:32:09+00:00
- Post Title: Night Trap/Double Switch: Archive & .AVC file

Anyone? Nobody's heard of this format? (Shameless bump).   
I found out that other games published by this company also use this format (specificly the Windows versions of [Corpse Killer](http://en.wikipedia.org/wiki/Corpse_Killer) and [Supreme Warrior](http://en.wikipedia.org/wiki/Supreme_Warrior)), as well as the Macintosh release of Night Trap (which I recently acquired; also has the odd extension-less archives).
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-02-01T23:50:38+00:00
- Post Title: Night Trap/Double Switch: Archive & .AVC file

This project is going open source soon. [http://www.freedo.org/](http://www.freedo.org/)
you can post on the forum there and ask for some information on the video format.
## Post #4
- Username: HarroSIN
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 26, 2009 1:56 pm
- Post datetime: 2009-02-02T00:32:47+00:00
- Post Title: Night Trap/Double Switch: Archive & .AVC file

Thanks, but I was looking for information about the MS-DOS release, not the 3DO version (which shares the same structure as the Sega one if I remember correctly).
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-02-02T00:53:37+00:00
- Post Title: Night Trap/Double Switch: Archive & .AVC file

nope the 3d0 and pc ones are same file structure sega was different.
## Post #6
- Username: HarroSIN
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 26, 2009 1:56 pm
- Post datetime: 2009-02-02T01:03:11+00:00
- Post Title: Night Trap/Double Switch: Archive & .AVC file

Well, considering the Sega CD/32X/3DO all have many video files, and the PC/Macintosh have only a single huge archive, I think the console variants are more similiar. Do you have any understanding if the 3DO/PC versions have the same file structure?
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-02-02T02:17:45+00:00
- Post Title: Night Trap/Double Switch: Archive & .AVC file

several articles show that the 3do and pc ports should be almost identical. 
here is the common video format used in those days
[http://www.multimedia.cx/film-format.txt](http://www.multimedia.cx/film-format.txt)
I do not have any more information on this.
what are you trying to do bye playing just the video files?
## Post #8
- Username: HarroSIN
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 26, 2009 1:56 pm
- Post datetime: 2009-02-02T03:03:28+00:00
- Post Title: Night Trap/Double Switch: Archive & .AVC file

I'm trying to extract files from the extension-less archive on Night Trap's PC CD-ROM. I mentioned the .AVC files because they are what I thought may be included inside the archive. So, yes, I am interested in playing the files, if not, getting some information regarding it so I may try to decode them. The Sega FILM and Sega Cinepak are used in the Sega CD and 32X versions of the game, but not the PC version. These files look nothing like FILM/Cinepak, and as I mentioned, the AVC headers have no relation to each other: there is no ASCII FOURCC signature, nor are any of the header bytes similar between the two examples I provided.
