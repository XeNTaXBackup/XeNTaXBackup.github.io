## Post #1
- Username: Nerd42
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 14, 2011 1:03 pm
- Post datetime: 2014-03-26T06:56:35+00:00
- Post Title: Project Spark audio (Linkin Park music)

So, basically, [this happened](http://www.youtube.com/watch?v=IfnhGW2Q_y0). Linkin Park put out an "remixable interactive music video" within Microsoft's new game maker called "Project Spark."

The multitracks / stems (separate tracks for each instrument useful to serious remixers) to Linkin Park's new single have got to be in there somewhere. Different instruments stop playing when you crash into obstacles in the level, and resume playing when you get healed.

So I downloaded Project Spark on the Windows Store on my Windows 8 PC. It's free, both for XBox and PC. I don't have an XBox, so I'm trying this on PC.

Within the Project Spark marketplace, there is a "LINKIN PARK - GUILTY ALL THE SAME FREE AUDIO PACK" which apparently has a bunch of sounds in it. I "bought" it for 0 credits, and then checked my AppData\Local\Packages\Microsoft.Dakota...\LocalState\marketplace_content folder for anything new.

I discovered a file called "cd6eae8ab7e8daf3.bundle" that's 16 MB, much bigger than any of the other files in there, and the newest: timestamped about the same time I said to download the audio pack, so I figure that must be it.

Anyone have any ideas on how to extract the audio out of that? You guys can follow these same steps cause it's all free-as-in-beer content for any Windows 8 users. Any help towards getting this audio would be appreciated! 

(later edit) There is some interesting text that looks like XML near the end of this file, which I can post shortly.

It contains statements like:

```
			<ShortName>MUS_LP_GuiltyAlltheSame_Bass_022814.wav</ShortName>
			<Path>sfx\mus_lp_guiltyallthesame_bass_022814_56b56e6e.wem</Path>
		</File>
```
and
```
			<ShortName>MUS_LP_GuiltyAlltheSame_Stinger_Guitar_02.wav</ShortName>
			<Path>sfx\mus_lp_guiltyallthesame_stinger_guitar_02_5ade1b48.wem</Path>
		</File>
```
## Post #2
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-03-26T13:48:12+00:00
- Post Title: Project Spark audio (Linkin Park music)

.wem implies wwise audio typically.
(look for riff/rifx headers in the file)
## Post #3
- Username: Nerd42
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Apr 14, 2011 1:03 pm
- Post datetime: 2014-03-26T18:33:35+00:00
- Post Title: Project Spark audio (Linkin Park music)

Great, thanks!
