## Post #1
- Username: Eeh
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jul 27, 2007 8:40 am
- Post datetime: 2007-07-27T17:01:17+00:00
- Post Title: Bust A Move Ghost PSP

This is the main datafile of the game. Dont know if any other games have this .uas format. Seems like it isn't compressed at all..

Hey Strobe, JaederNaub couldn't grab the PMF video out of it!

[http://www.megaupload.com/?d=MP36Y81E](http://www.megaupload.com/?d=MP36Y81E)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-08-02T06:40:44+00:00
- Post Title: Bust A Move Ghost PSP

The link does not seem to work.
## Post #3
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2007-08-04T15:02:56+00:00
- Post Title: Bust A Move Ghost PSP

The link does actually work. 

When I first looked at this file, I figured it'd be an archive, because of the header. However, further investigation made me realize that it's a MIDI header, a .mid file in other words. So, you can actually rename the file to .mid and play in winamp... just ~40 seconds though, which isn't very much for a file of over 20MB.

So looking a little closer at the file made me see that there's several mid-files located in the beginning of it, some null padding between them I believe. But the midi files stop appearing, and I'm not sure what's next. 

Also, I'm not too sure how the midi format works, even though the header is really simple (check out [http://www.wotsit.org/download.asp?f=midi&sc=239535413](http://www.wotsit.org/download.asp?f=midi&sc=239535413)), I can't seem to cut a single mid out by myself.. otherwise I would've created a BMS for that purpose at least.
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-08-04T15:32:08+00:00
- Post Title: Bust A Move Ghost PSP

So perhaps there is another file containing the directory?
## Post #5
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2007-08-04T15:54:02+00:00
- Post Title: Bust A Move Ghost PSP

> Reply from Rheini
>
> So perhaps there is another file containing the directory?
That might be the case. 

Eeh: check for a file with a similiar filename, maybe with another file extension.
## Post #6
- Username: Eeh
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jul 27, 2007 8:40 am
- Post datetime: 2007-08-04T17:53:47+00:00
- Post Title: Bust A Move Ghost PSP

> Reply from PXR
>
> Rheini wrote:So perhaps there is another file containing the directory?

That might be the case.
As i said, its the main - and only - datafile of the game.
There other files are all executables.

I could rip those midis with WinRipper.
## Post #7
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-08-05T08:31:24+00:00
- Post Title: Bust A Move Ghost PSP

Maybe there's a dictionary at the end of the file?
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-08-06T08:13:19+00:00
- Post Title: Bust A Move Ghost PSP

No, it seems all files have been saves in sequence, with some padding applied. 
There are GIM files, VAG files, one PMF file, some unknown 'PPHD' files and a chunk of MIDI files ('MThd'). 

Perhaps there still is another file that acts as a list of the files in the archive as already suggested? Check your folder for more files that could serve this purpose .

Another way would be to determine all possible file formats in the archive and then work your way through the archive, extracting and identifying as you go. Most (media) formats save their own size somewhere, so you can calculate the position of the next file in the archive (taking into account the padding) and ID that one ... and so on.

The PMF file is just the Taito logo-intro by the way.
## Post #9
- Username: OverLord115
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-08-06T08:59:58+00:00
- Post Title: Bust A Move Ghost PSP

Oh and there's some VAG files in there (audio), some PNG files (graphics that are in some odd PNG format). Padding is done up to blocks of 2048 bytes. 

Use the nice MFAudio from an unknown author to convert VAG to WAV and back: 

[http://www.xentax.com/uploads/author/mr ... FAudio.zip](http://www.xentax.com/uploads/author/mrmouse/MFAudio.zip)
## Post #10
- Username: Eeh
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jul 27, 2007 8:40 am
- Post datetime: 2007-08-09T09:13:52+00:00
- Post Title: Bust A Move Ghost PSP

I looked closely and it quite seems like file positions of the archive are hardcoded into the executables.

files in the iso:

```
PSP_GAME\ICON0.PNG
PSP_GAME\PARAM.SFO
PSP_GAME\PIC0.PNG
PSP_GAME\PIC1.PNG
PSP_GAME\SYSDIR\BOOT.BIN
PSP_GAME\SYSDIR\EBOOT.BIN
PSP_GAME\SYSDIR\UPDATE\DATA.BIN
PSP_GAME\SYSDIR\UPDATE\EBOOT.BIN
PSP_GAME\SYSDIR\UPDATE\PARAM.SFO
PSP_GAME\USRDIR\BAMG.UAS
PSP_GAME\USRDIR\module\audiocodec.prx
PSP_GAME\USRDIR\module\mpeg.prx
PSP_GAME\USRDIR\module\mpegbase.prx
PSP_GAME\USRDIR\module\sc_sascore.prx
PSP_GAME\USRDIR\module\videocodec.prx
```

And that`s all!

question: what do i use to view/convert GIM files?
## Post #11
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-08-09T11:19:36+00:00
- Post Title: Bust A Move Ghost PSP

> Reply from Eeh
>
> I looked closely and it quite seems like file positions of the archive are hardcoded into the executables.
Oh my god. 

> Reply from Eeh
>
> question: what do i use to view/convert GIM files?
Extract and attach them
