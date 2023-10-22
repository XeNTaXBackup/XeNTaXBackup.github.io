## Post #1
- Username: eisnerguy1
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jun 18, 2016 1:24 am
- Post datetime: 2021-02-20T04:43:54+00:00
- Post Title: Blizzard Arcade Collection .sprite archives

So, I'm trying to extract files from a .sprite archive.  In the [Blizzard Arcade Collection](https://us.shop.battle.net/en-us/product/blizzard-arcade-collection), there are 7 of these types of files.  I'm guessing these include the borders and other graphics from the 3 games (as I've looked through everything else and couldn't find those graphics): The Lost Vikings, Rock N Roll Racing & Blackthorne.  When viewed in a hex editor, the files start with this:

```
RIFFvc. SPRTsprs
```


If someone could take a look at this archive, that would be fantastic
[http://www.mediafire.com/file/o3fr3n602 ... prite/file](http://www.mediafire.com/file/o3fr3n602isg59a/rnrr.sprite/file)
## Post #2
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2021-02-21T18:28:54+00:00
- Post Title: Blizzard Arcade Collection .sprite archives

Looks like it is RIFF container ([https://en.wikipedia.org/wiki/Resource_ ... ile_Format](https://en.wikipedia.org/wiki/Resource_Interchange_File_Format))
Inside 1 "sprs" section (252 bytes) and 1 list section named "IMGS" with 4 subfiles inside. This 4 subfiles has signature "IMG fmt L".

You can extract this data by this offsets:
"sprs": 0x14, 252 bytes
img1: 0x124, 377746 bytes
img2: 0x5c4be, 393998 bytes
img3: 0xbc7d4, 1914054 bytes
img4: 0x28fca2, 2054912 bytes.

Hope that helps.
## Post #3
- Username: eisnerguy1
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jun 18, 2016 1:24 am
- Post datetime: 2021-02-24T03:56:33+00:00
- Post Title: Blizzard Arcade Collection .sprite archives

That kinda makes sense.  What program could I open and view img1 for example?  Thanks!
## Post #4
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2021-02-24T19:30:41+00:00
- Post Title: Blizzard Arcade Collection .sprite archives

This is custom format. I think that there must be a lot of variations inside.
In your example file 4 images that looks like a cover of the "Rock N' Roll Racing" cartridge/disc.
If you are familiar with Kaitai Struct and python, you can extract it using this format description:

```
  id: img_raw
  file-extension: img_raw
  encoding: ascii
  endian: le
seq:
  - id: magic
    contents: "IMG fmt L\0\0\0"
  - id: data_name
    type: str
    terminator: 0
  - id: unk_fill
    size: 54
    # repeats 0xfe
  - id: unk_data
    type: u4
  - id: compression
    contents: "lz4 "
  - id: width
    type: u2
  - id: height
    type: u2
  - id: data_magic
    contents: "data"
  - id: data_len
    type: u4
  - id: compressed
    size: data_len
```


```
import lz4.block as lb
from PIL import Image
import sys

if __name__ == "__main__":
    name = sys.argv[1]
    img = ImgRaw.from_file(name)

    res = lb.decompress(img.compressed, uncompressed_size=img.width * img.height * 4)

    res_img = Image.frombytes("RGBA", (img.width, img.height), res)
    res_img.save(name + ".png")
```
