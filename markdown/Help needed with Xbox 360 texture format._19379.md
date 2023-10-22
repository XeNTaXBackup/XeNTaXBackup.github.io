## Post #1
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-01-25T06:24:43+00:00
- Post Title: Help needed with Xbox 360 texture format.

I would like to know how I would go about adding compatibility for a new and unknown "to me" texture format, to my Noesis script.
Attached is a sample of the format.

Edit: I think it's R5G6B5, but I am not 100%.

Thanks, 
GHFear
[000a1e80.zip](https://xentaxbackup.github.io/file/15576_000a1e80.zip)
## Post #2
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2019-01-25T21:26:22+00:00
- Post Title: Help needed with Xbox 360 texture format.

Yes, It's probably R5G6B5. I converted your file to xpr and make rdf file with unbundler and got the texture format. I think you did same  

```

<RDF Version="XPR2">

<Texture
   Name   = "strName"
   Source = "strName.tga"
   Format = "D3DFMT_R5G6B5"
   Width  = "128"
   Height = "128"
   Levels = "8"
/>

</RDF>

```

However I have no idea how to open it with noesis, but hopefully someone will help you.
[000a1e80.xpr.zip](https://xentaxbackup.github.io/file/15580_000a1e80.xpr.zip)
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-01-25T21:58:24+00:00
- Post Title: Help needed with Xbox 360 texture format.

this was the only way i could get a sensible image from the sample:

```
        data = rapi.imageUntile360Raw(data, imgWidth, imgHeight, 2)
        data = rapi.imageDecodeRaw(data, imgWidth, imgHeight, "a8p8")
        texFmt = noesis.NOESISTEX_RGBA32
```

looks like asphalt pavement or something.
## Post #4
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-01-25T23:14:56+00:00
- Post Title: Help needed with Xbox 360 texture format.

> Reply from Acewell
>
> this was the only way i could get a sensible image from the sample:
Code: Select all    elif imgFmt == 0x44:
        data = rapi.imageUntile360Raw(data, imgWidth, imgHeight, 2)
        data = rapi.imageDecodeRaw(data, imgWidth, imgHeight, "a8p8")
        texFmt = noesis.NOESISTEX_RGBA32
looks like asphalt pavement or something.

I love you dude. You are a true hero!  That was the last format that the Skate games use ^^ Now every texture can be extracted.
Worked perfectly!
## Post #5
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2019-01-26T09:49:06+00:00
- Post Title: Help needed with Xbox 360 texture format.

It's a slightly difference between noesis and unbundler extracted images. Noesis extracted is grayscale and transparent instead of unbundler image is colored. I don't think how about other images but that is what I noticed.

[](https://imgbb.com/)
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-01-26T11:25:08+00:00
- Post Title: Help needed with Xbox 360 texture format.

okay i can get that same image as your unbundler with this:  

```
        data = rapi.imageUntile360Raw(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 2)
        data = rapi.imageDecodeRaw(data, imgWidth, imgHeight, "b5g6r5")
        texFmt = noesis.NOESISTEX_RGBA32

```

not sure why i didn't try swapping endianness before
## Post #7
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-01-26T19:03:40+00:00
- Post Title: Help needed with Xbox 360 texture format.

> Reply from Acewell
>
> okay i can get that same image as your unbundler with this:  
Code: Select all    elif imgFmt == 0x44:
        data = rapi.imageUntile360Raw(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 2)
        data = rapi.imageDecodeRaw(data, imgWidth, imgHeight, "b5g6r5")
        texFmt = noesis.NOESISTEX_RGBA32

not sure why i didn't try swapping endianness before

Huh.. its funny. That texture and like 1 other were the only ones coming out grayscaled. Every other one game out right. But I Will update it. 
Thanks so much.
## Post #8
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-01-26T21:11:15+00:00
- Post Title: Help needed with Xbox 360 texture format.

> Reply from Acewell
>
> okay i can get that same image as your unbundler with this:  
Code: Select all    elif imgFmt == 0x44:
        data = rapi.imageUntile360Raw(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 2)
        data = rapi.imageDecodeRaw(data, imgWidth, imgHeight, "b5g6r5")
        texFmt = noesis.NOESISTEX_RGBA32

not sure why i didn't try swapping endianness before

Okay, so implementing that doesn't work for me. It gives me the error "An integer is required" when I try to use b5g6r5. 
Any idea why that could be?
## Post #9
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-01-26T21:18:43+00:00
- Post Title: Help needed with Xbox 360 texture format.

> Reply from GHFear
>
> Acewell wrote:okay i can get that same image as your unbundler with this:  
Code: Select all    elif imgFmt == 0x44:
        data = rapi.imageUntile360Raw(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 2)
        data = rapi.imageDecodeRaw(data, imgWidth, imgHeight, "b5g6r5")
        texFmt = noesis.NOESISTEX_RGBA32

not sure why i didn't try swapping endianness before  

Okay, so implementing that doesn't work for me. It gives me the error "An integer is required" when I try to use b5g6r5. 
Any idea why that could be?

Oh wait... yeah it DOES work with that ONE texture and the other one that didn't work with the other a8p8 method...
So only those 2 seem to actually be b5g6r5, but both a8p8 and b5g6r5 seem to have the format ID 0x44... :/ So no idea how I would distinguish between the two.

Edit: So it seems I was a dumbass and forgot to remove an indentation.
It works perfectly fine now
