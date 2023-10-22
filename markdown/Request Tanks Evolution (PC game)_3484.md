## Post #1
- Username: songge
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri May 15, 2009 12:00 am
- Post datetime: 2009-05-15T02:28:09+00:00
- Post Title: Request: Tanks Evolution (PC game)

I very like the game -- Tanks Evolution, I want to develop a game use its game resource,
Could you add support to Tanks Evolution, which is a 2d pc game.

I find there are many formats file in the game, such as .rwg .wdt .pak.
Thank you!
## Post #2
- Username: songge
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri May 15, 2009 12:00 am
- Post datetime: 2009-05-15T02:53:11+00:00
- Post Title: Request: Tanks Evolution (PC game)

The file is too big, 10 MB, and I can not upload it. Sorry, but the game is very famous.
I need your help.
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-05-15T12:05:29+00:00
- Post Title: Request: Tanks Evolution (PC game)

Please read the request rules. if you have a link to a dowloadable demo of the game, or you have snippets (use the Fillecutter) you can upload those. Thanks.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-15T13:58:22+00:00
- Post Title: Request: Tanks Evolution (PC game)

note that the filenames are guessed by me without deeper reserarch, just a quick look at them so some of them could be different than their real name:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get FILES long
for i = 0 < FILES
    getdstring NAME 100
    get SIZE long
    get OFFSET long

    strlen NAMELEN NAME
    for j = 0 < NAMELEN
        getvarchr BYTE NAME j
        math BYTE -= 0x23
        if BYTE == 0x0e
            set BYTE byte 0x2e
        endif
        if BYTE == 0x0f
            set BYTE byte 0x5c
        endif
        if BYTE == 0x3f
            putvarchr NAME j 0x5f
        else
            if BYTE >= 0x10
                if BYTE <= 0x1f
                    math BYTE -= 0x10
                    math BYTE += 0x30
                endif
            endif
            putvarchr NAME j BYTE
        endif
   next j

   log NAME OFFSET SIZE
next i
```
p.s.: isn't this section wrong for this type of request?
## Post #5
- Username: songge
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri May 15, 2009 12:00 am
- Post datetime: 2009-05-16T19:18:02+00:00
- Post Title: Request: Tanks Evolution (PC game)

Hi, below is the demo download link:

[http://www.shabugames.com/genres/Shooti ... ution.html](http://www.shabugames.com/genres/Shooting/Tanks_Evolution/Tanks-Evolution.html)

Thank you very much  
Waiting for your answer.
