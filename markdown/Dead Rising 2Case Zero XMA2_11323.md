## Post #1
- Username: MaddaCheeb
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 13, 2011 12:43 pm
- Post datetime: 2014-03-16T01:32:35+00:00
- Post Title: Dead Rising 2:Case Zero XMA2

Hey all,

Been trying to figure out Case Zero's XMA format. Some files in the game are weirdly in the xma1 format and extract through toWav just fine; however, some, like the sample one here, seem to be an encrypted XMA2 format and come out a jumbled mess if i re-do the header and run it through toWav. None of the scripts i have tried running it through have worked, including xma_parse, xmash and many bms scripts. 

Any ideas?

[https://dl.dropboxusercontent.com/u/13825278/39704.xma](https://dl.dropboxusercontent.com/u/13825278/39704.xma)
## Post #2
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-03-17T01:12:21+00:00
- Post Title: Dead Rising 2:Case Zero XMA2

> Reply from MaddaCheeb
>
> Hey all,

Been trying to figure out Case Zero's XMA format. Some files in the game are weirdly in the xma1 format and extract through toWav just fine; however, some, like the sample one here, seem to be an encrypted XMA2 format and come out a jumbled mess if i re-do the header and run it through toWav. None of the scripts i have tried running it through have worked, including xma_parse, xmash and many bms scripts. 

Any ideas?

https://dl.dropboxusercontent.com/u/13825278/39704.xma
use the -2 (for xma 2) option in xma_parse commandline instead of -1. if you don't already have -1 in there, then it could also help to cut out the first 60 (3C in hex) bytes, as the generic riff header can sometimes confuse the parser.
