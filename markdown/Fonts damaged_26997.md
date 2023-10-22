## Post #1
- Username: Qkkskdkwks81
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jun 03, 2023 12:48 pm
- Post datetime: 2023-07-21T11:25:57+00:00
- Post Title: Fonts damaged

Hello guys, I have a big problem that I could not solve in the game Call of Duty: Modern Warfare 3, when I convert the gamefont.iwi file (which is located in localized_english_iw00.iwd/images) to .dds format and modify it with photoshop and add my language letters to an image, and when I convert it back to iwi and return it to localized_english_iw00/Images and enter the game, it appears Letters as if they were encrypted somewhat (like the one in the picture), I tried a lot to solve this, I used a lot of tools and convters, but this did not work, do you have any idea about this problem, please tell me
## Post #2
- Username: Nadya
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 23, 2023 12:47 am
- Post datetime: 2023-07-22T22:46:21+00:00
- Post Title: Fonts damaged

A bitmap font consists of two parts:
1) font texture
2) character coordinates

If the location of characters in the texture is different than specified in the character coordinates, the font will display crookedly in the game, just like in your screenshot.

I assume that you generated the texture in a third-party program, or changed the location of characters in the original texture, so the game font is displayed incorrectly.
## Post #3
- Username: Qkkskdkwks81
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jun 03, 2023 12:48 pm
- Post datetime: 2023-07-23T07:23:11+00:00
- Post Title: Fonts damaged

> Reply from Nadya ↑Sun Jul 23, 2023 6:46 am at Sun Jul 23, 2023 6:46 am
>
> 
A bitmap font consists of two parts:
1) font texture
2) character coordinates

If the location of characters in the texture is different than specified in the character coordinates, the font will display crookedly in the game, just like in your screenshot.

I assume that you generated the texture in a third-party program, or changed the location of characters in the original texture, so the game font is displayed incorrectly.

I created it with Photoshop, but this is something that happens completely without changing or modifying the program, and it is a conversion from iwi to dds and a conversion from dds to iwi without changing anything and also the same thing appears as it is in the image
