## Post #1
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-10T17:31:23+00:00
- Post Title: Adding more to the WiKi

Would it be possible to restucture the WiKi a bit to be even more usefull?

It would be nice if you could add 2 type of entries

* Game Archives
* Game Files Formats

The game files (.aud files for example) occasionaly get reused throughout different games, and therefore might have the right to be distinctly marked.

A nother thing is that within these Game File Formats, a link to which games they are used in would be nice.

If small variations to the format occur from game to game, it might be a good idea to have this information in seperate sections in the same wiki page. If formats differ to much, seperate pages would be better.

Besides the flow based details that i see on most pages, it might be usefull to add a bit more data, or even a walk thrue of the file.

Take a look at this file for an idea about what i am talking about: [http://en.wikipedia.org/wiki/Image:Mp3filestructure.jpg](http://en.wikipedia.org/wiki/Image:Mp3filestructure.jpg)

Also, don't be afraid to post a bit that is more then the bare data.

For example, here is a thread where X talkes about the format: [http://www.lucasforums.com/showthread.php?t=152418](http://www.lucasforums.com/showthread.php?t=152418)

Here is his WiKi entry: [Bone TTARCH](http://wiki.xentax.com/index.php?title=Bone TTARCH)

It is good the link to the forum is on that page, but the post might be moved/removed from that forum, having it in the wiki would make sure it'd be preserved.


Just my two cents 


Update:

Collecting more file formats or file detection algorithms would also be a nice addition, since this could help in discovering the layout of archives by being able to detect the unencrypted/uncompressed files within.
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-10-12T17:21:53+00:00
- Post Title: Adding more to the WiKi

> Reply from NKCSS
>
> Would it be possible to restucture the WiKi a bit to be even more usefull?

It would be nice if you could add 2 type of entries

* Game Archives
* Game Files Formats

The game files (.aud files for example) occasionaly get reused throughout different games, and therefore might have the right to be distinctly marked.
Actually, the entire wiki is being recast as a general "Game File Format" repository. To this end, Mr.Mouse even renamed the front page (from Main Page to Game File Format Central)!

> A nother thing is that within these Game File Formats, a link to which games they are used in would be nice.
Another part of the current wiki revision is that every format page is getting a list of the games known to use that format (in fact, all pages are being edited to use the same layout). More information can be found on [Help:Adding a format](http://wiki.xentax.com/index.php?title=Help:Adding a format) and [the Manual of Style](http://wiki.xentax.com/index.php?title=XW:MOS).

> If small variations to the format occur from game to game, it might be a good idea to have this information in seperate sections in the same wiki page. If formats differ to much, seperate pages would be better.
This is something that I was sure would come up eventually. Since most file formats (that I know of) which change slightly between games or over time have some sort of version field, the current practice is to identify different currently known versions and what format changes they respond to, and list them appropriately on the format page (I'll have to find an example for you).

> Besides the flow based details that i see on most pages, it might be usefull to add a bit more data, or even a walk thrue of the file.
>
> 
>
> Take a look at this file for an idea about what i am talking about: http://en.wikipedia.org/wiki/Image:Mp3filestructure.jpg
>
> 
>
> Also, don't be afraid to post a bit that is more then the bare data.
While I may not have previously vocalized it, it's always been my policy with the wiki (and possibly Mr.Mouse's and Captain's, too, though I certainly don't speak for them) that anyone adding or editing a format page on the wiki is free to add as little or as much information on the format as they wish, within reason.

> For example, here is a thread where X talkes about the format: http://www.lucasforums.com/showthread.php?t=152418
>
> 
>
> Here is his WiKi entry: Bone TTARCH
>
> 
>
> It is good the link to the forum is on that page, but the post might be moved/removed from that forum, having it in the wiki would make sure it'd be preserved.
That's an interesting idea. However, before it could be implemented, a proper system would have to be devised (which you are more than welcome to work on, if you wish  ). For instance, most threads discussing file formats on other forums will stretch for several pages, so it would be impractical to just copy and paste the text onto the format page - both for time spent and the resultant length of the page. Furthermore, we would need to figure out a reliable system for giving credit to the members that posted in the thread originally. This is a bigger problem than it first appears, since the same member name may be used by different people across different forums, and some forums allow guests to post. Further discussion on this topic would be necessary before any work towards it could be completed.


> Just my two cents
Hey, you're always welcome to contribute your two cents... I've been working off of mostly my own up to now, and they hardly come close to covering all the work...  


> Update:
>
> 
>
> Collecting more file formats or file detection algorithms would also be a nice addition, since this could help in discovering the layout of archives by being able to detect the unencrypted/uncompressed files within.
Additional file formats are a long-term goal of the wiki. My personal vision for it is to eventually document every game-related format that is documented anywhere else on the internet. And are you talking about some sort of program that could examine unknown files and return a (tenetative) format?
## Post #3
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-12T17:38:13+00:00
- Post Title: Adding more to the WiKi

> Reply from Dinoguy1000
>
> 
Actually, the entire wiki is being recast as a general "Game File Format" repository. To this end, Mr.Mouse even renamed the front page (from Main Page to Game File Format Central)!

Ok, sorry, this wasn't cleare to me by looking at a few entries, maybe I just saw the few entries that wern't up to par.

> Reply from Dinoguy1000
>
> 
Another part of the current wiki revision is that every format page is getting a list of the games known to use that format (in fact, all pages are being edited to use the same layout). More information can be found on Help:Adding a format and the Manual of Style.

Same story here, most of the entries i checked had part of the game name in the format definition but no listing of games at the bottom as you would expect

> Reply from Dinoguy1000
>
> 
This is something that I was sure would come up eventually. Since most file formats (that I know of) which change slightly between games or over time have some sort of version field, the current practice is to identify different currently known versions and what format changes they respond to, and list them appropriately on the format page (I'll have to find an example for you).

Great  I just think that it might be a case of having to remember to much things to add, without having the information you need on the screen at that time. It might be usefull to cook up a front end that generates a complete entry, ready for you to cut and paste, with dropdownlists to existing formats, games, etc. If you'd want, I could take a look at it in my spare time if you run a MS SQL server (.net programmer), I could create a webservice to safely extract the required data from the database which in turn could be used to feed a simple windows application that allows easy posting/maintaining of existing and new entries in the WiKi.

> Reply from Dinoguy1000
>
> 
While I may not have previously vocalized it, it's always been my policy with the wiki (and possibly Mr.Mouse's and Captain's, too, though I certainly don't speak for them) that anyone adding or editing a format page on the wiki is free to add as little or as much information on the format as they wish, within reason.

Good to know! Maybe worth adding to the help page.

> Reply from Dinoguy1000
>
> 
That's an interesting idea. However, before it could be implemented, a proper system would have to be devised (which you are more than welcome to work on, if you wish  ). For instance, most threads discussing file formats on other forums will stretch for several pages, so it would be impractical to just copy and paste the text onto the format page - both for time spent and the resultant length of the page. Furthermore, we would need to figure out a reliable system for giving credit to the members that posted in the thread originally. this is abigger problem than it first appears, since the same member name may be used by different people across different forums, and some forums allow guests to post. Further discussion on this topic would be necessary before any work towards it could be completed.

I didn't meen a exact copy of the entire thread, just the nitty gritty that is relevant. It was more of a addon to the previous question, but would be cool in the end 

> Reply from Dinoguy1000
>
> 
Hey, you're always welcome to contribute your two cents... I've been working off of mostly my own up to now, and they hardly come close to covering all the work...

Always glad to help, I love challenges and have had a lot of fun so far with the .bba archives, wouldn't mind helping out where I can.

> Reply from Dinoguy1000
>
> 
Additional file formats are a long-term goal of the wiki. My personal vision for it is to eventually document every game-related format that is documented anywhere else on the internet. And are you talking about some sort of program that could examine unknown files and return a (tenetative) format?

Great idea, would love that. The program thing is correct, removing or tagging known parts of the file could help examining the rest of the structure, less data to check out is always good
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-10-12T23:22:44+00:00
- Post Title: Adding more to the WiKi

> Reply from NKCSS
>
> Ok, sorry, this wasn't cleare to me by looking at a few entries, maybe I just saw the few entries that wern't up to par.
Heh, believe me, most of the wiki isn't up to par... I don't have as much time (or commitment  ) as I'd like to.

> Reply from NKCSS
>
> 
Same story here, most of the entries i checked had part of the game name in the format definition but no listing of games at the bottom as you would expect
Once again, that's because the majority of the wiki hasn't been updated yet.  

> Reply from NKCSS
>
> Great  I just think that it might be a case of having to remember to much things to add, without having the information you need on the screen at that time. It might be usefull to cook up a front end that generates a complete entry, ready for you to cut and paste, with dropdownlists to existing formats, games, etc. If you'd want, I could take a look at it in my spare time if you run a MS SQL server (.net programmer), I could create a webservice to safely extract the required data from the database which in turn could be used to feed a simple windows application that allows easy posting/maintaining of existing and new entries in the WiKi.
Hmm... I've actually had some (limited) talks with Mr.Mouse concerning parts of that. There's a lot of stuff that could be done with his BMS extension to the wiki, when he finally gets the time to have another look at it...  As for adding/updating entries on the wiki, I actually put in a request on Wikipedia a (long) while ago for a bot, but nothing ever came of it. If you'd like to try your hand at programming a client-side bot for the wiki, I could give you a couple of links that would (hopefully) help you.

> Reply from NKCSS
>
> Good to know! Maybe worth adding to the help page.
I'm pretty sure it'll get added eventually...

> Reply from NKCSS
>
> I didn't meen a exact copy of the entire thread, just the nitty gritty that is relevant. It was more of a addon to the previous question, but would be cool in the end
Hmm... well, I'd say the current system does a decent job of getting the 'nitty-gritty' as is, but suggestions are certainly welcome!  

> Reply from NKCSS
>
> Always glad to help, I love challenges and have had a lot of fun so far with the .bba archives, wouldn't mind helping out where I can.
I can definitely use all the help I can get, feel free to pitch in wherever you feel like.

> Reply from NKCSS
>
> Great idea, would love that. The program thing is correct, removing or tagging known parts of the file could help examining the rest of the structure, less data to check out is always good
There has been some discussion on that as well, if you think you can write a program to do that (however well), I'd be very interested to see what you can accomplish.
