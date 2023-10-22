## Post #1
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-03-25T13:45:09+00:00
- Post Title: Stacking (~H and ~p extensions)

Could anyone have a look at these strange files (at least the extensions are strange). I suspect they contain the texts for the game.


Thanks in advance!
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2012-03-25T16:39:35+00:00
- Post Title: Stacking (~H and ~p extensions)

I think that .~h file contains table of contents of .~p file. And this one .~p file contains only 56 DDS (DXT1 and DXT5) textures. They are zlib-ed into one package.

Try Aluigi's offzip tool to extract them. Extracted files will have .neo extension, but they are an ordinary DDS textures with added 68 bytes in the beginning of each file.
## Post #3
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-05-04T20:57:04+00:00
- Post Title: Stacking (~H and ~p extensions)

Texts in RgB_Stuff-files (stringtable/costumequest_usenglish, stringtable/cq1patch1_usenglish)
## Post #4
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2012-05-09T20:01:53+00:00
- Post Title: Stacking (~H and ~p extensions)

Tools for translate:


 DoubleFineTool.7z
(34.07 KiB) Downloaded 214 times
## Post #5
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-05-10T07:53:36+00:00
- Post Title: Stacking (~H and ~p extensions)

Does the TextTool.exe work for anybody? It always says "game option is required", but the -u is there.
## Post #6
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-05-10T10:30:21+00:00
- Post Title: Stacking (~H and ~p extensions)

lostprophet
Ex: TextTool.exe -g1 -u stacking_usenglish

-g1 - Stacking
-g2 - Costume Quest

Read ReadMe.txt
## Post #7
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-05-10T20:18:10+00:00
- Post Title: Stacking (~H and ~p extensions)

> Reply from Haoose
>
> lostprophet
Ex: TextTool.exe -g1 -u stacking_usenglish

-g1 - Stacking
-g2 - Costume Quest

Read ReadMe.txt
Since the ReadMe is in Russian or Chinese, I couldn't  Anyway, thanks for the help
## Post #8
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2012-05-11T17:51:48+00:00
- Post Title: Stacking (~H and ~p extensions)

> Reply from lostprophet
>
> Since the ReadMe is in Russian or Chinese, I couldn't  Anyway, thanks for the help
*Japanese
## Post #9
- Username: Rjack
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 14, 2012 4:53 pm
- Post datetime: 2012-06-14T09:12:46+00:00
- Post Title: Stacking (~H and ~p extensions)

> Reply from lostprophet
>
> Haoose wrote:lostprophet
Ex: TextTool.exe -g1 -u stacking_usenglish

-g1 - Stacking
-g2 - Costume Quest

Read ReadMe.txt  
Since the ReadMe is in Russian or Chinese, I couldn't  Anyway, thanks for the help

TextTool.exe -g1 -p costumequest_usenglish.csv

this will change the size of  "costumequest_usenglish.StringTable" from 374KB to 130KB
and then fail to pack "RgB_Stuff".
Anybody could tell me why ?
Thanks.
