## Post #1
- Username: Argonaut
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Sep 12, 2014 3:19 am
- Post datetime: 2014-09-11T21:53:00+00:00
- Post Title: Import Tuner Challenge - Potential GT5 Quality models

Hi,

I'm new here and i'm aware this is my first post. I've read the tutorials, but I think extracting anything out of this game will be tricky without an offical SDK/file opener.

Y'see, Import Tuner Challenge was a game released by the under-the-public-eye company called Genki, which have a history of making such quality games such as the Tokyo Xtreme Racer series which pinned itself on deep levels of car customization (Roll cages, Multiple Skirts, bumpers, sticker sheets, spoilers etc- this level of Customization for every car). Now Import Tuner Challenge was the localized version of the Xbox 360 game 'Shokoto Battle X', a somewhat poorly developed series continuation which ultimately proved to be it's last.

However, whilst the game was undoubtedly pretty shoddy, the deep level of customization persisted and unlike the rest of the game, the car models (the exteriors atleast) were given some pretty good attention- however, whilst (lamely) there were only like 10 cars you could own, the number of unobtainable, tuned (Full skirts, rollcages, decals etc) NPC cars with the same Poly rate was huge and it would be a massive waste not to try and atleast attempt an extraction/understanding of the game's data.

Were talking AE86 Levin/Truenos, IS300s, RX-8s, Supras both old and new, Z30/Z32s, Skylines, Sti's etc. All in this level of detail, pretuned: (This is a player-owned car btw)



Which brings me onto that itself- the data. Here's a screenshot of the ISO itself so I can explain:



Now i've explored all the folders and the 'BUILD' one is the only one of interest to the cause, the Movie folder has all the game cutscenes in a WMV format @ 1280x720 which could be extracted at any time (they're lame anyway), the Debug one is just a Debug font file ( could have been more interesting if someone got an earlier build) and the rest are self explanatory. 

Now the file with all the car data (perhaps other stuff) is BUILD.DAT, whereas the slightly larger BUILD_CRS.DAT is the map itself I assume (CRS an abbreviation of Course or perhaps CARS, i'm undecided). This can be proven with the Hex Editor being able to find Keywords such as Skyline, AE86 etc (Proving NPC vehicles within the data).

I've uploaded the BUILD.DAT to Dropbox, I doubt as Genki have shut their doors on the series they'll chase it up, so here it is: [https://www.dropbox.com/s/uiao93nte9qvm ... D.DAT?dl=0](https://www.dropbox.com/s/uiao93nte9qvm0j/BUILD.DAT?dl=0)
And the BUILD.TOC: [https://www.dropbox.com/s/j09g8h19tqe2s ... D.TOC?dl=0](https://www.dropbox.com/s/j09g8h19tqe2svz/BUILD.TOC?dl=0)
I can't explain much further atm as it's getting late, but anyone in the know who can give this a quick glance and return back with any info is greatly appreciated. I am looking to extend my so-so knowledge to do this myself, but I have little time available to really get stuck in for a day or two. Hopefully this will interest a couple of you.

Thanks for reading, lets see if this can get somewhere.
## Post #2
- Username: Argonaut
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Sep 12, 2014 3:19 am
- Post datetime: 2014-09-12T18:27:50+00:00
- Post Title: Import Tuner Challenge - Potential GT5 Quality models

Link added, sorry for the late upload.
## Post #3
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2014-09-12T22:29:49+00:00
- Post Title: Import Tuner Challenge - Potential GT5 Quality models

TableOfCotents (TOC) file is missing means you can't separate the data from the Data (DAT) file :'(
## Post #4
- Username: Argonaut
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Sep 12, 2014 3:19 am
- Post datetime: 2014-09-13T11:55:49+00:00
- Post Title: Import Tuner Challenge - Potential GT5 Quality models

> Reply from mariokart64n
>
> TableOfCotents (TOC) file is missing means you can't separate the data from the Data (DAT) file :'(

I'll upload it now.. Sorry :!
