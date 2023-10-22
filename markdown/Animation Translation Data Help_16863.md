## Post #1
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2017-08-12T23:17:59+00:00
- Post Title: Animation Translation Data Help

I'm in the process of writing an animation importer for DBZ Burst Limit and I'm having issues reading the translation information. When parsing some animations the format of the translation data is an array of vec3's containing floats but the animation data that produces broken models don't look like or read like floats. Considering this is one of the only games I've been able to read animation from, I'm left with little insight on what format this may be. Help would be appreciated, I'm sure it's something simple I'm overlooking. I attached a link to the max scene and the script to import the animation and an animation log  for better insight.

[https://pastebin.com/z2JnAQek](https://pastebin.com/z2JnAQek)
[https://www.dropbox.com/s/qvr5ufsrejb2a ... on.7z?dl=0](https://www.dropbox.com/s/qvr5ufsrejb2a8u/Burst%20Limit%20Animation.7z?dl=0)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-08-13T00:42:54+00:00
- Post Title: Animation Translation Data Help

> Reply from killercracker
>
> but the animation data that produces broken models don't look like or read like floats.did you consider compressed data? Such as 4 bytes = 32 bits splitted up into 11+11+10 bits for x, y, z?
(don't have max installed to try out your script)
## Post #3
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2017-08-13T15:18:02+00:00
- Post Title: Animation Translation Data Help

> did you consider compressed data? Such as 4 bytes = 32 bits splitted up into 11+11+10 bits for x, y, z?
>
> (don't have max installed to try out your script)

I don't think that would be the case. That would leave me with 8 bytes after the conversion that I'd have to work considering that it would still be in vec3 format and I couldn't find any flags or indications for any change of format. I think the issue is that the translation data is meant to referenced from a specific point instead of being used absolutely.
