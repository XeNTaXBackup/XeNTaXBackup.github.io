## Post #1
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2016-03-16T14:43:37+00:00
- Post Title: God Of War 3 DDS file

Hi all! How can I conver normal DDS file to DDS NVTT like this?

ORIGIN (A):

```
DDS |......P........................................................NVTT.... ...........................ÿ.......................
```


```
44 44 53 20 7C 00 00 00 0F 10 02 50 00 02 00 00 00 01 00 00 00 01 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 4E 56 54 54 00 01 02 00 20 00 00 00 02 00 00 00 00 00 00 00 08 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 FF 00 00 00 00 10 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
```


NEW FILE FROM ME (B):

```
DDS |....................................................................... .......DXT5........................................
```


```
44 44 53 20 7C 00 00 00 07 10 08 00 00 02 00 00 00 01 00 00 00 00 02 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 20 00 00 00 04 00 00 00 44 58 54 35 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 10 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
```


I can not convert (B) to (A)! Could you help me, please? Thanks

My example file: 

 Font Texture.rar
(71.54 KiB) Downloaded 37 times
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2016-03-16T17:27:37+00:00
- Post Title: God Of War 3 DDS file

In Photoshop
[](http://img4.uploadhouse.com/fileuploads/22229/222294442e58f32afad065a37892bcd6b2a037f4.jpg)

In GIMP + DDS plugin
[](http://img5.uploadhouse.com/fileuploads/22229/22229445d0646533a76c73cacc6cb14a51f7afa6.jpg)


BTW you don't need that "NVTT" mark, but if you want ,you can write it into new texture manually with hex editor.


Notice: On the end of the original texture, there is a font description.

[](http://img3.uploadhouse.com/fileuploads/22229/222294432d568f06da8122fcd6e260e6c071fefb.jpg)
## Post #3
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2016-03-17T00:57:40+00:00
- Post Title: God Of War 3 DDS file

> Reply from merlinsvk
>
> In Photoshop


In GIMP + DDS plugin



BTW you don't need that "NVTT" mark, but if you want ,you can write it into new texture manually with hex editor.


Notice: On the end of the original texture, there is a font description.

Thanks! Working perfect! Thank you very much.
