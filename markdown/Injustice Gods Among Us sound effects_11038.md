## Post #1
- Username: R1665
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 12, 2013 5:07 pm
- Post datetime: 2013-12-13T05:24:19+00:00
- Post Title: Injustice: Gods Among Us sound effects

As some of you may already be aware, NetherRealm Studios made a few subtle changes in the build process between Mortal Kombat 9 and IGAU.  Old extraction methods don't quite work anymore.  Texture editing has only recently been discovered for IGAU, but nobody seems to be working on the sound effects.  Shall we do something about that?

The MK9 sound extraction method worked like this:
1.  decompress .xxx file with Unreal Package Decompressor
2.  run newly-created .xxx file through Unreal Package Extractor
3.  Navigate newly-created sub-menus, find the proper FMODEVENTFILE, and run it through fsbii.
4.  Extract/Play/Convert newly-created .fsb file as desired.

Now, everything for IGAU works exactly like MK9 until you hit the fsbii point.  That's the key.  Prior to that point, you can take either the MK9 FmodEventFile or the IGAU FmodSourceData files, rename the extension to .fsb, and kinda-sorta open them as .fsb.  I say "kinda-sorta" because the resulting sound is not separated, organized, and much of it is distorted.

So... fsbii needs an update to get it working with IGAU FmodSourceData files.

I have no clue how to do that.  I can, however, provide fsbii as well as samples of both an MK9 FmodEventFile and an IGAU FmodSourceData file:

[http://tinyurl.com/kooj7vn](http://tinyurl.com/kooj7vn)

R1665
## Post #2
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-12-13T21:59:13+00:00
- Post Title: Injustice: Gods Among Us sound effects

> Reply from R1665
>
> As some of you may already be aware, NetherRealm Studios made a few subtle changes in the build process between Mortal Kombat 9 and IGAU.  Old extraction methods don't quite work anymore.  Texture editing has only recently been discovered for IGAU, but nobody seems to be working on the sound effects.  Shall we do something about that?

The MK9 sound extraction method worked like this:
1.  decompress .xxx file with Unreal Package Decompressor
2.  run newly-created .xxx file through Unreal Package Extractor
3.  Navigate newly-created sub-menus, find the proper FMODEVENTFILE, and run it through fsbii.
4.  Extract/Play/Convert newly-created .fsb file as desired.

Now, everything for IGAU works exactly like MK9 until you hit the fsbii point.  That's the key.  Prior to that point, you can take either the MK9 FmodEventFile or the IGAU FmodSourceData files, rename the extension to .fsb, and kinda-sorta open them as .fsb.  I say "kinda-sorta" because the resulting sound is not separated, organized, and much of it is distorted.

So... fsbii needs an update to get it working with IGAU FmodSourceData files.

I have no clue how to do that.  I can, however, provide fsbii as well as samples of both an MK9 FmodEventFile and an IGAU FmodSourceData file:

http://tinyurl.com/kooj7vn

R1665

try using FSB extractor instead, sometimes it handles the fsb mp3 padding better.
aezay.site11.com/aezay/fsbextractor/‎
you may need to use a proxy to access the site. my ISP/network doesn't load it at all unless i use a proxy (it just times out otherwise).
make sure you turn on mp3 frame verification on under options.
now, it won't just load the sourcedata as is, but all you have to do is remove the bytes before the "FSB5" string as seen in a hex editor.
this is blocks 0-23 (decimal, base 10) or 0-17 (hexadecimal, base 16) on the file you linked, block 24 (dec) 18 (hex) is the letter F.

I reccomend using HxD or any freeware hex editor.
[ftp://wa651f5:anonymous@mh-nexus.de/HxDSetupEN.zip](ftp://wa651f5:anonymous@mh-nexus.de/HxDSetupEN.zip)

all you do is open the sourcedata, look for "FSB5" use cursor to select everything before those letters (prior to the F) and hit delete. it warns you this changes the filesize, thats fine. hit ok. next, save as a .fsb

open with the fsb extractor linked above, it dumps into a "Dumps" folder when you preview/export. this folder should be in the same location as the extractor, it makes it for you whenever it needs to dump and the folder doesn't already exist.
## Post #3
- Username: R1665
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 12, 2013 5:07 pm
- Post datetime: 2013-12-14T02:57:26+00:00
- Post Title: Injustice: Gods Among Us sound effects

Spectacular!  Pepper, I shall laud you copiously in the credits of my next major project.  Much obliged.

R1665
## Post #4
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-12-14T18:23:06+00:00
- Post Title: Injustice: Gods Among Us sound effects

> Reply from R1665
>
> Spectacular!  Pepper, I shall laud you copiously in the credits of my next major project.  Much obliged.

R1665
just keep in mind to check for multiple FSB5 headers in other sourcedata files, I can't say for certain but i think some of the larger ones have multiple fsbs inside one file. ctrl+F in HxD and enter to search for FSB5 should work fine. just take care not to overwrite your original game files!
