## Post #1
- Username: Sparkles1903
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 02, 2022 4:27 am
- Post datetime: 2022-07-01T21:11:29+00:00
- Post Title: Capcom Fighting Collection (MT Framework) Textures

Hello, I'm looking for some help on getting the artwork from the new Capcom Fighting Collection (MT Framework game) on PC. The artwork looks to be stored in .arc format and I have those extracted into TEX. Unfortunately, I've been unable to get a usable DDS with a wide variety of tools I've tried. Any help would be greatly appreciated! 

An example is here: [https://1drv.ms/u/s!AitZ_fzmHhq9jsgv09W ... g?e=8aeV0M](https://1drv.ms/u/s!AitZ_fzmHhq9jsgv09WTlNGbIJTIpg?e=8aeV0M)
## Post #2
- Username: Sparkles1903
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 02, 2022 4:27 am
- Post datetime: 2022-07-04T06:08:09+00:00
- Post Title: Capcom Fighting Collection (MT Framework) Textures

Small update, added some additional example textures, but still can't sort what the offset may be in Rawtex (if that's even the issue)? Some additional screenshots/examples are in the linked folder in the OP.
## Post #3
- Username: Sparkles1903
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 02, 2022 4:27 am
- Post datetime: 2022-07-05T18:53:45+00:00
- Post Title: Capcom Fighting Collection (MT Framework) Textures

Progress has been made...

Textures appear to be in bc7_unom format with an offset of 0x18, but with a green tint that I am unable to remove at the moment. I have a hunch that the RGBA channels are mixed up?

Any guidance would be appreciated!
## Post #4
- Username: Sparkles1903
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 02, 2022 4:27 am
- Post datetime: 2022-07-06T04:08:27+00:00
- Post Title: Capcom Fighting Collection (MT Framework) Textures

As I suspected, the RGBA channels were mixed up. I was able to adjust in PS with the following instructions located on another forum:

1 - Copy Alpha channel to a new layer (Layer 1)
2 - Select Background in Layers
3 - Copy Green channel to Alpha
4 - Copy Layer 1 from Layers, select Background in Layers, and paste to Green in Channels
5 - Set Layer 1 style blending to Overlay and in "Advanced Blending" uncheck Green (that's "G" in the middle) channel

It still needs a bit of color grading, to properly look like the source image in-game, but essentially resolved at this point... 
(raw image below before any color work)
## Post #5
- Username: zibra
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 25, 2020 3:46 pm
- Post datetime: 2022-07-06T12:43:38+00:00
- Post Title: Capcom Fighting Collection (MT Framework) Textures

Great, I was searching for a method from D1.
Do you plan to upload the archive somewhere?
## Post #6
- Username: Sparkles1903
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 02, 2022 4:27 am
- Post datetime: 2022-07-06T19:05:33+00:00
- Post Title: Capcom Fighting Collection (MT Framework) Textures

> Reply from zibra ↑Wed Jul 06, 2022 8:43 pm at Wed Jul 06, 2022 8:43 pm
>
> 
Do you plan to upload the archive somewhere?

No plans to upload the archive. I only needed a few items, such as marquees and move strips, for higher rez artwork for my arcade cabinet.
## Post #7
- Username: zibra
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 25, 2020 3:46 pm
- Post datetime: 2022-07-07T05:54:47+00:00
- Post Title: Capcom Fighting Collection (MT Framework) Textures

unfortunately. 
Got it, thanks
## Post #8
- Username: DeepWeeb
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 12, 2019 7:13 am
- Post datetime: 2022-11-22T18:08:10+00:00
- Post Title: Capcom Fighting Collection (MT Framework) Textures

I've been having this problem for years with games like Mega Man 11 and Mega Man X Legacy Collection

I followed the steps the best as I could and this is what I got: kinda washed up   (I had to remove the transparency layer to regain some extra color)








Could you perhaps make a video guide on the steps?
