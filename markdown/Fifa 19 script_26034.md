## Post #1
- Username: TheSeeker25
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jan 12, 2021 11:20 am
- Post datetime: 2022-11-25T12:35:16+00:00
- Post Title: Fifa 19 script

I'm searching for a script to extract fbmod from fifa 19..
I tried to use current scripts for fifa 18 but nothing works just give me errors.
Here is a sample to extract 
[https://www.mediafire.com/file/8l6vkf5t ... 3.rar/file](https://www.mediafire.com/file/8l6vkf5tlomd3j1/National+Teams+Kits+22-23.rar/file)
## Post #2
- Username: TheSeeker25
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-11-26T10:41:03+00:00
- Post Title: Fifa 19 script

Luckily, Frosty Toolsuite is now open source, so if you have enough time and knowledge,
you could debug the source code and try to write your own parser [https://github.com/CadeEvs/FrostyToolsuite](https://github.com/CadeEvs/FrostyToolsuite)

And here's my attempt to document file format without debugging
[http://wiki.xentax.com/index.php/Frosty_Toolsuite_FBMOD](http://wiki.xentax.com/index.php/Frosty_Toolsuite_FBMOD)

(I don't even have Fifa installed, so I can't help you more)
## Post #3
- Username: TheSeeker25
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jan 12, 2021 11:20 am
- Post datetime: 2022-11-26T16:38:35+00:00
- Post Title: Fifa 19 script

Can you explain more please ? 
No not that much 
I'm just at the beginning, still learning this stuff
Thanks for your help
## Post #4
- Username: TheSeeker25
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-11-26T17:54:22+00:00
- Post Title: Fifa 19 script

Sure, I can explain.  

So the Frosty Toolsuite is a software that is capable of reading and writing FBMOD files.
This is open source software now. It means that you can just go to github page, download source code and compile it yourself.
Beside compiling, you are able to debug this source code if you have Visual Studio installed.
Check this link for more info [https://www.google.com/search?client=fi ... ual+studio](https://www.google.com/search?client=firefox-b-d&q=how+to+debug+program+in+visual+studio)

To be more specific, you need those things:
- Visual Studio installed on your PC
- Fifa 19 installed on your PC
- Source code downloaded from Github

When you have all of these, you can open SLN project file in Visual Studio and compile the tool in debug mode.
Then you can set some breakpoints to see how the FBMOD file is parsed.
More info here [https://www.google.com/search?client=fi ... ual+studio](https://www.google.com/search?client=firefox-b-d&q=how+to+set+breakpoints+in+visual+studio)


Then it is up to you how will you proceed. The easiest way is to choose programming thst you like and
rewrite the parser for your needs. You need some knowledge about file formats to do that.
Here is more info [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)
## Post #5
- Username: TheSeeker25
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jan 12, 2021 11:20 am
- Post datetime: 2022-11-26T22:05:00+00:00
- Post Title: Fifa 19 script

Thank you for the explanation i will try and inform you 
One more question what script did you use to extract cause i didn't see difference between what i have and you wrote to me and explain if I'm wrong 
Secondly is there a way to change the script to work 
I have the frosty and fifa 19 but not the VS and the VS becoming huge after installing
