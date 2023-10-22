## Post #1
- Username: Mikeee
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Apr 27, 2017 8:12 am
- Post datetime: 2017-10-02T20:56:24+00:00
- Post Title: Encrypted ogg in android/ios game

Here's a zip with a few example oggs: 
[https://mega.nz/#!39tUyKzC!2j3WZCAKPwJp ... yykfCuZgvM](https://mega.nz/#!39tUyKzC!2j3WZCAKPwJppyDYKiFBf40lkKHWaa9OPyykfCuZgvM)

My research:

The first unsigned int seems to be related to the data size. Although, it is a bit less than the filesize and vary slightly from file to file.

4h to 17h is always for every file:
C5 8B D4 F1 C5 83 D4 F1 6A 23 C6 4B A8 F4 F0 CB 01 DC C6 96
Å‹ÔñÅƒÔñj#ÆK¨ôðËÜÆ–

libdeal.so is the library of the game that deals with these encrypted Oggs/vorbis files, its included in the zip if someone can possibly find the encryption key from it.

Can anyone figure anything else out?
