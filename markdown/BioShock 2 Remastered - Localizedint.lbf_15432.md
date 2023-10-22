## Post #1
- Username: stapheen
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 11, 2014 10:24 pm
- Post datetime: 2016-10-31T20:54:39+00:00
- Post Title: BioShock 2 Remastered - Localizedint.lbf

Hello!

Is there any tool to unpack and repack Localizedint.lbf ?
[Localizedint.rar](https://xentaxbackup.github.io/file/11853_Localizedint.rar)
## Post #2
- Username: javurek91
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Feb 09, 2014 9:29 pm
- Post datetime: 2016-10-31T22:56:46+00:00
- Post Title: BioShock 2 Remastered - Localizedint.lbf

Hello u can try this. All text is in the file e.g. localizeddeu.lbf etc.

[https://www.sendspace.com/file/b97rn4](https://www.sendspace.com/file/b97rn4)
## Post #3
- Username: stapheen
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 11, 2014 10:24 pm
- Post datetime: 2016-11-01T07:50:27+00:00
- Post Title: BioShock 2 Remastered - Localizedint.lbf

> Reply from javurek91
>
> Hello u can try this. All text is in the file e.g. localizeddeu.lbf etc.

https://www.sendspace.com/file/b97rn4

edit:

I changed some text in subtitle but still nothing changed in the game still English :/
## Post #4
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2016-11-01T08:20:46+00:00
- Post Title: BioShock 2 Remastered - Localizedint.lbf

Love how they still left the GFWL lines untouched even if the game no longer uses the service.
## Post #5
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2019-02-28T12:40:11+00:00
- Post Title: BioShock 2 Remastered - Localizedint.lbf

Is there a working unpack/repack tool or an LBF editor for Bioshock 2 (Remastered) to edit LocalizedXXX.lbf files?
I'd like to fix some Italian typos in the text…

LocalizedIta.lbf is mainly a big UTF-16LE file, but contains also some additional bytes to probably define every string length I still can't figure out after a long analysis with my hex-editor... Attached samples.

[https://ufile.io/955qc](https://ufile.io/955qc)
## Post #6
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2020-08-12T11:54:26+00:00
- Post Title: BioShock 2 Remastered - Localizedint.lbf

Here is a working tool made by banz99!
[https://1drv.ms/u/s!ApMUGr0cuN39gcYoFp0 ... w?e=SLigyw](https://1drv.ms/u/s!ApMUGr0cuN39gcYoFp0HvU8oL6P8Rw?e=SLigyw) ("Bioshock 2 (Remastered) string manager final.zip\Bioshock string manager\bin\Debug\Bioshock string manager.exe")

Tested and perfectly working with Steam PC version of Bioshock 2 Remastered.
Don't use it for Bioshock (Remastered) that uses a similar and simpler file format you can easily modify with any hex-editor.

Will generate a subdir with the name of the archive + EXT (e.g. "Localizedita.lbf EXT") containing all extracted files, and starting from the same dir location will repack a new "...\Localizedita.lbf EXT\REBUILT.dat" file inside. Rename and move REBUILT.dat to the original game Localizedita.lbf position in the end of course (replace original file).
Enjoy and good luck!
