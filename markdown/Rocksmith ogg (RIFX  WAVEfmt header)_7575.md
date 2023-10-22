## Post #1
- Username: cml
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Dec 10, 2009 10:49 pm
- Post datetime: 2011-10-27T11:31:18+00:00
- Post Title: Rocksmith ogg (RIFX  WAVEfmt header)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-10-27T21:33:31+00:00
- Post Title: Rocksmith ogg (RIFX  WAVEfmt header)

Hmm, well, ww2ogg 0.13 ([http://hcs64.com/vgm_ripping.html](http://hcs64.com/vgm_ripping.html)) will convert it to standard Ogg Vorbis, but the resulting file is almost certainly wrong, lots of truncated packets.  There's probably a problem with a different set of packed codebooks being used on this game.

[edit]

Ah, actually there is another explanation.  This file doesn't use the shortened Vorbis packets that other files with 0x2A byte vorb chunks (merged with the fmt chunk in this case) have.  I've taken a wild guess as to what other byte in the header represents this, ww2ogg 0.15 will convert this file properly.  I don't know if it will work on other files, though.
## Post #3
- Username: cml
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Dec 10, 2009 10:49 pm
- Post datetime: 2011-10-28T08:02:17+00:00
- Post Title: Rocksmith ogg (RIFX  WAVEfmt header)

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-10-28T08:49:16+00:00
- Post Title: Rocksmith ogg (RIFX  WAVEfmt header)

0.15 Seems to work fine on those, though 0.13 would have worked, too, these use shortened packets and all have the same identification byte that I've been keying off of 0xCB, the special case I added for the other file you uploaded was to only use short packets if the byte != 0x70.  Another 0x2A-byte vorb chunk one I've got that's shortened uses 0xD9.  I don't know how much of this is just coincidence.

In any case, ww2ogg 0.15 should work on these, let me know if anything fails to convert or creates a bad file.
## Post #5
- Username: cml
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Dec 10, 2009 10:49 pm
- Post datetime: 2011-10-28T09:21:54+00:00
- Post Title: Rocksmith ogg (RIFX  WAVEfmt header)

thanks again hcs, i tried convert using ww2ogg 0.15 some files
some convert without errors , these bigger one give error 

C:\ww2ogg 435071557.ogg -o test
Audiokinetic Wwise RIFF/RIFX Vorbis to Ogg Vorbis converter 0.15 by hcs

Input: 435071557.ogg
RIFX WAVE 2 channels 48000 Hz 89704 bps
17046422 samples
- 6 byte packet headers, no granule
- stripped setup header
- external codebooks
- shortened Vorbis packets
Output: test
Parse error: page header truncated

Anyway i dont know why all converted files cant be played in audacity , also ogg players dont play these files
## Post #6
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-10-28T09:39:27+00:00
- Post Title: Rocksmith ogg (RIFX  WAVEfmt header)

Ok, if you upload 435071557.ogg I can try to fix that.

> Anyway i dont know why all converted files cant be played in audacity , also ogg players dont play these files
I don't know what you mean by this.  The files that you uploaded convert fine, and the converted files played without any trouble in audacity.  It is possible that it isn't working in an "ogg player" (can you be more specific?) because the granulepos isn't set correctly.  You can run revorb ([http://yirkha.fud.cz/progs/foobar2000/revorb.exe](http://yirkha.fud.cz/progs/foobar2000/revorb.exe)) on the converted files to correct this.

Maybe you are saying that some files can be played in audacity and some can't?  If so, there is probably an undetected issue in the conversion, please upload the original files for the ones that don't convert properly and I will try to fix it.
## Post #7
- Username: cml
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Dec 10, 2009 10:49 pm
- Post datetime: 2011-10-28T20:38:15+00:00
- Post Title: Rocksmith ogg (RIFX  WAVEfmt header)

after using revorb.exe all works fine .. thanks hcs
## Post #8
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-10-28T22:40:13+00:00
- Post Title: Rocksmith ogg (RIFX  WAVEfmt header)

There is still the question of that 435071557.ogg file you mentioned, which had an error during conversion.  Did you fix the extracted file, or is it still giving that error?  I'd like to fix that if I can.
## Post #9
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-10-29T22:52:20+00:00
- Post Title: Rocksmith ogg (RIFX  WAVEfmt header)

Oops, I hadn't noticed that you already uploaded that file.  It turns out that this error was in error anyway (I was always checking for a packet to be at least the size of the header, but I assumed the header was 6 bytes, not the 2 or 8 it can be in various other versions), I've fixed this in 0.16.  This will only result in a few more silent frames at the end of the file, so it isn't really anything to worry about.
## Post #10
- Username: cml
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Dec 10, 2009 10:49 pm
- Post datetime: 2011-10-30T11:00:46+00:00
- Post Title: Rocksmith ogg (RIFX  WAVEfmt header)

thanks for explanation hcs
## Post #11
- Username: pedront
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 02, 2011 7:44 pm
- Post datetime: 2011-12-02T11:50:38+00:00
- Post Title: Rocksmith ogg (RIFX  WAVEfmt header)

Hello guys,

I'd like to study the file format for Rocksmith songs, because I'd like to put my songs in the game.
I have the PS3 game version and I'd like to ask you guys how can I get the songs to my PC and start studying them.
If I can't get from PS3, is there any other way you guys could teach me?

Thanks,
Pedro Nakano
