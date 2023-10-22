## Post #1
- Username: rexnesia
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 09, 2020 2:47 pm
- Post datetime: 2020-09-09T07:59:03+00:00
- Post Title: [HELP] PSV Blue Reflection g1t

i've been trying to manually replacing some texture using several sw available on the net.

Replace one texture (clothes texture) with another using import *.png format.
( Confirmed that kukkii can replace and swizzled image back into *.g1t )
checked *.dds files inside "repacked" *.g1t manually

Problem with Kukkii :

"Replaced" texture (*.dds) is missing 1 mipmap layer,
Repacked *.g1t got some broken value, can't be load into PSV
i try to unpack "repacked" *.g1t using "gust_g1t" and get this error :
Assertion failed: expected_size >= texture_size + (unint32_t)size_of(g1t_tex_header)

I extract back "modded" *.dds from *.g1t using switch_toolbox, then check it manually on the file comparing with the original one.
i've conclusion :

1st and 2nd mipmap layer actually have different swizzle pattern (kukkii only re-create 1 mipmap layer)
1st layer swizzled by kukkii is correctly same as the original swizzled image.
then i try to manually create dds using directx tex tool, i can't find any other sw that have ability to generate custom mipmaps.
copied 1st swizzled layer ( 512x512 ) into 2nd mipmap layer ( 256x256 )

repack it back using gust_g1t, but the image pixel is swizzled incorrectly.


i also try using only 1 layer, but only show full black image on the character.


sample :
[https://mega.nz/file/wA1nxDhB#GYbn9-cEW ... I6cr23nsxE](https://mega.nz/file/wA1nxDhB#GYbn9-cEWstn0pZys_z4QgzO1Oyiup5yCI6cr23nsxE)

original dds sample extract using gust_g1t from PC00_Scl.g1t ( 1st and 2nd layer have different swizzle order ? )


 PC00_Scl.zip
(104.65 KiB) Downloaded 13 times



gladly to sent more sample's if anyone willing to help fixing this issue.
## Post #2
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-09-10T04:38:42+00:00
- Post Title: [HELP] PSV Blue Reflection g1t

> Reply from rexnesia ↑Wed Sep 09, 2020 3:59 pm at Wed Sep 09, 2020 3:59 pm
>
> 
i've been trying to manually replacing some texture using several sw available on the net.

Replace one texture (clothes texture) with another using import *.png format.
( Confirmed that kukkii can replace and swizzled image back into *.g1t )
checked *.dds files inside "repacked" *.g1t manually

Problem with Kukkii :

"Replaced" texture (*.dds) is missing 1 mipmap layer,
Repacked *.g1t got some broken value, can't be load into PSV
i try to unpack "repacked" *.g1t using "gust_g1t" and get this error :
Assertion failed: expected_size >= texture_size + (unint32_t)size_of(g1t_tex_header)

I extract back "modded" *.dds from *.g1t using switch_toolbox, then check it manually on the file comparing with the original one.
i've conclusion :

1st and 2nd mipmap layer actually have different swizzle pattern (kukkii only re-create 1 mipmap layer)
1st layer swizzled by kukkii is correctly same as the original swizzled image.
then i try to manually create dds using directx tex tool, i can't find any other sw that have ability to generate custom mipmaps.
copied 1st swizzled layer ( 512x512 ) into 2nd mipmap layer ( 256x256 )

repack it back using gust_g1t, but the image pixel is swizzled incorrectly.


i also try using only 1 layer, but only show full black image on the character.


sample :
https://mega.nz/file/wA1nxDhB#GYbn9-cEW ... I6cr23nsxE

original dds sample extract using gust_g1t from PC00_Scl.g1t ( 1st and 2nd layer have different swizzle order ? )
PC00_Scl.zip

gladly to sent more sample's if anyone willing to help fixing this issue.

No sure if this will help [viewtopic.php?f=16&t=21666](https://forum.xentax.com/viewtopic.php?f=16&t=21666)
## Post #3
- Username: rexnesia
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 09, 2020 2:47 pm
- Post datetime: 2020-09-10T17:00:48+00:00
- Post Title: [HELP] PSV Blue Reflection g1t

Yes helped to see original model and exporting unswizzled texture.

But not for swizzling back and repack to g1t.
