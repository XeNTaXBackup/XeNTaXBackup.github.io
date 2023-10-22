## Post #1
- Username: Honoire
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Aug 04, 2012 6:29 pm
- Post datetime: 2012-08-19T22:40:39+00:00
- Post Title: Kuroko no Basuke - -pak files

Last time you guys did a great job while supporting with Corpse Party, this time it's a different game.

After searching for a while I found the usual .cpk file, which contained a lot of .bins, a sound folder and another folder filled with .pak files. Now, I'm not really into extracting/repack tools creation but I was stucked with a similar problem with .pac files, which I think are archives like the .pak ones - judging by the size, I'm quite sure these are text-based. Since they're very small I believe it's possible to leave a sample here, just to let someone of you play a little with it. If it's possible to open and repack them somehow, it would be of great help. Thanks in advance, hope it isn't too much of a bother.
[scene_00000.rar](https://xentaxbackup.github.io/file/5692_scene_00000.rar)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-20T01:06:02+00:00
- Post Title: Kuroko no Basuke - -pak files

try the following and let me know how works with the other files:

```
# script for QuickBMS http://quickbms.aluigi.org

get SIZE asize
callfunction EXTRACT_OFS3

startfunction EXTRACT_OFS3
    idstring "OFS3"
    get DUMMY long
    get NUM short
    get DUMMY short
    get NAMES_OFF long
    savepos BASE_OFF
    math NAMES_OFF += BASE_OFF
    math NAMES_OFF_LIMIT = SIZE
    math NAMES_OFF_LIMIT += BASE_OFF
    math NAMES_OFF_LIMIT -= 0x10
    get FILES long
    for i = 0 < FILES
        get OFFSET long
        get SIZE long
        math OFFSET += BASE_OFF

        if SIZE != 0
            if NAMES_OFF < NAMES_OFF_LIMIT
                savepos TMP
                goto NAMES_OFF
                get NAME string
                savepos NAMES_OFF
                goto TMP
            else
                set NAME string ""
            endif

            savepos TMP
            goto OFFSET
            getdstring SIGN 4
            if SIGN == "OFS3"
                goto OFFSET
                callfunction EXTRACT_OFS3
            else
                log NAME OFFSET SIZE
            endif
            goto TMP
        endif
    next i
endfunction
```
## Post #3
- Username: Honoire
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Aug 04, 2012 6:29 pm
- Post datetime: 2012-08-20T06:36:13+00:00
- Post Title: Kuroko no Basuke - -pak files

Worked with all the .pak files and with .pk too, thank you.
At this time I'm a little concerned about the content of them, which seems to be a bunch of .trb files (first time I encounter these but, I suppose they're related to bigger image/model files) - in the end, no text to be found. Which is a little weird considering this is a game with a lot of text and dialogues.
