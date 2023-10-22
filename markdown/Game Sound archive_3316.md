## Post #1
- Username: Shroo
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jan 23, 2009 8:21 am
- Post datetime: 2009-01-23T10:29:45+00:00
- Post Title: Game Sound archive

Hmm, how to explain, lets say i want to rip a game, and a game has 2gb sound archive, i do know how to rip,extract audio from that archive using filestripper or other tools, i know how to inject wave files (CLASS/BACKLASH), but i cant find a solution to this problems.

I need to find a way to empty sounds from that archive, so it would use less space, and then i could do injection. 

I tried to explain as good as i can, i would look to get some help, or advice how to do this properly. 

Thank you!
## Post #2
- Username: Xino
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Dec 21, 2008 1:26 am
- Post datetime: 2009-01-23T13:03:10+00:00
- Post Title: Game Sound archive

Cant extract every file, dummy and rebuild?
## Post #3
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-01-23T22:41:20+00:00
- Post Title: Game Sound archive

Another person asking how to inject? and with the same tool?
What happens? 
It's another post opened asking about this...   
[viewtopic.php?f=17&t=3278](http://forum.xentax.com/viewtopic.php?f=17&t=3278)
And why you want to rip a game? warez?!! no warez here.
## Post #4
- Username: Shroo
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jan 23, 2009 8:21 am
- Post datetime: 2009-01-24T07:37:17+00:00
- Post Title: Game Sound archive

NO im not asking how to use inject! i just gave an example.

I am asking how to remove sounds from an archive.
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-01-30T10:06:54+00:00
- Post Title: Game Sound archive

Okay, so you wish to make the game files smaller in size, so the whole game takes up less hard drive space, by removing sounds and/or music from the archives?

This is not a simple task. These injectors were used by crackers in the past to downsize their releases by removing certain sounds, compress them thorougly, and reinject them upon installation. But what they needed to sometimes is the format of the archive they were in originally. What also happened is that they replaced existing waves with silent ones. This would not be difficult to do. 

Many archive instances store information about the specific content, such as size of the content. In case of sounds, each sound for example could be preceded by a variable that depicts the size of the sound file. The game's executable may need this information to process the sound correctly. In other words, to replace those sounds with new ones of different size, you need to know where in the archive the information about size is stored and adjust that if you start replacing stuff. A program that really removes sounds should be aware of this and perform this adjustment. 

Now, if you want to 'remove' sounds from an archive, simply to make a smaller compressed archive, you could just replace the WAVE sounds with silent sounds of exact same lenght of the original sound, but with silent data (compression of those will be more thorough). What you then need is a program that scans for WAVE files, notes the exact length of them when found, and replaces them at this position with a silent sound of the same lenght.
## Post #6
- Username: Shroo
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jan 23, 2009 8:21 am
- Post datetime: 2009-02-03T16:43:54+00:00
- Post Title: Game Sound archive

Thanks a lot now i understand how it works, i just need to find a program which does that!

Thanks Again!
