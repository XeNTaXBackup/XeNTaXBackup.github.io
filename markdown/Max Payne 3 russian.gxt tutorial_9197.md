## Post #1
- Username: uBAH
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 09, 2010 12:02 pm
- Post datetime: 2012-07-03T08:45:06+00:00
- Post Title: Max Payne 3 russian.gxt tutorial

Here is my tutorial on getting russian.gxt readable and editable with X GXT EDITOR by xmen [http://www.x-squares.com/TAG/i/14/How-t ... N-GXT.aspx](http://www.x-squares.com/TAG/i/14/How-to-Open-Max-Payne-3-RUSSIAN-GXT.aspx)
Read carefully ... surprise at the end
## Post #2
- Username: chipsman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Dec 20, 2010 5:15 am
- Post datetime: 2012-07-04T15:12:36+00:00
- Post Title: Max Payne 3 russian.gxt tutorial

The problems from this article are relevant only for GTA 4, because for cyrillic texts it use magic (idiotic) encoding (because the first versions of the game used one byte per char, this thing was changed to 2 bytes after patch, but encoding was the same), so you need to decode text for correctly viewing/reading. 

But in case of Max Payne 3 the manipulations, which are described in this article, have no sense because, the game use the most common UTF-8 encoding, so each char have size of 2 bytes. 

GTA 4 russian text files:

[https://dl.dropbox.com/u/1237757/share/ ... xt_001.png](https://dl.dropbox.com/u/1237757/share/07.2012/gxt_001.png)

Max Payne 3 russian text file: 

[https://dl.dropbox.com/u/1237757/share/ ... xt_002.png](https://dl.dropbox.com/u/1237757/share/07.2012/gxt_002.png)
## Post #3
- Username: uBAH
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 09, 2010 12:02 pm
- Post datetime: 2012-07-04T23:07:14+00:00
- Post Title: Max Payne 3 russian.gxt tutorial

Didn't get what you're saying ... but I can tell that GTA IV gxt has no such encoding at all ... it just uses other chars in characters table ... so there's no need for them to patch somehow ... just need correct charset which is from 8E to CD
## Post #4
- Username: chipsman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Dec 20, 2010 5:15 am
- Post datetime: 2012-07-06T08:17:07+00:00
- Post Title: Max Payne 3 russian.gxt tutorial

I just wanted to say that you don't need to do anything with MP3 text encoding, just edit text as UTF-8.
