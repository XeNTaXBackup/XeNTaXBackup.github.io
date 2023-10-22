## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-11-19T00:17:44+00:00
- Post Title: [PC] WWE 2K18 import maxscript

Hi guys! Here's maxscript to import [PC] WWE 2K18 import maxscript models with bones+weights (3ds max 2009-2015). 2K18 format differs from previous WWE games a bit, so here script for it separately. There's ton of bones, so script is slow wait a bit for model to import. Have fun, if you will find it useful!


[WWE_2k18_PC_Exclusive.7z](https://xentaxbackup.github.io/file/13562_WWE_2k18_PC_Exclusive.7z)
## Post #2
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2017-11-27T10:07:54+00:00
- Post Title: [PC] WWE 2K18 import maxscript

Thank you for the maxscript Zaramot. What tools are needed to extract the archives though?
## Post #3
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-11-29T03:15:50+00:00
- Post Title: [PC] WWE 2K18 import maxscript

I know there's a bms script on zenhax by aluigi. And there's a tool for wwe games, I forgot the name of it. I will ask friend of mine, who extracted the files and let you know (I pesonally used bms script, but it's not very handy for most users)
## Post #4
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2017-11-29T06:02:02+00:00
- Post Title: [PC] WWE 2K18 import maxscript

Found the thread on zenhax (I assume) 

[https://zenhax.com/viewtopic.php?t=3240](https://zenhax.com/viewtopic.php?t=3240)

and the script is "yuke" on his quickbms page.

[http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)

Doesn't seem to do textures though so I'm guessing the other tool gets those?
## Post #5
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2017-12-06T07:28:46+00:00
- Post Title: [PC] WWE 2K18 import maxscript

The yukes bms will decompress everything into bpe files, open them in a hex editor to see what files they are and resave them as either dds or yobj files.
The dds is a long process as its usually a few dds files in one bpe file.
Not sure if there is a tool to export bpe files.
## Post #6
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2019-11-30T08:22:53+00:00
- Post Title: [PC] WWE 2K18 import maxscript

Hi there. Thanks for your script, much appreciated. 

I've added a value of zero for the endianess type on the weights so that it loads the weights for pc games older than 2k18. I also removed the transforms on the model in you script to make it compatible with my import tools. 

I'm attaching the updated script:
[WWE_2k18_PC_Exclusive.rar](https://xentaxbackup.github.io/file/17128_WWE_2k18_PC_Exclusive.rar)
