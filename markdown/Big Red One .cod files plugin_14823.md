## Post #1
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-08-08T12:23:14+00:00
- Post Title: Big Red One .cod files plugin?

So I tried using GameExtractor to open the .cod files from Call of Duty Big Red one, which it claimed to support.
However the program itself is missing the plugin for .cod files. Anyone have a copy of this plugin?
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-08-08T14:06:33+00:00
- Post Title: Big Red One .cod files plugin?

its in the form of plugin named "Plugin_COD_KAPF.class" in GameExtractor.jar
open a file with plugins instead of scripts
File>Read Archive>Open With Plugin
## Post #3
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-08-08T20:28:26+00:00
- Post Title: Big Red One .cod files plugin?

I had checked the plugin list before. It is not there. Whenever I try to open it, be with scripts or plugins it says there is not a plugin to open the file type.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-08-09T10:58:36+00:00
- Post Title: Big Red One .cod files plugin?

i searched through the source files and Plugin_COD_KAPF.java is the
only one that referenced "Call Of Duty 2: Big Red One" for Xbox.
it is also the only plugin that references the "KAPF" magic.
the only plugin i see in the list with "KAPF" is "PAK_KAPF", it has to be that one  
if that doesn't work then maybe you have an unknown variant and 
would be better off getting a bms script made for it instead.
## Post #5
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-08-09T13:34:00+00:00
- Post Title: Big Red One .cod files plugin?

The PAK_KAPF plugin is for .PAK files, not .COD files. It even says it's made for a different game.
My copy of game extractor is lacking the COD_KAPF plugin, I need it.
## Post #6
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-08-17T08:24:52+00:00
- Post Title: Big Red One .cod files plugin?

Does anyone have a different copy of game extractor I can try? I still cannot find a version with a working cod_kapf plugin.
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-08-17T13:28:19+00:00
- Post Title: Big Red One .cod files plugin?

i just tried opening a cod file from COD2:Big Red One (Xbox) with GameExtractor and
it opened it just fine but it only listed unnamed dds textures in the archive.
maybe you can have Mr watto add support for names and all files in it   
[http://www.watto.org/contact.html](http://www.watto.org/contact.html)

also is there a reason you can't just upload a *.cod sample to Zenhax and
have a bms script made for it? it will usually be solved in the same day!  

edit
aha!   
[http://zenhax.com/viewtopic.php?f=9&t=1492](http://zenhax.com/viewtopic.php?f=9&t=1492)
