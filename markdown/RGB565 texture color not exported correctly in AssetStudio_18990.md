## Post #1
- Username: lurenx
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Mar 13, 2017 9:37 am
- Post datetime: 2018-10-28T05:57:35+00:00
- Post Title: RGB565 texture color not exported correctly in AssetStudio

I was trying to look at models from DragonBall Z Strongest War. (you can find apk online, very nicely made game and in beta)
The resources *.u can be viewed in AssetStudio. Models and animation can all be exported into blender, etc.
But the texture is shown as RGB565 format. I looked up online and I believe the color code is not the same as standard RGB
[http://www.barth-dev.de/online/rgb565-color-picker/](http://www.barth-dev.de/online/rgb565-color-picker/)
So all the textures exported as if they are standard RGB. They have a blue hue and are not correct. 
I also found this website where you can test different color modes and you can see how the color will be messed up (change the "predefined format)
[http://rawpixels.net/](http://rawpixels.net/)

I wonder if there is a good way to convert the color back to the correct values? Thanks!

It looks like they made it this way because the cartoon rendering has limited color so this saves resources. Also they used a color ramp for color and there is no normal map.
[texture.png](https://xentaxbackup.github.io/file/15098_texture.png)
## Post #2
- Username: devmode
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Jun 07, 2016 2:51 am
- Post datetime: 2018-10-28T12:04:21+00:00
- Post Title: RGB565 texture color not exported correctly in AssetStudio

Maybe manual making/replacing a DDS header will help?

Example:

Make or open any image with 512x512 sizes, and export with photoshop & Nvidia dds filter to 5.6.5 RGB 16 bpp | unsigned.

Open exported image with any HEX editor and copy first 128 bytes. Next open your DDS with a wrong RGB and replace same 128 bytes header by paste. Save image and see how it's look after.

Is better, if AssetStudio can export DXT textures in a RAW. Then just insert copyed header to start of file.
## Post #3
- Username: lurenx
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Mar 13, 2017 9:37 am
- Post datetime: 2018-10-29T01:49:12+00:00
- Post Title: RGB565 texture color not exported correctly in AssetStudio

> Reply from devmode
>
> Maybe manual making/replacing a DDS header will help?

Example:

Make or open any image with 512x512 sizes, and export with photoshop & Nvidia dds filter to 5.6.5 RGB 16 bpp | unsigned.

Open exported image with any HEX editor and copy first 128 bytes. Next open your DDS with a wrong RGB and replace same 128 bytes header by paste. Save image and see how it's look after.

Is better, if AssetStudio can export DXT textures in a RAW. Then just insert copyed header to start of file.
thanks for the reply, I tried something like that but it did not work. It will make the file corrupted.
I tried to manually covert the color but it looks more complicated than expected. I guess the developer used custom formula to convert the color code from file to the actual value. I was playing with the hex and binary codes but have not made sense out of it. the bottom line is that it is not as straightforward as I thought.
