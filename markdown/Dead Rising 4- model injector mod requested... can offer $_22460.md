## Post #1
- Username: DJLarryt
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Oct 19, 2014 12:15 pm
- Post datetime: 2020-07-28T18:04:08+00:00
- Post Title: Dead Rising 4- model injector mod requested... can offer $

Hello experts.  I hope this is allowed here, if not, let me know and I will delete/move it.

Dead Rising 4... lost opportunities, poor execution, sloppy build and hasty release.  Could have been a great game under another team,
but I digress.  

Is there anyone who can help build a tool that can inject/replace the Frank West model in-game for a better playing experience?

So much clipping, model tearing, orbiting polys... I could go on.  Would be nice to maybe replace the in-game model with something a little more functional.  I read the game uses the same engine as the RE5 build (Forge? it is Capcom after all) and know that RE has been modded, so no reason why this one can't either.

I have a script for 3ds2016 that will pull models, elements, and skeleton already.  What I'm looking for is something to put the modded model back in- I'm aware Frank may have his own skeleton, poly limit, etc.  Maybe this script to pull the model can be reverse engineered?

Thanks for considering, I can offer $ for a serious modder who is willing to take this on (within reason).
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2020-07-30T00:12:30+00:00
- Post Title: Dead Rising 4- model injector mod requested... can offer $

u should post what u have; tools, source codes, scripts, any notes and samples! everyone always forgets samples..
## Post #3
- Username: DJLarryt
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Oct 19, 2014 12:15 pm
- Post datetime: 2020-07-31T14:37:40+00:00
- Post Title: Dead Rising 4- model injector mod requested... can offer $

Hi @Mariokart64n!  Long time no speak    Hope you are well.

@Zaramot produced an effective script for pulling models and their skeletons from the .mdl files in DR4 to 3DSMax (it works in 2016).  It is attached.


 Dead_Rising_4_UPD_B.7z
(4.75 KiB) Downloaded 17 times



If you're having trouble seeing the .tex files, let me know, there's  script to fix those too.

I can help with testing as well.  Thanks for any input.
## Post #4
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2020-08-05T04:21:06+00:00
- Post Title: Dead Rising 4- model injector mod requested... can offer $

I spent a decent amount of time coding up a tool, but when I tried to test a mod ingame I had discovered that the game would crash..   

Initially I had assumed it was an error on my part, so I had spent a few more days debugging and double checking outputs byte for byte.

Eventually I was at a point where I had no idea what was causing the game to crash  . 

So on a desperate last effort I did a simple edit by just changing a random byte in one of the original game files. To my surprise the game crashed AGAIN!!! with something as simple as a single byte change that means something is NOT right.

I don't believe the game was crashing, I think its actively detecting for file changes and will self terminate when a change is discovered.
I based this assumption on the byte test I did and also that the DR4 executable is oddly large. Over 100mbs compared to DR2 which was only 9mbs, this may indicate that they are storing checksum's for each file in the game executable and are actually verifying every file..which is... CRAZY   

TO SUMMARIZE: 
!!!  THIS GAME CAN NOT BE MODDED !!!

I'm assuming the developers saw how rampant the modding was in DR2 and sought to eliminate that happening in DR4. Likely they knew their sales were down from DR2 and they were probably pushing the game towards DLC's and micro-transactions in DR4 to save face with CAPCOM.

But we all know how that went when CAPCOM closed the studio down after DR4 released    also if you watch any of the dev interviews on DR4 its VERY obvious that they knew the end was coming   not to mention the director quit months before DR4's release...

It's for the best anyway, any dev / employer that thinks their consumers or their employees opinions are the problem DON'T deserve support of their staff or consumers! its a team effort after all!

Here is a in-depth video of me going over the methods I used to verify that the game implements some sort of file protection

[](https://youtu.be/jdY0_eVVxTY)
## Post #5
- Username: DJLarryt
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Oct 19, 2014 12:15 pm
- Post datetime: 2020-08-10T14:36:35+00:00
- Post Title: Dead Rising 4- model injector mod requested... can offer $

Hey man!

Thanks for this very informative, detailed and well-presented summary.  I knew there were lots of issues going on during the development of this game but this releasing a half-assed, messy, broken game yet finding time to incorporate a security/checksum block to prevent anyone else from modding/fixing their shite is A-List level douchebaggery.  I hope none of them ever get a job anywhere else.

It's no wonder CV was shut down, this team sounds like a federation of self-absorbed jerkoffs (especially since they put effigies of themselves in the game as bonus mission characters).

I'll reach out to you on Steam-
