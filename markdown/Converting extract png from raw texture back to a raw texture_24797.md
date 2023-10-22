## Post #1
- Username: Cantthinkofausername
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 30, 2021 1:59 am
- Post datetime: 2021-11-29T18:03:42+00:00
- Post Title: Converting extract png from raw texture back to a raw texture

I'm modding the 3ds version of puyo puyo tetris and some of the graphics are raw textures. I managed to convert them to png with kuriimo2 but i can't can't find a way to convert them back.
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-11-29T19:37:07+00:00
- Post Title: Converting extract png from raw texture back to a raw texture

Well, PNG is chunk based file format [http://wiki.xentax.com/index.php/PNG_Image](http://wiki.xentax.com/index.php/PNG_Image)
All the image data should be in IDAT chunk and it should be compressed with zlib,
so you could use offzip to extract zlib data from PNG.

Another way could be creating a Noesis plugin which will export RAW data.
(maybe something similar is already built-in in Noesis, I'm not sure)

One more way would be to just ask Kuriimu2 developers for export feature in the "Issues" section
[https://github.com/FanTranslatorsIntern ... mu2/issues](https://github.com/FanTranslatorsInternational/Kuriimu2/issues)
## Post #3
- Username: Cantthinkofausername
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 30, 2021 1:59 am
- Post datetime: 2021-12-04T22:58:30+00:00
- Post Title: Converting extract png from raw texture back to a raw texture

When i used offzip, i get a png without any data. Also, how can i add "3ds swizzle"? The original image has it.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-04T23:28:05+00:00
- Post Title: Converting extract png from raw texture back to a raw texture

> When i used offzip, i get a png without any data.
I don't really know what's the problem here. 
I have just tested this method on some example picture [https://i.imgur.com/YTuk7aa.png](https://i.imgur.com/YTuk7aa.png)

And offzip has extracted data for me without any issues. [https://i.imgur.com/3WmLeIS.png](https://i.imgur.com/3WmLeIS.png)

Then I could view RAW data in TextureFinder [https://i.imgur.com/qeWpWk5.png](https://i.imgur.com/qeWpWk5.png)

So I'm 100% sure that offzip method works fine.
But if you don't know how to do data conversion yourself, you should try to use tool that already exist or ask Kuriimu developers for support.

> Also, how can i add "3ds swizzle"? The original image has it.
That's something that could be added by custom piece of code.
Try to search the internet for some example swizzler or try to do it in Noesis.
## Post #5
- Username: Cantthinkofausername
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 30, 2021 1:59 am
- Post datetime: 2021-12-05T18:55:17+00:00
- Post Title: Converting extract png from raw texture back to a raw texture

I believe i'm doing something wrong, but i now get a .vap file. Could i have the command you used?
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-05T21:53:14+00:00
- Post Title: Converting extract png from raw texture back to a raw texture

> Reply from Cantthinkofausername ↑Mon Dec 06, 2021 2:55 am at Mon Dec 06, 2021 2:55 am
>
> 
I believe i'm doing something wrong, but i now get a .vap file. Could i have the command you used?

Sure, it's this one:

```
offzip.exe -a test.png
```
## Post #7
- Username: Cantthinkofausername
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 30, 2021 1:59 am
- Post datetime: 2021-12-06T17:26:25+00:00
- Post Title: Converting extract png from raw texture back to a raw texture

Tried using that command and i still got a .vap file. Opening it with texture finder, i can only see things that look like the edited png. 
[https://imgur.com/a/o3UUkb0](https://imgur.com/a/o3UUkb0)
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-06T18:28:37+00:00
- Post Title: Converting extract png from raw texture back to a raw texture

Yeah, this VAP file is your uncompressed raw data from png. You just need to adjust some parameters like width, skew, bpp etc. in TextureFinder.

You can now make some manual conversion if you want. But I would strongly recommend using Noesis for such things. It's easier with the API.
