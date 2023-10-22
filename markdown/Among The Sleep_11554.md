## Post #1
- Username: TRfan
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Jul 12, 2012 11:44 pm
- Post datetime: 2014-05-31T12:39:18+00:00
- Post Title: Among The Sleep

Hi all.

 I feel like someone has a solution for me in this forum 

I need to edit text files from assets file of this game. I tried a tool called Unity Assets Explorer ([viewtopic.php?f=10&t=10085](http://forum.xentax.com/viewtopic.php?f=10&t=10085)) but I only managed to extract files. I found text files but couldn't import them back into the file. I hope someone will reply soon.
## Post #2
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2014-06-05T08:00:33+00:00
- Post Title: Among The Sleep

Use the tool that Haoose linked here: [viewtopic.php?f=33&t=10739&start=22](http://forum.xentax.com/viewtopic.php?f=33&t=10739&start=22)
## Post #3
- Username: TRfan
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Jul 12, 2012 11:44 pm
- Post datetime: 2014-06-05T10:30:38+00:00
- Post Title: Among The Sleep

Thanks but it's all russian and I don't know how to use the tool.
## Post #4
- Username: kofola
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Mar 10, 2014 12:12 am
- Post datetime: 2014-06-13T19:41:03+00:00
- Post Title: Among The Sleep

I need too.
Can some do import/extract tool.
I need translate for my country.

Thank you for any help.
## Post #5
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-06-14T13:04:01+00:00
- Post Title: Among The Sleep

Just use Haoose's Unity Assets Explorer. Plus some hex editor and some text editor.
For faster "searching" through .assets files, you can use Barracuda's DisUnity tool.
## Post #6
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2014-06-15T09:25:29+00:00
- Post Title: Among The Sleep

Here is how you can translate this game (I think it'll work with other Unity games too):
1. Download the Unity Asset Editor from this link: 
```
http://7daystodie.com/forums/showthread.php?5030-Grim-s-Unity-Asset-Editor
```

2. Open up resources.asset with it.
3. Search up all texts (they will have "Text" type and if you're looking for the English texts, they'll have "_en" in the end).
4. Right click on each of them and "Export".
5. Translate them.
6. Right click on each of them and "Import".
7. "File -> Save as" and overwrite the original resources.asset file.
8. Profit! 

Some texts are not translatable sadly (like the text in Options like "Audio", "Video", "Controls", but they are in the files. Why the game doesn't use those lines, who knows?).
## Post #7
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-06-15T12:00:40+00:00
- Post Title: Among The Sleep

> Reply from lostprophet
>
> 
Some texts are not translatable sadly (like the text in Options like "Audio", "Video", "Controls", but they are in the files. Why the game doesn't use those lines, who knows?).

Probably a bug. Those words (and "ago" and "<New Profile>") are in Among the Sleep_Data\Managed\Assembly-CSharp.dll file. I used .NET Reflector to edit that .dll.
## Post #8
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2014-06-17T20:04:57+00:00
- Post Title: Among The Sleep

> Reply from merlinsvk
>
> lostprophet wrote:
Some texts are not translatable sadly (like the text in Options like "Audio", "Video", "Controls", but they are in the files. Why the game doesn't use those lines, who knows?).

Probably a bug. Those words (and "ago" and "<New Profile>") are in Among the Sleep_Data\Managed\Assembly-CSharp.dll file. I used .NET Reflector to edit that .dll.
I opened up .NET Reflector, opened "Assembly-CSharp.dll" and tried searching for eg. "New Profile" but there is no such text like that in it. Am I doing something wrong?
## Post #9
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-06-17T22:13:55+00:00
- Post Title: Among The Sleep

[](http://imiger.eu/image/174.html)


But I totally forgot to mention that you have to use Reflexil add-in (it's free) for Reflector to be able modify .NET source code. Sorry about that
## Post #10
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2014-06-18T04:48:19+00:00
- Post Title: Among The Sleep

> Reply from merlinsvk
>
> 


But I totally forgot to mention that you have to use Reflexil add-in (it's free) for Reflector to be able modify .NET source code. Sorry about that
Oh, okay, I got a bit further now 
1. I opened up Assembly-CSharp.dll.
2. I've done what you have shown me.
3. After finding <New profile>, I can't edit it.
4. I chose Tools > Reflexil v1.7.
5. I clicked on New profile with the right mouse button and chose Edit.
6. Modified "<New Profile>" and clicked "Update".
7. I couldn't find any Save button and the modified text doesn't show up in-game.
## Post #11
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-06-18T06:59:34+00:00
- Post Title: Among The Sleep

Yeah, it's hidden in the context menu.
