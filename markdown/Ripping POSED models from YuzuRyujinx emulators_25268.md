## Post #1
- Username: wardialer6000
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jun 09, 2016 2:05 am
- Post datetime: 2022-04-19T14:49:14+00:00
- Post Title: Ripping POSED models from Yuzu/Ryujinx emulators

the best i can get are t-posed models using intel GPA frame analyzer.


has anyone successfully hooked into either emulator using some kind of intercept tool?

i still have to try 3D via printscreen, but i've tried most of the others.  from what i can remember, renderdoc will only give me a point cloud with no face data, but maybe there's some kind of obscure linux program that would get me the posed models i want.

it would be hugely appreciated if anyone has any some info on which OS/tool/video card works best for ripping POSED models from emulators.

thanks
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2022-04-22T00:12:35+00:00
- Post Title: Ripping POSED models from Yuzu/Ryujinx emulators

The emulators only use OpenGL and Vulkan, currently there aren't really any rippers outside of what you've mentioned that work with those two tools.

Honestly the easiest solution would be for someone to edit the emulators themselves to dump frames, it wouldn't be easy but it would be easier than creating a whole new software that loops into the existing process unfortunately.

That said, a *lot* of switch games use the same file formats, so you might be better off looking through the dumps themselves, getting the bones and then posing them.
