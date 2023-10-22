## Post #1
- Username: Lordryu
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Apr 22, 2016 6:11 am
- Post datetime: 2016-05-20T21:36:06+00:00
- Post Title: "Noesis has crashed"

For some reason, Noesis can only run for a couple seconds before it immediately crashes and closes.

HELP.
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-08-03T13:42:20+00:00
- Post Title: "Noesis has crashed"

> Reply from sankalppatil
>
> Noesis appears to have difficulty reading information for models that do not exist as a single, self-contained file. This means character models for NPCs work just fine, but models for player characters don't work. Or at least, I haven't figured out how to get them to work. Maybe I'm just not using the program correctly. I dunno. I'll have to experiment with this a little more.
Nope, you can read from multiple streams if mesh information is stored across multiple files. See NoeBitStream.

Edit: Take a look at my Rise of the Tomb Raider mesh importer. I load skeletons from a different file. Should be enough to help you figure out how to create multiple file streams.
## Post #3
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-08-03T20:43:16+00:00
- Post Title: "Noesis has crashed"

Yeah, you can read multiple files, and you can even generate multiple models at once using multiple geometry contexts if you want. Not that this has anything at all to do with Noesis crashing.

99% of Noesis startup crashes come from botched ATi OpenGL implementation updates, so barring doing something like providing more useful information about the crash and your system, you can always try reverting any recent driver updates.
