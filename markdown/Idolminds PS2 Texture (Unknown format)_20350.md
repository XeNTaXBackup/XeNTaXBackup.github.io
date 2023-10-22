## Post #1
- Username: tormunds
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Dec 11, 2015 1:52 am
- Post datetime: 2019-05-09T06:59:31+00:00
- Post Title: Idolminds PS2 Texture (Unknown format)

Hi, how's it going? I've been trying to convert some PS2 textures from a game called Neopets: The Darkest Faerie, but I've had no luck and could really use some help. I think these are some kind of .tga files, but I'm not experienced with PS2 formats so I'm just doing trial and error (with mostly error!)

The idm extension is made up. Those were the magic bytes of every file so that's why I used it as an extension, but in reality I have no idea what these files should be.

Sample files:
[https://drive.google.com/file/d/1VmAZPb ... sp=sharing](https://drive.google.com/file/d/1VmAZPbDjlWM1k9i_W64gvevM_9AxDMSh/view?usp=sharing)

Thank you!
## Post #2
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-05-14T14:47:10+00:00
- Post Title: Idolminds PS2 Texture (Unknown format)

oof. looks a bit messy. seems hard to get the structure data pointers. 2 surface descriptions. those are the 50,51,52,53 bits. it's actually only 1 tho. 5 kinda 'fragment' descriptions. but... nasty to figure out the positions and sizes. the leftmost textures are 2 fragments to puzzle together. tricky

for a raw attempt... this is the raw binary surface after the header. 2 textures with swizzled indices and 2 raw palettes



you could try noesis. it has a ps2 unswizzle operation. you definetely need to separate the textures and palettes for the imageDecodeRawPal.
