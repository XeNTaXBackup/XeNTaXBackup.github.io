## Post #1
- Username: StarQuake
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 03, 2009 8:22 pm
- Post datetime: 2010-05-29T08:15:42+00:00
- Post Title: Help with BMS script for .PAC file

Hi Guys, i need some help with making a BMS script for a .PAC file.
It contains .VOC sounds, I'm not sure how to apply the BMS tutorial 
to this file. Can anyone help me out?  
[PAC.rar](https://xentaxbackup.github.io/file/3079_PAC.rar)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-29T08:52:45+00:00
- Post Title: Help with BMS script for .PAC file

```
get PAC_SIZE asize
get OFFSET long
math FILES = 0x7fffffff
for i = 0 <= FILES
    if i == 0
        math FILES = OFFSET
        math FILES /= 4
        math FILES -= 1
    endif
    get NEXT_OFF long
    if i == FILES
        math NEXT_OFF = PAC_SIZE
    endif
    math SIZE = NEXT_OFF
    math SIZE -= OFFSET
    if SIZE != 0
        log "" OFFSET SIZE
    endif
    math OFFSET = NEXT_OFF
next i
```
## Post #3
- Username: StarQuake
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 03, 2009 8:22 pm
- Post datetime: 2010-05-29T12:35:43+00:00
- Post Title: Help with BMS script for .PAC file

Thanks for your reply, The script extracts the files as it should but they have a .DAT extension instead of .VOC, How can i fix this?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-05-29T12:54:07+00:00
- Post Title: Help with BMS script for .PAC file

endian big
get PAC_SIZE asize
get OFFSET long
math FILES = 0x7fffffff
for i = 0 <= FILES
    if i == 0
        math FILES = OFFSET
        math FILES /= 4
        math FILES -= 1
    endif
    get NEXT_OFF long
    if i == FILES
        math NEXT_OFF = PAC_SIZE
    endif
    math SIZE = NEXT_OFF
    math SIZE -= OFFSET
    if SIZE != 0
   set NAME string i
string name += ".voc"
        log name OFFSET SIZE
    endif
    math OFFSET = NEXT_OFF
next i
## Post #5
- Username: StarQuake
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 03, 2009 8:22 pm
- Post datetime: 2010-05-29T13:53:15+00:00
- Post Title: Help with BMS script for .PAC file

Thank you both for the help, everything's working OK. I really don't like making more demands than I should, but could you possibly take a 
look at one more file? It uses the same format as the previous one and also contains .VOC files but is from a different game. Once again, 
your help is greatly appreciated.
[PAC2.rar](https://xentaxbackup.github.io/file/3081_PAC2.rar)
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-29T15:55:26+00:00
- Post Title: Help with BMS script for .PAC file

note that the VOC extension is added automatically by quickbms using my script, you must have a version of the tool major/equal than 0.4 for having this feature.

about eff.pac the problem is that the file seems cut from the middle of the pac archive because there is not an initial header.
I have also checked if it's used a possible xor obfuscation (with decreasing values) but nothing
