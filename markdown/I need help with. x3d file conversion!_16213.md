## Post #1
- Username: heavenss89
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 28, 2017 4:33 pm
- Post datetime: 2017-04-28T13:36:48+00:00
- Post Title: I need help with. x3d file conversion!

Hello guys! 

I desperately need your help. There is a game,  from what I extracted the 3d model files which it happen, that they are. X3d files.  Now I have tried to open with several viewers, and with 3d editor programs, and they cannot open it. All of them gives error, some of them says it a parser error. I found a viwer (Noesis), i added a plugin for x3d, and it opens them. From there i can convert it to another extension, for ex. FBX and with that file i can work in a 3d modeler program. Now when im done,  I convert back to x3d and repack the file, and runs the game, but when loads that model ingame it gives an error, that it dosn't recognizes the file type. My question it would be that, how can I convert back to the same file extension. Because there it is obviously a difference between the old x3d and the new x3d. And im not talking avout the new extensions of x3d like. X3dv.  Please help me guys!!     

Thanks in advance!!!
Ps. The game is 9Dragons.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-04-28T22:41:54+00:00
- Post Title: I need help with. x3d file conversion!

> Reply from heavenss89
>
> Now when im done,  I convert back to x3dHow?

Without giving more details (including the sample file you're working with) noone would know what the problem might be.
## Post #3
- Username: heavenss89
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 28, 2017 4:33 pm
- Post datetime: 2017-05-01T08:43:38+00:00
- Post Title: I need help with. x3d file conversion!

So here are some samples, from the original files:

[https://www.dropbox.com/s/h7f7vuvmj2dn4 ... 0.x3d?dl=0](https://www.dropbox.com/s/h7f7vuvmj2dn428/z_mask_m_40.x3d?dl=0)
[https://www.dropbox.com/s/ojtro6ielr4lf ... 0.x3d?dl=0](https://www.dropbox.com/s/ojtro6ielr4lf9q/z_mask_w_20.x3d?dl=0)

And Here is the script for Noesis, which with you can open it.

[https://www.dropbox.com/s/i6cs87vi9cld8 ... ns.py?dl=0](https://www.dropbox.com/s/i6cs87vi9cld85k/9dragons.py?dl=0)

I open it with Noesis, I export it to .obj then I open it with Blender, export from Blender to x3d, then I try to open in game , and it is not working.
Here is the converted files from obj to x3d:

[https://www.dropbox.com/s/ssafd1vuy5i2u ... t.x3d?dl=0](https://www.dropbox.com/s/ssafd1vuy5i2u9w/z_mask_m_20out.x3d?dl=0)
[https://www.dropbox.com/s/3kcywx1ijjc4q ... t.x3d?dl=0](https://www.dropbox.com/s/3kcywx1ijjc4qlc/z_mask_m_40out.x3d?dl=0)

So, my question is that the file coding changes? Even if I convert back to the original extension ?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-05-01T10:53:35+00:00
- Post Title: I need help with. x3d file conversion!

> Reply from heavenss89
>
> So, my question is that the file coding changes? Even if I convert back to the original extension ?obviously. Your original .x3d is of binary format whilst the .x3d export from blender is xml:

```
<!DOCTYPE X3D PUBLIC "ISO//Web3D//DTD X3D 3.0//EN" "http://www.web3d.org/specifications/x3d-3.0.dtd">
<X3D version="3.0" profile="Immersive" xmlns:xsd="http://www.w3.org/2001/XMLSchema-instance" xsd:noNamespaceSchemaLocation="http://www.web3d.org/specifications/x3d-3.0.xsd">
	<head>
[...]
```
## Post #5
- Username: heavenss89
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 28, 2017 4:33 pm
- Post datetime: 2017-05-01T17:26:44+00:00
- Post Title: I need help with. x3d file conversion!

Thanks for looking into it ! Now I need to find a converter what  it converts to x3d in binary?
