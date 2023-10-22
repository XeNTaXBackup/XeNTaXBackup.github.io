## Post #1
- Username: kiminru
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Nov 12, 2021 12:42 am
- Post datetime: 2022-05-22T16:42:41+00:00
- Post Title: Ported PS2 Silent Hill 2 text files (mes), need to do is find the font

The inside of the etc.mgf file was replaced, and it was ported.
![1]([https://user-images.githubusercontent.c ... 3bf2f8.png](https://user-images.githubusercontent.com/84241069/169640375-0ad08be9-c710-4f52-9f67-d96d623bf2f8.png))
![2]([https://user-images.githubusercontent.c ... 0b63f8.png](https://user-images.githubusercontent.com/84241069/169640379-4e847363-3fa0-467b-a93c-5642fb0b63f8.png))
![3]([https://user-images.githubusercontent.c ... 25be8b.png](https://user-images.githubusercontent.com/84241069/169640383-52bc1973-22c4-4b2a-982a-0ebc7a25be8b.png))

This is the story of the modder who made the PC version of Silent Hill 2 Korean language patch.

"The font is included in the executable file of sh2pc.exe and is self-compressed. Unfortunately, fortunately, it was ported to XBOX and PC, and it was made with Japanese and Chinese characters included, so the font included in the file was a little over 2000 characters in total. Among them, about 500 characters are used in English ASCII and extended ASCII space, and the rest are in the area where there are fonts but are not used.
The characters of the lines are in the order of the count number of the font. For example, the hex value of ' ' is 0x20, but it is used as 0x00, which becomes - 0x20 in the dialogue file. With this formula, all ASCII values can be obtained as - 0x20. For other characters, first check how many times they are stored, then change the font of the corresponding part to the newly created Korean font and match the number with Korean. The complete Hangul has 2350 characters (Korean is divided into consonants and vowels). I was able to translate it into Korean with about 640 characters."


This is KOREAN font image bmp
There are two in total. large size and small size.

![big]([https://user-images.githubusercontent.c ... 56290e.jpg](https://user-images.githubusercontent.com/84241069/169640456-2c90c5e8-20dc-4b76-96b7-d8c47a56290e.jpg))
![small]([https://user-images.githubusercontent.c ... e25752.jpg](https://user-images.githubusercontent.com/84241069/169640463-0cd497ef-17e2-47d5-8d7f-fe0430e25752.jpg))

Replaced Japanese and Chinese fonts to Korean fonts. Unfortunately, Silent Hill 2 did not have a Korean language at all, so users created it this way. 

Now the lines have been ported, and the fonts used in PS2 and the fonts used in the PC language patch are ported to PS2 and you're done.

The problem is that I do not know where the font image of the PS2 is, and I cannot extract the entire font image of the PC version and the Korean font image. At least not with my skills.
Can someone please help? If you ask for a file, we'll give it to you right away!
## Post #2
- Username: rocstar000
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 19, 2017 3:21 pm
- Post datetime: 2022-05-31T04:11:29+00:00
- Post Title: Ported PS2 Silent Hill 2 text files (mes), need to do is find the font

> The problem is that I do not know where the font image of the PS2 is Hello. Font of the PS2 version is in the SLUS/SLES file.
