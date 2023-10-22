## Post #1
- Username: fallorn
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 14, 2005 7:57 pm
- Post datetime: 2005-12-14T12:26:06+00:00
- Post Title: help request P o Persia - Two Thrones music sb0 conversion

Hi, just beat Prince of Persia: The Two Thrones and Im hoping to extract the music. Specifically the song used in the credits (Stuart Chatwood - I Still Love You)

GameExtractor ( [http://www.watto.org/extract/](http://www.watto.org/extract/) ) and Rahly's bigextractor.exe ( [http://www.terrygoodkind.net/~rahly/bgae.php](http://www.terrygoodkind.net/~rahly/bgae.php) ) open up the sound.big file easily, but this leaves me with a bunch of .sb0 files, which are less than useful to me.
I've tried VAG's tools for Warrior Within ( [http://ga-agent.nm.ru/stuff/popwwtools05b.zip](http://ga-agent.nm.ru/stuff/popwwtools05b.zip) ) and Sands of Time ( [http://ga-agent.nm.ru/stuff/popsottools05.zip](http://ga-agent.nm.ru/stuff/popsottools05.zip) ), but both fail in converting the .sb0 files to some usable format. 
somewhere else on the forums ( [viewtopic.php?t=1329](http://forum.xentax.com/viewtopic.php?t=1329) ) I read that the program awave should help me convert these but no matter what combination I try, all I get is a sonic icepick to my brain.
anybody have a clue how to convert this new demonic form of .sb0 files?
(sample attatched as extracted with Rahly's bigextractor.exe)

thanks,
fallorn
[000.rar](https://xentaxbackup.github.io/file/491_000.rar)
## Post #2
- Username: fallorn
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 14, 2005 7:57 pm
- Post datetime: 2005-12-14T12:46:38+00:00
- Post Title: help request P o Persia - Two Thrones music sb0 conversion

Boy, I sure deserve that ultra-noob title under my name to the left... the credits are in .bik format with the music attatched, I think some work with necrotools' fmv extractor and rad tools will yield me the specific song im looking for, something to try in the morning at least. This does not negate the actual problem with the .sb0 files for the rest of the soundtrack, but it does solve the specific problem regarding that particular song that I was attempting to retrieve.
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-14T19:54:17+00:00
- Post Title: help request P o Persia - Two Thrones music sb0 conversion

I don't think sb0 files are actually sounds. Hmm.
## Post #4
- Username: fallorn
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Dec 14, 2005 7:57 pm
- Post datetime: 2005-12-14T23:11:22+00:00
- Post Title: help request P o Persia - Two Thrones music sb0 conversion

Hmmm indeed.  I know that in the past the .sb0's were found to be a variety of PCM. And when I listened to it as a PCM 8 Bit Signed, it  did sound like some kind of garbled musical... what's the word? spike? maybe? but if it was even there it was still pretty garbled, and i was kinda tired, and definitely tired of listening to very loud high pitched static, so i might have been imagining that.  

-fallorn

P.S. the fmv extractor and bink tools did the trick to get it to wav, and a few seconds later winamp moved it into mp3 format. (would have done ogg but my portable mp3 player wont play that file type)
## Post #5
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-12-15T00:04:38+00:00
- Post Title: help request P o Persia - Two Thrones music sb0 conversion

the .sb0 files change with game engine versions, they are the sound, and you can extract the sound from the BIK credits if you use RAD Tools (maker of BInK format). the tools are free for personal use.
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-15T07:14:21+00:00
- Post Title: help request P o Persia - Two Thrones music sb0 conversion

Ah! Good!
## Post #7
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2005-12-16T03:37:45+00:00
- Post Title: help request P o Persia - Two Thrones music sb0 conversion

I'm currently working on a [Prince of Persia trilogy toolset](http://prince.turfster.be) (which will hopefully end up just as powerful in the end as my [BloodRayne](http://vampire.turfster.be) one). Anyway, the current version can extract all in-SB0 sounds for all three games.
I'm still stuck on the ones that refer to external stream files, though.
I know that it's compressed *somehow* (obviously), and I'm pretty sure it's some form of 4bit ADPCM compression, but then I'm completely stuck. I've tried running the data through Benjamin Haisch's xbox adpcm decoder and I've tried to decode it using a PS2 adpcm decoder, but both gave pretty useless output files.

Any ideas/insights/help are/is welcome 

The current version extracts the files tagged as "does not extract correctly" as the raw data with a fake wave header, so if you want to take a look at the data for yourself, just remove/skip the first 44 bytes of the wav file.
## Post #8
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2005-12-16T14:17:57+00:00
- Post Title: help request P o Persia - Two Thrones music sb0 conversion

Hi. I just post here to say that the SB0 files are the SFX ( sound effects ) and there is a .SS0 file that is 232mb! I think that one contains the music. It's called stream.ss0. I would like that you ( or another guy ) managed to extract it...

BTW: I extracted it with Persian Rug because I coudn't extract it with game extractor or MultiEx Commander...
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2005-12-16T21:10:27+00:00
- Post Title: help request P o Persia - Two Thrones music sb0 conversion

> Reply from Turfster
>
> 
 and I'm pretty sure it's some form of 4bit ADPCM compression, but then I'm completely stuck. I've tried running the data through Benjamin Haisch's xbox adpcm decoder and I've tried to decode it using a PS2 adpcm decoder, but both gave pretty useless output files.
Any ideas/insights/help are/is welcome ;)

This week-end I have in mind to write a raw2wave program for many adpcm algorithms (ms, dvi, various gsm, gamecube and possibly others).
But where you have found the codecs and their source code for Xbox and PS2 adpcm?
## Post #10
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2005-12-16T21:42:44+00:00
- Post Title: help request P o Persia - Two Thrones music sb0 conversion

Got the Xbox code from [Benjamin Gorman](http://quick.mixnmojo.com) (see the psychonauts explorer 1.2 source), PS2 ADPCM is basically XA ADPCM with a larger set of delta's, as far as I've been able to figure out.
## Post #11
- Username: dimi
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Apr 29, 2005 8:09 am
- Post datetime: 2005-12-16T22:27:09+00:00
- Post Title: help request P o Persia - Two Thrones music sb0 conversion

Check my post [viewtopic.php?t=692](http://forum.xentax.com/viewtopic.php?t=692)
for XBox ADPCM codec
## Post #12
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2005-12-20T00:41:38+00:00
- Post Title: help request P o Persia - Two Thrones music sb0 conversion

I let the compressed audio streams rest for a moment (it was that or go mad...) and turned to the actual data files.

I've managed to uncompress the BIN files (at least, it seems to give good valid data for the few I've tried that were actually compressed), so I can start working on the actual data file formats now. 
Not that this is of much use to anyone else yet (unless they want to help me figure out the data file formats *hint hint* ), just keeping you informed.
Anyway, the new version is up on my [crappy POP tool site](http://prince.turfster.be)
## Post #13
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2006-04-22T13:31:31+00:00
- Post Title: help request P o Persia - Two Thrones music sb0 conversion

(Not really about the SB0 files, since I'm still stuck on the damn audio format, but this is the best sort of relevant thread to post this in imho  )

Anyway, I figure it's time to finally release version 2.0 of my [POP Toolset](http://prince.turfster.be/). 
Still can't decode all the music/sound files, but, on the other hand, you should be able to extract all textures and static 3D data from (almost) all *wow*.bin files (remember, static level data only, no character meshes or traps). Try to stick to the Game Objects in the list if you want useful files 

It's still pretty hacky, so if anyone runs into any problems with files, drop me a line.

Easiest way to view/export everything that's in the file in one go : 
- Make sure "Write 3D models" and "Clear previous" are not checked on the options page.
- Open the bin file
- hit the extract all objects button
(if you want to export, hit the extract all textures button too)
- go to the display tab
- hit Export data
Voila, you now have an OBJ/3DS file with the same name as the bin file that should contain everything decodeable in the file.

How to use the display tab : 
* LMB on viewscreen looks around
* MMB zooms in-out
* RMB moves on the X/Y plane
* The slider is a multiplier (number is in the lower right corner) for zoom/movement
## Post #14
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-10-07T18:31:43+00:00
- Post Title: help request P o Persia - Two Thrones music sb0 conversion

I found a new version of POpt2t music extracto it's the 0.7 of vag's tools i tried and works great!!!..but....
Any tool to reverse this: .wav/ogg to Sb0?
[t2t_FXex.zip](https://xentaxbackup.github.io/file/894_t2t_FXex.zip)
## Post #15
- Username: SMaz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Feb 26, 2006 9:58 pm
- Post datetime: 2007-02-17T15:09:27+00:00
- Post Title: help request P o Persia - Two Thrones music sb0 conversion

I use Persian Rug to extract the Textures from the Prince. Now I edit the Textures and add some cool Tattoos. How can I import the *.tga File back into the Game ?

Anyone an Idea (like Turfster, seems you managed this ? (Screenshot on [http://prince.turfster.be/](http://prince.turfster.be/))

cya
## Post #16
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2010-05-28T20:37:20+00:00
- Post Title: Re: help request P o Persia - Two Thrones music sb0 conversion

> Any tool to reverse this: .wav/ogg to Sb0?
+1, pls brainbreakers! please do something how to wav is in this sb0 compressed and how can we decompress ?

PoP SoT
there is only tool to extract sb0 and convert it to wav by someone russian VAG but who knows where is he

So here pls help guys how to convert back, i'm with friends are going to translate game and record translated speech and becoz i need it

therefore game is so old and no one can help to do this stuff?

thanks
