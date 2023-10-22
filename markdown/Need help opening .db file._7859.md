## Post #1
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2011-12-14T10:46:15+00:00
- Post Title: Need help opening .db file.

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-12-23T20:15:32+00:00
- Post Title: Need help opening .db file.

Have you opened the file in a text or hex editor to confirm it's compressed? Your program could just be extracting extraneous data found in the file. .db is pretty generic, there's a lot of data types stored in them, so you could be extracting text and integers or the text you could be getting might not even be meant to be text.

Try opening it up raw in something like notepad or a hex editor. If you can't see any intelligible text it may not be compressed at all and in fact it just doesn't contain text.
