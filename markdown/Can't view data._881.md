## Post #1
- Username: ZippyV
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-25T16:49:35+00:00
- Post Title: Can't view data.

I loaded music.big from c&c generals into MultiEx. The autopreview works fine (but the preview doesn't play the full song).
So when I double click on a song, Windows Media Player opens and gives a file not found error. For some reason the file path was cut down to "C:\Program"
When I look in the Debug log I can see the full path: "18:41:50 - MAIN: ShowSelFileTemp of C:\Program Files\MultiEx Commander\data\CHI_07.mp3 Result: 0"

Any idea to fix this problem/bug?
It used to work fine in previous versions.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-27T07:54:45+00:00
- Post Title: Can't view data.

This is weird and I will take a look at it. To my knowledge this all works fine in my book, but I don't have the chance to check every supported format each time a new release comes out, bugs may slip in. 

The autopreview just plays for a couple of seconds, never continously, although you can set the number of seconds in the Options menu. 

The entry in the log file you posted just shows that extraction went without problems. MultiEx Commander then passes the path to the temporary file to an external program  (Result : 0 , no errors). It does not check whether the external program was succesful (it couldn't care less  ).    

Anyway. this bug is on my to-do list.
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-09-01T20:39:11+00:00
- Post Title: Can't view data.

I fixed it. It will be gone in the next release.
## Post #4
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-09-05T21:54:52+00:00
- Post Title: Can't view data.

Thank you very much!
