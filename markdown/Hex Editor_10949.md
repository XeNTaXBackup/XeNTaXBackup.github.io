## Post #1
- Username: connortg12
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Nov 10, 2013 9:19 pm
- Post datetime: 2013-11-10T14:45:45+00:00
- Post Title: Hex Editor

Hi, I'm editing a file with HxD. But I need to insert word. When I added, the file is corrupted. Please help me.

[http://www.mediafire.com/download/rtc5s ... xtract.dat](http://www.mediafire.com/download/rtc5sirp6xqw8mj/code_post_gfx-extract.dat)
## Post #2
- Username: connortg12
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Nov 10, 2013 9:19 pm
- Post datetime: 2013-11-12T13:33:53+00:00
- Post Title: Hex Editor

Anyone?
## Post #3
- Username: GimmyBreaker
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Jul 06, 2012 12:24 am
- Post datetime: 2013-11-13T09:32:42+00:00
- Post Title: Hex Editor

Pointer/Pointers? Of the file size?
Game doesn't have any tools? If not, you will probably have to calculate new pointers and check coding.
## Post #4
- Username: connortg12
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Nov 10, 2013 9:19 pm
- Post datetime: 2013-11-13T15:12:22+00:00
- Post Title: Hex Editor

I couldn't find any tools, help me
## Post #5
- Username: GimmyBreaker
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Jul 06, 2012 12:24 am
- Post datetime: 2013-11-13T19:54:47+00:00
- Post Title: Hex Editor

What is a name of the game?
I can see that strings are between (00) FF FF FF FF FF FF FF FF 54 75 72 74 6C 65 20 50 6F 77 65 72 (00).
Probably size pointer first four bytes: 9C 99 26 00 will be 2529692 so difference is 43 from real size.
What do you want exactly to do? Insert what and where? Replace what and where?

Microsoft (R) HLSL Shader Compiler. Interesting.
## Post #6
- Username: connortg12
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Nov 10, 2013 9:19 pm
- Post datetime: 2013-11-13T21:56:03+00:00
- Post Title: Hex Editor

Game Call of Duty Modern Warfare 3. I extracted the FF file, and .dat as output. But how do I edit?
## Post #7
- Username: GimmyBreaker
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Jul 06, 2012 12:24 am
- Post datetime: 2013-11-13T22:53:23+00:00
- Post Title: Hex Editor

I wrote you in previous post, first four bytes will probably be a size pointer, you need to calculate new pointer. It's Little Endian, save changes, check new size of file, subtract 43, and write from right to left your result in file of course in hexadecimal.

If there are no tools, you will probably have to write your own. Editing in hex editor is suicide.
And no, I will not do this for free if you are not from Polish community fan translators.
If therere are no documentary of files for this game, I can only give you advices.
If it's only one file, I can check yours in free time, and try to repair your mistakes. But normal file, within reason, not with Gigabytes of data.
