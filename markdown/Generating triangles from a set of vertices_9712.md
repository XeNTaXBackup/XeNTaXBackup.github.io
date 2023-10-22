## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-10-05T19:18:52+00:00
- Post Title: Generating triangles from a set of vertices

What is the easiest way to generate a set of triangle indices with as little duplicate vertices as possible?
Lol I can't figure this out.

Doing some openGL programming and I'm only given a set of vertices. The direction of the face is not important atm.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-10-06T13:29:25+00:00
- Post Title: Generating triangles from a set of vertices

generating indices for an array of vertices? that depends how the array of vertices is stored.

if i remember, triangle strips are more efficient -  see [http://en.wikipedia.org/wiki/Triangle_strip](http://en.wikipedia.org/wiki/Triangle_strip)
