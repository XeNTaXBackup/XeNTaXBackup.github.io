## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-02T17:57:49+00:00
- Post Title: 3D rendering in a browse

While looking around for sites that can render 3D models in a browser, I came across two things

Unity3D's browser plugin (which I've played some games in)
webGL

While it does sound cool, being able to render 3D in my browser...

Ya that's about it.

I wonder if I can use google's servers to process all that stuff and also put a viewer on their server as well  

Google seems to have some O3D thing.
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-01-02T18:09:50+00:00
- Post Title: 3D rendering in a browse

There are 3D renderers built entirely out of Javascript, though I'm not sure of their maturity or practicality at this point.
## Post #3
- Username: 0xFAIL
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-01-03T00:04:19+00:00
- Post Title: 3D rendering in a browse

Unfortunately, WebGL has had a messy start, and last I heard Microsoft was still refusing to implement it to spec because of the security issues it imposes. I'm personally of the opinion that not establishing a new translation layer standard for WebGL shader code was a bad oversight. I never played around with Google O3D much either, but last time I went looking for info on it, it had become (or was becoming) a complimentary framework for WebGL.

Silverlight 5 will be an option for common deployment soon, but as with most of Microsoft's web offerings, the platform exclusivity completely defeats the point. Then there's Flash 11 with the Stage 3D implementation which seems like it's probably got the best chance of becoming a useful standard. Or you can just do your own T&L, clipping, etc. and do your own 3D renderer with Flash's 2D rendering. I did that for a work project a few months back, specifically because there are still no good and widely-supported web-based 3D rendering standards.
## Post #4
- Username: practicing01
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 29, 2010 10:52 am
- Post datetime: 2012-01-22T17:46:02+00:00
- Post Title: 3D rendering in a browse

The contents of this post was deleted because of possible forum rules violation.
