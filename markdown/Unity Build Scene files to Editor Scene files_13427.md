## Post #1
- Username: IronArthur
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 05, 2015 9:25 pm
- Post datetime: 2015-10-16T13:54:44+00:00
- Post Title: Unity Build Scene files to Editor Scene files?

Hi,

I´m trying to reopen an scene file from Unity (Heroes of Normandie) on the Editor.

When you try to reopen the scene file the Editor crashes and the log is like this:

> The file 'C:/***/Assets/unity0POST2.unity' - 'Assets/unity0POST2.unity' is corrupted! Remove it and launch unity again!
>
> [Position out of bounds! 4112 > 4108]

I´ve try to resave the file after opening it with disunity to reinsert the classes tree but i think the problem is in data section.

Anyone know whats the structure of the data section? is there a tool to reconvert them to an usable format?
## Post #2
- Username: Loomy
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Sep 12, 2015 9:16 am
- Post datetime: 2015-11-24T20:03:44+00:00
- Post Title: Unity Build Scene files to Editor Scene files?

ive been looking into this too , in a sense , moreso restoring original scenes / levels / editor in general from compiled, and what little i do know, if u do find a .unity file, it is more likely a type of bundle or unityraw file, and not necessarily in a useable state by editor, or in another such case, a completeyl custom encrypted binary format of somesort written by devs of a particular game,and just named .unity for whatever reason.  mostof what you would find in a scene or level, is found byb means of dissasmbly or reversing of the actual c# code - reflexil, redgates tools, or other similar tool.  the one and only tool coming close to what we need would be AssetsBundleExtractor - play with it and see for urself it can recover a great deal of info, not necessarily usable but gives an idea.  noone has really been able to repack original prefabs, and extract animation data and so on, though, its not far off, i would lookto abe tool, maybe guy will one day share the source for it.

i couldbe way off base, but u should share more technical info or the actual file in question, maybe others can have a look or a try.
