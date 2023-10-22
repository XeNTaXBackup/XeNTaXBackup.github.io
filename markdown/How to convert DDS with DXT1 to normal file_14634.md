## Post #1
- Username: fuhuan416
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 22, 2015 6:16 pm
- Post datetime: 2016-07-13T09:11:23+00:00
- Post Title: How to convert DDS with DXT1 to normal file?

I used below QuickBMS script to convert a file of DDS with DXT3, it can be converted and i will see a normal picture. 
But use this script convert DXT1, the image will become a mosaic picture.
I just want to convert DXT1 to a normal picture, any one help me please?
I uploaded a package to the mega.nz, there're 2 files in there, 9700.dds is DXT1, 9728.dds is DXT3, the first one will be mosaic, the second one will be normal converted.
The download key code: !JRS0D7ttupMyzfyP6WgXcYNg22RPGbc9RWguaT6TgvE

> set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
>
> endian big
>
> get size long
>
> getdstring null 0xF
>
> get type byte
>
> get width1 byte
>
> get width2 byte
>
> get height1 byte
>
> get height2 byte
>
> if type == 1
>
> putVarChr MEMORY_FILE 0x57 0x33
>
> endif
>
> if type == 0
>
> putVarChr MEMORY_FILE 0x57 0x31
>
> endif
>
> putVarChr MEMORY_FILE 0x11 width1 byte
>
> putVarChr MEMORY_FILE 0x10 width2 byte
>
> putVarChr MEMORY_FILE 0xD height1 byte
>
> putVarChr MEMORY_FILE 0xC height2 byte
>
> get name filename
>
> append
>
> math size - 0x50
>
> log MEMORY_FILE 0x50 SIZE
>
> append
>
> set count size
>
> math count / 2
>
> goto 0x80 MEMORY_FILE
>
> for i = 0 < count
>
> savepos start MEMORY_FILE
>
> endian little
>
> get num short MEMORY_FILE
>
> endian big
>
> putVarChr MEMORY_FILE start num short
>
> next i
>
> endian little
>
> math SIZE += 0x80
>
> log NAME 0 SIZE MEMORY_FILE
## Post #2
- Username: fuhuan416
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 22, 2015 6:16 pm
- Post datetime: 2016-07-13T09:24:05+00:00
- Post Title: How to convert DDS with DXT1 to normal file?


## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-23T06:52:37+00:00
- Post Title: How to convert DDS with DXT1 to normal file?

Would be worth to mention that you're converting from big to little endian, right?

Your link mega.nz/keycode doesn't work, btw
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-23T08:39:41+00:00
- Post Title: How to convert DDS with DXT1 to normal file?

this problem was solved here some time ago but OP didn't update status   
[http://zenhax.com/viewtopic.php?p=15240#p15240](http://zenhax.com/viewtopic.php?p=15240#p15240)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-23T14:13:12+00:00
- Post Title: How to convert DDS with DXT1 to normal file?

thx!

(yeah, my blacklist of such dumbos is growing bigger...  )
