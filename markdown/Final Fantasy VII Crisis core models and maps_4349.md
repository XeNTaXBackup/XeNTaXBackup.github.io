## Post #1
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-04-18T20:42:58+00:00
- Post Title: Final Fantasy VII Crisis core models and maps

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-04-18T21:00:28+00:00
- Post Title: Final Fantasy VII Crisis core models and maps

Well, just to clarify, myself and koral did get the model files 100% mapped out, which included bone hierarchies (which are used properly). The textures are also completely understood/decoded, they just use standard PSP "swizzling" (tiling). I don't know if koral's tool was ever updated to reflect this though.

Actual positions/rotations for the bones are not in the model files, they are in separate animation files. My tool takes the correct bone hierarchies out of the model and uses vertex weights/bone indices to auto-generate bone positions/rotations because of this.

But yeah, if you want animation/skeletal data, then you need animation files corresponding to the character model (no way to directly establish which animation file matches which model file was established, seeing as G's ripper does not retrieve actual file names). Making the match without a lot of manual digging or hacky methods of trying to haphazardly match bone counts, would likely require reverse-engineering the PSP executable.

I personally plan on never bothering with the anim data, and thought drudging it back up here was a bit of a silly idea. But if anyone is so inclined, help yourself. koral and I have also since left Qhimm's (well, we didn't know it was run by socially dysfunctional mutants, and had been abandoned by all of the actual talent from the FF7/FF8 RE days, when we started contributing there), so you probably won't find anything useful remaining on their actual forums. The wiki info is probably very outdated too, but I dunno.
## Post #3
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2010-04-18T21:20:17+00:00
- Post Title: Final Fantasy VII Crisis core models and maps

Yeah, i thought there was something else i needed to add in there. I *THINK* the last tool on that wiki is able to get the actual file names, i've never actually tried it.

MrAdults is right, you wont really get anything by going to Qhimm's forums. The wiki itself is out of date, its been over a year since it was last updated.
