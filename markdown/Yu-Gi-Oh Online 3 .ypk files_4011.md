## Post #1
- Username: astro
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 24, 2006 4:34 pm
- Post datetime: 2010-01-05T09:20:28+00:00
- Post Title: Yu-Gi-Oh Online 3 .ypk files

Information about olger games in the series [http://yugiohextractor.sourceforge.net/ ... tation.htm](http://yugiohextractor.sourceforge.net/documentation.htm)
Yu-Gi-Oh Online 1  used LZSS compression on some files

Full Beta version of game here: [http://www.yugioh-online.net/top/common ... or/?lng=en](http://www.yugioh-online.net/top/common/duel_accelerator/?lng=en)


Here are some files [http://www.sendspace.com/file/bqdses](http://www.sendspace.com/file/bqdses)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-05T13:39:04+00:00
- Post Title: Yu-Gi-Oh Online 3 .ypk files

these files are simply ZIP archives with different signatures and luckily the "magic" zip.bms can do a perfect job with them:
[QuickBMS](http://aluigi.org/papers.htm#quickbms) and [zip.bms](http://aluigi.org/papers/bms/zip.bms)
## Post #3
- Username: astro
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 24, 2006 4:34 pm
- Post datetime: 2010-01-05T14:27:43+00:00
- Post Title: Yu-Gi-Oh Online 3 .ypk files

Thank you aluigi. Everything works perfectly
## Post #4
- Username: skylinewsw
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jan 19, 2010 1:42 am
- Post datetime: 2010-01-18T18:42:01+00:00
- Post Title: Yu-Gi-Oh Online 3 .ypk files

yes it still worx but what about these files? i add this as an rar to this post need a script for this type

thx anyway
[1.rar](https://xentaxbackup.github.io/file/2741_1.rar)
## Post #5
- Username: Tattva
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 14, 2010 5:33 pm
- Post datetime: 2010-03-14T13:32:45+00:00
- Post Title: Yu-Gi-Oh Online 3 .ypk files

> Reply from aluigi
>
> these files are simply ZIP archives with different signatures and luckily the "magic" zip.bms can do a perfect job with them:
QuickBMS and zip.bms

Maybe I am totally wrong, but if the .bms file contains the necessary information to extract the data from these ypk zip files,
wouldn't it be also possible to create such archives?
What I would like to do is extract the textfile containing the words censored in the ingame chat from the ypk, alter it - i.e. delete all words
or at least change them - and then save that textfile into the ypk. In Yu-Gi-Oh! Online 3: Stardust Accelerator the censoring is extremely
annoying. The file containing the censored words is really just a plain textfile containing *quickly checking* 998 words. Even if a word you enter
contains a word from the list as a part it is censored - for example you couldn't write classy … that would result in cl***y, because
the word ass is of course censored. Maybe you can imagine how much fun it is to use that chat. ^_^'

I hope there is some tool somewhere that can create archives based on the algorythm information contained in .bms files.

Tattva
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-14T15:40:43+00:00
- Post Title: Yu-Gi-Oh Online 3 .ypk files

the archives are simple ZIP files with the following differences:
- instead of having the PK signature they use YO
- it's used only the local file header of the ZIP archive so without end and central

I guess you can pack the extracted files in the following easy way:
- zip them using the deflate algorithm (I tell you because some archivers like winzip use other algorithms like 7zip/ppm if you set the highest compression)
- open the zip archive with a hex editor and replace any occurrence of the bytes "50 4b 03 04" with "59 4f 03 04"
- change the extension from zip to ypk
## Post #7
- Username: astro
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 24, 2006 4:34 pm
- Post datetime: 2010-03-14T15:44:22+00:00
- Post Title: Yu-Gi-Oh Online 3 .ypk files

> Reply from Tattva
>
> be I am totally wrong, but if the .bms file contains the necessary information to extract the data from these ypk zip files,
wouldn't it be also possible to create such archives?
......
This change would probably be visible on your pc only and all other players would still see stars ****
## Post #8
- Username: Tattva
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 14, 2010 5:33 pm
- Post datetime: 2010-04-03T07:47:56+00:00
- Post Title: Yu-Gi-Oh Online 3 .ypk files

> Reply from aluigi
>
> 
I guess you can pack the extracted files in the following easy way:
- zip them using the deflate algorithm (I tell you because some archivers like winzip use other algorithms like 7zip/ppm if you set the highest compression)
- open the zip archive with a hex editor and replace any occurrence of the bytes "50 4b 03 04" with "59 4f 03 04"
- change the extension from zip to ypk

OK. That's giving me hope ^_^
Please tell me what tool I can use to zip them using the algorithm from the bms file. Please make it some sort of manual if possible 
Hex-Editor is OK. I know how to use these.
## Post #9
- Username: Tattva
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 14, 2010 5:33 pm
- Post datetime: 2010-04-11T04:58:48+00:00
- Post Title: Yu-Gi-Oh Online 3 .ypk files

> Reply from Tattva
>
> aluigi wrote:
I guess you can pack the extracted files in the following easy way:
- zip them using the deflate algorithm (I tell you because some archivers like winzip use other algorithms like 7zip/ppm if you set the highest compression)
- open the zip archive with a hex editor and replace any occurrence of the bytes "50 4b 03 04" with "59 4f 03 04"
- change the extension from zip to ypk

OK. That's giving me hope ^_^
Please tell me what tool I can use to zip them using the algorithm from the bms file. Please make it some sort of manual if possible 
Hex-Editor is OK. I know how to use these.

I usually don't do this, but I urgently need help/guidance with this.
So   

#bump#
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-11T06:54:27+00:00
- Post Title: Yu-Gi-Oh Online 3 .ypk files

mah, I said that any archiver was ok anyway use 7-zip that allows to choose any field:
[http://www.7-zip.org](http://www.7-zip.org)
