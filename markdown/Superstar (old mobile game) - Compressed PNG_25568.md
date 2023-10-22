## Post #1
- Username: barquetin16
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Mar 21, 2017 12:16 am
- Post datetime: 2022-07-01T15:54:33+00:00
- Post Title: Superstar (old mobile game) - Compressed PNG

Compressed PNG file it looks like it upside down with compress data, it is from an old mobile game no longer in service.
I have been trying to figure it out but nothing, i really hope you guys can help me.

Files:[https://drive.google.com/file/d/1i9Yk98 ... sp=sharing](https://drive.google.com/file/d/1i9Yk98W0cqMaME_H5ZiqYsVXcSV-7nvI/view?usp=sharing)
## Post #2
- Username: barquetin16
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-07-01T17:27:37+00:00
- Post Title: Superstar (old mobile game) - Compressed PNG

What game is it from?

This is just regular PNG file, but saved backwards xD
See the format here [http://wiki.xentax.com/index.php/PNG_Image](http://wiki.xentax.com/index.php/PNG_Image)


You can convert it to PNG by just reading data, reversing it and saving to output file with PNG extension.
(or just reading/saving data backwards...)

Here is an example Python script to do this:

```


def main():
    print("Starting main...")
    bytes_file = open("C:\\Users\\username\\Desktop\\background\\3.i.bytes", "rb")
    out_file = open("C:\\Users\\username\\Desktop\\background\\3.i.png", "wb")

    file_data = []
    original_data = bytes_file.read()

    for raw_byte in original_data:
        file_data.append(raw_byte)

    file_data.reverse()

    for list_byte in file_data:
        raw_byte = struct.pack("B", list_byte)
        out_file.write(raw_byte)

    bytes_file.close()
    out_file.close()
    print("PNG file saved successfully!")


if __name__ == '__main__':
    main()
```
## Post #3
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-07-01T20:20:24+00:00
- Post Title: Superstar (old mobile game) - Compressed PNG

I made a simple script tool in python.

I converted it to executable for easier handling.

just click on the program and choose the file you want to reverse png.

25mb i know, sorry, its the conversor.
But the tool works!

[https://mega.nz/file/yAZSQZQZ#oHuo3ehyM ... PE62BBMv8E](https://mega.nz/file/yAZSQZQZ#oHuo3ehyMa7Ua-X6PmE02Q1wq6jASDV7wPE62BBMv8E)
## Post #4
- Username: barquetin16
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Mar 21, 2017 12:16 am
- Post datetime: 2022-07-02T03:55:32+00:00
- Post Title: Superstar (old mobile game) - Compressed PNG

Thanks for the replies both ways works thanks, the game name i belive it was superstar it was a music kinda game
