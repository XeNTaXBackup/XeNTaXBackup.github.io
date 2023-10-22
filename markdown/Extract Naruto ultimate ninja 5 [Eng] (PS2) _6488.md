## Post #1
- Username: dragons
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 24, 2011 5:21 pm
- Post datetime: 2011-04-24T09:49:07+00:00
- Post Title: Extract Naruto ultimate ninja 5 [Eng] (PS2) ?????

Hi ...
please how can I extract the characters from the "Naruto ultimate ninja 5" and import them to 3DSMAX . 

the files in Data folder :
DATA.CVM   = 725 mb ( maybe the characters here ).
GF4.BIN
GF4C.BIN
GRF4.BIN
PLVOICE.AFS
RPGVOICE.AFS
SF1.BIN
SF1C.BIN
SNDDATA.BIN
SOUND.AFS
STREAM.AFS

The AFS files contain ADX Audio files.
I don't know were the file of the characters , and how can I extract it 
I tried many and many way but no one is work .
## Post #2
- Username: dragons
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 24, 2011 5:21 pm
- Post datetime: 2011-04-26T10:10:11+00:00
- Post Title: Extract Naruto ultimate ninja 5 [Eng] (PS2) ?????

Pleassssssssssse any idea
## Post #3
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2011-05-06T13:27:06+00:00
- Post Title: Extract Naruto ultimate ninja 5 [Eng] (PS2) ?????

DATA.CVM is encrypted
## Post #4
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-09-11T00:13:54+00:00
- Post Title: Extract Naruto ultimate ninja 5 [Eng] (PS2) ?????

Sorry for bumping but are there any ways to decrypt it?
## Post #5
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-14T18:17:54+00:00
- Post Title: Extract Naruto ultimate ninja 5 [Eng] (PS2) ?????

CVM I think is a format bandai/namco use a lot, I think it was the same package format used in most of the .hack games, and as such there should be info avalable or tools for it if you look around. I've heard a lot of people, (perhaps too many e.e) looking into naruto formats. It seems most of the games are made by the same studio division that made the .hack games, so that's where you might start looking.

For instance, you -may- find some textures if you open up data.cvm in a program called hackstract. Honestly I loathe naruto, but if it gets more attention on these files maybe I should be grateful...
## Post #6
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2011-09-15T02:14:22+00:00
- Post Title: Extract Naruto ultimate ninja 5 [Eng] (PS2) ?????

The CVM header in this game is encrypted. The files in the CVM look as though they are probably compressed also. There's a reference in the eeMemory.bin from PCSX2 that suggests they may be gzipped but this is just a wild guess. I'll look at it here in a few mins and see what I can see... This is also in the wrong forum, mods should move to Game Archive Research.

EDIT: 
Confirmed that files in CVM are gzipped.

EDIT2:
I can't confirm this yet but according to these files there are MAX and BMP files stored in the archives inside the gzipped files. Seems unlikely that either would be the case but theres definitely some texture data in there thats plain enough to see with the naked eye in a hex editor... I'll look at it more tomorrow.
## Post #7
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-09-15T11:02:17+00:00
- Post Title: Extract Naruto ultimate ninja 5 [Eng] (PS2) ?????

> Reply from Satoh
>
> CVM I think is a format bandai/namco use a lot, I think it was the same package format used in most of the .hack games, and as such there should be info avalable or tools for it if you look around. I've heard a lot of people, (perhaps too many e.e) looking into naruto formats. It seems most of the games are made by the same studio division that made the .hack games, so that's where you might start looking.

For instance, you -may- find some textures if you open up data.cvm in a program called hackstract. Honestly I loathe naruto, but if it gets more attention on these files maybe I should be grateful...

That worked , and the textures were in the tmp folders also same with the models that are also in the tmp so I tried to use ccs2obj but the same results, no model files were extracted and even the textures, they are just viewed from hackstract..
