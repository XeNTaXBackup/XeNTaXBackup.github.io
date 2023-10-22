## Post #1
- Username: digitalutopia1
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 09, 2017 10:43 am
- Post datetime: 2018-11-04T07:53:24+00:00
- Post Title: Witcher 3 Bone Data

First off, apologies if I have the wrong forum - it's coding related, but it's also model related.

So, long story short - I wanted Witcher 3 models, but I wanted them with skeleton - something that the normal tool of choice (The Witcher 3D Model Converter by JLouis-B) couldn't do. So, since he made the source available, I thought I'd take a crack at it. As I've had a bit of experience with file parsing, including 3D formats. 

Unfortunately my attempt so far, has had mixed results. The good news is, that I've got the format down. Bad news is, that I think I found out why there's no skinning support, and I'm spinning my wheels at the same point. So I figured maybe, hopefully someone might have some ideas. 

The problem is the bone data - it works out to 48 bytes per bone, which the author believes is Position, Rotation, and Scale data, or 16 bytes per set in four 32 bit floats. And that seems pretty reasonable, except...all of these floats are basically between -1 and 1...with only a few exceptions, and those are just a hair over 1. This data also includes some really tiny floats - like 2.0e-12. So there's no way this data can be used as-is, without some additional processing. This isn't without precedence either, vertex data, which is stored in half-floats, needs to be divided by 65535 (ushort max) and then have a scale and offset added to it. 

Unfortunately, while the CMesh object has a property for "cookedData" which includes sub-properties with this scale and offset data, CSkeleton only has two properties - one for bone names, and one for parent indices. At any rate, below is a link to the bone data I speak of - which covers 89 bones. To get even groupings of 48 bytes per bone, you'll have to skip the first two bytes. For the sake of completeness, I just took everything from the end of the properties, to the end of the object.

[http://digital-utopia.org/downloads/boneData.bin](http://digital-utopia.org/downloads/boneData.bin)
