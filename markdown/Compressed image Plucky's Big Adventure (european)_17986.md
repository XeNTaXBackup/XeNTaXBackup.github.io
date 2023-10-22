## Post #1
- Username: CruisnEma
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Apr 17, 2018 1:14 am
- Post datetime: 2018-04-16T17:25:57+00:00
- Post Title: Compressed image Plucky's Big Adventure (european)

Hello, I'm a new user. I translated an entire PS1 game called Plucky's big adventure to my language, but there is a problem, I want to overwrite the graphic flag texture in the selection menu, 'cause I translated it overwriting the german language, but also if I change the flag textures with the TIM tool I replace it only when is highlighted, otherwise remain the original german flag, 'cause is an entire image, I have to replace the entire image. The problem is that also if I can find it in the memory dump (is a 16 bit BGR image if I remember correctly) I can't find it directly in the iso files, is certainly compressed. The image is this:



Someone could help me to find it please? If is necessary I can provide also the uncompressed graphic image from the memory dump.

I miss only this detail to complete the translation.
## Post #2
- Username: CruisnEma
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Apr 17, 2018 1:14 am
- Post datetime: 2018-04-22T11:15:34+00:00
- Post Title: Compressed image Plucky's Big Adventure (european)

Please can you help me? Is very important, I miss only this to finish the translation.
## Post #3
- Username: CruisnEma
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Apr 17, 2018 1:14 am
- Post datetime: 2018-05-08T12:56:48+00:00
- Post Title: Compressed image Plucky's Big Adventure (european)

Please help me, I think the compression method could be the same of Tom and Jerry Housetrap, I found leftovers from it in the uncompressed data.
## Post #4
- Username: CruisnEma
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Apr 17, 2018 1:14 am
- Post datetime: 2018-05-23T21:52:32+00:00
- Post Title: Compressed image Plucky's Big Adventure (european)

UP please help me. I want to close this project and I need only this silly thing...
## Post #5
- Username: CruisnEma
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Apr 17, 2018 1:14 am
- Post datetime: 2018-11-09T02:37:39+00:00
- Post Title: Compressed image Plucky's Big Adventure (european)

Noone could help me?
## Post #6
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2021-12-29T07:04:09+00:00
- Post Title: Compressed image Plucky's Big Adventure (european)

Hi!

is not compressed, its just layer chunk.

use this script in resource.res and scan with some tim tools like timview or PSicture

```
# script for QuickBMS http://quickbms.aluigi.org

goto 0x2c
get SIZE asize
putvarchr MEMORY_FILE SIZE 0
log MEMORY_FILE 0 0
append
for OFFSET = 0 u< SIZE
    idstring "\x00\xff\xff\xff\xff\xff\xff\xff\xff\xff\xff\x00"
    get DUMMY long
    get DUMMY long
    get DUMMY long
    savepos OFFSET
    log MEMORY_FILE OFFSET 0x800
    math OFFSET + 0x800
    math OFFSET + 0x118
    goto OFFSET
next
append

get SIZE asize MEMORY_FILE
get NAME basename
get EXT extension
string NAME + "_unchunked."
string NAME + EXT
log NAME 0 SIZE MEMORY_FILE

```
## Post #7
- Username: CruisnEma
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Apr 17, 2018 1:14 am
- Post datetime: 2023-08-24T01:56:14+00:00
- Post Title: Compressed image Plucky's Big Adventure (european)

> Reply from Rabatini ↑Wed Dec 29, 2021 3:04 pm at Wed Dec 29, 2021 3:04 pm
>
> 

Hi @Rabatini, thank you for your reply, sorry for the late.

Just tried with the tool you told me, but I think didn't work, 'cause tools still continues however to find only the same resources, but not the entire image I'm searching. There are some individual TIM for the flags (already replaced by me), but are the animations, but the first frame for everyone are in the huge image that I showed. I would replace the flag before highlight it, considering that 'til do it, will remain the one that you can see in this image. If I highlight it, it change with the animations, but not before.

Then the issue is find that image, that is a 640x480 one.
## Post #8
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2023-08-28T13:34:58+00:00
- Post Title: Compressed image Plucky's Big Adventure (european)

Did you use quickbms?
## Post #9
- Username: CruisnEma
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Apr 17, 2018 1:14 am
- Post datetime: 2023-08-28T15:50:49+00:00
- Post Title: Compressed image Plucky's Big Adventure (european)

> Reply from Rabatini ↑Mon Aug 28, 2023 9:34 pm at Mon Aug 28, 2023 9:34 pm
>
> 
Did you use quickbms?Yup, but simply made a different file where I found she same TIMs... Only with an improved alignment, but the issue is that I can't find the entire image I'm searching. Like I said the flags are in TIMs but are only the animations and not the entire 640x480 background image I posted with the 3 flags that 'til are highlighted don't change swapping the animations TIMs.

i don't know then if is compressed or perhaps a specific proprietary image type... Could you help please?
