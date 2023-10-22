## Post #1
- Username: Ploytondo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jan 26, 2011 10:14 pm
- Post datetime: 2011-01-26T14:57:51+00:00
- Post Title: [Wii] Trauma Center (.pak)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-01-26T16:55:55+00:00
- Post Title: [Wii] Trauma Center (.pak)

u8 name[252];
u32 size;
u8 data[size aligned to 64 bytes];
(repeat until end of file)

The last entry in the file should have a null name and size of 0.
## Post #3
- Username: Ploytondo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jan 26, 2011 10:14 pm
- Post datetime: 2011-01-26T17:26:53+00:00
- Post Title: [Wii] Trauma Center (.pak)

Wow thanks a lot!  

Now I just need to make a script... (or wait for someone to make one for me )
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-01-26T17:56:16+00:00
- Post Title: [Wii] Trauma Center (.pak)

> Reply from Rick
>
> u8 name[252];
u32 size;
u8 data[size aligned to 64 bytes];
(repeat until end of file)

The last entry in the file should have a null name and size of 0.

should have just typed out the script

```
endian big

for
  getdstring NAME 252
  get SIZE long
  if SIZE == 0
    cleanexit
  endif
  savepos POS
  log NAME POS SIZE
  math POS += SIZE
  goto POS
  padding 64
next

```


edit: forgot that the wii uses big endian
## Post #5
- Username: Ploytondo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jan 26, 2011 10:14 pm
- Post datetime: 2011-01-26T18:44:24+00:00
- Post Title: [Wii] Trauma Center (.pak)

Thanks for the script, WRS.

I know that the Wii uses big endian, but for some reason the pak file is in little endian.  
So I suggest you modify the script once more.
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-01-27T05:59:31+00:00
- Post Title: [Wii] Trauma Center (.pak)

> Reply from Ploytondo
>
> Thanks for the script, WRS.

I know that the Wii uses big endian, but for some reason the pak file is in little endian.  
So I suggest you modify the script once more.

just remove the line with the endian declaration! quickbms defaults to little endian
## Post #7
- Username: Ploytondo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jan 26, 2011 10:14 pm
- Post datetime: 2011-01-27T07:56:09+00:00
- Post Title: [Wii] Trauma Center (.pak)

Oh ok, and once again thanks for the script!
## Post #8
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-01-29T04:46:46+00:00
- Post Title: [Wii] Trauma Center (.pak)

> Reply from WRS
>
> should have just typed out the scriptI typically don't use quickbms which is why I didn't.
