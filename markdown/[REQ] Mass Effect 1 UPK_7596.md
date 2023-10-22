## Post #1
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2011-10-30T15:14:09+00:00
- Post Title: [REQ] Mass Effect 1 UPK

Greetings.

My request this time is that I receive a QuickBMS script, or an unpacker/repacker for the file attached. For translation reasons. Of course, I am well aware that the TLK within this will also have to be hacked but that's more for Localization forum than a Game Archive one. So, in order to keep things clean, I ask for a method to extract the contents of the file attached and pack the modified file back in.

Thanks in advance for any reply.
## Post #2
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-10-30T19:25:41+00:00
- Post Title: [REQ] Mass Effect 1 UPK

UPK stands for Unreal Package.

General structure of this format is well-known, however mainly the header changes in almost every game. You can use [url=[http://code.google.com/p/unhood/](http://code.google.com/p/unhood/)]UnHood[/b] as basis.

However, it seems that you're trying to translate the Pinnacle Station DLC. An editor, which will be able to edit all 3 games (ME1-3) TLK files, will be released some time after ME3 release (not by BioWare, of course). It's up to you, if you want to wait until then.
## Post #3
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2011-10-30T21:47:14+00:00
- Post Title: [REQ] Mass Effect 1 UPK

I'd prefer having it earlier, but I'll wait if I must. Who is the author of this editor? I'd contact him directly.

Also, I need to know how to extract and repack this particular Unreal Package version.
## Post #4
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2011-10-31T18:46:41+00:00
- Post Title: [REQ] Mass Effect 1 UPK

This UnHood: how exactly do I change it to support ME1, and how do I make an exe out of that svn mess? First time ever I'll be touching that.
## Post #5
- Username: guki
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Apr 12, 2010 3:55 am
- Post datetime: 2011-11-07T05:42:58+00:00
- Post Title: [REQ] Mass Effect 1 UPK

try these tools

[http://www.gildor.org/news](http://www.gildor.org/news)

downloads -> umodel.exe
write a .bat file to unpack every upk or other archives in the cookedpc folder - read the pdf here
umodel.exe helped me unpacking the files from off-road drive 3 which also uses the unreal engine

actorx import 3ds max script - can open the mesh anims and so on

ignore the other tools here

you can find a PDF on google - "how to convert mass effect pdf" gives you that link

[http://www.google.de/url?sa=t&rct=j&q=h ... Lw&cad=rja](http://www.google.de/url?sa=t&rct=j&q=how%20to%20convert%20mass%20effect%20pdf%20meshes&source=web&cd=3&ved=0CDAQFjAC&url=http%3A%2F%2Fwww.foundation3d.com%2Fforums%2Fattachment.php%3Fattachmentid%3D36627%26d%3D1266510164&ei=g263Tsy9L8ex8QPJ7Yj-BA&usg=AFQjCNEWtlg_0OXTUbwSGS0jKypI50AQLw&cad=rja)


ask if you need more help
## Post #6
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2011-11-07T16:04:25+00:00
- Post Title: [REQ] Mass Effect 1 UPK

I tried UModel as first before I even started this topic. It won't extract TLK files. It's not meant to do it.
## Post #7
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-03-06T12:04:36+00:00
- Post Title: [REQ] Mass Effect 1 UPK

Greetings again. Would it be possible to try and help me with this?
## Post #8
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-03-07T01:13:31+00:00
- Post Title: [REQ] Mass Effect 1 UPK

> Reply from Delacroix
>
> Greetings again. Would it be possible to try and help me with this?try to rename 'tlk' to 'xxx' or 'upk'
## Post #9
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-03-07T07:08:44+00:00
- Post Title: [REQ] Mass Effect 1 UPK

Haven't even managed to extract the tlk out of the upk in the first place. Hm.
## Post #10
- Username: bodicuakp
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 24, 2012 5:29 pm
- Post datetime: 2012-04-24T22:26:06+00:00
- Post Title: [REQ] Mass Effect 1 UPK

I have same problem. I want to translate mass effect game but I can't find the way to edit the globaltlk.upk file.
I can extract the upk file using this tool:
http:[www.gildor.org/downloads](http://www.gildor.org/downloads)
dowload --> unreal package extractor.
the problem is after I extract that file I don't find .tlk file but only some text file and two file extention .biotlkfile. 
Is there a tool to edit that file and re-pack it back to upk file? Please help me. Im the beginner for editing game files.
Im sorry my english is bad.
## Post #11
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2012-04-25T06:53:59+00:00
- Post Title: [REQ] Mass Effect 1 UPK

Well, the most important thing about modifying texts in ME1, is that the texts for all dialogs is stored in GlobalTlk.upk file, but those are not used when displaying them in game. Real texts, that are actually used, are located in packages located in this folder Mass Effect/BioGame/CookedPC/Maps.
## Post #12
- Username: bodicuakp
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 24, 2012 5:29 pm
- Post datetime: 2012-04-26T06:18:48+00:00
- Post Title: [REQ] Mass Effect 1 UPK

> Reply from mnn
>
> Well, the most important thing about modifying texts in ME1, is that the texts for all dialogs is stored in GlobalTlk.upk file, but those are not used when displaying them in game. Real texts, that are actually used, are located in packages located in this folder Mass Effect/BioGame/CookedPC/Maps.
So that mean I don't need the globaltlk.upk to translate that game. What file have to I go with to edit in-game text? thanks
## Post #13
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2012-04-26T08:00:01+00:00
- Post Title: [REQ] Mass Effect 1 UPK

No, you actually need to do that - all texts not used in dialogs are loaded from GlobalTlk.upk. However there are some texts, which are not used in dialogs but are not loaded from GlobalTlk.upk either (e.g. Score board in Pinnacle Station DLC).
## Post #14
- Username: bodicuakp
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 24, 2012 5:29 pm
- Post datetime: 2012-04-27T21:58:32+00:00
- Post Title: [REQ] Mass Effect 1 UPK

> Reply from mnn
>
> No, you actually need to do that - all texts not used in dialogs are loaded from GlobalTlk.upk. However there are some texts, which are not used in dialogs but are not loaded from GlobalTlk.upk either (e.g. Score board in Pinnacle Station DLC).
ok, I get it. but I found new problem. After I extract any upk file that contain in-game text. I always get file like blahblah.biotlkfile and I have no idea how to open these files. Anyone can help me?
## Post #15
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-07-12T22:45:04+00:00
- Post Title: [REQ] Mass Effect 1 UPK

[http://jpmod.blogspot.com/search/label/Mass%20Effect](http://jpmod.blogspot.com/search/label/Mass%20Effect)

Found a tlk tool in the bottom post. Converts contents to .csv.
