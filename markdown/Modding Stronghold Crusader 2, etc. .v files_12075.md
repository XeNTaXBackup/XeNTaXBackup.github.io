## Post #1
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2014-10-09T12:44:42+00:00
- Post Title: Modding Stronghold Crusader 2, etc. .v files

Modding the new Stronghold Crusader 2 release (and other Stronghold games) which use the .v pack file format.

Just some research info to file away somewhere.

Yes, I know someone outside of this group has already created a tool a couple of years ago to unpack/pack .v files.

To unpack assets.v, en.v, etc.:

1. XOR each byte of file with x55
2. Change file extension of result to .zip
3. Unzip using normal methods
4. You're done.

To repack file structure (example: assets.v):

1. Zip up entire file structure (don't zip the \assets folder itself, but zip the CONTENTS of the assets folder).
2. XOR each byte of zip with x55
3. Rename zip to assets.v
4. You're done.

-timetraveller
## Post #2
- Username: Parsenry
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 16, 2015 12:34 pm
- Post datetime: 2015-12-16T04:49:57+00:00
- Post Title: Modding Stronghold Crusader 2, etc. .v files

Help me understand about your data or not.
## Post #3
- Username: Crobit
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 01, 2017 11:10 pm
- Post datetime: 2017-02-06T22:18:07+00:00
- Post Title: Modding Stronghold Crusader 2, etc. .v files

Here it is what you wanted: [http://www.strongholdnation.co.uk/artic ... ld-3-files](http://www.strongholdnation.co.uk/article/195-unarchiving-stronghold-3-files)
