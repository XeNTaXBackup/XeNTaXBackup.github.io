## Post #1
- Username: Mugenh
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 05, 2015 1:57 am
- Post datetime: 2018-11-02T22:46:57+00:00
- Post Title: Tips and Resources on reading .bnk files

Hello! So, I've been trying my damnedest to figure this out, going on four days now of researching and fiddling with it, and I've, to an extent, got some of it, but I'm at a loss for reading what is inside sections. I'm not exactly caring for extracting any files here, as I'm dealing with an Init. I've been able to halfway half-ass an understanding of it, but I don't really *know* what I'm doing... It's more a case of, "well, that worked... but *how*?" My biggest frame of reference is, of course, this:

[http://wiki.xentax.com/index.php/Wwise_ ... RC_section](http://wiki.xentax.com/index.php/Wwise_SoundBank_%28*.bnk%29#HIRC_section) 

Now, I can understand the identifier of the sections, that part is simple enough, and I can manually find the length of a section by selecting the start of it, up to the start of the next identifier. But, what confuses me is everything actually inside the section. The HIRC is the biggest thing I'm lost on. For the general format of the HIRC, it says this:

> 48 49 52 43 -- HIRC
>
>      uint32: length of section
>
>      uint32: number of objects
>
>      FOR EACH (object) {
>
>           byte: single byte identifying type of object
>
>           uint32: length of object section (= 4-byte id field and additional bytes)
>
>           uint32: id of this object
>
>           byte[]: additional bytes, depending on type of object and section length
>
>      } END FOR

I understand the first portion just fine - that is the identifier of the section, HIRC, where the section starts. But the thing that is really throwing me off is the unit32. What exactly does it mean here by "uint32: length of section" and "uint32: number of objects"? I know that uint32 is an unsigned int that is 4 bytes long, but I don't know how to apply that here to find the length of the section and the number of objects, not to even mention all the rest at the moment. I have the same issue with the BKHD, where it says "uint32: length of section", "uint32: version number of this SoundBank", and "uint32: id of this SoundBank" (though what I'm trying to tinker with isn't in there, it's the HIRC, but just as a means of figuring it out, I've been looking at it). I simply have no idea what this means, here, I don't know how to get the length, or the id, or anything, really, from uint32. 

If it wasn't obvious enough, I'm new to playing with .bnks, which is why I've tried researching so much on it, but I am just at a complete loss with the uint32 and how to find - or use - that whatsoever. I'm used to .lua and (rudimentary).xml coding, but reading this is just out of my spectrum at the moment. If anyone has any tips, advice, or any additional resources, I'd really appreciate it. Thank you.
## Post #2
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2018-11-03T04:42:58+00:00
- Post Title: Tips and Resources on reading .bnk files

Try extracting files that produce proper names for the files instead of numbers, I get that when extracting games that use this sound system.
## Post #3
- Username: Mugenh
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 05, 2015 1:57 am
- Post datetime: 2018-11-03T17:29:41+00:00
- Post Title: Tips and Resources on reading .bnk files

> Reply from Puterboy1
>
> Try extracting files that produce proper names for the files instead of numbers, I get that when extracting games that use this sound system.

Therein lies my problem, here. I've been able to do that for other .bnks, but for the Init - or at least, this Init - there are no actual extractable files in here; it's all settings. I haven't been able to get anything out of this .bnk. Specially, it's acoustic effects and volume - so reverbs, echoes, stuff like that, that simply *modifies* sounds in other existing Soundbanks. Unless... there's something I'm missing or doing wrong with extracting the Init, but I'm able to extract any other .bnk just fine.
## Post #4
- Username: ARAJediMaster
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Jun 12, 2015 12:17 pm
- Post datetime: 2018-11-09T04:25:51+00:00
- Post Title: Tips and Resources on reading .bnk files

Have you tried this: [https://github.com/eXpl0it3r/bnkextr](https://github.com/eXpl0it3r/bnkextr)

Or this: [https://github.com/Vextil/Wwise-Unpacker](https://github.com/Vextil/Wwise-Unpacker)

Maybe these may help you a great deal.
