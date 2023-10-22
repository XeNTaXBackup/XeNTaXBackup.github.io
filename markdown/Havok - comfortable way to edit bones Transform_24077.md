## Post #1
- Username: sanyabane
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Oct 31, 2014 3:37 am
- Post datetime: 2021-06-18T10:06:18+00:00
- Post Title: Havok - comfortable way to edit bones "Transform"

Hello.
Does anyone knows if is it possible to edit bones of Havok skeleton in some GUI?

Currently I can do this manually thorugh Notepad++ by exporting skeleton from "Havok: Preview Tool" as xml, so workflow looks like this:
1. Export skeleton as XML.
2. Find bone index - which is equal to <hkobject> position inside <hkparam name="bones">.
3. Find line by this index inside <hkparam name="referencePose">.
4. Edit Trasnform in this line as i want (position, rotation, scale).
5. Save file.

It's... quite uncomfortable. 

Is it possible to do this in some easier way? Maybe inside Havok itself, or by some 3rd party tool?
