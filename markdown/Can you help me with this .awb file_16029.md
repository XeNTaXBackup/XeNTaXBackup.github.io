## Post #1
- Username: Zyotunravel
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 19, 2017 8:28 am
- Post datetime: 2017-03-19T00:31:59+00:00
- Post Title: Can you help me with this .awb file?

I tried to use Atom viewer and some criware export program but does not work. I just got weird sounds.
[http://rgho.st/7Z9mZspvJ](http://rgho.st/7Z9mZspvJ) Here is the file. Can you help me please !
## Post #2
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2017-03-19T17:11:56+00:00
- Post Title: Can you help me with this .awb file?

```
#   thanks to Taylor&Lion for the alignment field
# script for QuickBMS http://quickbms.aluigi.org

idstring "AFS2"
get FLAGS long
get FILES long
get MYALIGN long
for i = 0 < FILES
    get ALIGN short
    putarray 0 i ALIGN
next i

    callfunction GET_OFFSET 1
    math OFFSET = VALUE
for i = 0 < FILES
    callfunction GET_OFFSET 1
    math NEXT_OFFSET = VALUE
    if MYALIGN != 0
        math ALIGN = MYALIGN
    else
        getarray ALIGN 0 i
    endif
    math OFFSET x= ALIGN
    math SIZE = NEXT_OFFSET
    math SIZE -= OFFSET
    log "" OFFSET SIZE
    math OFFSET = NEXT_OFFSET
next i

startfunction GET_OFFSET
    if FLAGS & 0x200
        get VALUE short
    else
        get VALUE long
    endif
endfunction

```


Aluigi's AWB script. Should work, but I don't know what the outputs are.
## Post #3
- Username: Zyotunravel
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 19, 2017 8:28 am
- Post datetime: 2017-03-19T22:12:59+00:00
- Post Title: Can you help me with this .awb file?

> Reply from Anexenaumoon
>
> Code: Select all# AWB AFS2 (script 0.1.3)
#   thanks to Taylor&Lion for the alignment field
# script for QuickBMS http://quickbms.aluigi.org

idstring "AFS2"
get FLAGS long
get FILES long
get MYALIGN long
for i = 0 < FILES
    get ALIGN short
    putarray 0 i ALIGN
next i

    callfunction GET_OFFSET 1
    math OFFSET = VALUE
for i = 0 < FILES
    callfunction GET_OFFSET 1
    math NEXT_OFFSET = VALUE
    if MYALIGN != 0
        math ALIGN = MYALIGN
    else
        getarray ALIGN 0 i
    endif
    math OFFSET x= ALIGN
    math SIZE = NEXT_OFFSET
    math SIZE -= OFFSET
    log "" OFFSET SIZE
    math OFFSET = NEXT_OFFSET
next i

startfunction GET_OFFSET
    if FLAGS & 0x200
        get VALUE short
    else
        get VALUE long
    endif
endfunction


Aluigi's AWB script. Should work, but I don't know what the outputs are.

I got .dat files, what should i do with them?
