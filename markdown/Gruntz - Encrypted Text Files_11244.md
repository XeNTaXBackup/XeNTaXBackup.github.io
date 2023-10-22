## Post #1
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2014-02-23T09:56:37+00:00
- Post Title: Gruntz - Encrypted Text Files

Hey all. I'm trying to figure out some undiscovered cheat codes from a PC game called Gruntz.
Gruntz was made in 1998 by Monolith Productions, and is now considered abandonware.
The game's main archive (GRUNTZ.REZ) contains 3 text files: ATTRIBUTEZ.TXT, CREDITZ.TXT AND CHEATZ.TXT.
CREDITZ.TXT is a plaintext file, readable and editable in Notepad. But the ATTRIBUTEZ.TXT and CHEATZ.TXT files seem to be encrypted.

Here is a list of currently known cheat codes for search material:

```
mpletsblowstuffup, mpusetheforce, mpgolfandgamez, mpmakemesomepie, mpyouresomoney, mplemonbuttercremez, mpriorio, mpcheatcheatcheat, mpihatethisgame, mpilovethisgame, mplambert, mpwawawawawawa, mpindianajonez, mpelephantpork, mpfaoschwartz, mpback2life, mptacobell, mpchillout, mpclostrophobia, mplightzout, mpseizure, mppicasso, mpmeepmeep, mpcreatine, mpplusfivemagicalplate, mphighlander, mpohmygodtheykilledkenny, mpbillgatez, mpbluebrick, mpredbrick, mpgoldbrick, mpblackbrick, mptimer, mpbombage, mplametoy, mpmousey, mpmagicpaper, mpboingee, mpgetinshape, mpultimatecheeseburger, mpmalibugrandprix, mpwheeliez, mptheball, mpgerber, mpfearofflying, mpvasflam, mpcopperfield, mpquackage, mpplastiquez, mparrrrrrr, mpxfilez, mpkinetic, mpfuninthebarn, mptrojan, mprockon, mpfirepower, mphardhatmack, mphitopz, mprealmendontusestrawz, mppunchout, mpbrassknucklez, mpungabunga, mphomeimprovement, mpremotecontrol, mpkamikaze, mpcloakingdevice, mpstepitup, mpstepitdown, mpmonolith, mpfps, mppos, mptraitor, mpgoble
```


Could someone please take a look into these files (or at least CHEATZ.TXT) for me?
Thanks.

[ATTRIBUTEZ.TXT](https://docs.google.com/uc?id=0B_1NoA3ghF2PZXZxUngtbzdGdlk&export=download)
[CHEATZ.TXT](https://docs.google.com/uc?id=0B_1NoA3ghF2PbU9JQVNIUHRWT1U&export=download)
## Post #2
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2014-12-17T09:10:13+00:00
- Post Title: Gruntz - Encrypted Text Files

Hey all. I'd like to politely request help for this again.
Thanks.
## Post #3
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2015-01-03T12:44:35+00:00
- Post Title: Gruntz - Encrypted Text Files

Could anyone please suggest another forum, or a tutorial on decryption, to help me with this request?
## Post #4
- Username: dniel888
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Dec 17, 2014 7:01 am
- Post datetime: 2015-01-04T21:41:13+00:00
- Post Title: Gruntz - Encrypted Text Files

the ATTRIBUTEZ.TXT file is encrypted by blowfish with the key "1212"

use this script to decrypt:

```
get NAME filename
get SIZE asize
string NAME += ".dec"
log NAME 0 SIZE

```
## Post #5
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2015-01-05T06:18:10+00:00
- Post Title: Gruntz - Encrypted Text Files

> Reply from dniel888
>
> the ATTRIBUTEZ.TXT file is encrypted by blowfish with the key "1212"
...Thank you very much. Was the key bruteforced?
## Post #6
- Username: dniel888
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Dec 17, 2014 7:01 am
- Post datetime: 2015-01-05T08:39:49+00:00
- Post Title: Gruntz - Encrypted Text Files

> Reply from Friedslick6
>
> dniel888 wrote:the ATTRIBUTEZ.TXT file is encrypted by blowfish with the key "1212"
...Thank you very much. Was the key bruteforced?
No, I reversed the game and found the key.
