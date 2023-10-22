## Post #1
- Username: Digitkel
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 12, 2010 5:01 am
- Post datetime: 2010-10-02T22:36:23+00:00
- Post Title: ollydbg help

Sorry it this is in the wrong section.

Could I get a tutorial of how to open a win32 console app in Ollydbg and get it to accept parameters?

Specifically I need to know how to give it input and output filenames for the program to do anything, so I can debug it.

It's probably very easy, but I can't figure it out. And can't find any examples of anyone doing this.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-10-03T13:20:25+00:00
- Post Title: ollydbg help

"File->Open" and select the executable to debug
"File->Set New Arguments" and put the command-line arguments in the second text entry
CTRL+F2 for restarting the process with the new arguments
## Post #3
- Username: Digitkel
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 12, 2010 5:01 am
- Post datetime: 2010-10-03T13:43:58+00:00
- Post Title: ollydbg help

Thank you aluigi that does work. Like I said simple.  

The older versions are missing the "File->Set New Arguments" so anyone else having trouble get ollydbg2.0 or newer.
