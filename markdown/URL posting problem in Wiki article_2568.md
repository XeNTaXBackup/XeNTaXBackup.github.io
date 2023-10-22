## Post #1
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-04-04T20:57:52+00:00
- Post Title: URL posting problem in Wiki article

Hi all (and especially the server and Wiki gods),

I justed added a new format description [here](http://wiki.xentax.com/index.php/The_Longest_Journey_TM). While adding URLs to the "Supported by Programs" section, I encountered a strange problem. Whenever this code --

```
* [http://www.geo!cities.com/rescosoftware/ TLJ Viewer] (works only with the original 4 CD release)
```

-- was in the article's source (between the two other links, to be exact), neither previewing nor committing the article worked. Instead, the server responded with a "500 internal server error". I tried various combinations (with or without comment, different link title, different URL -- I even typed the URL manually instead of copying it from the browser's address bar to prevent the possible inclusion of unwanted characters) and it seems to me that the server dislikes any URL pointing to geocities.com. 

Note: Actually, even the forum software does not let me post the link above. After having inserted the "!" in the obvious place it works flawlessly, though.

So ... I admit I am a bit confused. I suspect this to have a good reason, but which one?
## Post #2
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2007-04-05T09:01:27+00:00
- Post Title: URL posting problem in Wiki article

This is weird. It does seem to happen only with geocities.com urls. But we've not made any changes to the software to block that kind of stuff. What's even stranger is that both phpbb and mediawiki have the same behavior, which makes me suspect it has something to do with apache or mysql.

I'll look into the error logs tonight. I can't reach them from here.
## Post #3
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-04-05T21:57:08+00:00
- Post Title: URL posting problem in Wiki article

Good to hear that I am not only one experiencing this -- I really started doubting myself. 

Thanks!
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-04-06T20:27:27+00:00
- Post Title: URL posting problem in Wiki article

That is a very weird problem, indeed... We'll just have to wait for Captain to look into it, then.
## Post #5
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2007-04-07T12:38:16+00:00
- Post Title: URL posting problem in Wiki article

Looks like it's an overzealous apache security module. I've contacted the webhost. Stay tuned.
## Post #6
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2007-04-07T12:59:40+00:00
- Post Title: URL posting problem in Wiki article

[http://www.geocities.com/](http://www.geocities.com/)

They fixed it.
## Post #7
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-04-07T16:13:49+00:00
- Post Title: URL posting problem in Wiki article

Works flawlessly now. Thanks, Captain!
