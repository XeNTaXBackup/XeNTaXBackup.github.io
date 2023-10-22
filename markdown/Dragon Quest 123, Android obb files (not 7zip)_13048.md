## Post #1
- Username: GHANMI
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 11, 2014 4:23 pm
- Post datetime: 2015-07-10T03:41:01+00:00
- Post Title: Dragon Quest 1/2/3, Android obb files (not 7zip)

Square Enix was using apk+obb files that were openable with 7zip to view their contents inside, at least for DQ4/5/8.

However, then their English releases for Dragon Quest 3 had a new type of obb file that wasn't zipped.
File name is main.9.com.square_enix.android_googleplay.dq3_gp.obb
When opened with a hex editor, no obvious headers, in the end of the file there's only this part readable "com.square_enix.android_googleplay.dq3_gpA" followed by the hex sequence 00 00 00 83 99 05 01 if this is any help 
(I once isolated a working png image out of a custom archive (Powerduck Mobile, Buster PC, Akuji the Demon) by recognizing these sort of stuff, but here I'm really clueless and I think it's beyond my abilities (not that I wouldn't like learning about handling compressions some day   ).

The accompaigning apk file isn't encrypted, it's openable with winzip/7zip.

This seems like a new file format introduced by Square Enix.
A similar compression is in effect, besides Dragon Quest 3, for Dragon Quest 1 and Dragon Quest 2 for Android.

I'm interested in this mainly for doing a script dump of the translation unique to this version.
Thanks a lot
