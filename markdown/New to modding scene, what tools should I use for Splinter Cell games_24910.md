## Post #1
- Username: DaLeX97
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 03, 2022 3:26 am
- Post datetime: 2022-01-02T20:05:45+00:00
- Post Title: New to modding scene, what tools should I use for Splinter Cell games?

Apologies if this is not the correct forum to create this thread, it didn't seem appropriate to post in the "Tutorials" subforum of the "Game Modding" forum, so I thought this might be the right place.

Anyway, what I'm looking for is to be able to mod Splinter Cell: Chaos Theory to include subtitles when the "Use Native Language" option is turned on. In brief, within that game exists an option for the enemy soldiers to use their native languages (Peruvian, Korean, Japanese, etc.) instead of English with an accent, which makes it much more immersive and realistic. The problem, however, is when you enable that option, you don't get any subtitles or translations for what they're saying, and seeing how the game is based around stealth, interrogation and eavesdropping are essential to getting useful information out of your enemies which can help you progress through the mission easier. This is unfortunately hard to accomplish when a player is not a polyglot.

This is just the primary reason why I'm looking to mod this game, of course, there are plenty of other things I'd like to do, as modding games was always something that I wanted to do, just lacked any motivations/goals to do that. I always liked the community and creativity around it.

So far from what I've seen, the modding scene for the Chaos Theory is either dead, or it's simply hard to find with common search engines.

As I mentioned before, I have no prior modding experience, neither for this series nor any other, so I would like to start from somewhere.

I do have programming experience, but mostly with high-level programming languages. I work in an IT company as a Junior Software Developer, but low-level programming like Assembly, OllyDbg, WinDbg, IDA, etc. is something that I have no experience or idea how to work with.

Any suggestions from where I can start, and what tools would I need?

Happy New Year, and apologies for the long post!
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-01-03T15:37:01+00:00
- Post Title: New to modding scene, what tools should I use for Splinter Cell games?

> Any suggestions from where I can start, and what tools would I need?

You can start here [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)

Your goal to include subtitles is basically to change game's logic for some function. So the tools needed for that would be probably IDA, Ghidra or Cheat Engine.

After you'll reverse engineer this "subtitle function" you can create a patch in assembly or create a DLL file with a hook.
Some tutorials from the link above can explain how to do that.


Beside that you can search for some game specifig tools by googling something like "Splinter Cell: Chaos Theory github", "Splinter Cell: Chaos Theory tool" etc. Maybe you'll find something useful.
## Post #3
- Username: NadiaThomson
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 01, 2022 4:29 pm
- Post datetime: 2022-02-02T07:36:57+00:00
- Post Title: New to modding scene, what tools should I use for Splinter Cell games?

This mod contains multiple INI files that change some of the gameplay mechanics, to make it feel similar to older Splinter Cell games such as Chaos Theory
