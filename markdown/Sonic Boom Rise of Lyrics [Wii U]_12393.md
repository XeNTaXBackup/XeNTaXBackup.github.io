## Post #1
- Username: SonicBoom
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 16, 2014 12:51 am
- Post datetime: 2014-12-15T17:01:16+00:00
- Post Title: Sonic Boom: Rise of Lyrics [Wii U]

So, Wii U Sonic Boom used Cry Engine 3. All files packed in "wiiu.stream" format. That's something new for CryEngine. Maybe anyone can unpacked this format?
[https://dl.dropboxusercontent.com/u/818 ... iiu.stream](https://dl.dropboxusercontent.com/u/8181113/heroes.wiiu.stream)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-12-15T17:25:13+00:00
- Post Title: Sonic Boom: Rise of Lyrics [Wii U]

How did you get wii-u files?
## Post #3
- Username: SonicBoom
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 16, 2014 12:51 am
- Post datetime: 2014-12-15T17:54:29+00:00
- Post Title: Sonic Boom: Rise of Lyrics [Wii U]

> Reply from chrrox
>
> How did you get wii-u files?
Private program.
## Post #4
- Username: SonicBoom
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-12-16T10:53:43+00:00
- Post Title: Sonic Boom: Rise of Lyrics [Wii U]

Well here is  a quickbms script.
The compression is unknown currently.
I think it will most likely be in the wii-u sdk but i do not have it.

```
idstring "strm"
get tsize asize
for 
savepos tmp
if tmp == tsize
cleanexit
endif
get zsize long
get size long
get hash long
get unk long
get name string
savepos offset
log name offset zsize
math offset + zsize
goto offset
next
```
## Post #5
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-12-16T12:32:55+00:00
- Post Title: Sonic Boom: Rise of Lyrics [Wii U]

> Reply from SonicBoom
>
> chrrox wrote:How did you get wii-u files?
Private program.
Well it looks like a certain someone doesn't need access to this "private program". This is why the wii-u/3ds/nintendo scene is so trashy. All the fools get access and people who actually know what they're doing are left out.

I suggest that you share that application which would be useful for the community rather than keeping it to your selfish selves. People here help other people for free. I wouldn't condone helping someone who withelds other tools.

My opinion.
## Post #6
- Username: SonicBoom
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 16, 2014 12:51 am
- Post datetime: 2014-12-16T12:40:32+00:00
- Post Title: Sonic Boom: Rise of Lyrics [Wii U]

> Reply from Gh0stBlade
>
> SonicBoom wrote:chrrox wrote:How did you get wii-u files?
Private program.
Well it looks like a certain someone doesn't need access to this "private program". This is why the wii-u/3ds/nintendo scene is so trashy. All the fools get access and people who actually know what they're doing are left out.

I suggest that you share that application which would be useful for the community rather than keeping it to your selfish selves. People here help other people for free. I wouldn't condone helping someone who withelds other tools.

My opinion.

I am not the author of this program (key). I have only the files of the game. When files are opened, all game resources will appear on the Internet.
## Post #7
- Username: SonicBoom
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 16, 2014 12:51 am
- Post datetime: 2015-01-13T18:43:49+00:00
- Post Title: Sonic Boom: Rise of Lyrics [Wii U]

Also, model .chr format. Noesis can open that.
