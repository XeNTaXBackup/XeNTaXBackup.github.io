## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-22T01:33:39+00:00
- Post Title: Unswizzling images

Any techniques to unswizzling images?
Approaches?

Any libraries that would make it easier? Preferably in python cause I can quickly throw stuff at it and look at the results.

I imagine it boils down to pixel manipulation (for..bitmap images anyways), like just shifting these pixels here, maybe rotating these pixels here and there...adjusting the rgb's...

Looks like a huge puzzle game to me, but I don't have the proper tools to try to solve it effectively.
Like randomly turning a 10x10 rubik's cube hoping to solve it.
## Post #2
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-22T05:34:38+00:00
- Post Title: Unswizzling images

One of the most common forms of "swizzling" (twiddling!) you'll find comes from storing pixels or blocks in Morton coordinates. Converting x/y coordinates to Morton is easy: [http://permalink.gmane.org/gmane.games. ... thms/15463](http://permalink.gmane.org/gmane.games.devel.algorithms/15463)

Beyond that, it varies between systems/architectures and there isn't another particularly universal standard for the ways in which people like to fuck around with their data to make it easier/faster for them to access under any given condition.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-22T07:41:38+00:00
- Post Title: Unswizzling images

[Twiddling?](http://en.wikipedia.org/wiki/Thumb_twiddling)

Anyways it looks like python provides a picture module for manipulating pixels. I guess I could play around with that and see where I get.
## Post #4
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-03-22T08:34:44+00:00
- Post Title: Unswizzling images

[http://forums.ps2dev.org/viewtopic.php? ... 504bd0dd93](http://forums.ps2dev.org/viewtopic.php?p=88157&sid=81c808dcd2a9c618908859504bd0dd93)

here's an example for the standard psp
## Post #5
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-22T10:09:54+00:00
- Post Title: Unswizzling images

Noesis already has rapi.imageUntwiddlePSP, rapi.imageUntwiddlePS2, rapi.imageUntile360Raw, and rapi.imageUntile360DXT. So you don't have to worry about those systems. If you ever come across a new platform standard that it doesn't support, just let me know, I'm always happy to add system-wide stuff like that because that's what helps the most in making life easier.
