## Post #1
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-09-10T05:15:04+00:00
- Post Title: [Question]3D Max and the Polygon reduction

I expend lot of time to search solution for this and i cant found, not for Max, Max have multires function this help to reduce the polygons in models but every time u try use this the weights are lost, i download something plugins and its the same, if somebody know a good plugin or metod to do that, reduce models faces or polygons and keep the weights i apreciate the info.
## Post #2
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2012-09-11T14:09:06+00:00
- Post Title: [Question]3D Max and the Polygon reduction

I don't see how it would be possible to keep the weights.  The weights are assigned to the vertices which in turn determine the polygons.  When you reduce the polygons you are also reducing the vertices.  In the majority of cases the vertices will not retain their original position thus making any weight applied to it invalid.
## Post #3
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-09-12T05:58:27+00:00
- Post Title: [Question]3D Max and the Polygon reduction

> Reply from Rimbros
>
> I expend lot of time to search solution for this and i cant found, not for Max, Max have multires function this help to reduce the polygons in models but every time u try use this the weights are lost, i download something plugins and its the same, if somebody know a good plugin or metod to do that, reduce models faces or polygons and keep the weights i apreciate the info.

Make a copy of the mesh you're gonna reduce (lod) and then assign a skin wrap modifier and in your paramater pres add and select your high poly model. After that jus click on convert to skin and that's all. You'll have to fix the rig and maybe play with the skin wrap values.

Check this:

[http://www.youtube.com/watch?v=1PvjLw7d_x4](http://www.youtube.com/watch?v=1PvjLw7d_x4)

See ya.
