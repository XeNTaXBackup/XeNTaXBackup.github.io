## Post #1
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-01-16T16:26:33+00:00
- Post Title: koei old texture format *.xftx

This is the texture format used by old koei. So far, 
have confirmed that it was used in crimson sea and Dynasty Warriors 4 (Sangoku Musou 3).
Texture Cooker didn't give good results, but kurrimu2's vita swizzle did quite well.

As for crimson sea, renderdoc can capture from xemu, so I have a sample of the correct result.
I hope I can convert xftx to a texture that can be used correctly. I would appreciate it if anyone could cooperate.

[https://drive.google.com/file/d/1MCRByw ... sp=sharing](https://drive.google.com/file/d/1MCRByw5K8mCSuB7KD-4SoUJl0See2XXW/view?usp=sharing)

*EDIT
still investigating, but I'm guessing that it's probably the palette's color information near the end of the data. Probably because it does not match the normal RGB value, tools such as texture cooker do not give proper color arrangement, but I think it is almost certain.

By the way, this kind of texture has a common file size, so if know where and what texture is used, could replace the data and capture it from the game. It doesn't seem difficult to get an image even if no conversion method is established.
[muso3.png](https://xentaxbackup.github.io/file/21625_muso3.png)
