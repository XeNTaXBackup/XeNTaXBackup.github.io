## Post #1
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2012-09-12T15:43:18+00:00
- Post Title: [PS3]Accel World GPDA archive

Anybody can help with this file to extract GPDA archive.
Here is a resource.dat file cut from Accel World.
[http://www.mediafire.com/?nj5u29mf1x041os](http://www.mediafire.com/?nj5u29mf1x041os)
Thanks.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-12T16:41:51+00:00
- Post Title: [PS3]Accel World GPDA archive

What, accel world game already exists?
lol can't wait to get models of kuroyukihime.

Looks like a recursively defined archive (or at least, they put archives inside other archives).
Don't have quickbms on me but it looks like

```
get unk long
get null long
get FILES long
for i = 0 < FILES
  get OFFSET long
  get unk long
  get SIZE long
  get unk long
  putarray 0 i SIZE
  putarray 1 i OFFSET
next i

for i = 0 < FILES
  get nameLen long
  getdstring NAME nameLen
  putarray 2 i NAME
next i

```


But data is obfuscated I don't know what it is hopefully someone will know lol

EDIT: damn, looks like the only models are the avatars.
## Post #3
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-09-13T09:33:23+00:00
- Post Title: [PS3]Accel World GPDA archive

> Reply from finale00
>
> 

EDIT: damn, looks like the only models are the avatars.

Are u sure? take a look at this small pic: 
[http://sgcafe.com/2012/09/accel-world-p ... -streamed/](http://sgcafe.com/2012/09/accel-world-ps3psp-1st-of-3-countdown-pvs-streamed/)

I think the characters seem to lowpoly to be pre-rendered . It's an hope.
## Post #4
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-09-14T22:57:40+00:00
- Post Title: [PS3]Accel World GPDA archive

> Reply from finale00
>
> EDIT: damn, looks like the only models are the avatars.
I think you're wrong about that.
Look at this!
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-15T03:32:29+00:00
- Post Title: [PS3]Accel World GPDA archive

Guess there are the characters.
Is that the PSP version or the PS3? Or are they both the same low-poly?
## Post #6
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-09-15T07:02:38+00:00
- Post Title: [PS3]Accel World GPDA archive

> Reply from finale00
>
> Guess there are the characters.
Is that the PSP version or the PS3? Or are they both the same low-poly?
PSP version.

Maybe, the PS3 version is bigger than the PSP version.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-15T13:48:51+00:00
- Post Title: [PS3]Accel World GPDA archive

Maybe. Or maybe not.
What did you use to unpack the archives?
## Post #8
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-09-15T14:46:13+00:00
- Post Title: [PS3]Accel World GPDA archive

> Reply from finale00
>
> Maybe. Or maybe not.
What did you use to unpack the archives?
It's just JPcsp rip data
