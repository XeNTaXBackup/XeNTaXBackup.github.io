## Post #1
- Username: Online_Dude
- Rank: beginner
- Number of posts: 20
- Joined date: Wed May 11, 2005 5:16 am
- Post datetime: 2005-05-18T18:53:02+00:00
- Post Title: Jade Empire (.RIM)

.rim lol
[Jade Empire.rar](https://xentaxbackup.github.io/file/232_Jade Empire.rar)
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-23T10:06:07+00:00
- Post Title: Jade Empire (.RIM)

Here is the Game Extractor (Basic Version) plugin for this game. Unzip it into your plugins/ directory. If you use the full version of Game Extractor, send me an email and I will give you a plugin for the full version.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Plugin_RIM_RIMV10.zip](https://xentaxbackup.github.io/file/248_Plugin_RIM_RIMV10.zip)
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-23T10:17:52+00:00
- Post Title: Jade Empire (.RIM)

And here I am thinking this is a forum where users post requests for MultiEx Commander.
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-23T10:28:37+00:00
- Post Title: Jade Empire (.RIM)

Yeah sorry - i will try to do some scripts for these games too hey. Its just that I redirect all the Game Extractor requests to this forum too so I normally try to get my plugins out to them. I do realise that they are the MexCom forums though, thus the reason why I do try to do the mexcom scripts for the archives as well.

Sorry mate.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-23T10:37:41+00:00
- Post Title: Jade Empire (.RIM)

> Reply from friendsofwatto
>
> Yeah sorry - i will try to do some scripts for these games too hey. Its just that I redirect all the Game Extractor requests to this forum too so I normally try to get my plugins out to them. I do realise that they are the MexCom forums though, thus the reason why I do try to do the mexcom scripts for the archives as well.

Sorry mate.

WATTO
watto@watto.org
http://www.watto.org

No problem. Seeing as you redirect them. Perhaps we should consider a common forum.
## Post #6
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-23T10:42:14+00:00
- Post Title: Jade Empire (.RIM)

Yeah well I always just redirect the people to the forums here because I figured that it would be better to have all requests on the one forums so we can both analyse and add support for the games - rather than me create my own forums for just Game Extractor.

Anyway, in terms of MexCom scripts, here is one for this game...

```
GoTo 12 0 ;
Get FNum Long 0 ;
Get DirOff Long 0 ;
GoTo DirOff 0 ;
For n = 1 to FNum ;
SavePos FNJump 0 ;
Math FNJump += 24 ;
Get FN String 0 ;
GoTo FNJump 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Log FN FO FOO FS FSO ;
Next n ;

```


And as always, an attached compiled script. To use it, go to Tools --> Use Custom Script

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[rim.zip](https://xentaxbackup.github.io/file/249_rim.zip)
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-23T10:55:09+00:00
- Post Title: Jade Empire (.RIM)

I understand.   Thanks for the script, by the way. Soon this Run Custom Script option will become obsolete (well just to test a script perhaps) , and anyone can add the script immediately to the base MRF file from within the program.
## Post #8
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-23T11:01:49+00:00
- Post Title: Jade Empire (.RIM)

That will be a nice addition - can't wait 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-23T12:51:33+00:00
- Post Title: Jade Empire (.RIM)

The script works, 

apart from the Log statement. It's 

```
Log Filename FileOffset FileSize FileOffsetOffset FileSizeOffset ;
```



So 

```
GoTo 12 0 ;
Get FNum Long 0 ;
Get DirOff Long 0 ;
GoTo DirOff 0 ;
For n = 1 To FNum ;
SavePos FNJump 0 ;
Math FNJump += 24 ;
Get FN String 0 ;
GoTo FNJump 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Log FN FO FS FOO FSO ;
Next n ;

```


Not too sure about the importation, as it seems this format uses padding of some kind.

It's available from Web update in MexCom.
## Post #10
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2005-05-23T13:00:56+00:00
- Post Title: Jade Empire (.RIM)

Nice rimjob 

Sorry, I had to.
## Post #11
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-23T22:48:39+00:00
- Post Title: Jade Empire (.RIM)

Oops yeah, I usually don't have a problem with the Log statement - I was making the new script off an old one that didn't have it all filled in. Thanks for the fix.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
