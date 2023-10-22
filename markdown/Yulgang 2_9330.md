## Post #1
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-22T05:55:42+00:00
- Post Title: Yulgang 2

I download the game its huge, but bms script really doesnt work in .mpki Data file.

```
#yulgang2 .mpki
#from chrrox
#fix iaw

open FDDE mpki 1
set arcnum 0

goto 0x0c 1
get files long 1

goto 0x20001c 1

for i = 0 < files
    get offset long 1
    get zsize long 1
    get null3 long 1
    get size long 1
    get arcnum long 1
#   print "%arcnum%"
       
    get null1 long 1
    get null2 long 1

    get name string 1
    Padding 4 1
    get null long 1
    set ofile string "ko-kr"

if  name & ofile

    set NAME1 string "ko-KR_"
    set MYEXT string arcnum
    string NAME1 += MYEXT
    string NAME1 += .mpk
    open FDSE NAME1 0

else

    set NAME1 string "Common_"
    set MYEXT string arcnum
    string NAME1 += MYEXT
    string NAME1 += .mpk
    open FDSE NAME1 0

endif

if zsize == size
        log name offset zsize
else
        clog name offset zsize size
endif
next i
```


Error window, hope somebody can help.
## Post #2
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2012-07-22T06:10:59+00:00
- Post Title: Yulgang 2

Common_*.mpk
ko-KR_*.mpk 
data.mpki
On the same directory
## Post #3
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-22T06:36:01+00:00
- Post Title: Yulgang 2

Thanks my friend, its working now.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-22T17:40:55+00:00
- Post Title: Yulgang 2

[viewtopic.php?f=16&t=9086](http://forum.xentax.com/viewtopic.php?f=16&t=9086)
## Post #5
- Username: rexuexiaoz
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jan 17, 2021 4:14 pm
- Post datetime: 2021-01-17T14:29:33+00:00
- Post Title: Yulgang 2

where can I get the 'date.mpki'
I do not have this file
