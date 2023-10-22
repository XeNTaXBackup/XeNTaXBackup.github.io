## Post #1
- Username: registerer1111
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 24, 2020 11:05 am
- Post datetime: 2022-02-02T00:39:44+00:00
- Post Title: Deathloop - open resources in quickbms

so im trying to use quickbms to open .resources files from deathloop. it doesnt matter what i select or in what order or if i select the file it wants or not, but it will consistently fail every conversion saying i need to select master_resources.index, which i have done and have put in different orders in the command to start converting but nothing works, it will consistently throw an error. does anyone know how to fix this? is the bms file bugged? if it is, does anyone have a mirror to a working bms file?
## Post #2
- Username: zhelatinobambino
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-02-02T20:28:56+00:00
- Post Title: Deathloop - open resources in quickbms

Every software can have bugs, but in case of quickbms it is more likely fault of a bad written script.

So you should contact script's author in the first place and ask for update.
## Post #3
- Username: registerer1111
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 24, 2020 11:05 am
- Post datetime: 2022-02-02T23:57:58+00:00
- Post Title: Deathloop - open resources in quickbms

alright i figured it out. man am i an idiot... 

i had to ONLY select master_resources.index, not anything else. i guess the reason that it was spitting out errors was bc it was trying to tell me that what i selected wasnt master_resources.index, not that it needed to be in the stack of files to open or whatever i was thinking before
## Post #4
- Username: RogerEye1253
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue May 31, 2022 2:13 am
- Post datetime: 2022-06-24T03:29:22+00:00
- Post Title: Deathloop - open resources in quickbms

> Reply from registerer1111 ↑Thu Feb 03, 2022 7:57 am at Thu Feb 03, 2022 7:57 am
>
> 
alright i figured it out. man am i an idiot... 

i had to ONLY select master_resources.index, not anything else. i guess the reason that it was spitting out errors was bc it was trying to tell me that what i selected wasnt master_resources.index, not that it needed to be in the stack of files to open or whatever i was thinking before

Lol same thing has been happening with me. I was thinking why I was not expecting thisNulls Brawl APK.
## Post #5
- Username: Thethinker
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 09, 2022 6:40 pm
- Post datetime: 2022-10-07T09:28:52+00:00
- Post Title: Deathloop - open resources in quickbms

> Reply from registerer1111 ↑Thu Feb 03, 2022 7:57 am at Thu Feb 03, 2022 7:57 am
>
> 
alright i figured it out. man am i an idiot... 
yowhatsapp apk
i had to ONLY select master_resources.index, not anything else. i guess the reason that it was spitting out errors was bc it was trying to tell me that what i selected wasnt master_resources.index, not that it needed to be in the stack of files to open or whatever i was thinking before

The same was happening with me also. Although it is the issue of master_resources.index I couldn't figure it out.
## Post #6
- Username: fuvegotado
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jun 24, 2019 1:30 am
- Post datetime: 2023-07-05T17:09:04+00:00
- Post Title: Deathloop - open resources in quickbms

I manage to extract a lot of files but the script crashes:

```
*EXCEPTION HANDLER*
-------------------
An error or crash occurred:

*EH* ExceptionCode      c00000fd stack overflow
*EH* ExceptionFlags     00000000
*EH* ExceptionAddress   12B26CB7
*EH* NumberParameters   00000002
*EH*                    00000000
*EH*                    0A642000

Last script line before the error or that produced the error:
  59  clog NAME OFFSET ZSIZE SIZE 1

- OFFSET       0x000000000cc6aae4
- ZSIZE        0x00000000040fd939
- SIZE         0x000000003a2d0e83
  coverage file 0    26%   15839594   60215404   . offset 0000000000f1b16a
  coverage file 1    16%   68147525   425645457  . offset 0000000010d6841d

Press ENTER or close the window to quit
```


Not sure if stuff is missing yet.
