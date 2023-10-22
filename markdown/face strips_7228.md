## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-23T22:32:14+00:00
- Post Title: face strips

Are there some common patterns that is used for this type of face index storage? 

I've only seen one format (project diva PS3) where it kept grabbing new values until all three indices were unique, and then append them to the list of faces. I guess that's what a tri-strip is?
## Post #2
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-23T23:53:44+00:00
- Post Title: face strips

tri strip is just his
imagine a square
it has 4 points
in tri list its listed
1 2 3
2 3 4
in tri strip its just
1 2 3 4
you just reuse the last 2 indecies.
