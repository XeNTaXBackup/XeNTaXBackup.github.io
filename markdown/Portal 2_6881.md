## Post #1
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-07-01T04:45:59+00:00
- Post Title: Portal 2

Hello,

Can anyone help me to repack this files please? What i need is to subtitles_czech.txt file turn into subtitles_english.360.dat format for x360. it should be the same format as it is for PC expect it is big endiannes. So if you repack the PC file than X360 would be piece of cake after all. 

Original File in TXT form - PC:

```
http://loadfiles.in/lrzusd3xh1d0/subtitles_czech.txt
```


Original File in dat form - PC - little endianess:

```
http://loadfiles.in/jr1mqa35bmyr/subtitles_czech.dat
```


Original File in dat form - X360 - big endianess:

```
http://loadfiles.in/1hqnbmvmz7s9/subtitles_english.360.dat
```


Thank you in advance
## Post #2
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-07-04T10:48:16+00:00
- Post Title: Portal 2

please anyone ?
## Post #3
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-07-07T16:15:13+00:00
- Post Title: Portal 2

i think source sdk can convert txt to dat format.
with captioncompiler  that is in source sdk.
## Post #4
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-07-08T20:23:57+00:00
- Post Title: Portal 2

> Reply from rengareng
>
> i think source sdk can convert txt to dat format.
with captioncompiler  that is in source sdk.

Ok i have it just need to try thx a lot for kick up
## Post #5
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-07-10T10:23:03+00:00
- Post Title: Portal 2

> Reply from rengareng
>
> i think source sdk can convert txt to dat format.
with captioncompiler  that is in source sdk.

Idid worked but only for PC, i would like to get something for X360 . Anyone pls ?
## Post #6
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-07-11T14:51:17+00:00
- Post Title: Portal 2

you can change little endian to big endian with notepad++. just from coding, choose convert to big endian. then try to this txt file  compile in sdk.
## Post #7
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-07-11T15:39:04+00:00
- Post Title: Portal 2

> Reply from rengareng
>
> you can change little endian to big endian with notepad++. just from coding, choose convert to big endian. then try to this txt file  compile in sdk.

Hm, you cant do it as it is byte reversed!
## Post #8
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2011-07-20T12:27:44+00:00
- Post Title: Portal 2

notepad++ automatically, should reverse bytes.
## Post #9
- Username: cfarl
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 21, 2017 2:49 am
- Post datetime: 2017-11-20T19:10:10+00:00
- Post Title: Portal 2

> Reply from michalss
>
> rengareng wrote:i think source sdk can convert txt to dat format.
with captioncompiler  that is in source sdk.

Idid worked but only for PC, i would like to get something for X360 . Anyone pls ?

First of all, generate the .dat file using captioncompiler. This .dat is in PC format.

Then, submit the PC .dat file to the following quickbms script:

```
get DUMMY long
get DUMMY long
get DUMMY long
get FILES long
get DUMMY long
for i = 0 < FILES
    get DUMMY long
    get DUMMY long
    get DUMMY short
    get DUMMY short
next i
get DAT_SIZE asize
for
    savepos TMP
    if TMP u>= DAT_SIZE
        break
    endif
    get CHAR short
next
```


I'm doing a Portal translation to PT-BR, and it worked to me.

Ps. I'm using the following command: quickbms.exe -E -w script.bms closecaption_english.dat
