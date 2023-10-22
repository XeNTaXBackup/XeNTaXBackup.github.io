## Post #1
- Username: MrComputerRevo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 28, 2016 11:11 pm
- Post datetime: 2017-01-06T09:38:07+00:00
- Post Title: [Help needed] PS Vita CatSystem2 Image formats

Hello everyone! I am trying to figure out the image formats CatSystem2 (a Visual Novel engine) uses on PS Vita. As far as I could find out there are 3 different formats with headers of CZ0, CZ1 and CZ2. CZ0 is primarily used for system graphics it seems, CZ1 for fonts and CZ2 for CGs. From what I could see they all use the same header format as follows:
Byte 0,1,2 - Magic (CZ0, CZ1, CZ2)
Byte 4 - Size of header?
Byte 8,9 - Horizontal resolution
Byte A,B - Vertical resolution
Byte C - color format (8bit, 24bit, 32bit...)

I've tried messing with CZ0 and got it to display by putting it's data with a bmp header, but the colors are wrong and whole image is "wonky", but I'm pretty sure CZ0 is an uncompressed format of some sort. CZ1 seems to be uncompressed as well. CZ2 looks like it's compressed, but my second to none knowledge in graphics formats can't confirm that... Here is a zip with samples of all 3 formats.
[https://drive.google.com/file/d/0B3coby ... sp=sharing](https://drive.google.com/file/d/0B3cobyOfIYGeQW9jSGpIZkNsbE0/view?usp=sharing)
Any help is appreciated!
