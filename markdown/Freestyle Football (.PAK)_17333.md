## Post #1
- Username: Cheeky
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 27, 2017 4:48 am
- Post datetime: 2017-11-26T21:24:49+00:00
- Post Title: Freestyle Football (*.PAK)

Hello!

I hope you can help me.

The PAK files seem to be a bit different from Freestyle Basketball: [viewtopic.php?f=10&t=9237](http://forum.xentax.com/viewtopic.php?f=10&t=9237)
[Potrait.zip](https://xentaxbackup.github.io/file/13600_Potrait.zip)
## Post #2
- Username: Cheeky
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 27, 2017 4:48 am
- Post datetime: 2017-11-26T21:51:13+00:00
- Post Title: Freestyle Football (*.PAK)

OK i think i found the difference, the name is 256 long.

> # Freestyle Football (PAK format) 
>
> #  
>
> # Written by Ekey (h4x0r) for Freestyle basketball 
>
> # https://progamercity.net
>
> # Modified for Freestyle Football by Cheeky
>
> #  
>
> # script for QuickBMS http://quickbms.aluigi.org 
>
> 
>
> idstring "PACK" 
>
> get TABLEOFFSET long 
>
> get FILES long 
>
> math FILES /= 136 
>
> 
>
> for i = 0 < FILES 
>
>    getdstring NAME 256
>
>    get OFFSET long 
>
>    get SIZE long 
>
>    log NAME OFFSET SIZE 
>
> next i
