## Post #1
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2008-02-25T11:35:36+00:00
- Post Title: Mabinogi, PMG model format

I do not have much experience with model formats other than very basics, so I thought I'd ask here.

This is what I have determined of the file format so far:

```
byte majorversion // 2
byte minorversion // 1
dword unk1
char[128] name
dword groupcount

structure * groupcount
char[64] groupname
dword meshcount
substructure * meshcount
dword meshdatasize
char[32] meshname
char[168] unk2

...more data follows... I believe more mesh data equalling of meshdatasize
```


Attached are many example models.
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-02-28T15:14:25+00:00
- Post Title: Mabinogi, PMG model format

Someone hade already made a .x exporter for this. But I can't found the link ATM! Although the format he expressed is not 100% correct, it works for most models! Google Search it if you only want models!

If you want Bones and Animations as well, I can post the format, the only things I can't figure out is the joint blending data inside pmg!

So good luck to you!
## Post #3
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2008-03-06T06:09:44+00:00
- Post Title: Mabinogi, PMG model format

> Reply from fatduck
>
> Someone hade already made a .x exporter for this. But I can't found the link ATM! Although the format he expressed is not 100% correct, it works for most models! Google Search it if you only want models!

If you want Bones and Animations as well, I can post the format, the only things I can't figure out is the joint blending data inside pmg!

So good luck to you!I would appreciate if you could post any information that you do have, thanks in advance .
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-03-27T03:27:41+00:00
- Post Title: Mabinogi, PMG model format

The contents of this post was deleted because of possible forum rules violation.
