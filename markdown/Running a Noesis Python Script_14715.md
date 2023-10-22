## Post #1
- Username: IAmTheClayman
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Aug 01, 2016 8:46 am
- Post datetime: 2016-08-02T19:10:17+00:00
- Post Title: Running a Noesis Python Script

I recognize this is a very simple question but it's one I can't solve, possibly because I'm trying to wrap my head around too many things at once and possibly because my Pythong scripts actually don't show up in the file explorer when I'm running Noesis. How do you actually run one of these Python scripts?  Do you just select it from inside Noesis or do you have to run it from the Python IDE on the command line?
## Post #2
- Username: Mattzocrazy
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-08-23T01:21:20+00:00
- Post Title: Running a Noesis Python Script

> Reply from IAmTheClayman
>
> I recognize this is a very simple question but it's one I can't solve, possibly because I'm trying to wrap my head around too many things at once and possibly because my Pythong scripts actually don't show up in the file explorer when I'm running Noesis. How do you actually run one of these Python scripts?  Do you just select it from inside Noesis or do you have to run it from the Python IDE on the command line?

You must place the python plugins in the folder: Noesis/Plugins/Python. Noesis automatically loads all C++/Python modules upon initialisation. Noesis executes plugins based on file extensions. If you open a file with an extension that matches a specific module all code will be executed. You do not manually select which Python scripts you wish to run.

Also moving this thread as it's not a tutorial.

Cheers.
