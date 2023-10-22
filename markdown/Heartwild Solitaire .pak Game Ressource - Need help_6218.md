## Post #1
- Username: Tweety77
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Mar 14, 2011 10:25 pm
- Post datetime: 2011-03-14T14:50:54+00:00
- Post Title: Heartwild Solitaire .pak Game Ressource - Need help

Hello there,

first I'd like to thank for all the contributions here. 

I started reading andgoing through all the tutorial and infos here and I think it'll take 100 years until I get all of that! ^^

I would like to ask if someone could help me on creating a bms script for the above mentioned game.
I already tried doing so myself with the help of a tutorial but I guess it's a bit much for the beginning.

I uploaded one of the two .pak files from this Game as a .zip file here:
[http://www.2shared.com/file/6k9V0_58/solitaire.html](http://www.2shared.com/file/6k9V0_58/solitaire.html)

The Game itself is done by OrchidGames 
A link to the game itself: [http://www.orchidgames.com/heartwild_solitaire](http://www.orchidgames.com/heartwild_solitaire)

Any help would be appreciated and I hope to learn even more from this 

Thanks,

Tweety
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-14T16:31:48+00:00
- Post Title: Heartwild Solitaire .pak Game Ressource - Need help

job done, have fun:
[http://aluigi.org/papers/bms/orchid_games.bms](http://aluigi.org/papers/bms/orchid_games.bms)
## Post #3
- Username: Tweety77
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Mar 14, 2011 10:25 pm
- Post datetime: 2011-03-14T17:07:58+00:00
- Post Title: Heartwild Solitaire .pak Game Ressource - Need help

oh woow!

Thanks a lot aluigi!

I am totally impressed!

Now, that makes me wonder how that works.. I would love to be able to do that (and at such speed) to do that with a few other games..

Thanks a lot again!

Greetings,

Tweety
## Post #4
- Username: betatester
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 26, 2011 4:56 pm
- Post datetime: 2012-09-30T14:05:11+00:00
- Post Title: Heartwild Solitaire .pak Game Ressource - Need help

New game from orchidgames: [Spirit Walkers: Curse of the Cypress Witch download](http://www.screenseven.com/download/files/60022/SpiritWalkersTheCypressWitch.exe) or [download](http://www.orchidgames.com/media/spirit_walkers_install.exe)
New file format "data.pck". Any script ?
## Post #5
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-09-30T22:28:59+00:00
- Post Title: Heartwild Solitaire .pak Game Ressource - Need help

> Reply from betatester
>
> New game from orchidgames: Spirit Walkers: Curse of the Cypress Witch download or download
New file format "data.pck". Any script ?

Not sure how those lua scripts are compressed, but this extracts all others:

```
# QuickBMS script by WRS (xentax.com)

get DATASTART long
get FILES long

for f = 0 < FILES
  get FNAMELEN long
  get FZSIZE long
  get FOFFSET long
  getdstring FNAME FNAMELEN
  get FTYPE char
  get FSIZE long

  if FTYPE == 0
    log FNAME FOFFSET FSIZE
  else
    print "%FNAME% not dumped (%FZSIZE%-%FSIZE%)"
  endif
next f

savepos POS

if POS == DATASTART
  print "Success"
endif

```
## Post #6
- Username: betatester
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 26, 2011 4:56 pm
- Post datetime: 2012-10-01T17:35:26+00:00
- Post Title: Heartwild Solitaire .pak Game Ressource - Need help

Extracted all, except all lua scripts.
Mb they not compressed at all ? 'cause in "build_config.lua not dumped (172-170)" - 172 is real file size in bytes.

> build_config.lua not dumped (172-170)
>
> ...
>
> framework/scene_transition.lua not dumped (4821-4819)
>
> framework/tools.lua not dumped (8039-8037)
>
> init.lua not dumped (79-77)
>
> scripts/achievements.lua not dumped (10826-10824)
>
> scripts/components/fading_component.lua not dumped (1195-1193)
>
> ....

Modified script like this now seems all fine

```
# QuickBMS script by WRS (xentax.com)

get DATASTART long
get FILES long

for f = 0 < FILES
  get FNAMELEN long
  get FZSIZE long
  get FOFFSET long
  getdstring FNAME FNAMELEN
  get FTYPE char
  get FSIZE long

  if FTYPE == 0
    log FNAME FOFFSET FSIZE
  else
    log FNAME FOFFSET FZSIZE 
#    print "%FNAME% not dumped (%FZSIZE%-%FSIZE%)"
  endif
next f

savepos POS

if POS == DATASTART
  print "Success"
endif
```


Thanks !
## Post #7
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-10-01T17:44:19+00:00
- Post Title: Heartwild Solitaire .pak Game Ressource - Need help

> Reply from betatester
>
> Modified script like this now seems all fine

They didn't look like lua scripts.. but they all start 00 0F if i remember correctly
