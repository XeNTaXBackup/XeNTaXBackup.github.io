## Post #1
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-03-21T03:23:36+00:00
- Post Title: Giana Sisters Twisted Dreams

hey guys im trying to get into this files ( im trying to find somone that can make a script for this game)

the headers are SBPAK V 1.0  the file format is .pak
iv tried the Helldorado script found on this site but no go here are some file im uploading the big file as we speak

level files
[http://www.mediafire.com/?y75z44f7x68bd8z](http://www.mediafire.com/?y75z44f7x68bd8z)

game .pak
[https://mega.co.nz/#!jBdHxYLS!Ueso5Bd_- ... hy3stJduHY](https://mega.co.nz/#!jBdHxYLS!Ueso5Bd_-3RDb1ca9jJfrVVjb34r2FyEHhy3stJduHY)

and some random files if anyone is willing
[http://www.mediafire.com/?u1w2141zbi79pm6](http://www.mediafire.com/?u1w2141zbi79pm6)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-21T07:17:49+00:00
- Post Title: Giana Sisters Twisted Dreams

[http://aluigi.altervista.org/papers/bms/helldorado.bms](http://aluigi.altervista.org/papers/bms/helldorado.bms)
## Post #3
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-03-21T12:33:51+00:00
- Post Title: Giana Sisters Twisted Dreams

lol sorry but like i said iv tried it and it doesnt work at all

gives a error right away
## Post #4
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-03-21T20:07:47+00:00
- Post Title: Giana Sisters Twisted Dreams

okay i found a modded version of aluigi script it works with the .pak "tweaked by mvil"

IF ANYONE CAN LOOK IN TO THE OTHER FILES  THAT WOULD BE VERY NICE

idstring "SBPAK V 1.0\r\n\0\0\0"
get DUMMY long  # ever the same
get DUMMY long  # ever the same
filexor 0x08

get DUMMY long
get DUMMY long
get DUMMY long
get FILES long
get DUMMY long
get BASE_OFFSET long
get TOTAL_SIZE long

for i = 0 < FILES
    get SIZE long
    get OFFSET long
    get DUMMY long
    get DUMMY long
    math OFFSET += BASE_OFFSET

    log "" OFFSET SIZE
next i
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-03-21T21:46:58+00:00
- Post Title: Giana Sisters Twisted Dreams

the script you posted is the same available on my website.

anyway I have modified it so that idstring doesn't cover the last 2 bytes so probably it works
## Post #6
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-03-21T23:28:49+00:00
- Post Title: Giana Sisters Twisted Dreams

worked perfect ^_^
 would u be able to look into theses files? if not its cool i asked alot already XD

and some random files if anyone is willing
[http://www.mediafire.com/?u1w2141zbi79pm6](http://www.mediafire.com/?u1w2141zbi79pm6)
## Post #7
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2014-06-17T02:47:46+00:00
- Post Title: Giana Sisters Twisted Dreams

i was looking into these myself, and though I know nothing about model converting, I've figured out which ones ARE the models. Problem is that they're all numerically-named and have the extension ".x86". I'd really love to have a look at them in a compatible format, but like I said, I have no clue on how to do conversion.

Hopefully someone will have luck with it. Here's a sample file.

[https://www.dropbox.com/s/8558j829bpgez ... 000026.x86](https://www.dropbox.com/s/8558j829bpgezgl/0_00000026.x86)
## Post #8
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2014-06-17T14:15:17+00:00
- Post Title: Giana Sisters Twisted Dreams

Noticed dropbox is having a bit of a problem sending out the file, so I also uploaded it to sendspace.

[https://www.sendspace.com/file/u2urmm](https://www.sendspace.com/file/u2urmm)

Sorry for the double post.
