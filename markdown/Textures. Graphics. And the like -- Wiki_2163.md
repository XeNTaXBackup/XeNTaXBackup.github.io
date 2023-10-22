## Post #1
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-20T11:41:32+00:00
- Post Title: Textures. Graphics. And the like --> Wiki

Hi all, 

It would be swell if you could not only figure out new texture formats etc here at the forums, but also post the specs of these at the Game File Format Central [http://wiki.xentax.com](http://wiki.xentax.com) ! 

This way there will be a repository of known texture formats, that may save future time of investigation, when it can be seen from those specs that new formats are the same. 

I've made a brief headstart of the new section at the wiki that should include all resource formats, except game archives. Common formats can be referred to if encountered instead of reproduced. 
[http://wiki.xentax.com/index.php?title= ... le_Formats](http://wiki.xentax.com/index.php?title=Game_File_Formats)

What say you?
## Post #2
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2006-10-20T20:00:26+00:00
- Post Title: Textures. Graphics. And the like --> Wiki

Wouln't it be better to have converters/viewers as plug ins for mexcom?
that way we wouldn't need to code interfaces for every little program
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-20T21:48:08+00:00
- Post Title: Textures. Graphics. And the like --> Wiki

> Reply from alera
>
> Wouln't it be better to have converters/viewers as plug ins for mexcom?
that way we wouldn't need to code interfaces for every little program

Not better, but something else. To have the information at the wiki for everyone else to learn from is one of our primary aims. To share knowledge. 

Converter/viewers as plugins for MexCom is definitely a good idea, and should be implemented in future versions.
## Post #4
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2006-10-21T05:42:35+00:00
- Post Title: Textures. Graphics. And the like --> Wiki

oh :) I was refering to the little pict2bmp program :) not the actual info on the wiki
## Post #5
- Username: OneOneSeven
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Jul 16, 2006 1:54 pm
- Post datetime: 2007-01-11T22:06:29+00:00
- Post Title: Textures. Graphics. And the like --> Wiki

... Perhaps a project can be started that functions along the lines of MexCom/Game Extractor, except for the opening/conversion of image formats? For example a general-purpose image viewer that could open up the VTF format and save me the time of booting up Photoshop/using one of the loads of inconvenient small tools for TGA conversion? Irfanview would be a great base for this, as it loads extraordinarily quickly and already has a pretty big format support list.
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-01-11T22:17:15+00:00
- Post Title: Textures. Graphics. And the like --> Wiki

> Reply from OneOneSeven
>
> ... Perhaps a project can be started that functions along the lines of MexCom/Game Extractor, except for the opening/conversion of image formats? For example a general-purpose image viewer that could open up the VTF format and save me the time of booting up Photoshop/using one of the loads of inconvenient small tools for TGA conversion? Irfanview would be a great base for this, as it loads extraordinarily quickly and already has a pretty big format support list.

Well, there are already a lot of such programs available on the net.
## Post #7
- Username: OneOneSeven
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Jul 16, 2006 1:54 pm
- Post datetime: 2007-01-11T23:13:23+00:00
- Post Title: Textures. Graphics. And the like --> Wiki

Yes, this is true, however being able to combine the really wide range of file formats found in the forums would be of real benefit. Combine this with the wiki and new formats could be added on-the-fly.
## Post #8
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2007-01-12T01:55:34+00:00
- Post Title: Textures. Graphics. And the like --> Wiki

I was thinking something along those lines :)
basically allow mexcom to open/preview pictures inside the archives it can open.

graphics file formats are usualy just picture containers so once you get past the header the rest is raw image data arranged in one way or another

something like the mexscript could do the trick
I think it could be great for modders
## Post #9
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-01-12T19:20:32+00:00
- Post Title: Textures. Graphics. And the like --> Wiki

I think that perhaps the best approach would be to either expand the BMS scripting language to enable support of graphics/texture (and probably audio) formats, or to develop a second scripting language specifically for said file types, to operate side-by-side with the current BMS language. I believe that Rahly (or someone else) is working on-and-off on a new version of the BMS language; these updates and expansions could therefore be worked into the new version.
## Post #10
- Username: OneOneSeven
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Jul 16, 2006 1:54 pm
- Post datetime: 2007-01-13T00:30:25+00:00
- Post Title: Textures. Graphics. And the like --> Wiki

Once I finalize my learning of the anatomy of a Windows app (I just have experience with D3D) I'd be more than happy to write a framework. I already know about the window classes, event handler/message loop, etc. I guess I may even be able to take a good chunk out of it now/in the near future, my only problem is familiarity.
