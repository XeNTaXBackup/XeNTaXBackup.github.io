## Post #1
- Username: alanlcarlos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Oct 24, 2018 7:03 am
- Post datetime: 2019-05-31T23:20:06+00:00
- Post Title: Resident Evil Remaster (Nintendo Switch)

The tools I found to extract Tex files from the Resident  Remaster (PC, XBOX 360, PS3) are not compatible with the .TEX of the  Nintendo Switch .

Does anyone know how to extract Tex DDS from Resident Evil Remaster from Nintendo Switch?
I translated the GMD files into Portuguese, just need to edit the Tex files.

Thank you! Sorry for my bad English

Resident Evil Remaster  .Tex (Nintendo Switch)


 t_id00_01_BM.zip
(18.71 KiB) Downloaded 29 times
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-06-01T10:01:21+00:00
- Post Title: Resident Evil Remaster (Nintendo Switch)

you can use daemon1's Raw Texture tool.   
offset 0x18
width 512
height 256
format BC7
switch swizzle



t_id00_01_BM.PNG (47.69 KiB) Viewed 198 times
## Post #3
- Username: alanlcarlos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Oct 24, 2018 7:03 am
- Post datetime: 2019-06-01T13:54:00+00:00
- Post Title: Resident Evil Remaster (Nintendo Switch)

Worked, thank you!

I was able to extract but I can not save a file in the same format.
If save in Photoshop as DDS (BC7) or as PNG and try to convert to Raw Texture Tool, the DDS file it generates is different from the original and the Switch does not recognize it.
## Post #4
- Username: alanlcarlos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Oct 24, 2018 7:03 am
- Post datetime: 2019-06-01T16:15:49+00:00
- Post Title: Resident Evil Remaster (Nintendo Switch)

Edited post for uploading correct file.

I tried extracting this other file, but I could not.
I tried the same settings above and below.

Offset:0X1C
width 512
height 256
format BC7
swizzle switch
[title01_ID_HQ.7z](https://xentaxbackup.github.io/file/16314_title01_ID_HQ.7z)
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-06-02T03:13:05+00:00
- Post Title: Resident Evil Remaster (Nintendo Switch)

best i can do with your new sample is this, not sure about the colors though.   
offset - 0x14
width - 2048
height - 1024
format - dxt5 (bc3)
no swizzle
## Post #6
- Username: alanlcarlos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Oct 24, 2018 7:03 am
- Post datetime: 2019-06-02T03:51:41+00:00
- Post Title: Resident Evil Remaster (Nintendo Switch)

ooops! I uploaded the wrong file, the file I sent was the PC file. I uploaded it correctly now.
[title01_ID_HQ.7z](https://xentaxbackup.github.io/file/16315_title01_ID_HQ.7z)
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-06-02T05:29:12+00:00
- Post Title: Resident Evil Remaster (Nintendo Switch)

nearly the same as before.   
offset - 0x18
width - 2048
height - 1024
format - dxt5 (bc3)
switch swizzle
## Post #8
- Username: alanlcarlos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Oct 24, 2018 7:03 am
- Post datetime: 2019-06-02T07:02:15+00:00
- Post Title: Resident Evil Remaster (Nintendo Switch)

Thank you very much!

How to find the offset and the format, is there something I can learn, 
hex editor, or discovered just testing in the Raw Texture do daemon ?

I want to know how to find offset and format because I think there is 
more tex with different configurations, so I would not need to upload each file. Thank you!
## Post #9
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2019-06-03T01:24:18+00:00
- Post Title: Resident Evil Remaster (Nintendo Switch)

I've got a QuickBMS script that I originally wrote for Mega Man 11's Switch version which should work with those:
[https://mega.nz/#!ilBCQIQB!9xkd_KXlfUrB ... 2UwpwwJ-6U](https://mega.nz/#!ilBCQIQB!9xkd_KXlfUrB81gcLJPi3pF7W74n3mTqg2UwpwwJ-6U)

Unfortunately those "_HQ" textures have something odd going on with those which I've still yet to figure out.
## Post #10
- Username: a13456393713
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 05, 2023 7:41 pm
- Post datetime: 2023-08-05T14:13:36+00:00
- Post Title: Resident Evil Remaster (Nintendo Switch)

Thank you very much!
