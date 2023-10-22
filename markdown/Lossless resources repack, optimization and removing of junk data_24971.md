## Post #1
- Username: necros2k7
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jul 17, 2017 9:28 pm
- Post datetime: 2022-01-20T01:30:33+00:00
- Post Title: Lossless resources repack, optimization and removing of junk data

Sorry if wrong section
Hi, I wonder if anyone knows if it`s possible to shrink 3DS, TGA, TIF files losslessly not breaking game / software execution?
Didn`t see such thread anywhere, would be great to have all tools in one place.
My 5 cents would be such great tool as 
1. FileOptimizer [https://sourceforge.net/projects/nikkho ... Optimizer/](https://sourceforge.net/projects/nikkhokkho/files/FileOptimizer/) which do a great job of removing junk data from PNG JPG ZIP quite a lot of other formats
It`s not a magic knife but still best I saw.
2. AGS engine - [https://github.com/rofl0r/agsutils](https://github.com/rofl0r/agsutils)
3. UE4 - [https://github.com/panzi/rust-u4pak](https://github.com/panzi/rust-u4pak)
Please share tools/scripts/cmd you know which losslessly decrease resources size.
If interest would be I can continue this list and tell about FileOptimizer in more details
Of course if you are programmer you can enhance/fix above projects with your skills.
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2022-01-20T06:44:47+00:00
- Post Title: Lossless resources repack, optimization and removing of junk data

Optimization of "standard" formats (PNG, JPEG, WAV...) is well-explored in other projects, e.g. FileOptimizer (my current go-to, which you also already mentioned). Repacking of these files for use in games is going to be super game-specific - for one, it relies on repacking even being possible with current knowledge/tooling; beyond that, optimized files may or may not work (it depends on how the format support is implemented in the game engine, especially whether it uses an off-the-shelf library versus something developed in-house versus whatever else might be out there).

I guess the real question here is, what would be the purpose of this? The existence of e.g. [7-zip](https://www.7-zip.org/) should make for easier sharing of mod packs and the like (though I do know from first-hand experience that even using the .7z format with custom settings, it's often possible to get smaller archive sizes by also optimizing the files in the archive separately). You should also note that some of the data which many of these optimizers view as "junk" may not be for a given application - e.g. many of them remove some amount of metadata by default, which may or may not be desirable to any given modder (e.g. it can be used to watermark files in a way that doesn't impact in-game visuals or the like).
## Post #3
- Username: necros2k7
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jul 17, 2017 9:28 pm
- Post datetime: 2022-01-20T08:54:08+00:00
- Post Title: Lossless resources repack, optimization and removing of junk data

Of course we discuss only working solutions here. I understand it`s engine specific. Didn`t exactly understand what watermarks for. It`s not practical if goal is to protect images. By junk I mean data like for example in JPGs JFIF header, ICC_PROFILE         mntrRGB XYZ strings  ;CREATOR: gd-jpeg v1.0 (using IJG JPEG v62), quality = 8 etc. metadata not necessary for final game/mod/user. Also don`t forget PNG and other formats can be more efficiently recompressed including 7Z or ZIP formats, MP3 cbr to vbr.
Moreover there are junk files which have no practical use, I saw lotta of mods which hold
desktop.ini
thumbs.db
MacOS Explorer leftovers?
I don`t understand why Unity have screenselector.bmp - you do know what game you run don`t you?) (Same for output_log.txt)
Unreal engine 4 pak content folders safe to delete - slate, vreditor, engine content tutorial ?
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2022-01-22T05:04:02+00:00
- Post Title: Lossless resources repack, optimization and removing of junk data

If you're talking specifically about optimizing already-existing mods, this is not an area we should step into - if you're really that bothered, you should raise an issue with the mod's maintainer(s) by whatever channels they have specified. I'm going to note, though, that modern mods can be many megabytes in size (probably into the gigabytes for total conversion mods and the like), and even removing every last byte of unused cruft and squeezing every possible byte through improved compression would not significantly impact the final size for many of them.

In general, we aren't going to support usurping others' work here, regardless of the motivation for that usurpation (the only argument for it I see as even slightly defensible would be in the event of an abandoned mod or disappeared author, and even then I don't think this forum should be involved with such).
