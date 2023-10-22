## Post #1
- Username: MeteoraMan
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jul 08, 2010 4:39 am
- Post datetime: 2010-08-25T22:04:43+00:00
- Post Title: Worms Reloaded .bdl file

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Agret
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jan 26, 2006 12:48 pm
- Post datetime: 2010-09-06T14:30:47+00:00
- Post Title: Worms Reloaded .bdl file

```

Signsrch 0.1.6a
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org
  optimized search function from Andrew http://www.team5150.com/~andrew/
  disassembler engine from Oleh Yuschuk

- open file "FrontEnd.bdl"
- 3749390 bytes allocated
- load signatures
- open file H:\Games\Steam\SteamApps\common\worms reloaded\DataPC\Bundles\signsrch.sig
- 1774060 bytes allocated for the signatures
- 2278 signatures in the database
- start signatures scanning:

  offset   num  description [bits.endian.size]
  --------------------------------------------
  00040aeb 309  padding used in hashing algorithms (0x80 0 ... 0) [..64]

- 1 signatures found in the file
```


Would like someone to have a look at this format as I really want it editable too
## Post #3
- Username: Agret
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jan 26, 2006 12:48 pm
- Post datetime: 2010-09-24T07:36:43+00:00
- Post Title: Worms Reloaded .bdl file

Bump
## Post #4
- Username: dogkarl
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Sep 10, 2010 2:56 pm
- Post datetime: 2010-09-30T06:26:57+00:00
- Post Title: Worms Reloaded .bdl file

Actually I've figured this format out. I am trying to translate this game into chinese. The font has a severe limit on glyphs every texture can hold. So now I am working hard to let the texture hold the chinese glyphs.
   The file is a pile of different type of objects. It's a real pain in the ass to modify this bundle file, because it's hard to modify some content without influent the objects afterwards. It's hard to even locate the objects you want to modify. I use binary analysis to locate the font, which changes address every update.
    After I nail this, I think translate to russian would be no big deal. After all, Russian characters is no more than 100, am I right?
## Post #5
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2010-09-30T12:32:05+00:00
- Post Title: Worms Reloaded .bdl file

Great news, dogkarl. Good luck 

> Reply from dogkarl
>
> After all, Russian characters is no more than 100, am I right?

Right, there are 33 characters.
## Post #6
- Username: dogkarl
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Sep 10, 2010 2:56 pm
- Post datetime: 2010-10-01T05:59:43+00:00
- Post Title: Worms Reloaded .bdl file

Well it's done. if you want to see this game in chinese ,please goto " [http://bbs.3dmgame.com/showtopic-1482623.html](http://bbs.3dmgame.com/showtopic-1482623.html)"
, it's in chinese, so do not to be surprised if you got a screen of strange glyphs.
    So if anyone still want to translate this game into their home language, please post the UNICODE range of the glyphs. I will try to help. But for the reason I mentioned above, I will only surport V4 skidrow version of this game.
    As for source code... Its comment and messages are all in chinese, so I will not post it out...at least for now.
