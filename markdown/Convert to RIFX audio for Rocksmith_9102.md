## Post #1
- Username: PikminGuts92
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jun 16, 2012 11:16 pm
- Post datetime: 2012-06-16T15:49:07+00:00
- Post Title: Convert to RIFX audio for Rocksmith?

Hello, I'm working on creating customs songs in the video game called Rocksmith for the Xbox 360. I already have all of the game files extracted on my computer. The song audio files are RIFX from AudioKinetic Wwise.

By using ww2ogg.exe and revorb.exe (located [here](http://hcs64.com/vgm_ripping.html)) I can convert the song audio files to a listenable format in Audacity. That's all fine and dandy but I want be able to replace the audio in the game with my own. To my knowledge, I don't think I can create the proper RIFX audio files by using those two programs mentioned.

So does anyone know how I can go about creating RIFX audio files for the game? Maybe I can somehow use ww2ogg.exe in reverse?
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2012-06-16T23:30:43+00:00
- Post Title: Convert to RIFX audio for Rocksmith?

There's a lot of data in those Wwise files that ww2ogg throws away, so it really isn't feasible to just "run it in reverse".  It was created because Audiokinetic didn't provide any tools to convert their modified Vorbis back to standard Ogg Vorbis, there's not much sense in replicating a converter to their proprietary format.

If you want to encode, you should get Wwise from Audiokinetic, it's free to evaluate and for non-commercial use.  I have no idea how specifically to do encoding with it for a particular game.  You can get it here: [http://www.audiokinetic.com/en/downloads](http://www.audiokinetic.com/en/downloads)

[edit]
You will probably need to get an older version if you're generating stuff for Rocksmith, though.  According to my notes it should be something older than 2011.2, but I'm not quite sure how old.  The Vorbis packing format was changed frequently between releases.
## Post #3
- Username: PikminGuts92
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jun 16, 2012 11:16 pm
- Post datetime: 2012-06-17T01:28:34+00:00
- Post Title: Convert to RIFX audio for Rocksmith?

Thank you for your reply hcs.   

I have copy of Wwise that I downloaded shortly after Rocksmith's release last year. Since then, I haven't been actively pursuing putting custom songs in the game. It's just that now I actually have free time to do this. I have yet to get a grasp of the interface of Wwise but it can't imagine it'd be too hard. My version of Wwise is v2011.2.2.

The developers have been releasing new songs for the game bi-weekly post launch. So maybe they've kept their tools up to date perhaps. I honestly wouldn't know.
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2012-06-17T02:57:45+00:00
- Post Title: Convert to RIFX audio for Rocksmith?

2011.2.2 might be too new, 2011.2 switched to a aoTuV instead of libvorbis, and they use a different hardcoded set of codebooks.  I doubt the developers would go to the effort of integrating new versions of middleware, generally you only want to handle bugfixes.
