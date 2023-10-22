## Post #1
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2010-04-18T06:30:10+00:00
- Post Title: BattleCorogy .npk

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-18T09:15:52+00:00
- Post Title: BattleCorogy .npk

in my opinion the table with the informations about the files is encrypted, probably with blowfish.
while the other files are simply compressed (acid_effect.npk and posteffect.npk) or encrypted too.
try to upload also the executables and dlls of the game but I doubt there will be a solution
## Post #3
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2010-04-18T10:06:28+00:00
- Post Title: BattleCorogy .npk

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-18T17:14:29+00:00
- Post Title: BattleCorogy .npk

no luck, so use offzip on the npk archives that have compressed files in them (so not script.npk)
offzip -a file.npk c:\output_folder 0
## Post #5
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2010-04-20T05:25:34+00:00
- Post Title: BattleCorogy .npk

I found this

[http://code.google.com/p/npk/](http://code.google.com/p/npk/)

NPK

    * C library.
    * Store many files into one file.
    * Support compression with zlib.
    * Support encryption with tea.
    * Header encryption.
    * Platform independent. (linux/mac/windows)
    * Support command-line tool.
    * Multithread safety. (windows only, yet)
    * Unit test with CMake
    * Minimal build option for read-only usages.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-21T13:24:51+00:00
- Post Title: BattleCorogy .npk

the tea key is choosed by the developers so: no key, no party
