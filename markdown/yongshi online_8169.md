## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-01T04:53:15+00:00
- Post Title: yongshi online

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-01T11:44:21+00:00
- Post Title: yongshi online

it's only a customized zip file:

```
# script for QuickBMS http://quickbms.aluigi.org

get zip_filesize asize
for offset = 0 < zip_filesize
    idstring "hry"
    get sign threebyte
    if sign == 0x030201     # Local file header
        get flag            short
        get method          short
        get modtime         short
        get moddate         short
        get crc             long
        get comp_size       long
        get uncomp_size     long
        get name_len        short
        get extra_len       short
        getdstring name     name_len
        getdstring extra    extra_len
        savepos offset

        if method == 0
            Log name offset uncomp_size
        else
            if method == 8
                ComType deflate
            else
                print "unsupported compression method %method%"
                cleanexit
            endif
            CLog name offset comp_size uncomp_size
        endif
        math offset += comp_size
        goto offset
    else
        cleanexit
    endif
    savepos offset
next
```
*edit* script updated
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-01T17:04:43+00:00
- Post Title: yongshi online

> Reply from aluigi
>
> it's only a customized zip file:
Code: Select all# Yongshi Online
# script for QuickBMS http://quickbms.aluigi.org

get zip_filesize asize
for offset = 0 < zip_filesize
    idstring "hry"
    get sign threebyte
    if sign == 0x030201     # Local file header
        get flag            short
        get method          short
        get modtime         short
        get moddate         short
        get crc             long
        get comp_size       long
        get uncomp_size     long
        get name_len        short
        get extra_len       short
        getdstring name     name_len
        getdstring extra    extra_len
        savepos offset

        if flag != 0
            if method == 0
                Log name offset uncomp_size
            else
                if method == 8
                    ComType deflate
                else
                    print "unsupported compression method %method%"
                    cleanexit
                endif
                CLog name offset comp_size uncomp_size
            endif
            math offset += comp_size
        endif
        goto offset
    else
        cleanexit
    endif
    savepos offset
next
thanks for scripts aluigi but I try unpack some files and with all get errors.
[Error.jpg](https://xentaxbackup.github.io/file/5025_Error.jpg)
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-01T17:34:54+00:00
- Post Title: yongshi online

sorry a lot for the error, I have fixed it immediately so recheck the previous post
## Post #5
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-01T18:10:46+00:00
- Post Title: yongshi online

> Reply from aluigi
>
> sorry a lot for the error, I have fixed it immediately so recheck the previous postdon't worry aluigi, you're welcome bro, thanks for all support you give, I need learn how make my own bms scripts for don't disturb others, cool job again now it worked fine.

Is a Gamebryo File Format, Version 20.3.0.9.

Some models tested.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-01T18:22:23+00:00
- Post Title: yongshi online

if you learn the bms language and make some script, remember to post it here on xentax.
here we share everything.

and don't worry "to disturb" me, this is my hobby and I plan to have scripts for almost all the games in the world :)
## Post #7
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-01T18:47:10+00:00
- Post Title: yongshi online

> Reply from aluigi
>
> if you learn the bms language and make some script, remember to post it here on xentax.
here we share everything.

and don't worry "to disturb" me, this is my hobby and I plan to have scripts for almost all the games in the worldeh yeah don't worry about that, i'm a good person and like help alway when I can, ofc this is all new for me because need learn not only 1 thing, but I try take some lesson soon have a nice day, take care.
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-08T05:12:30+00:00
- Post Title: yongshi online

That's weird.
Is anyone else getting models that look very...2D?

Cause I'm looking at 20.6 engine and the coords are also very...2D
## Post #9
- Username: EasterSudharta
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 16, 2012 1:48 pm
- Post datetime: 2012-02-16T05:54:36+00:00
- Post Title: yongshi online

Hi anyone have alternative file? i mean hosting file. i can't download it, too bad!
