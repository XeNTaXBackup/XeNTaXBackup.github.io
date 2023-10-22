## Post #1
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-03-14T22:57:39+00:00
- Post Title: tony hawks project 8 a8r8g8b8 not opening correctly with NOESIS.

Hello. 
So I have this texture here with the format a8r8g8b8 and it is the same format as some other textures I CAN open on Skate 3 and NHL, but it will not open for some reason. I am reading the correct format, width and height and everything seems to be fine, but it still won't open. Would really appreciate some help on this.
File is attached.
Script is attached.

Thanks!
/GHFear
[None](https://xentaxbackup.github.io/file/15892_None)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-15T00:52:20+00:00
- Post Title: tony hawks project 8 a8r8g8b8 not opening correctly with NOESIS.

make sure you read integers etc as unsigned if you sure they are meant to be positive.

```
    imgFmt = bs.readByte()
```

should be

```
    imgFmt = bs.readUByte()
```

the image is too small with no proper name to know if the result is correct though.   

there is also a typo on line 45

```
        data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 83)
```

should be

```
        data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 8)
```
## Post #3
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-03-15T01:08:05+00:00
- Post Title: tony hawks project 8 a8r8g8b8 not opening correctly with NOESIS.

> Reply from Acewell ↑Fri Mar 15, 2019 8:52 am at Fri Mar 15, 2019 8:52 am
>
> 
make sure you read integers etc as unsigned if you sure they are meant to be positive.
Code: Select all    imgFmt = bs.readByte()
should be
Code: Select all    imgFmt = bs.readUByte()
the image is too small with no proper name to know if the result is correct though.   

there is also a typo on line 45
Code: Select all        data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 83)
should be
Code: Select all        data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 8)

I changed it, but I still get the error "TypeError: an integer is required". :/ Did it work for you?
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-15T06:33:56+00:00
- Post Title: tony hawks project 8 a8r8g8b8 not opening correctly with NOESIS.

> Reply from GHFear ↑Fri Mar 15, 2019 9:08 am at Fri Mar 15, 2019 9:08 am
>
> Did it work for you?
yes or i wouldn't have posted.
## Post #5
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-03-15T11:57:45+00:00
- Post Title: tony hawks project 8 a8r8g8b8 not opening correctly with NOESIS.

> Reply from Acewell ↑Fri Mar 15, 2019 2:33 pm at Fri Mar 15, 2019 2:33 pm
>
> 
GHFear wrote: ↑Fri Mar 15, 2019 9:08 amDid it work for you?
yes or i wouldn't have posted.

yeah I changed it all to read UInt and UByte and even changed the imgFMT to read as a UInt, but it just gives me the same error. Send me the script you have working and Ill see if it works on my end. If it doesn't, somethings up with my noesis.
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-16T02:46:13+00:00
- Post Title: tony hawks project 8 a8r8g8b8 not opening correctly with NOESIS.

> Reply from GHFear ↑Fri Mar 15, 2019 7:57 pm at Fri Mar 15, 2019 7:57 pm
>
> Send me the script you have working and Ill see if it works on my end. If it doesn't, somethings up with my noesis.
i already told you what i changed in your script to make it work, readByte() to readUByte(),
otherwise a negative number would be returned and wouldn't satisfy any imgFmt conditions.
## Post #7
- Username: GHFear
- Rank: advanced
- Number of posts: 50
- Joined date: Tue Dec 04, 2018 4:29 pm
- Post datetime: 2019-03-16T14:19:12+00:00
- Post Title: tony hawks project 8 a8r8g8b8 not opening correctly with NOESIS.

> Reply from Acewell ↑Sat Mar 16, 2019 10:46 am at Sat Mar 16, 2019 10:46 am
>
> 
GHFear wrote: ↑Fri Mar 15, 2019 7:57 pmSend me the script you have working and Ill see if it works on my end. If it doesn't, somethings up with my noesis.
i already told you what i changed in your script to make it work, readByte() to readUByte(),
otherwise a negative number would be returned and wouldn't satisfy any imgFmt conditions.

It was the Noesis version I had. I updated to the latest version and now it loads correctly. Thank you for the information man.
I didn't know that about signed and unsigned's. So that's really useful.

Edit: Another problem I am facing now is that any textures larger than 16x16 will give me the error "bad array size". here is a sample on a larger texture with the same format.
[None](https://xentaxbackup.github.io/file/15905_None)
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-16T23:10:01+00:00
- Post Title: tony hawks project 8 a8r8g8b8 not opening correctly with NOESIS.

after closer examination your 2 samples look like fx textures, the first one is a cubemap with a
canvas size of 32x128, the other looks like some color gradient with a canvas size of 64x512.
i only have the 2 samples, you may need to do more investigating into the header flags etc.
