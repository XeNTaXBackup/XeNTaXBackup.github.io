## Post #1
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2012-03-26T21:21:18+00:00
- Post Title: reverse Bob Jenkins hash to string

I have an archive which is using Bob Jenkins hash's instead of file names, is there a way to reverse the hash's in order to get the original strings?
## Post #2
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-31T08:56:26+00:00
- Post Title: reverse Bob Jenkins hash to string

Nope. Even if you could spare the time to try bruteforcing strings to match the hash, Jenkins hashing can result in plenty of false positives, so a match doesn't make it certain that you really have the right original name.
