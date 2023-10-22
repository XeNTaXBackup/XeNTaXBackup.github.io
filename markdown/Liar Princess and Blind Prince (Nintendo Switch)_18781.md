## Post #1
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2018-09-07T22:53:04+00:00
- Post Title: Liar Princess and Blind Prince (Nintendo Switch)

Hey Guys, 

currently I'm looking for Games that didn't got a localization.
I just found the Game "Liar Princess and Blind Prince" which is a Korean-only Game.





I've looked into the Gamefiles and I believe I've found the Files that needs to be changed:

File Location: romfs/database/




The Korean Text is readable when you open the files in Notepad++ and Convert it to UTF-8





Editing them in Hexeditor or Notepad++ would break stuff I believe, because the pointers will be wrong.

Would you help me with an Editor for these files (or a Tool that convert this file to editable textfiles and to rebuild them?
The Format seems to be very simple.


I've uploaded the files and attached them to this post
[database.zip](https://xentaxbackup.github.io/file/14821_database.zip)
