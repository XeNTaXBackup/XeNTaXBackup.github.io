## Post #1
- Username: maizeblue11
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Dec 23, 2017 10:59 am
- Post datetime: 2017-12-28T19:56:02+00:00
- Post Title: NCAA 14 (Xbox 360) XPR Textures

I have a couple of textures I want to view in Noesis and they are coming out like this:



Here are the files:

[https://nofile.io/f/MTQ8gM1EEYv/00000000.xpr](https://nofile.io/f/MTQ8gM1EEYv/00000000.xpr)
[https://nofile.io/f/8WJUFcJvR5y/00000001.xpr](https://nofile.io/f/8WJUFcJvR5y/00000001.xpr)

 I will appreciate anyone who can help me with this.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-28T21:20:43+00:00
- Post Title: NCAA 14 (Xbox 360) XPR Textures

like i said on Zenhax, its just big-endian dxt3 untiled  
change line 52 in the xpr script from this:

```

```

to this:

```
            data = rapi.swapEndianArray(data, 2)
```
## Post #3
- Username: maizeblue11
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Dec 23, 2017 10:59 am
- Post datetime: 2017-12-28T22:25:32+00:00
- Post Title: NCAA 14 (Xbox 360) XPR Textures

> Reply from AceWell
>
> like i said on Zenhax, its just big-endian dxt3 untiled  
change line 52 in the xpr script from this:
Code: Select all            data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 16)

to this:
Code: Select all            data = rapi.swapEndianArray(data, 2)
 Sorry dude. I completely missed that. Thanks!
