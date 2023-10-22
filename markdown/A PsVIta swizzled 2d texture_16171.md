## Post #1
- Username: Eldinen
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 10, 2009 2:26 am
- Post datetime: 2017-04-19T15:14:12+00:00
- Post Title: A PsVIta swizzled 2d texture

I am playing around with the textures of a NIS PsVita game, and I could see all of them are swizzled.
I could unswizzled them using a modified code from [viewtopic.php?f=18&t=2640&hilit=UnSwizzle](http://forum.xentax.com/viewtopic.php?f=18&t=2640&hilit=UnSwizzle)

But there are some kind of files I dont get completely well.
One of them is this one:
[https://drive.google.com/file/d/0B2552r ... sp=sharing](https://drive.google.com/file/d/0B2552rsEmf9wY0JjVklnbF9rblk/view?usp=sharing)

And I get this wrong PNG. To see why is wrong, just do zooming in.
[https://drive.google.com/file/d/0B2552r ... sp=sharing](https://drive.google.com/file/d/0B2552rsEmf9wQmV5akVaTUhaTFE/view?usp=sharing)

Maybe my code is wrong or I need another unswizzling code. I have done a lot of tests but I dont get a right image of this texture.

The working code is this, maybe it could be useful for someone else:

```
import png

#Set to false for yx swizzle order
xy = False


def chunks(l, n):
    for i in range(0, len(l), n):
        yield l[i:i + n]


def unswizzle(writebuf, readbuf, writeoffset, segwidth, segheight, datawidth):
    global readoffset, buffer
    if segwidth == 2 and segheight == 2:
        if xy:
            writebuf[writeoffset:writeoffset + 2] = readbuf[readoffset:readoffset + 2]
            writebuf[writeoffset + datawidth:writeoffset + datawidth + 2] = readbuf[readoffset + 2:readoffset + 4]
        else:
            writebuf[writeoffset] = readbuf[readoffset]
            writebuf[writeoffset + datawidth] = readbuf[readoffset + 1]
            writebuf[writeoffset + 1] = readbuf[readoffset + 2]
            writebuf[writeoffset + datawidth + 1] = readbuf[readoffset + 3]
        readoffset += 4
    else:
        if xy:
            unswizzle(writebuf, readbuf, writeoffset, segwidth // 2, segheight // 2, datawidth)
            unswizzle(writebuf, readbuf, writeoffset + segwidth // 2, segwidth // 2, segheight // 2, datawidth)
            unswizzle(writebuf, readbuf, writeoffset + datawidth * (segheight // 2), segwidth // 2, segheight // 2,
                      datawidth)
            unswizzle(writebuf, readbuf, writeoffset + datawidth * (segheight // 2) + segwidth // 2, segwidth // 2,
                      segheight // 2, datawidth)
        else:
            unswizzle(writebuf, readbuf, writeoffset, segwidth // 2, segheight // 2, datawidth)
            unswizzle(writebuf, readbuf, writeoffset + datawidth * (segheight // 2), segwidth // 2, segheight // 2,
                      datawidth)
            unswizzle(writebuf, readbuf, writeoffset + segwidth // 2, segwidth // 2, segheight // 2, datawidth)
            unswizzle(writebuf, readbuf, writeoffset + datawidth * (segheight // 2) + segwidth // 2, segwidth // 2,
                      segheight // 2, datawidth)


def vita2bitmap(fileName1, width, height):
    global readoffset, bufferz
    if width == height:
        unswizzle(buffer, bitmap, 0, width, height, width)
    elif width > height:
        for w in range(0, width, height):
            unswizzle(buffer, bitmap, w, height, height, width)
    elif height > width:
        for h in range(0, height * width, width ** 2):
            unswizzle(buffer, bitmap, h, width, width, width)
    else:
        print('error')

    p = list(chunks(buffer, width))
    with open(fileName1, 'wb') as f:
        w = png.Writer(len(p[0]), len(p), greyscale=True)
        w.write(f, p)

fileName = "1ch6020.BTM"
#This file has not palette
paletteSize = 0
#In this case, all the file is bitmap
bitmapSize = os.path.getsize(fileName)
width = 1024
height = 1024

fileName1 = fileName.rsplit(".", 1)[0] + ".png"
with open(fileName, 'rb') as f:
    palette = f.read(paletteSize)
    bitmap = f.read(bitmapSize)
buffer = bytearray(len(bitmap))  #Output buffer
readoffset = 0  #Input position counter
vita2bitmap(fileName1, width, height)

```
## Post #2
- Username: Eldinen
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 10, 2009 2:26 am
- Post datetime: 2017-04-26T15:36:36+00:00
- Post Title: A PsVIta swizzled 2d texture

Fixed
## Post #3
- Username: Eldinen
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 10, 2009 2:26 am
- Post datetime: 2017-04-28T10:44:58+00:00
- Post Title: A PsVIta swizzled 2d texture

Another texture, funny, dont you think so?

This is the original file
[https://drive.google.com/file/d/0B2552r ... sp=sharing](https://drive.google.com/file/d/0B2552rsEmf9wZjBxZ1lvekNhTFk/view?usp=sharing)



Some idea?
## Post #4
- Username: Eldinen
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Nov 10, 2009 2:26 am
- Post datetime: 2017-05-07T13:59:03+00:00
- Post Title: A PsVIta swizzled 2d texture

Fixed! haha
