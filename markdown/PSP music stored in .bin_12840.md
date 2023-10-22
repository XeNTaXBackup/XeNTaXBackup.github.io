## Post #1
- Username: anonuk
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 29, 2011 11:33 pm
- Post datetime: 2015-05-14T13:15:36+00:00
- Post Title: PSP music stored in .bin?

Converted the game (Umihara Kawase PSP) from CSO to ISO, successfully extracted the ISO, found the music folder, which contains a 5MB "music.bin" file. Header looks like this:



[http://i.imgur.com/kmNuHhO.jpg](http://i.imgur.com/kmNuHhO.jpg)

Any ideas how to extract the music? Any tools available?

Edit: tried Nova extractor and got two tiny MIDI files (that sound wrong when played back on their own), and two ~2.5MB .psb files, which Nova can't find anything else in. I'm guessing the game has its own MIDI sound font which rules out any easy ripping of those, but anyone have any ideas on the latter two?
## Post #2
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2015-05-21T17:53:36+00:00
- Post Title: PSP music stored in .bin?

> Reply from anonuk
>
> Converted the game (Umihara Kawase PSP) from CSO to ISO, successfully extracted the ISO, found the music folder, which contains a 5MB "music.bin" file. Header looks like this:



http://i.imgur.com/kmNuHhO.jpg

Any ideas how to extract the music? Any tools available?

Edit: tried Nova extractor and got two tiny MIDI files (that sound wrong when played back on their own), and two ~2.5MB .psb files, which Nova can't find anything else in. I'm guessing the game has its own MIDI sound font which rules out any easy ripping of those, but anyone have any ideas on the latter two?
Psb is probably a false detection due to it searching for any possible header of known files, I would try using psound on the music.bin and hopefully you might find some samples that the midi is supposed to use. If you already did that, maybe dig into the developer's other games on psp/ps2, see if anyone else has figured anything out about their methods. Sorry I can't be much more help, I'll try to secure a copy of the game myself to check it out in the meantime.

Edit: PSound (from [http://snailrush.online.fr/](http://snailrush.online.fr/) ) found 319 instrument-like samples. typically vag audio (i still dont know why sony named it that) doesnt store names except in a few rare scenarios, so it might be a challenge to link them all the right tracks/spots in the midi.
## Post #3
- Username: anonuk
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 29, 2011 11:33 pm
- Post datetime: 2015-05-21T18:18:31+00:00
- Post Title: PSP music stored in .bin?

Thanks for the help! I'll take a look at psound.
## Post #4
- Username: RossRapper
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Sep 18, 2014 9:22 am
- Post datetime: 2019-01-15T20:02:31+00:00
- Post Title: PSP music stored in .bin?

> Reply from Pepper
>
> 
Psb is probably a false detection due to it searching for any possible header of known files, I would try using psound on the music.bin and hopefully you might find some samples that the midi is supposed to use. If you already did that, maybe dig into the developer's other games on psp/ps2, see if anyone else has figured anything out about their methods. Sorry I can't be much more help, I'll try to secure a copy of the game myself to check it out in the meantime.

Edit: PSound (from http://snailrush.online.fr/ ) found 319 instrument-like samples. typically vag audio (i still dont know why sony named it that) doesnt store names except in a few rare scenarios, so it might be a challenge to link them all the right tracks/spots in the midi.

Thanks. Had spent about half an hour trying to extract music from Ridge Racer 2 PSP game (.bin file). PSound worked perfectly, I hope others will find this topic much faster.
## Post #5
- Username: Ya begitulah
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Jun 07, 2021 6:53 pm
- Post datetime: 2021-08-22T01:24:26+00:00
- Post Title: PSP music stored in .bin?

Is the header of the file Npsf? If yes I would like to try porting songs from that game to MotoGP psp
