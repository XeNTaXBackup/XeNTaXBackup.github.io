## Post #1
- Username: d4rkds
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 08, 2020 7:00 pm
- Post datetime: 2022-07-03T23:12:01+00:00
- Post Title: ObsCure 2 (PS2) - Trying to load images

Hello, I've been trying to load images from a Ps2 game, more specifically, the demo of ObsCure 2 found on issue 87 of the Official Ps2 Magazine demo discs. I was able to extract the game's .HVP files with Game Extractor.

The files are extracted without names or any folder structure or extensions, but some of them are bitmap files that can be viewed with any image viewer if given the .bmp extension.
Most of them however can't normally be opened. I've tried opening them with Texture Finder, and while I can see the shape of the image, the colors are all messed up.

I've tried to figure out how to try and load the correct palette in Texture Finder, but I'm not really sure how to use the program and I can't find much info about it.

Could anyone help me out here? I've uploaded a sample file from the game, which looks like this with the default settings on Texture Finder:


[Unnamed File 000177.zip](https://xentaxbackup.github.io/file/22446_Unnamed File 000177.zip)
## Post #2
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2022-07-04T06:29:46+00:00
- Post Title: ObsCure 2 (PS2) - Trying to load images

You can use "Console Texture Explorer", I tried your sample using that tool and the option "PS2" but the colors look weird, so I changed it to "PSP" and now works fine.

Open the file in Hex editor, you can find:

Width at 0xC(00 02 00 00), read the bytes from right to left, so it is: 00 00 02 00 = 200 HEX or 512 DEC
Height at 0x10(00 01 00 00), read the bytes from right to left: 00 00 01 00 = 100 HEX or 256 DEC

palette offset: 0x18, 18 HEX = 24 DEC
image data offset: 0x418, 418 HEX = 1048 DEC

NOTE: You need DEC numbers to use them in CTE.
[sample.jpg](https://xentaxbackup.github.io/file/22447_sample.jpg)
## Post #3
- Username: d4rkds
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 08, 2020 7:00 pm
- Post datetime: 2022-07-04T13:05:34+00:00
- Post Title: ObsCure 2 (PS2) - Trying to load images

> Reply from roocker666 ↑Mon Jul 04, 2022 2:29 pm at Mon Jul 04, 2022 2:29 pm
>
> 
You can use "Console Texture Explorer", I tried your sample using that tool and the option "PS2" but the colors look weird, so I changed it to "PSP" and now works fine.

Open the file in Hex editor, you can find:

Width at 0xC(00 02 00 00), read the bytes from right to left, so it is: 00 00 02 00 = 200 HEX or 512 DEC
Height at 0x10(00 01 00 00), read the bytes from right to left: 00 00 01 00 = 100 HEX or 256 DEC

palette offset: 0x18, 18 HEX = 24 DEC
image data offset: 0x418, 418 HEX = 1048 DEC

NOTE: You need DEC numbers to use them in CTE.

Thank you! This works, but there's something strange going on with the images' colors, all of them have a blue tint, which they don't have in-game. Any idea why this might be happening?
## Post #4
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2022-07-04T20:14:29+00:00
- Post Title: ObsCure 2 (PS2) - Trying to load images

Don't know, maybe you need to swap red and blue channels. Can you upload the in-game texture and the one from CTE?
## Post #5
- Username: d4rkds
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 08, 2020 7:00 pm
- Post datetime: 2022-07-05T12:56:10+00:00
- Post Title: ObsCure 2 (PS2) - Trying to load images

> Reply from roocker666 ↑Tue Jul 05, 2022 4:14 am at Tue Jul 05, 2022 4:14 am
>
> 
Don't know, maybe you need to swap red and blue channels. Can you upload the in-game texture and the one from CTE?

I've attached the extracted files from the demo (the original file and the version I exported with CTE), and here's a screenshot of how the item looks in-game, and also the texture of the same item but exported from the final pc version of the game: [https://imgur.com/a/ct5KDWf](https://imgur.com/a/ct5KDWf)
[sg_shells_item_obs2.zip](https://xentaxbackup.github.io/file/22450_sg_shells_item_obs2.zip)
## Post #6
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2022-07-05T22:44:54+00:00
- Post Title: ObsCure 2 (PS2) - Trying to load images

Yeah, you need to swap red and blue channels, you can do that with Photoshop or Gimp2. Maybe the best way is to write a script for quickbms or Noesis to extract the texture with the right order of colors but I am not good on that..

I used Gimp2 and this is my result:
[demo_convert fix.bmp](https://xentaxbackup.github.io/file/22458_demo_convert fix.bmp)
## Post #7
- Username: d4rkds
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 08, 2020 7:00 pm
- Post datetime: 2022-07-06T15:46:21+00:00
- Post Title: ObsCure 2 (PS2) - Trying to load images

> Reply from roocker666 ↑Wed Jul 06, 2022 6:44 am at Wed Jul 06, 2022 6:44 am
>
> 
Yeah, you need to swap red and blue channels, you can do that with Photoshop or Gimp2. Maybe the best way is to write a script for quickbms or Noesis to extract the texture with the right order of colors but I am not good on that..

I used Gimp2 and this is my result:
Thanks a lot, this seems to work. Sadly I don't know how to automate it either, but it probably won't take me too much time to do it manually.
