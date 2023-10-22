## Post #1
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-03-31T01:00:46+00:00
- Post Title: Wiki URL format change

Well, you all should remember a few week back, I was talking some pretty big game about changing the format for XW URLs once and for all. Well, I talked the talk, and then tried to walk the walk... and I found out it's a helluvalot harder than I thought it would be.  That's not all I discovered, though...

For starters, it struck me that the most natural structure for the URLs, based on simplicity as well as MediaWiki's installation directory, is not wiki.xentax.com/wiki/Page name, as was previously decided, but actually wiki.xentax.com/Page name, which (IMHO) is much cleaner-looking, and which should be (in theory, for what it's worth) easier to implement.

The other important thing that struck me is that computers are fickle as hell. It's the type of thing you should really know all along, but you never truly appreciate it until you're trying to implement something perfectly in a live environment when you've never really done it before, and you've got to call on the webmaster to bail your sorry ass out of a nonfunctional tight spot for, like, the third time (sorry Mr.Mouse, and many thanks for your seemingly limitless patience  ).

So, to wrap up this update/mini-rant, I'm going to re-approach this update as I get the time, reading reference material, taking a more careful look at files, jotting down notes, and finally, carefully documenting what I actually try in this thread. If anyone else cares to pitch in with comments, suggestions, observations, or personal insults, feel free to. 

EDIT: As a bit of a footnote, should this stay in the WIKI forum, where only WAdmins (Wiki Admins, I made it up on the spot, whaddaya think? ...no? Okay, didn't think so...) can read and comment on it, or should it be moved to the "Miscellany" forum for everyone to have a look?
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-03-31T06:32:25+00:00
- Post Title: Wiki URL format change

Hehe, no problem, if you screw up a fourth time, I'll still bail you out  

Anyway, implementing (web) updates can be a pain, you have to take heed of the version of the wiki needed, in this case php5 versus php4, which files to edit when etc. Don't worry, we've all been there. 

We can bring this URL matter out in the open, yes. I'll move the thread.
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-04-05T15:42:27+00:00
- Post Title: Wiki URL format change

All right, after doing some research, I've learned a few things:
MediaWiki is unnecessarily complicated and fickle when it comes to shortening its URLs
Even people with a great deal of experience with PHP, Regular Expressions, MediaWiki, and .htaccess struggle to get MediaWiki to play nice with shorter URLs - one person commented that he worked with it for two hours before getting results
Even after the necessary changes were made and tweaked so that MediaWiki accepted them, many people had problems with several subfolders, and in some cases, random.php, and even Favicon.ico
All of this is really making my head hurt

If anyone has any comments to make or anything at this point, I'm all ears.
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-04-05T16:32:41+00:00
- Post Title: Wiki URL format change

It seems your analysis would argue against the change of the URL. I say let's forget it then.
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-04-05T17:55:20+00:00
- Post Title: Wiki URL format change

Well, I'd really rather not, but I'm also not about to argue. I don't intend to give up on it in the long run, but there are other, better things to be done in the meantime (for instance, I was intending to get back to working on SVG support). In any case, did you ever get around to doing the custom BBCode I requested?
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-04-27T13:35:27+00:00
- Post Title: Wiki URL format change

[GRAFs/All](http://wiki.xentax.com/index.php?title=GRAFs/All)

And 

[This is the ludicrous long alternative text message to the XeNTaX page at the Game File Format Central courtesy of yours truly that is of course Mr.Mouse of Xentax who happens to name himself The Age of Chaos when in multiplayer after Deathbringer and Double Deathbringer were found insufficient to carry the message of supreme superiority beyond the alpha and the omega but unfortunately did carry sufficient enough idiocy for Mr.Mouse to become the laughing stock in his circle of friends :/](http://wiki.xentax.com/index.php?title=XeNTaX)

How's that, Phillip?
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-04-28T16:15:06+00:00
- Post Title: Wiki URL format change

Aah, very nice! Now I don't have to worry about breaking a million and one links from the forum if/when I ever get the new URLs working... 

EDIT: I'm not quite sure how best to say this, so I'll come right out and say it: it seems that for the wiki= tag, you crossed the pagename and label variables, ending up with [ wiki=label]pagename[/wiki ], which is opposite of how url= does it. The fix should be just a simple swapping of variable numbers in either the BBCode or the replacement HTML (whichever you choose). But then, I should just be happy that you finally got around to doing it...
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-04-28T17:21:53+00:00
- Post Title: Wiki URL format change

DOne....It was actually my own logic to RevErse it. oO/
## Post #9
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-04-28T18:47:48+00:00
- Post Title: Wiki URL format change

Aah, I see... it *does* make sense in certain circumstances, I suppose... In any case, thanks for putting up with my constant badgering and nitpicking...
