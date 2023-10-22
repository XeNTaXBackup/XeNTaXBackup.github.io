## Post #1
- Username: ThisGameIsFrk
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Feb 27, 2022 6:35 pm
- Post datetime: 2022-03-07T01:24:47+00:00
- Post Title: Project Kat: Paper LiLy (Godot Engine) Localization

Hi, I'm Vietnamese Translator, today I have a little problem need you guys solve, I want to translate game "Project Kat: Paper LiLy" but I don't know how to unpack this game, if you want to test the game you can download it from steam, it's free. Sry for my bad English
## Post #2
- Username: ThisGameIsFrk
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-03-07T19:06:18+00:00
- Post Title: Project Kat: Paper LiLy (Godot Engine) Localization

Godot engine uses PCK archives for storing data [http://wiki.xentax.com/index.php/Godot_Engine_PCK](http://wiki.xentax.com/index.php/Godot_Engine_PCK)

In your case text is stored in 
\steamapps\common\Paper Lily - Project Kat\pack\_def.pck file.

You can use for example Godot PCK Explorer or any other program/script listed on the wiki to get the data.

After extracting, you will find text in LSF files which seems to be game script files, for example in:
\definitions\rooms\Prologue_Club_Occult\event_conversation_1.lsf
or
\definitions\events\prologue_intro.lsf
## Post #3
- Username: ThisGameIsFrk
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Feb 27, 2022 6:35 pm
- Post datetime: 2022-03-08T11:56:34+00:00
- Post Title: Project Kat: Paper LiLy (Godot Engine) Localization

Thank you very much bro, I love you
## Post #4
- Username: IGBT001
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Mar 24, 2022 5:27 pm
- Post datetime: 2022-03-24T09:59:12+00:00
- Post Title: Project Kat: Paper LiLy (Godot Engine) Localization

Sorry, with all due respect, not every game is stored in this location, such as banana_ Hello, this game is to store the text in this location, banana_ hell\dialogue\Dialogue_ Jane_ 2.1. JSON file
