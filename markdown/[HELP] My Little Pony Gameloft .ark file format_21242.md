## Post #1
- Username: Spyrohat
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 13, 2019 7:07 pm
- Post datetime: 2019-10-13T11:15:08+00:00
- Post Title: [HELP] My Little Pony Gameloft .ark file format

Hello. Can someone help with decrypting .ark format files? I’ve looked all over the Internet and nowhere is there a way to open these files. Who can help and write a program to open such files? Or maybe there is already a way to decrypt such files?

I attach a link to a file of this type:
[https://mega.nz/#!FwZiSQTS!bQyCgN8kW7ya ... OjN5MddcI8](https://mega.nz/#!FwZiSQTS!bQyCgN8kW7yaLI180P2FxN2ZoB81jNrU8OjN5MddcI8)

Please help anyone than you can!
## Post #2
- Username: LolHacksRule
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Oct 02, 2018 8:50 am
- Post datetime: 2019-10-30T17:19:22+00:00
- Post Title: [HELP] My Little Pony Gameloft .ark file format

Not encrypted, ZLib compressed, but if you want filenames and directories, you have to decrypt the metadata then extract, unfortunately they changed the key as of some update.
## Post #3
- Username: LolHacksRule
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Oct 02, 2018 8:50 am
- Post datetime: 2019-11-07T17:27:58+00:00
- Post Title: [HELP] My Little Pony Gameloft .ark file format

Ekey made this script:

```
#   Ice Age Adventures (Android / iOS)
#   Littlest Pet Shop (Android)
#   MY LITTLE PONY: Magic Princess (Android)
# script for QuickBMS http://quickbms.aluigi.org

set KEY binary "\x4F\x94\x32\x01\xA1\x5B\x02\x00\x4F\x94\x32\x01\xB5\x88\x99\x00"

get TABLE_SIZE asize
get FILES long
get TABLE_OFFSET long
math TABLE_SIZE -= TABLE_OFFSET

callfunction DecryptTable 1

for i = 0 < FILES
    getdstring NAME 64 MEMORY_FILE
    getdstring PATH 64 MEMORY_FILE
    get OFFSET long MEMORY_FILE
    get SIZE long MEMORY_FILE
    get ZSIZE long MEMORY_FILE
    get ESIZE long MEMORY_FILE
    get TIMESTAMP long MEMORY_FILE
    getdstring MD5 16 MEMORY_FILE
    get RESERVED long MEMORY_FILE
   
    string PATH += NAME
   
    if ESIZE != 0
        log MEMORY_FILE2 OFFSET ESIZE
        encryption xxtea KEY "0x9e3779b9 0" 0 16
        goto 0
        if ZSIZE == SIZE
           log PATH 0 SIZE MEMORY_FILE2
        else
           clog PATH 0 ESIZE SIZE MEMORY_FILE2
        endif
        encryption "" ""
    else
        if ZSIZE == SIZE
           log PATH OFFSET SIZE
        else
           clog PATH OFFSET ZSIZE SIZE
        endif
    endif
next i

startfunction DecryptTable
    encryption xxtea KEY "0x9e3779b9 0" 0 16
    log MEMORY_FILE TABLE_OFFSET TABLE_SIZE
    encryption "" ""
endfunction

```


Like I said due to the encryption key change, this script will only output a memory error when trying to extract this game's ARKs.
## Post #4
- Username: Spyrohat
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 13, 2019 7:07 pm
- Post datetime: 2019-11-09T05:05:01+00:00
- Post Title: [HELP] My Little Pony Gameloft .ark file format

It’s sad.  As I understand it, no one knows how to decrypt these files at present?
## Post #5
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2019-11-09T07:29:38+00:00
- Post Title: [HELP] My Little Pony Gameloft .ark file format

You could try asking on the [game's subreddit](https://www.reddit.com/r/MLPIOS/), since that's where past reverse engineering work has generally been located, but I have no idea if anyone that did that work in the past is still involved or interested these days.
## Post #6
- Username: Spyrohat
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 13, 2019 7:07 pm
- Post datetime: 2019-11-09T07:40:04+00:00
- Post Title: [HELP] My Little Pony Gameloft .ark file format

Thanks, but hardly anyone will help me there. About a year ago I tried to ask for help there, but, unfortunately, no one knows anything about this type of file.
