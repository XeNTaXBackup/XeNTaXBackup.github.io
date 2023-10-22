## Post #1
- Username: AlexonlyAlex
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Oct 22, 2010 4:27 am
- Post datetime: 2010-10-21T21:35:19+00:00
- Post Title: GH6 Warriors of Rock 360/PS3 .FSB files

Hello everyone on this forum,
right now I'm trying to figure out if it's possible to decrypt the new FSB encryption, to basicly get the stems out of the archives.

According to [Wikipedia](http://en.wikipedia.org/wiki/Guitar_Hero:_Warriors_of_Rock) the game was developed:
-Xbox 360, PS3 versions by [Neversoft](http://en.wikipedia.org/wiki/Neversoft)
-Wii version by [Vicarious Visions](http://en.wikipedia.org/wiki/Vicarious_Visions)

The funny thing is that Wii version does not have this new encryption, I'm not sure why, but I was able to extract those song stems with very common tools.

I've also created a thread about this situation at ["Alugi's Forum"](http://aluigi.freeforums.org/newest-guitar-game-encryption-undecryptable-t1570.html). 
As written there I've got the songfiles. I've uploaded fully unmodified or untouched in any way files on mediafire:
-[Xbox 360 Version](http://www.mediafire.com/?5szfjmwobx5ghsh) 
-[PS3 Version](http://www.mediafire.com/?5qrf7tl5ccro2xy)

What you guys might also want to know is that all the songs are having this structure:

Xbox 360: song_1.fsb.xen | song_2.fsb.xen |song_3.fsb.xen | song_preview.fsb.xen

Ps3: SONG_1.FSB.PS3 | SONG_2.FSB.PS3 |SONG_3.FSB.PS3 | SONG_PREVIEW.FSB.PS3

In case you need all 4 files to a song, let me know.


You might ask why I want the stems out of other versions, though I have those from Wii already, the answer is simple.
Looking back to older Guitar Hero versions it's been proven that in the most cases the Xbox 360 versions had more layers, for example:

What I've Done - Linkin park comparing Wii and Xbox 360 vocal stem
- Wii version had vocals + piano in one channel
- Xbox 360 had clear vocals and piano in separated channels
Thats a little example, there are 1000s of such cases.


Just like my associate [here](http://forum.xentax.com/viewtopic.php?f=17&t=5243), I really hope you guys can help.
## Post #2
- Username: AlexonlyAlex
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Oct 22, 2010 4:27 am
- Post datetime: 2010-10-27T19:07:47+00:00
- Post Title: GH6 Warriors of Rock 360/PS3 .FSB files

very very sad...
## Post #3
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-11-07T06:24:11+00:00
- Post Title: GH6 Warriors of Rock 360/PS3 .FSB files

I took a long look at this tonight, one interesting thing is that corresponding files in the 360 and PS3 version have many bytes in common, I am guessing that they use the same key which produces the same stream (it seems to be a random stream directly XORed with the data, seems to be no scrambling beyond that). This may mean that the key is based on a hash of the file name base (before the .xen or .ps3).  What's more, among the preview songs there are quite a few pairs (and a triplet and quadruplet) on the same system that also seem to share the same randoms. I have confirmed that the 360 files "interstatelovesong_preview.fsb.xen" and "theoutsider_preview.fsb.xen" also share some large blocks within the stream, this must be where the XMA padding FFs line up, and indeed it occurs just before the start of blocks, assuming 0x8000 block size (most other pairs on the 360 do this as well, these two just have the most).

I wasn't able to make any progress towards identifying the pRNG used, unfortunately. Unlike normal FSB encryption it doesn't just use a 31 byte key, and I didn't identify any cycles in what little exposed data was identifiable. It seems like it should be doable with enough digging.
## Post #4
- Username: AlexonlyAlex
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Oct 22, 2010 4:27 am
- Post datetime: 2010-12-13T00:58:38+00:00
- Post Title: GH6 Warriors of Rock 360/PS3 .FSB files

U guys srsly cant help, or is there something going on like an agreement with neversoft or w/e that you wont try to decrypt that stuff?
## Post #5
- Username: Nerd42
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 14, 2011 1:03 pm
- Post datetime: 2011-05-14T14:27:01+00:00
- Post Title: GH6 Warriors of Rock 360/PS3 .FSB files

They certainly haven't made the passwords obvious
## Post #6
- Username: Kalecgos
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 16, 2011 7:20 pm
- Post datetime: 2011-11-16T11:26:12+00:00
- Post Title: GH6 Warriors of Rock 360/PS3 .FSB files

I know the fat Guitar Hero/Rock Band times are over, but I am still interested in this, because of a project to convert all Guitar Hero songs into RB3 customs. As a worst case scenario it would be okay to use the Wii GH:WoR audio instead, but some DLC has never been released for Wii and it is important to decrypt the Xbox360 versions of those songs
## Post #7
- Username: trojannemo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 19, 2011 12:46 pm
- Post datetime: 2011-11-19T04:55:28+00:00
- Post Title: GH6 Warriors of Rock 360/PS3 .FSB files

Kalecgos,

it seems we're both on the same trail. found this post after so more googling.
still no solution for me.

can you at least tell me how to go from my Wii .bin files to a usable .mid file that I can import into Reaper? I think i can hammer out the rest from there with what i've learned...and it should keep me busy until you post that guide of yours i'm sooooo looking forward to
