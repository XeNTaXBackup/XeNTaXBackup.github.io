## Post #1
- Username: EldritchDecross
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 27, 2010 10:39 am
- Post datetime: 2010-08-23T11:45:05+00:00
- Post Title: I need a batch file quickly.

Hello fine folks. I was wondering if someone could whip up a quick batch file for me using the following program:
[http://www.sendspace.com/file/9gstjz](http://www.sendspace.com/file/9gstjz)
I need this program to process all 'PCK' files in the directory it lies in, and extract them to 'C:\PCK'.
I would do this myself and I know it's supposed to be relatively easy, but I'm pretty much brainless when it comes to programming and I can't access the internet very often to learn.

Thanks for any help!
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-08-23T13:19:43+00:00
- Post Title: I need a batch file quickly.

```
FOR %%i IN (*.pck) DO tool...
```

%%i gets filled with the current pck filename. Just replace tool... with the correct commandline for the program.
## Post #3
- Username: EldritchDecross
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 27, 2010 10:39 am
- Post datetime: 2010-08-23T15:31:29+00:00
- Post Title: I need a batch file quickly.

Oh, thanks for your reply. However this doesn't seem to work.

What I need is essentially the equivalent of this:

```
ff12div.exe *.pck C:\PCK
```

 The only problem is this program doesn't accept the wildcard.

Edit: Never mind, got it to work, thanks for your help!
