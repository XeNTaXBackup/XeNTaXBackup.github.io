## Post #1
- Username: szfzafa
- Rank: advanced
- Number of posts: 56
- Joined date: Sun Feb 27, 2011 6:46 pm
- Post datetime: 2011-04-21T13:02:12+00:00
- Post Title: [Req]  .pac format for PSP (Magical Girl Lyrical Nanoha A's)

The game is called Magical Girl Lyrical Nanoha A's Portable: The Battle of Aces.


Here are some samples of .pac package, from ?:\PSP_GAME\USRDIR\
[http://www.gamefront.com/files/20246953/pac_samples.rar](http://www.gamefront.com/files/20246953/pac_samples.rar)

They contain .gim images/textures and .gmo 3d models. You can see filenames inside them.

Also, I found some bytes with certain meanings:
[(click to enlarge)](http://postimage.org/image/2sr2fblb8/)
But still cannot get the correct file context. Maybe it's using a LZS algorithm.

Anyone take a look into this format would be a great help.. thx~
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-21T15:14:34+00:00
- Post Title: [Req]  .pac format for PSP (Magical Girl Lyrical Nanoha A's)

I don't know what compression it is or if it could be an lzss with different parameters (those I tested gave no good results) so the following is the script without decompression:

```
idstring "add"
goto 0x10
get FILES long
goto 0x20
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    get DUMMY long
    get DUMMY long
    get NAME_OFF long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    savepos TMP
    goto NAME_OFF
    get NAME string
    goto OFFSET
    getdstring SIGN 3
    if SIGN == "LZS"
        get DUMMY byte
        get DUMMY long
        get HEAD_SIZE long
        get DUMMY long
        get SIZE long
        get ZSIZE long
        math ZSIZE  -= HEAD_SIZE
        math OFFSET += HEAD_SIZE
        #clog NAME OFFSET ZSIZE SIZE
        log NAME OFFSET ZSIZE
    else
        log NAME OFFSET SIZE
    endif
    goto TMP
next i
```
so it's mainly for developers who want to find what is the algorithm
## Post #3
- Username: szfzafa
- Rank: advanced
- Number of posts: 56
- Joined date: Sun Feb 27, 2011 6:46 pm
- Post datetime: 2011-04-21T15:59:25+00:00
- Post Title: [Req]  .pac format for PSP (Magical Girl Lyrical Nanoha A's)

> Reply from aluigi
>
> I don't know what compression it is or if it could be an lzss with different parameters (those I tested gave no good results) so the following is the script without decompression:
......
so it's mainly for developers who want to find what is the algorithm
Seems hopeless..  
This game cannot be emulated yet; it's almost impossible to get assembly instructions. Then how can we know the algorithm? That's really hard..  

Correctly I even dunno if this compression is in byte-level or bit-level.. 

Anyway, thx 4 your scripts!
## Post #4
- Username: szfzafa
- Rank: advanced
- Number of posts: 56
- Joined date: Sun Feb 27, 2011 6:46 pm
- Post datetime: 2011-05-13T05:09:55+00:00
- Post Title: [Req]  .pac format for PSP (Magical Girl Lyrical Nanoha A's)

> Reply from aluigi
>
> ...
problem solved.
take a look at this: [viewtopic.php?p=53922#p53922](http://forum.xentax.com/viewtopic.php?p=53922#p53922) 

if u really care about the details, i'll translate the Chinese comments in the src into English.   but i still misunderstand how unpac works..
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-13T09:04:42+00:00
- Post Title: [Req]  .pac format for PSP (Magical Girl Lyrical Nanoha A's)

post the tool?
## Post #6
- Username: szfzafa
- Rank: advanced
- Number of posts: 56
- Joined date: Sun Feb 27, 2011 6:46 pm
- Post datetime: 2011-05-13T10:22:23+00:00
- Post Title: [Req]  .pac format for PSP (Magical Girl Lyrical Nanoha A's)

> Reply from chrrox
>
> post the tool?
As i said in [viewtopic.php?p=53907#p53907](http://forum.xentax.com/viewtopic.php?p=53907#p53907), leoheart, the translator, posted the tool in his fc2 blog ([http://leoheart.blog43.fc2.com/?mode=edit&rno=2150](http://leoheart.blog43.fc2.com/?mode=edit&rno=2150)) in a MF link.
don't forget to add "-z" parameter. usage: [viewtopic.php?p=53926#p53926](http://forum.xentax.com/viewtopic.php?p=53926#p53926)

btw, i saw u in gameresearch.5d6d, chrrox~
## Post #7
- Username: kinlyki
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Jun 21, 2015 12:36 am
- Post datetime: 2019-01-10T15:06:36+00:00
- Post Title: [Req]  .pac format for PSP (Magical Girl Lyrical Nanoha A's)

Can someone reupload the unpac tool? The mediafire link is dead
