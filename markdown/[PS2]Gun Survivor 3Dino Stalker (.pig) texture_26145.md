## Post #1
- Username: wtrace3zh
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Mar 28, 2022 10:56 pm
- Post datetime: 2023-01-05T07:48:00+00:00
- Post Title: [PS2]Gun Survivor 3:Dino Stalker (*.pig) texture

Hello everyone

I'm trying to make a Simplified Chinese translation for Gun Survivor 3 : Dino Stalker

But I'm having trouble modifying the .pig map file, I can't find any tools and information on modifying PIG files

The .pig file appears to be an uncompressed and encrypted texture file, you can observe incorrect images using the CryStal Tile 2 software



QQ图片20230105154211 (1).png (208.6 KiB) Viewed 108 times



Sorry for my poor English, is there any software or method to view and modify the generated pig texture files?

Here is an example pig file,Its header is flag as Pi2Ga

[https://drive.google.com/file/d/1pcpDGa ... sp=sharing](https://drive.google.com/file/d/1pcpDGaSWxGo50GBV_mOb4GyYTVj61rnh/view?usp=sharing)
## Post #2
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2023-01-05T12:59:05+00:00
- Post Title: [PS2]Gun Survivor 3:Dino Stalker (*.pig) texture

Use mummggtool.

Search in the forum.



loading@0000000000.png (1.06 KiB) Viewed 105 times
## Post #3
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2023-01-05T22:49:14+00:00
- Post Title: [PS2]Gun Survivor 3:Dino Stalker (*.pig) texture

C̶a̶n̶ ̶y̶o̶u̶ ̶s̶e̶n̶d̶ ̶m̶o̶r̶e̶ ̶s̶a̶m̶p̶l̶e̶ ̶f̶i̶l̶e̶?̶
̶Y̶o̶u̶r̶ ̶s̶a̶m̶p̶l̶e̶ ̶l̶a̶c̶k̶s̶ ̶t̶h̶e̶ ̶p̶a̶l̶e̶t̶t̶e̶ ̶d̶a̶t̶a̶ ̶n̶e̶e̶d̶e̶d̶ ̶f̶o̶r̶ ̶t̶h̶e̶ ̶c̶o̶r̶r̶e̶c̶t̶ ̶c̶o̶l̶o̶r̶s̶ ̶t̶o̶ ̶s̶h̶o̶w̶n̶.̶
̶O̶r̶ ̶m̶a̶y̶b̶e̶ ̶t̶h̶e̶ ̶p̶a̶l̶e̶t̶t̶e̶ ̶d̶a̶t̶a̶ ̶a̶r̶e̶ ̶i̶n̶ ̶t̶h̶e̶ ̶s̶e̶p̶a̶r̶a̶t̶e̶ ̶f̶i̶l̶e̶?̶ ̶I̶f̶ ̶t̶h̶a̶t̶'̶s̶ ̶t̶h̶e̶ ̶c̶a̶s̶e̶ ̶a̶n̶d̶ ̶t̶h̶e̶r̶e̶'̶s̶ ̶a̶ ̶s̶i̶m̶i̶l̶a̶r̶ ̶n̶a̶m̶e̶d̶ ̶f̶i̶l̶e̶ ̶w̶i̶t̶h̶ ̶d̶i̶f̶f̶e̶r̶e̶n̶t̶ ̶e̶x̶t̶e̶n̶s̶i̶o̶n̶,̶ ̶s̶e̶n̶d̶ ̶i̶t̶ ̶h̶e̶r̶e̶ ̶t̶o̶o̶.̶

Nevermind, the palette data is already there, at offset 0x80. 4-bytes per color (32-bit).
I think I can create some bms script to convert the pig to tm2 and vice versa. Give me some time.
## Post #4
- Username: wtrace3zh
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Mar 28, 2022 10:56 pm
- Post datetime: 2023-01-06T04:47:01+00:00
- Post Title: [PS2]Gun Survivor 3:Dino Stalker (*.pig) texture

> Reply from Rabatini ↑Thu Jan 05, 2023 8:59 pm at Thu Jan 05, 2023 8:59 pm
>
> 
Use mummggtool.

Search in the forum.

loading@0000000000.png

Thanks for your reply, but MummGGTool still can't display the correct color, just like CryStal Tile2
## Post #5
- Username: wtrace3zh
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Mar 28, 2022 10:56 pm
- Post datetime: 2023-01-06T04:51:05+00:00
- Post Title: [PS2]Gun Survivor 3:Dino Stalker (*.pig) texture

> Reply from BloodRaynare ↑Fri Jan 06, 2023 6:49 am at Fri Jan 06, 2023 6:49 am
>
> 
C̶a̶n̶ ̶y̶o̶u̶ ̶s̶e̶n̶d̶ ̶m̶o̶r̶e̶ ̶s̶a̶m̶p̶l̶e̶ ̶f̶i̶l̶e̶?̶
̶Y̶o̶u̶r̶ ̶s̶a̶m̶p̶l̶e̶ ̶l̶a̶c̶k̶s̶ ̶t̶h̶e̶ ̶p̶a̶l̶e̶t̶t̶e̶ ̶d̶a̶t̶a̶ ̶n̶e̶e̶d̶e̶d̶ ̶f̶o̶r̶ ̶t̶h̶e̶ ̶c̶o̶r̶r̶e̶c̶t̶ ̶c̶o̶l̶o̶r̶s̶ ̶t̶o̶ ̶s̶h̶o̶w̶n̶.̶
̶O̶r̶ ̶m̶a̶y̶b̶e̶ ̶t̶h̶e̶ ̶p̶a̶l̶e̶t̶t̶e̶ ̶d̶a̶t̶a̶ ̶a̶r̶e̶ ̶i̶n̶ ̶t̶h̶e̶ ̶s̶e̶p̶a̶r̶a̶t̶e̶ ̶f̶i̶l̶e̶?̶ ̶I̶f̶ ̶t̶h̶a̶t̶'̶s̶ ̶t̶h̶e̶ ̶c̶a̶s̶e̶ ̶a̶n̶d̶ ̶t̶h̶e̶r̶e̶'̶s̶ ̶a̶ ̶s̶i̶m̶i̶l̶a̶r̶ ̶n̶a̶m̶e̶d̶ ̶f̶i̶l̶e̶ ̶w̶i̶t̶h̶ ̶d̶i̶f̶f̶e̶r̶e̶n̶t̶ ̶e̶x̶t̶e̶n̶s̶i̶o̶n̶,̶ ̶s̶e̶n̶d̶ ̶i̶t̶ ̶h̶e̶r̶e̶ ̶t̶o̶o̶.̶

Nevermind, the palette data is already there, at offset 0x80. 4-bytes per color (32-bit).
I think I can create some bms script to convert the pig to tm2 and vice versa. Give me some time.

Thank you very much, I packaged some other pig texture files and hope it can help you 

[https://drive.google.com/file/d/1SvaDlV ... sp=sharing](https://drive.google.com/file/d/1SvaDlV8Z5fORCLdT20N5t-3EdjfkpcAZ/view?usp=sharing)

Sorry for my bad English
## Post #6
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2023-01-06T06:49:22+00:00
- Post Title: [PS2]Gun Survivor 3:Dino Stalker (*.pig) texture

Here's some BMS script to deal with the format conversion.

Some P2IG are packed inside BIN files so you might have to extract/replace it manually with hex editor and keep the size the same as the original.

Oh, the TIM2 to P2IG script are still WIP so the files generated by this script may be incorrect (for instance the replacement textures may look dim/brighter than the original).
[p2ig_scripts.zip](https://xentaxbackup.github.io/file/23266_p2ig_scripts.zip)
## Post #7
- Username: wtrace3zh
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Mar 28, 2022 10:56 pm
- Post datetime: 2023-01-06T08:53:38+00:00
- Post Title: [PS2]Gun Survivor 3:Dino Stalker (*.pig) texture

> Reply from BloodRaynare ↑Fri Jan 06, 2023 2:49 pm at Fri Jan 06, 2023 2:49 pm
>
> 
Here's some BMS script to deal with the format conversion.

Some P2IG are packed inside BIN files so you might have to extract/replace it manually with hex editor and keep the size the same as the original.

Oh, the TIM2 to P2IG script are still WIP so the files generated by this script may be incorrect (for instance the replacement textures may look dim/brighter than the original).

Thank you very much, this BMS script is great, I have not encountered pig files with wrong colors after conversion.

May I add your nickname to the list when the translation is done?