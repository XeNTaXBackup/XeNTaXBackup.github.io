## Post #1
- Username: Julia Litost
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 23, 2016 9:41 am
- Post datetime: 2016-06-23T01:58:07+00:00
- Post Title: Metal Gear Snake Eater Lost Track

I've been searching for an unreleased track of the Metal Gear 3. You can hear it in this part: [https://youtu.be/WaTjhnD4isc?list=PLU4G ... q7B&t=1304](https://youtu.be/WaTjhnD4isc?list=PLU4GD_G543eODgA4sqYoN9VppfLfzZq7B&t=1304) And also in this: [https://youtu.be/h3jKd6J36UY?t=95](https://youtu.be/h3jKd6J36UY?t=95) I searched everywhere on the internet. Unreleased rips, bonus albums, everywhere. But I could not find it.

So being the obsess human being that I am, I walked far enough into the realm of demux_dat.exe, demux_dat_be and test.exe. 
I do not know the details of what I'm doing, but thanks to my intuition I managed to extract the MTAF files and decode just ONE into wave. And that's where my problem resides, i cannot convert any MTAF file anymore. Don't know why. 

So, if anyone wants to help me with his or her knowledge I would be grateful to end this journey that I had since 2004 and adquiere that song. 
The truth is that this has become something kind of personal with the game. The song is not that great but I cannot tolerate to lose. I just need to get. 

Anyway, aside from that, if someone can also help me regarding where to look in the files, because I have the feeling that this song in particular is not part of the audio files per se, that's why people cannot find it and they never uploaded in those "Game-Rips Ost". 

Metal Gear 3 has: BGM. Dat, CODEC.Dat, DEMO.Dat, MOVIE.Dat, SLOT.dat, STAGE.Dat, VOX.Dat 
So according to my line of reasoning, the song must be hidden somewhere in MOVIE.DAT. 

Mind my english, I'm no native speakear. 

Needless to say, I would be eternally grateful.
## Post #2
- Username: snkryu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 19, 2016 6:32 am
- Post datetime: 2016-06-23T06:09:10+00:00
- Post Title: Metal Gear Snake Eater Lost Track

VOX.DAT contains codec calls and additional music.
the first file you're looking for is "File3884.vag" (extracted using Konami DAT Utility).
it's the second biggest file in the list (16.3 Mo).
the track is 5m40s codec conversation with the boss while the music plays in the background - so no separate soundtrack.

the boss battle cutscene audio is found in DEMO.DAT (using demux_dat).
it's "00100_0011.mtaf"  (12.8 Mo).
the track is 04m24s, and the music is mixed with the dialogue there as well.

(both files converted to wav using vgstream; the DAT files are from MGS3 Subsistence.)

cheers.
## Post #3
- Username: Julia Litost
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 23, 2016 9:41 am
- Post datetime: 2016-06-23T08:12:02+00:00
- Post Title: Metal Gear Snake Eater Lost Track

Well, my friend. I've done it. My journey can rest...
But men, what a bummer. Can't believe that the worst case scenario is the one I got. 
I considered the fact that maybe the audio was "attach" to the codec conversation and the video...but hope tricked me. 

It's a pity that I cannot have that track unless someone is talking over the song. 
But hey, at least I got the codec conversation with The Boss. That's...something. 

I think that I will face the same luck with the HD version too, right?

Anyway, I'm quite thankful, truly.
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-06-23T11:56:22+00:00
- Post Title: Metal Gear Snake Eater Lost Track

I used sox oops (Out of phase stereo, Vocal Remover in Audacity) to isolate the music from the codec conversation in the VOX, unfortunately there is a lot of noise spilling over from the voices so this isn't perfect (and it is mono).

```
sox dump.wav dump_oops.wav oops
```
It's possible that the HD version uses better audio compression and this approach would be more successful then, don't know.

[http://hcs64.com/files/3884_oops.flac](http://hcs64.com/files/3884_oops.flac)
## Post #5
- Username: Julia Litost
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 23, 2016 9:41 am
- Post datetime: 2016-06-23T20:38:58+00:00
- Post Title: Metal Gear Snake Eater Lost Track

Well, it is not perfect, but is very good. Thanks. Maybe the HD version would be better. I will check it out.
## Post #6
- Username: stellarren21
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 02, 2016 12:59 pm
- Post datetime: 2016-06-27T07:13:45+00:00
- Post Title: Metal Gear Snake Eater Lost Track

Pachislot-Adapted Version of Metal Gear Solid: Snake Eater is about to be released in Autumn of 2016 and it is known as 'Big Boss' featuring 32'' LCD Monitor in Full HD capabilities.
Check this new version and you will surely love it ...Yeah.........! Yeah..............!!
