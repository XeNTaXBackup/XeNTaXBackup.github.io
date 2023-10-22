## Post #1
- Username: jgoldshlag
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Feb 01, 2008 12:23 am
- Post datetime: 2008-02-01T20:35:55+00:00
- Post Title: Pirates of the Burning Sea .IGB files - Alchemy engine

I was wondering if you guys would be willing to look at the .igb files in Pirates of the Burning Sea. They appear, from my research, to be the binary serialization format for the Alchemy engine by Insight/Vicarious Visions/Activision.

It looks like some people may have looked into this format in the past, see [viewtopic.php?t=1448](http://forum.xentax.com/viewtopic.php?t=1448). I think the X-Men/Marvel Ultimate alliance files are from a slightly older version of the engine.

The full file size of the file is 6016700 bytes (about 6 megs), and I can email it if needed.

Thanks!
[potbs.igb.zip](https://xentaxbackup.github.io/file/1437_potbs.igb.zip)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-02-24T21:08:27+00:00
- Post Title: Pirates of the Burning Sea .IGB files - Alchemy engine

Well, from what I can see, i'd need bigger parts of the file. There's a long list of filenames in the header (front) part of the file, but that goes on BEYOND the snippet you cut out. There could be much more info there that is needed to support this one.
## Post #3
- Username: jgoldshlag
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Feb 01, 2008 12:23 am
- Post datetime: 2008-02-25T12:48:59+00:00
- Post Title: Pirates of the Burning Sea .IGB files - Alchemy engine

OK, I uploaded the full file at [http://www.goldshlag.com/potbs.zip](http://www.goldshlag.com/potbs.zip). Let me know if you need anything else.
## Post #4
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2008-03-10T15:21:23+00:00
- Post Title: Pirates of the Burning Sea .IGB files - Alchemy engine

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2008-03-12T14:45:45+00:00
- Post Title: Pirates of the Burning Sea .IGB files - Alchemy engine

I should also mention that IGB files aren't archives.  They're animations, models with the textures inside, or texture-only files -- so this should probably be moved out of the Game Archive section.
## Post #6
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2008-03-15T04:45:16+00:00
- Post Title: Pirates of the Burning Sea .IGB files - Alchemy engine

I'm pretty sure the pirates .igb files also had sound and data files in them
## Post #7
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2008-03-17T11:25:09+00:00
- Post Title: Pirates of the Burning Sea .IGB files - Alchemy engine

hmm...  Certainly possible.  I mean considering when Intrinsic owned the engine it stored animations/models/textures it would still technically be an archive.  Maybe Vicarious Visions started pushing it to store other formats too.
## Post #8
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2012-04-30T01:15:01+00:00
- Post Title: Pirates of the Burning Sea .IGB files - Alchemy engine

Another bump, I apologize. But I can now confirm that IGB files store only models, textures and animations or any combination of the three. They are generated from the 3D Studio Max/Maya exporter (there's only one version publicly available, and it's hard to find, but AFAIK it supports both 3DSMax and Maya exports with the proper plugin). The tools are commercial, however before Vicarious Visions purchased the Alchemy engine Intrinsic Software released their export tools for version 2.5 of the engine. It has been used to create new Marvel: Ultimate Alliance models.
## Post #9
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-30T16:06:17+00:00
- Post Title: Pirates of the Burning Sea .IGB files - Alchemy engine

holy thread resurrection batman lol! ha ha ha the IGB format is a complex scene graph format similar to PSSG but harder; nobody in their right mind would want to touch it unless they have a few months to spare mapping out 100+ different scene graph nodes.
