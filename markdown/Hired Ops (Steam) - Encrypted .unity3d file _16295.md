## Post #1
- Username: rpopulik
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Nov 12, 2015 8:28 pm
- Post datetime: 2017-05-19T07:25:35+00:00
- Post Title: Hired Ops (Steam) - Encrypted *.unity3d file ?

Hi there,
I've recently bought on Steam Hired Ops game. It's a standalone version of Contract Wars unity webplayer shooter. I bought this game because I wanted to work with its weapons models. I had no problems with extracting webplayer version assets before, but in webplayer version, I didn't have access to all game resource, only to these downloaded for game sessions. That's why I got standalone version. And generally, in this version I don't have problem with extracting game assets (in *unity3d format) except one folder, unfortunately the most important one, which contains all HQ weapons assets (mostly models and textures files I guess). This folder contains files which look like they are some kind of encrypted. I attached two files: sil_pbs4-lod.unity3d, which extracts with no problems, and ak74.unity3d, which is probably encrypted:
[http://www.mediafire.com/file/jc3xd7w7q ... nity3d.zip](http://www.mediafire.com/file/jc3xd7w7qm65and/unity3d.zip)

So - is there any way to decrypt or convert in other way the second file to make it readable by one of the known unity3d asset extractors ?

Thanks in advance for any help.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-05-19T08:18:56+00:00
- Post Title: Hired Ops (Steam) - Encrypted *.unity3d file ?

its xored with 0x47  

```

get SIZE asize
get EXT extension
get NAME basename
string NAME + "_unxored."
string NAME + EXT
filexor 0x47 0x0
log NAME 0x0 SIZE
```
## Post #3
- Username: rpopulik
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Nov 12, 2015 8:28 pm
- Post datetime: 2017-05-19T10:04:35+00:00
- Post Title: Hired Ops (Steam) - Encrypted *.unity3d file ?

> Reply from AceWell
>
> its xored with 0x47

Thanks Man!   You really made me happy. If you need help with modelling, texturing or animating, don't bother to write.

However unity quickmbs scritp doesn't extract unxored file too, I still can successfully use some of the other available tools (already did it )
## Post #4
- Username: rpopulik
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Nov 12, 2015 8:28 pm
- Post datetime: 2021-04-28T15:56:41+00:00
- Post Title: Hired Ops (Steam) - Encrypted *.unity3d file ?

Looks like it is not only xored anymore :-/
Here are files: [https://www.mediafire.com/file/pm46t3jh ... he.7z/file](https://www.mediafire.com/file/pm46t3jhwdx29ya/Cache.7z/file)
Any help will be appreaciated.
