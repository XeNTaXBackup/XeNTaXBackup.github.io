## Post #1
- Username: travistrue
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Mar 23, 2020 6:14 am
- Post datetime: 2023-06-15T22:26:32+00:00
- Post Title: TM2 File Questions

I've been writing a TM2 loader in Rust for my FF4 clone project, and it's been going pretty well. There's over 13k TM2 files in the PSP ISO of FF4. I'm still running into a few bugs and compatibility here and there. I'm not sure how portable my TM2 loader is for other games.

I've done some digging online here and there over the years, I've [read the file format spec from this Xentax](http://wiki.xentax.com/index.php/TM2_TIM2_Image), I've also read the [TM2 docs on OpenKH](https://openkh.dev/common/tm2.html), and I've looked at the [Rainbow editor code on GitHub](https://github.com/marco-calautti/Rainbow/tree/master) quite extensively. In fact, that code is what helped me write my loader.

I've still got some questions though:

- Is there any documentation on how the textures are swizzled? I couldn't find much on it, in fact, the only documentation that I could find was the swizzle implementation code in the Rainbow editor.

- When TM2 files' image data are pre-swizzled, are they swizzled to some common, generic swizzling algorithm that's standard for the TM2 file format spec, or is the image data swizzled according to the specific target hardware that the file was made for? For example, the PS2 and PSP both benefit from swizzled textures. If I had to guess, the way the PS2 wants its textures swizzled can (and probably is) different from the way the PSP wants its textures swizzled, right?

- Is there a way to tell if the TM2 file's image data is swizzled? There doesn't appear to be any explicit field. One thing that I noticed is that every swizzled TM2 file that I've noticed in FF4 for PSP has its frames' `format` header field set exactly to `4`. I'm not sure if the value for `format` is supposed to be some sort of code, or a bitfield though. I've also noticed that every TM2 file with a `format` field set to `134` fails to swizzle with an out-of-bounds array error. Now, `134` isn't `4`, but the 3rd bit is set to `1` in that value. So my guess is that `format` might not be a bitfield...

- Is there any documentation on what the frame header's `format` field is?

- Are all 8-bit images meant to be paletted, or can some 8-bit images represent grayscale or alpha-only textures as well? If the latter is true, then is there something in the texture header to describe if that texture is meant to be grayscale or alpha-only? Just curious cuz that seems like a useful config option to bake into a texture.

- Is there any documentation on how to tell whether or not a palette should be linearized or not?

- Are those GPU/hardware register fields towards the bottom of the frame header important for loading things into memory? It seems like those flags/settings were meant more for hardware-specific things.
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-06-16T04:24:10+00:00
- Post Title: TM2 File Questions

You can check out PS2 SDK. Search for "PlayStation 2 July 2005 SDK (version 3.0.3)". It's available on web archive.
There are some tools and docs there that should help you with answering your questions.
For example there is "swizzle.exe" executable that you may reverse engineer to make your code more accurate.

Also search for "tim2v4b_e.zip" as it contains full (official?) specification for this format.
