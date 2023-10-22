## Post #1
- Username: qscrgn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jun 26, 2015 11:19 pm
- Post datetime: 2016-09-03T18:38:28+00:00
- Post Title: YULGANG 2 QuickBMS script help

Hi i have a problem 
I have used this bms script on the forum that it's written for yulgang 2

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


But when i use i have this error





Can you help me?
Link to ko_kr_4.mpk
[https://mega.nz/#!2MtEmTIS!YN41sINFnd0H ... n3srd5Kq-k](https://mega.nz/#!2MtEmTIS!YN41sINFnd0Hj7W-BF5jk-Py9REqPdlqGn3srd5Kq-k)
