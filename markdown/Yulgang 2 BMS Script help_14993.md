## Post #1
- Username: qscrgn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jun 26, 2015 11:19 pm
- Post datetime: 2016-09-03T18:31:58+00:00
- Post Title: Yulgang 2 BMS Script help

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
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-09-03T19:15:40+00:00
- Post Title: Yulgang 2 BMS Script help

the script searches for ko-KR_0-mpki which you didn't provide

lines which (indirectly) causes the error:
open FDDE mpki 1

from quickbms.txt:

```
    It opens a file for reading, practically it assigns a file number/id
    to an existent file that you want to use

    arguments:
      FOLDER    FDDE, means that you want to open the file in the same
                  location of the input one which has the extension
                  provided with NAME
```


You also could do a forum search:
[viewtopic.php?f=16&t=9330](http://forum.xentax.com/viewtopic.php?f=16&t=9330)

> Reply from iaw
>
> Common_*.mpk
ko-KR_*.mpk 
data.mpki
On the same directory
## Post #3
- Username: qscrgn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jun 26, 2015 11:19 pm
- Post datetime: 2016-09-03T19:40:13+00:00
- Post Title: Yulgang 2 BMS Script help

So i muat to put data.mpki all the common_*.mpk and ko-kr_*.mpk in the same folder?
## Post #4
- Username: godskin
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Nov 05, 2015 9:45 pm
- Post datetime: 2016-09-04T02:25:44+00:00
- Post Title: Yulgang 2 BMS Script help

> Reply from qscrgn
>
> So i muat to put data.mpki all the common_*.mpk and ko-kr_*.mpk in the same folder?
unpack data.mpki this main for all
## Post #5
- Username: qscrgn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jun 26, 2015 11:19 pm
- Post datetime: 2016-09-04T08:12:48+00:00
- Post Title: Yulgang 2 BMS Script help

Merci beacoup.
I solved thanks to your suggestions.

Next step find the noesis plugin who work
## Post #6
- Username: troll1981
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jun 10, 2014 2:28 am
- Post datetime: 2016-09-08T09:32:31+00:00
- Post Title: Yulgang 2 BMS Script help

have anybody the client from this game for Download! Homepage is offline from this game !
## Post #7
- Username: godskin
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Nov 05, 2015 9:45 pm
- Post datetime: 2016-09-08T13:53:08+00:00
- Post Title: Yulgang 2 BMS Script help

> Reply from troll1981
>
> have anybody the client from this game for Download! Homepage is offline from this game !
coment 2
[viewtopic.php?f=10&t=14990](http://forum.xentax.com/viewtopic.php?f=10&t=14990)
