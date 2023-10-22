## Post #1
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2012-02-28T20:32:33+00:00
- Post Title: [Request] Ratchet and Clank *.WAD Archive

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2012-03-02T20:34:36+00:00
- Post Title: [Request] Ratchet and Clank *.WAD Archive

Nothing? Not even a BMS Script? I'd Really like to figure out the File Formates of the Game
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-03T03:07:03+00:00
- Post Title: [Request] Ratchet and Clank *.WAD Archive

horrible format, I don't know if the content can be useful anyway:

```
get MAX_OFF long
math EXPECT = MAX_OFF
math EXPECT x= 0x800
math EXPECT /= 0x800
for
    do
        savepos INFO_OFF
        if INFO_OFF > MAX_OFF
            cleanexit
        endif
        get OFFSET long
    while OFFSET != EXPECT
    get SIZE long
    math EXPECT = OFFSET
    math EXPECT += SIZE
    math OFFSET *= 0x800
    math SIZE *= 0x800
    math TMP = OFFSET
    math TMP += SIZE
    if TMP > FILESIZE
        math SIZE = FILESIZE
        math SIZE -= OFFSET
    endif
    log "" OFFSET SIZE
next
```
*edit* updated
## Post #4
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2012-03-03T03:23:26+00:00
- Post Title: [Request] Ratchet and Clank *.WAD Archive

What dose this do exactly it seems to only pop out a few files... non of them being the VAGp's i've been finding
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-03T03:36:20+00:00
- Post Title: [Request] Ratchet and Clank *.WAD Archive

I see a VAGp file in the audio wad.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-03T13:55:36+00:00
- Post Title: [Request] Ratchet and Clank *.WAD Archive

I see vag files in any archive, they are inside some SBsomething containers
## Post #7
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2012-03-03T16:58:29+00:00
- Post Title: [Request] Ratchet and Clank *.WAD Archive

oh ok i see that now hmm.. SB1... "Sound Banks"?

Any way about the Hidden files... Do i have to Manually Dump the Data to get that?
