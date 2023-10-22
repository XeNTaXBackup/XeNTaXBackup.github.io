## Post #1
- Username: Catonx18
- Rank: beginner
- Number of posts: 33
- Joined date: Wed Oct 08, 2014 7:26 am
- Post datetime: 2017-03-22T05:56:24+00:00
- Post Title: How to open froggy castle data.stf?

[https://drive.google.com/open?id=0B4BWT ... TRQMXdUX0k](https://drive.google.com/open?id=0B4BWTzCXfYtdOUJlLTRQMXdUX0k)
## Post #2
- Username: devmode
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Jun 07, 2016 2:51 am
- Post datetime: 2017-03-22T13:34:56+00:00
- Post Title: How to open froggy castle data.stf?

Script for QuickBMS:

```

get unknown_1 long
get unknown_2 long
get unknown_3 long # Count of sub-folders?

get fileCount long

get dataBlockSize long

get infoBlockSize long

for I = 1 to fileCount
get ff byte
get nameLen short
GetDString fName nameLen
get isFolder byte

if isFolder == 1
math I - 1
get objCount long
else 
get fSize long
get fOffset long
math fOffset + 9  
log fName fOffset fSize
endif

next I
```
## Post #3
- Username: Catonx18
- Rank: beginner
- Number of posts: 33
- Joined date: Wed Oct 08, 2014 7:26 am
- Post datetime: 2017-06-04T23:49:26+00:00
- Post Title: How to open froggy castle data.stf?

Thanks
## Post #4
- Username: Catonx18
- Rank: beginner
- Number of posts: 33
- Joined date: Wed Oct 08, 2014 7:26 am
- Post datetime: 2018-02-08T23:36:55+00:00
- Post Title: How to open froggy castle data.stf?

How do I repack the archive?
I want to do game modding on this game.
## Post #5
- Username: Catonx18
- Rank: beginner
- Number of posts: 33
- Joined date: Wed Oct 08, 2014 7:26 am
- Post datetime: 2022-03-22T13:33:24+00:00
- Post Title: How to open froggy castle data.stf?

Could you post a new script so you can repack the data without the game crashing? thanks.
## Post #6
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2023-10-09T17:19:22+00:00
- Post Title: How to open froggy castle data.stf?

The quickbms script that devmode did allows repacking.
Just make sure your edited files have the same size as the original. A trick you can do is just select what you want to edit.
I've managed to translate this game thanks to that script.

Cheers!
