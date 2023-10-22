## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-21T10:39:33+00:00
- Post Title: Tang Dynasty 2

Name: 大唐2
HP: [http://www.dt2.com.cn/](http://www.dt2.com.cn/)
Download: under the registration form, go to step 3 and then click on the button under it



t.jpg (53.28 KiB) Viewed 40 times



Unpacker

```

idstring "TPK"
get unk byte
get unk long
get unk long

for i = 0
  get unk1 long
  get unk long
  get OFFSET long
  get null long
  get SIZE long
  get ZSIZE long
  get unk long
  get unk long
  get unk long
  get unk long
  
  if unk1 != 0
  
    savepos BACK
    goto OFFSET
    get nameLen long
    getdstring NAME nameLen
    math OFFSET += nameLen
    math OFFSET += 4
    log NAME OFFSET SIZE
    goto BACK
  endif
  
  savepos curr
  if curr == 2621412
    break
  endif
next i

```
