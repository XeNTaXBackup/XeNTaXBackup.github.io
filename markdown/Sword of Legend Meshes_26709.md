## Post #1
- Username: Singasong10
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Oct 04, 2022 5:00 am
- Post datetime: 2023-04-29T00:51:24+00:00
- Post Title: Sword of Legend Meshes?

Anyone know how to extract the meshes from Sword of Legend Online? 

I used the Quickbms Script to open the data files but I cannot open the .models or .dat files.

Download link: [https://store.steampowered.com/app/1418 ... ds_Online/](https://store.steampowered.com/app/1418100/Swords_of_Legends_Online/)

example .model file: [https://mega.nz/file/OdRnyahL#FZOo-VtLQ ... xBlWSZTLUk](https://mega.nz/file/OdRnyahL#FZOo-VtLQj0yKCO9ziElEqC2-ezCxr6d-xBlWSZTLUk)
example .dat file: [https://mega.nz/file/2IJXxISa#0Ktxrqcwy ... mNl8nZbEws](https://mega.nz/file/2IJXxISa#0KtxrqcwyFgCtKaNEIPEmNryKLsqx6vC9mNl8nZbEws)

Any help is appreciated! Thanks!
## Post #2
- Username: roocker666
- Rank: advanced
- Number of posts: 71
- Joined date: Sat Jan 06, 2018 8:39 am
- Post datetime: 2023-04-29T01:31:11+00:00
- Post Title: Sword of Legend Meshes?

Easy, use Model Researcher:



actor1.model.jpg (236.08 KiB) Viewed 115 times



at 0x60 number of vertices(B4 58 00 00) =58B4 Hex = 22708 Dec
0X75 number of faces(8188) = 8881 Hex = 34945 Dec

0x86 vertices address
0x9A Uvs address
0xB1706 Faces address.
## Post #3
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2023-04-29T17:12:17+00:00
- Post Title: Sword of Legend Meshes?

> Reply from Singasong10 ↑Sat Apr 29, 2023 8:51 am at Sat Apr 29, 2023 8:51 am
>
> 
Anyone know how to extract the meshes from Sword of Legend Online?

You can open the Havok Vision Engine .model format since February 16, 2016 using the 3D Object Converter.

How to get the 3D Object Converter:
Download the 3D Object Converter from [ http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it or download and use the portable version (if you don’t have it yet).




Sword_of_Legends.jpg (36.91 KiB) Viewed 92 times
## Post #4
- Username: Singasong10
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Oct 04, 2022 5:00 am
- Post datetime: 2023-04-30T01:01:23+00:00
- Post Title: Sword of Legend Meshes?

Thank you! Both work very well for .model!

Any thoughts for the .dat file?
## Post #5
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-04-30T12:27:03+00:00
- Post Title: Sword of Legend Meshes?

> Reply from Singasong10 ↑Sat Apr 29, 2023 8:51 am at Sat Apr 29, 2023 8:51 am
>
> 
example .model file

send more .model examples
