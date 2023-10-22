## Post #1
- Username: ElyosOfTheAbyss
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jan 24, 2016 6:42 pm
- Post datetime: 2016-11-16T23:29:28+00:00
- Post Title: SL01 Encryption? (Golden Time: Vivid Memories)

I decided to rip Golden Time: Vivid Memories sprites but when I tried to convert the .gtx they didn't work. I opened them in a hex editor and they all start with SL01 and it looks like its a type of encryption rather than a container.

Here are some sample files: [https://drive.google.com/open?id=0ByT2b ... Uw0YVF6M3M](https://drive.google.com/open?id=0ByT2bSlsZ3XGYzlfeUw0YVF6M3M)

Would there be any way to decrypt them?
## Post #2
- Username: happydance
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 17, 2014 10:11 pm
- Post datetime: 2016-11-17T19:51:57+00:00
- Post Title: SL01 Encryption? (Golden Time: Vivid Memories)

it's not an encryption it's just a lzo1x compression

just made this simple script and worked for the files you've uploaded but don't know if it will work for the rest of the files .

```
goto 0x4
get SIZE long
get ZSIZE long
get NAME FILENAME
string NAME p= "extracted/%s" NAME
clog NAME 0xc ZSIZE SIZE
```
## Post #3
- Username: ElyosOfTheAbyss
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jan 24, 2016 6:42 pm
- Post datetime: 2016-11-18T02:21:10+00:00
- Post Title: SL01 Encryption? (Golden Time: Vivid Memories)

Thank's that works. 
Yeah I meant to say compression not encryption. I was really tired when I wrote that.
## Post #4
- Username: happydance
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 17, 2014 10:11 pm
- Post datetime: 2016-11-18T07:17:51+00:00
- Post Title: SL01 Encryption? (Golden Time: Vivid Memories)

> Reply from ElyosOfTheAbyss
>
> Thank's that works. 
Yeah I meant to say compression not encryption. I was really tired when I wrote that.

no problemo, btw how are you ripping the image from the gxt? by [scarlet](https://github.com/xdanieldzd/Scarlet) or [gxt convert](https://github.com/xdanieldzd/GXTConvert)?
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-18T07:32:29+00:00
- Post Title: SL01 Encryption? (Golden Time: Vivid Memories)

Noesis also has native support to open those decompressed gxt textures
## Post #6
- Username: happydance
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 17, 2014 10:11 pm
- Post datetime: 2016-11-18T10:54:29+00:00
- Post Title: SL01 Encryption? (Golden Time: Vivid Memories)

> Reply from AceWell
>
> Noesis also has native support to open those decompressed gxt textures

it seems neosis cant handle some of those vita gxt, but scarlet/gxt convert can extract some but a few can't still be exported.
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-18T12:53:04+00:00
- Post Title: SL01 Encryption? (Golden Time: Vivid Memories)

according to MrAdults it should be able to handle all of them and you should
upload any that won't work so he might update his plugin if he feels up to it,
but i was mainly referring to the samples provided in this thread when i posted.
## Post #8
- Username: ElyosOfTheAbyss
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jan 24, 2016 6:42 pm
- Post datetime: 2016-11-20T03:58:58+00:00
- Post Title: SL01 Encryption? (Golden Time: Vivid Memories)

> Reply from happydance
>
> ElyosOfTheAbyss wrote:Thank's that works. 
Yeah I meant to say compression not encryption. I was really tired when I wrote that.

no problemo, btw how are you ripping the image from the gxt? by scarlet or gxt convert?
I'm using scarlet since the normal GXTConverter seems to give me a jumbled up mess when I convert it to png. Though I'm about to try the .gtx noesis plugin.
