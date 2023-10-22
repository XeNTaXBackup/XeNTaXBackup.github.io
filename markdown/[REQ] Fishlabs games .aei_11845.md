## Post #1
- Username: foggys
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Aug 26, 2014 6:11 pm
- Post datetime: 2014-08-26T10:53:19+00:00
- Post Title: [REQ] Fishlabs games *.aei

Hi guys, can anyone help me extract the texture of these files? Thanks

```
https://www.sendspace.com/file/dlg98u
```
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-08-27T23:01:34+00:00
- Post Title: [REQ] Fishlabs games *.aei

Briefly skimmed through the files, from what I've seen they're all RGBA8888. File begins with "AEimage" magic, followed by short with value 256, followed by shorts containing width and height (or the other way around). But what on earth is the stuff after it? It's over a kilobyte of seemingly random bytes or 00s before the actual image data starts.
## Post #3
- Username: darla
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 20, 2014 4:56 pm
- Post datetime: 2014-09-20T09:05:30+00:00
- Post Title: [REQ] Fishlabs games *.aei

Doesn't the Photoshop dds plugin suffice? I've never had a problem with it, but then again, my use of it hasn't been too extensive. It does save in a wide range of formats though, and has a ton of options.
