## Post #1
- Username: Cyberpixie
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 23, 2017 8:22 pm
- Post datetime: 2018-08-21T16:12:45+00:00
- Post Title: Writing a Noesis Export plugin from a Import one?

I want to mod the game Hatsune Miku: Project Diva Extend, For that I would need a .igb exporter. I found a Noesis script made by Minmode on deviantArt that imports Project Diva’s .igb , But it doesn’t exports. How can i write a plugin based on the importer, but that exports instead? Maybe is there any tool that writes an exporter based on an importer???

PS: I’m a total coding noob, I just started learning phyton, So please try to give me as much details as possible about the process so i can learn it well.
## Post #2
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-08-21T17:55:02+00:00
- Post Title: Writing a Noesis Export plugin from a Import one?

To write an exporter for a custom format you need to understand how the format is structured from start to finish. For importing you can get away with skipping some parts, and only read the data you need. For exporting though you would need to write all the data that the game engine requires. Otherwise it will probably not work correctly or not load at all.

The importer script would help you understand the igb format, but you might have hard time with it if you can't read others' code. Also I don't think you can make an exporter without knowing how to code. I mean importer/exporter is an algorithm at its core, and you need to implement it in some way. In this case it is by programming.

I am not saying this to discourage you in any way. The first step if to fully understand the format. To write a code that exports a file, you need to know what the file should be like. You can analyze the format (via hex editor or something) and later you can team up with someone who knows how to code. Or maybe you can improve your python skills and start working on an exporter yourself.

I don't know anything about the igb format, but from my experience it is usually much harder to make an exporter than an importer. Just take a look at the format and know what you are getting into before spending too much time on it.
## Post #3
- Username: Cyberpixie
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 23, 2017 8:22 pm
- Post datetime: 2018-08-21T20:33:00+00:00
- Post Title: Writing a Noesis Export plugin from a Import one?

I see... Maybe I can rip one of the models for making it easier.
But I’ll probably take a really long time. I really wish there was any kind of tool for automatically writing the script based on the 3D file and maybe on the import plugin too, But I’m not sure if that’s even possible. Thanks anyway!

The bad thing here is that I’ll have to take a long time to learn more Phyton... Maybe if someone would like to help me, I would be really happy!

PS: I heard there was a Maxscript called “Alchemy” that can export .igb, But unfortunately I can’t find the download anywhere... It really would help me to mod Project Diva...
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-08-21T21:43:28+00:00
- Post Title: Writing a Noesis Export plugin from a Import one?

info on the engine
VV Alchemy is a game engine designed by Intrinsic (firstly called Intrinsic Alchemy) and later purchased by Vicarious Visions. First used in 2002.
original website
[http://www.siliconstudio.co.jp/products ... e/alchemy/](http://www.siliconstudio.co.jp/products-service/middleware/alchemy/)
The igb format is very complex and you need to map out every structure.
They are all hard coded in size so you need to follow the sdk or be good at reversing to map them all out.

you are much better off modding the ps3 games much better format.
