## Post #1
- Username: Argonaut
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Sep 12, 2014 3:19 am
- Post datetime: 2014-09-27T17:29:37+00:00
- Post Title: Tokyo Xtreme Racer Series (xxx.DAT xxx.TOC)

This thread will hopefully be the future home of all TXR-related game archive extraction on this forum; with many desirable models to extract all in the same data formats, I'd thought it'd be good to keep it to just one thread.

Items of interest for each game are after the screenshots.

Things to know:
-All the games have a large Data file (either .DAT or a weird .000 file in Zero's case) and a TOC/LOC file (Table of contents)
-All the games after Zero used this format, so if an extraction method is found then we've got a whole lotta car models to pick from (atleast 400+ different Japanese vehicles)
-I've tried to get screenshots of data integers that appear more than once and are obvious to find multiple examples of perhaps assets to the game.

Tokyo Xtreme Racer Zero (PS2)

Files:

CDDATA.000: [https://www.dropbox.com/s/ltpysnajasxt0 ... 0.DAT?dl=0](https://www.dropbox.com/s/ltpysnajasxt05t/CDDATA.000.DAT?dl=0)  (for some reason identified as a .DAT file, doesn't matter anyway)
CDDATA.LOC: [https://www.dropbox.com/s/29byeo1xbpwr9 ... A.LOC?dl=0](https://www.dropbox.com/s/29byeo1xbpwr9ei/CDDATA.LOC?dl=0)

Screenshot sample of CDDATA.000:



At the start of the file, there's one .TM2 file which is the A-Z character selection for car names.


Tokyo Xtreme Racer Drift 2 (PS2)

Files:

BUILD.DAT: [https://www.dropbox.com/s/1vi4h6u3pte1u ... T.zip?dl=0](https://www.dropbox.com/s/1vi4h6u3pte1uap/BUILD.DAT.zip?dl=0)
BUILD.TOC: [https://www.dropbox.com/s/mtrrzdtymk57n ... D.TOC?dl=0](https://www.dropbox.com/s/mtrrzdtymk57n0n/BUILD.TOC?dl=0)

Screenshot samples of BUILD.DAT:



There's a couple of headers for TM2 files, but no data afterwards. Found keywords of cars in this plus some seemingly compressed words such as "BA77LE" instead of Battle, (Kaido Battle being the Japanese equivalent name).


Import Tuner Challenge (360)

BUILD.DAT: [https://www.dropbox.com/s/uiao93nte9qvm ... D.DAT?dl=0](https://www.dropbox.com/s/uiao93nte9qvm0j/BUILD.DAT?dl=0)
BUILD.TOC: [https://www.dropbox.com/s/j09g8h19tqe2s ... D.TOC?dl=0](https://www.dropbox.com/s/j09g8h19tqe2svz/BUILD.TOC?dl=0)

Screenshot samples of BUILD.DAT:






-Keywords such as Skyline, Battle, Chal(lenge missing) and text strings about 'Microsoft Shader Compli 2.0' (which got repeated an awful lot) were found
-Every bit of data starts with .eUCLy
-TXD2 (Tokyo Xtreme Drift 2?) found occasionally
-180, 32, 34, 86 (180SX, R32 GTR, R34 GTR, AE86) Integers found all in the first scroll section


That'll be all for now.. probably Import Tuner Challenge is the most exciting with the high quality models, but TXR Drift 2 has D1 machines galore..
And if your wondering what's so special about these games (and why they're worthwhile): [https://www.youtube.com/watch?v=7ZMmzAamRxs](https://www.youtube.com/watch?v=7ZMmzAamRxs)
## Post #2
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-09-28T01:22:02+00:00
- Post Title: Tokyo Xtreme Racer Series (xxx.DAT xxx.TOC)

> Reply from Argonaut
>
> -Keywords such as Skyline, Battle, Chal(lenge missing) and text strings about 'Microsoft Shader Compli 2.0' (which got repeated an awful lot) were foundSounds like a bunch of compiled shaders, possibly XMem compressed. Notice how the word "Compiler" contains "er", which is also in the word "Shader"?
## Post #3
- Username: Argonaut
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Sep 12, 2014 3:19 am
- Post datetime: 2014-09-28T09:12:25+00:00
- Post Title: Tokyo Xtreme Racer Series (xxx.DAT xxx.TOC)

> Reply from GMMan
>
> Argonaut wrote:-Keywords such as Skyline, Battle, Chal(lenge missing) and text strings about 'Microsoft Shader Compli 2.0' (which got repeated an awful lot) were foundSounds like a bunch of compiled shaders, possibly XMem compressed. Notice how the word "Compiler" contains "er", which is also in the word "Shader"?

Shader files are in a different folder within the ISO.. I'll try looking into that Compression method and see whether I can do anything with it.. Thanks for commenting.
## Post #4
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2015-04-06T15:26:04+00:00
- Post Title: Tokyo Xtreme Racer Series (xxx.DAT xxx.TOC)

I've used the aluigi's script for quickbms at Tokyo Xtreme Racer Zero and what i have now are a some .dat files one with 43.3 mb a lot of .nfc files with 800kb more or less and the rest are .0iv files with less weight, something about that?

I can upload all the extracted files if someone are interested.
[0000008c.rar](https://xentaxbackup.github.io/file/8969_0000008c.rar)
## Post #5
- Username: QOTSANINSOADKORN
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jul 01, 2016 7:26 pm
- Post datetime: 2017-06-11T13:22:35+00:00
- Post Title: Tokyo Xtreme Racer Series (xxx.DAT xxx.TOC)

2017 UPDATE - Are we any closer to Figuring out the file types?
## Post #6
- Username: Pix
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Nov 18, 2016 7:23 am
- Post datetime: 2017-12-20T17:13:29+00:00
- Post Title: Tokyo Xtreme Racer Series (xxx.DAT xxx.TOC)

For real? Because i really want the Autozam AZ-1 and Pulsar GTi-R from the game.
## Post #7
- Username: kil0gram
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 21, 2017 5:59 am
- Post datetime: 2017-12-20T22:14:06+00:00
- Post Title: Tokyo Xtreme Racer Series (xxx.DAT xxx.TOC)

Can you repost the dat/loc files please?
## Post #8
- Username: jellyorange647
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 01, 2019 6:33 pm
- Post datetime: 2019-10-22T18:31:44+00:00
- Post Title: Tokyo Xtreme Racer Series (xxx.DAT xxx.TOC)

Still nothing? That Nissan Cefiro and Laurel models look sweet.
## Post #9
- Username: Machinedramon
- Rank: advanced
- Number of posts: 77
- Joined date: Tue Apr 09, 2019 1:13 am
- Post datetime: 2019-10-29T19:26:51+00:00
- Post Title: Tokyo Xtreme Racer Series (xxx.DAT xxx.TOC)

Lel hello there people, on the itc xentax thread i recently posted a script for mrp that works for extracting geometry, cars in itc arent too different from trcaks but the script wont work, structure is different yet not impossible, been also working on txr3 and txrd2, though the geometry for tracks in txr3 is kinda plausible to extract, rn txrd2 facing isnt any easy, eucly is the header for ucl colpressed files, the script from aluigi/bms works on it(when it doesnt its because it has the big endian configured to it, for itc; in contrast ps2 games are on little endian) on the other hand, for txrd2 dats nfc and 0iv can have all different type of geometry, cars are to be found in nfcs, in dats there can be found the road mesh and 0iv has the single segments of tracks(but again the format for faces aint that clear)
