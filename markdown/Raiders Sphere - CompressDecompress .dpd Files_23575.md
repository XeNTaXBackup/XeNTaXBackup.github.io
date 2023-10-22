## Post #1
- Username: phobosavenger
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 01, 2018 5:38 am
- Post datetime: 2021-03-11T03:53:36+00:00
- Post Title: Raiders Sphere - Compress/Decompress *.dpd Files

I'm trying to get inside a file to create mods of the game Raiders Sphere but unfortunately I can't, the file type is * .dpd could someone help me with a script that decompresses the file?
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-11T09:00:46+00:00
- Post Title: Raiders Sphere - Compress/Decompress *.dpd Files

Can you upload some samples?
## Post #3
- Username: phobosavenger
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 01, 2018 5:38 am
- Post datetime: 2021-03-12T02:38:12+00:00
- Post Title: Raiders Sphere - Compress/Decompress *.dpd Files

> Reply from ikskoks ↑Thu Mar 11, 2021 5:00 pm at Thu Mar 11, 2021 5:00 pm
>
> 
Can you upload some samples?

Yeah!

SpeSystem.pac
[https://drive.google.com/file/d/1NXfCrf ... pGCuV/view](https://drive.google.com/file/d/1NXfCrfu4nFLEAN2ZqVqhzz5JBhDpGCuV/view)

RSE3.dpd
[https://drive.google.com/file/d/1opbizq ... yyDfs/view](https://drive.google.com/file/d/1opbizqVk4Y9JLcylpoFdjecusJ4yyDfs/view)

I forgot to quote the * .pac file but I already sent it too
## Post #4
- Username: phobosavenger
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-13T10:59:44+00:00
- Post Title: Raiders Sphere - Compress/Decompress *.dpd Files

As for PAC file, it was easy to figure out.
Here is documentation [http://wiki.xentax.com/index.php/Raiders_Sphere_PAC](http://wiki.xentax.com/index.php/Raiders_Sphere_PAC)

And here is tool to extract data [https://github.com/bartlomiejduda/Tools ... AC_Tool.py](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/Raiders%20Sphere/Raiders_Sphere_PAC_Tool.py)


As for DPD file, it seems to be more complicated. Offset array looks encrypted and most of the files are compressed, so no easy way to extract until someone will figure out the encryption.
## Post #5
- Username: phobosavenger
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 01, 2018 5:38 am
- Post datetime: 2021-03-13T12:23:01+00:00
- Post Title: Raiders Sphere - Compress/Decompress *.dpd Files

> Reply from ikskoks ↑Sat Mar 13, 2021 6:59 pm at Sat Mar 13, 2021 6:59 pm
>
> 
As for PAC file, it was easy to figure out.
Here is documentation http://wiki.xentax.com/index.php/Raiders_Sphere_PAC

And here is tool to extract data https://github.com/bartlomiejduda/Tools ... AC_Tool.py


As for DPD file, it seems to be more complicated. Offset array looks encrypted and most of the files are compressed, so no easy way to extract until someone will figure out the encryption.

This has already helped me a lot 
Anyway I thank you for the help

There is another pack file with more resources inside it only extracts half, so I just didn’t send you because there wasn’t time to upload
[https://drive.google.com/file/d/1qGFwXw ... sp=sharing](https://drive.google.com/file/d/1qGFwXwJElSW0NBAqw8BfqF0QrPv9rvwY/view?usp=sharing)

Error:
## Post #6
- Username: phobosavenger
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 01, 2018 5:38 am
- Post datetime: 2021-03-13T15:19:28+00:00
- Post Title: Raiders Sphere - Compress/Decompress *.dpd Files

> Reply from phobosavenger ↑Sat Mar 13, 2021 8:23 pm at Sat Mar 13, 2021 8:23 pm
>
> 
ikskoks wrote: ↑Sat Mar 13, 2021 6:59 pm
As for PAC file, it was easy to figure out.
Here is documentation http://wiki.xentax.com/index.php/Raiders_Sphere_PAC

And here is tool to extract data https://github.com/bartlomiejduda/Tools ... AC_Tool.py


As for DPD file, it seems to be more complicated. Offset array looks encrypted and most of the files are compressed, so no easy way to extract until someone will figure out the encryption.


This has already helped me a lot 
Anyway I thank you for the help

There is another pack file with more resources inside it only extracts half, so I just didn’t send you because there wasn’t time to upload
https://drive.google.com/file/d/1qGFwXw ... sp=sharing

Error:

I managed to correct it, changing the decoding method from "utf-8" to "shift-jis"

Is the repack process very difficult?
## Post #7
- Username: phobosavenger
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-13T16:25:19+00:00
- Post Title: Raiders Sphere - Compress/Decompress *.dpd Files

> I managed to correct it, changing the decoding method from "utf-8" to "shift-jis"
Yes, I did the same on my github.  One of the file paths had japaneese characters in it and that's why this error occured.

> Is the repack process very difficult?
No, it's not difficult, because file format for PAC archive is simple. 
You can try to write repacker with some programming language like Python or use QuickBMS scripting for that.
Here are some tutorials explaining this [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)
