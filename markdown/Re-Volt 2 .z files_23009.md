## Post #1
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2020-11-16T02:13:33+00:00
- Post Title: Re-Volt 2 .z files

I'm trying to get the bmp out of this. I'm trying to get the car "FROZEN" from RV2. As far as I know, RV2 ran on the same engine as the original Re-Volt. I've got the PRMs and the parameters, now I'm trying to get the bmps out of these Z files. Can anybody help?
file: [https://www.mediafire.com/file/xyk3wrsh ... bmp.z/file](https://www.mediafire.com/file/xyk3wrshsrrzi4k/CarSkin0.bmp.z/file)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-11-16T08:39:29+00:00
- Post Title: Re-Volt 2 .z files

It is just headerless BMP compressed with ZLIB.
You can use offzip and texturefinder to convert it to BMP.

```
offzip.exe -a CarSkin0.bmp.z out
```


See the wiki article for reference [http://wiki.xentax.com/index.php/Re-Volt_2_Z_Image](http://wiki.xentax.com/index.php/Re-Volt_2_Z_Image)
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-11-17T11:57:22+00:00
- Post Title: Re-Volt 2 .z files

here is Noesis python script to open your one sample.  


 tex_Re-Volt2_z.zip
(596 Bytes) Downloaded 29 times


supports rgba8888
this script will read the header and decompress
and parse the image data on the fly.
## Post #4
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-06-18T17:20:53+00:00
- Post Title: Re-Volt 2 .z files

> Reply from Acewell ↑Tue Nov 17, 2020 7:57 pm at Tue Nov 17, 2020 7:57 pm
>
> 
here is Noesis python script to open your one sample.   
tex_Re-Volt2_z.zip
supports rgba8888
this script will read the header and decompress
and parse the image data on the fly.

Only works with the files you uploaded
Too lazy to upload the files for the other cars, so you will have to find the game files online
