## Post #1
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2019-06-04T19:21:00+00:00
- Post Title: Star Wars Episode III (PS2, .rp2 files)

Does anyone have a way of opening these? They contain the dialogue files: [https://www.zenhax.com/download/file.ph ... 99f6bc48d4](https://www.zenhax.com/download/file.php?id=6458&sid=ffb0c7feb7f90b48fde42599f6bc48d4)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-04T21:52:29+00:00
- Post Title: Star Wars Episode III (PS2, .rp2 files)

The audio in that archive is all standard Playstation 4-bit ADPCM, so you can open and convert them with PSound - there are 103 audio files.
## Post #3
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2019-06-06T06:15:35+00:00
- Post Title: Star Wars Episode III (PS2, .rp2 files)

> Reply from DKDave ↑Wed Jun 05, 2019 5:52 am at Wed Jun 05, 2019 5:52 am
>
> 
The audio in that archive is all standard Playstation 4-bit ADPCM, so you can open and convert them with PSound - there are 103 audio files.

Yeah, but I want them ripped with proper file names.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-06-06T11:24:00+00:00
- Post Title: Star Wars Episode III (PS2, .rp2 files)

here is bms script.  

```

get FOLDER basename
get UNK long
get FILES long
goto 0x18 0 seek_cur
for i = 0 < FILES
    get NAME string
    string NAME p "%s\%s.msv" FOLDER NAME
    goto 0x19 0 seek_cur
    get OFFSET long
    get SIZE long
    get UNK2 long
    log NAME OFFSET SIZE 
next i
```
## Post #5
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2019-06-06T19:26:02+00:00
- Post Title: Star Wars Episode III (PS2, .rp2 files)

Also a little side-note, if you replace this line in Acewell's script from:

```
string NAME p "%s\%s" FOLDER NAME
```


to

```
string NAME p "%s\%s.msv" FOLDER NAME
```


That will extension the files to .msv which is playable with foobar + vgmstream component.
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-06-06T21:51:33+00:00
- Post Title: Star Wars Episode III (PS2, .rp2 files)

> Reply from Pingu ↑Fri Jun 07, 2019 3:26 am at Fri Jun 07, 2019 3:26 am
>
> Also a little side-note, if you replace this line in Acewell's script....
i was going to do this at first but decided against it because
i wasn't sure what proper extension these files should be.   
i have edited the above script to add msv extension now that there is confirmation.
