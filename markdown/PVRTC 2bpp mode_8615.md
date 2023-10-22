## Post #1
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-22T20:43:09+00:00
- Post Title: PVRTC 2bpp mode

I wrote a PVRTC decompressor around this paper: [http://web.onetel.net.uk/~simonnihal/as ... excomp.pdf](http://web.onetel.net.uk/~simonnihal/assorted3d/fenney03texcomp.pdf)

Everything generally works, but I'm not sure about this bit regarding 2bpp:

> The second mode uses 2-bit modulation values for every second texel, arranged in a chequerboard pattern. The remaining texel modulation values are then obtained, according to one of three sub-modes, by averaging the neighbouring two vertical, two horizontal, or all four modulation values.
I haven't been able to figure out how to determine that sub-mode. I guessed that for 2bpp maybe both colors are 15 bits, and I or'd the first bit of the 2nd color into the high bit with the first mode flag to get a 2-bit sub-mode flag. That actually seems to work on all the data I've tested, but it's often producing different results from the official PVRTC texture tool. My results at 4bpp and on 2bpp images that don't use the checkerboard mode look identical though.

Anyone happen to have experience with this? It's such a widespread format, but I can't find any actual specs or source code on it at all, and disassembling the texture tool just to find this tiny thing seems like a waste.

Edit: Ah, nevermind, I found [http://code.google.com/p/orange-grass/s ... n369&r=369](http://code.google.com/p/orange-grass/source/browse/trunk/engine/src/pvr/PVRTC.cpp?spec=svn369&r=369)

Edit 2: Maybe nevermind again. That code produces worse results than mine. And it seems to implement all 3 offset submodes yet only sets the submode with the first bit of the mode flag so it's impossible for it to ever do anything but average all 4 neighbors. Maybe that's the only mode actually implemented in the format or something.

Edit 3: I think I got it. You have to treat the first texel mod in checkerboard blocks as a 1 bit modulation and use the first bit in block as the high bit for your mode value to get the sub-mode. Seems to look right at least.
