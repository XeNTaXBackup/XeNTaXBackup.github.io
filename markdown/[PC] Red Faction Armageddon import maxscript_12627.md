## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-02-20T12:56:21+00:00
- Post Title: [PC] Red Faction: Armageddon import maxscript

Hi guys! Here's maxscript to import [PC] Red Faction: Armageddon character models (3ds max 2009-2014). No bones and weight just geometry+uv's, so take it as it is  

P.S. I'm having some issues with skeleton/faces direction here. Good friend of mine asked me to take a look at format, so I did. Game is pretty old, but if there will be an interest about it, I'll try to finish my script. Also, textures could be obtained with any ripper or directly from .gpeg_pc files, they are containers with straight headerless .dds images.


[Red_Faction.7z](https://xentaxbackup.github.io/file/8712_Red_Faction.7z)
## Post #2
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-02-21T11:27:37+00:00
- Post Title: [PC] Red Faction: Armageddon import maxscript

> Reply from zaramot
>
> Hi guys! Here's maxscript to import [PC] Red Faction: Armageddon character models (3ds max 2009-2014). No bones and weight just geometry+uv's, so take it as it is  

P.S. I'm having some issues with skeleton/faces direction here. Good friend of mine asked me to take a look at format, so I did. Game is pretty old, but if there will be an interest about it, I'll try to finish my script. Also, textures could be obtained with any ripper or directly from .gpeg_pc files, they are containers with straight headerless .dds images.nice to having this, thanks. Is it something wrong with the uv? I see the seem on her face/neck/pubis.
## Post #3
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-02-21T12:02:40+00:00
- Post Title: [PC] Red Faction: Armageddon import maxscript

Yeah, maybe this is due to texture extraction. I extracted them manually, so maybe there's a shirt of pixels in image. If someone could confirm this issue still exist with textures ripped with Ninha Ripper or any 3d ripper. I'll scale uv's to prevent this
## Post #4
- Username: Nexus Elite
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 16, 2011 1:36 am
- Post datetime: 2015-02-22T07:03:19+00:00
- Post Title: [PC] Red Faction: Armageddon import maxscript

> Reply from zaramot
>
> Yeah, maybe this is due to texture extraction. I extracted them manually, so maybe there's a shirt of pixels in image. If someone could confirm this issue still exist with textures ripped with Ninha Ripper or any 3d ripper. I'll scale uv's to prevent this
Will this work on Red Faction Guerrilla?
## Post #5
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2015-02-28T10:13:00+00:00
- Post Title: [PC] Red Faction: Armageddon import maxscript

> Reply from zaramot
>
> Hi guys! Here's maxscript to import [PC] Red Faction: Armageddon character models (3ds max 2009-2014).

The 3ds max 2012 64 bit version does not like this script:

"Vertex Start @ 0x15290L"
-- Error occurred in x loop; filename: C:\Program Files\Autodesk\3ds Max 2012\Scripts\Red_Faction.ms; position: 2361; line: 95
--  Frame:
--   vy: -5.00949e+027
--   tv: undefined
--   unk00: undefined
--   tu: undefined
--   vz: 0.0
--   x: 15204
--   unk01: undefined
--   vx: 0.0
-- Error occurred during fileIn in #C:\Program Files\Autodesk\3ds Max 2012\Scripts\Red_Faction.ms; line number: 95
>> MAXScript FileIn Exception:
-- No ""/"" function for undefined <<
