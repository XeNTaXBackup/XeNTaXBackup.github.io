## Post #1
- Username: Xino
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Dec 21, 2008 1:26 am
- Post datetime: 2008-12-23T20:09:22+00:00
- Post Title: Dissidia Final Fantasy. LBA help

Hey there. I want to extract the files from the Munge file "PACKAGE.BIN" from Dissidia FF (PSP)
The LBA is in another file called "PACKAGE_INFO.BIN" but i can´t find the structure...

I uploaded both files. Munge file splitted into two 5 Mb parts, one for Begin of file and one for end.

```
http://www.mediafire.com/?0ogxpndqz3o
```


Any help will be appreciated.
## Post #2
- Username: MysterySword
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Dec 25, 2008 3:39 am
- Post datetime: 2008-12-25T06:44:29+00:00
- Post Title: Dissidia Final Fantasy. LBA help

Hmm... what are you trying to do, extract the files from Dissidia? If so, I have an extractor for that...
## Post #3
- Username: Xino
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Dec 21, 2008 1:26 am
- Post datetime: 2008-12-25T13:22:43+00:00
- Post Title: Dissidia Final Fantasy. LBA help

> Reply from MysterySword
>
> Hmm... what are you trying to do, extract the files from Dissidia? If so, I have an extractor for that...

Yep. I´m looking for a ext/reb tool. Better for me to understand the LBA structure itself. The only value i founded is the size of LBA file (blue marked)
## Post #4
- Username: MysterySword
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Dec 25, 2008 3:39 am
- Post datetime: 2008-12-25T13:54:31+00:00
- Post Title: Dissidia Final Fantasy. LBA help

Here's the extractor (coded by someone from EndlessParadigm):

[http://endlessparadigm.com/forum/attach ... p?aid=2437](http://endlessparadigm.com/forum/attachment.php?aid=2437)

There are some unusual formats within package.bin. The GIM files are the images (character icons and tip images). The ARC and PAK files are like ZIP files (and I've heard they contain images). The GMO files are the text files, I believe, but I can't open them correctly (I think GNU gettext can, but I don't know how to use that).
## Post #5
- Username: Xino
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Dec 21, 2008 1:26 am
- Post datetime: 2008-12-25T15:08:55+00:00
- Post Title: Dissidia Final Fantasy. LBA help

Thanks. I think the LBA is encrypted, so the values cant match with the BIN files offsets....
## Post #6
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2008-12-25T16:04:52+00:00
- Post Title: Dissidia Final Fantasy. LBA help

Here you are some tools of MINE:

Arc Extractor v0.91:             [Download](http://www.tbhreloaded.it/Vash/Dissidia_Final_Fantasy_Arc_Extractor_v0.91_By_Vash.rar)
Package.Bin Extractor v0.5  : [Download](http://www.tbhreloaded.it/Vash/Dissidia_Final_Fantasy_Bin_Extractor_v0.5_By_Vash.rar)
Mpk Extractor v0.9:              [Download](http://www.tbhreloaded.it/Vash/Dissidia_Final_Fantasy_Mpk_Extractor_v0.9_By_Vash.rar)

the extractor made by that guy is just mine, not even renamed. The file name and extensions are the same (I invented them studying each file header), the readme structure is the same, an error with file extensions is still there (pmf instead of sfo). He just changed from "by Vash v0.5 -www.romhacking.it-" to "by Kratosjohn -". I hate those kind of people.
## Post #7
- Username: MysterySword
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Dec 25, 2008 3:39 am
- Post datetime: 2008-12-25T17:53:40+00:00
- Post Title: Dissidia Final Fantasy. LBA help

The ARC and MPK extractors need to be run from command prompt, right?

How is that done?
## Post #8
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2008-12-25T18:02:37+00:00
- Post Title: Dissidia Final Fantasy. LBA help

yes, they're in command line.

mpkextr file.mpk or   for %%i in (*.mpk) do mpkextr "%%i"    for multiple files

arcextr  file.arc  or   for %%i in (*.arc) do arcextr "%%i"      for multiple files
## Post #9
- Username: MysterySword
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Dec 25, 2008 3:39 am
- Post datetime: 2008-12-26T04:47:58+00:00
- Post Title: Dissidia Final Fantasy. LBA help

Thanks!

I extracted the MPK and ARC files and looked around. Any way to extract the PAK files?

EDIT: Nevermind, I don't need it anymore...
## Post #10
- Username: safersephiroth
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 05, 2009 2:26 pm
- Post datetime: 2009-03-05T08:51:07+00:00
- Post Title: Dissidia Final Fantasy. LBA help

Hi there,

Is there a tool to compile extracted data from Package.Bin because most of the tools available so far are for extraction only?
## Post #11
- Username: amandak695
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 06, 2010 9:59 am
- Post datetime: 2010-10-06T03:04:39+00:00
- Post Title: Dissidia Final Fantasy. LBA help

> Reply from Xino
>
> Hey there. I want to extract the files from the Munge file "PACKAGE.BIN" from Dissidia FF (PSP)
The LBA is in another file called "PACKAGE_INFO.BIN" but i can´t find the structure...

I uploaded both files. Munge file splitted into two 5 Mb parts, one for Begin of file and one for end.
Code: Select allhttp://www.mediafire.com/?0ogxpndqz3o

Any help will be appreciated.
Thanks you for the post.
