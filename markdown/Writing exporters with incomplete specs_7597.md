## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-10-30T15:25:31+00:00
- Post Title: Writing exporters with incomplete specs

I'm sure most of the time when reversing a model format, there's always stuff that just doesn't seem obvious what it's doing. Especially for those that aren't too experienced or know too much about 3D, 3D engines, and whatnot.

So for example you've imported a model into some software, made your changes, and now want to export it back into the game. But your importer probably only cared about the data required to build the model and animate it, so there's a lot of data you have potentially ignored from the original file that the engine will use (you may have ignored it because you didn't know what it was for anyways and it didn't seem to make a difference)

What kind of techniques are there for writing exporters to a format that the game will read and use?

The first time I wrote such an exporter, I simply took the original file, the modified file, a new empty file, and then read them according to the incomplete format I drafted out. Anything that I didn't know, I just copied to the new file. Anything that I wanted to modify, I went to my modified file and wrote out the appropriate values. In the end, I basically merged the two files and hoped for the best. Well, it didn't work as well as I hoped (there were some results, but the game still crashed), but that got me curious as to how people actually write these exporters.
