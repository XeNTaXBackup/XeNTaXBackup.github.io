## Post #1
- Username: ricky12
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 24, 2014 6:47 pm
- Post datetime: 2015-07-22T14:56:37+00:00
- Post Title: nevermind


## Post #2
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2015-07-23T00:28:19+00:00
- Post Title: nevermind

Try Unluac [http://sourceforge.net/projects/unluac/](http://sourceforge.net/projects/unluac/) + luac.exe

Decompiler.bat
ren OpeningCredits.lua OpeningCredits.luac
java -jar unluac.jar OpeningCredits.luac > OpeningCredits.lua

Compiler.bat
luac.exe OpeningCredits.lua
ren luac.out NEW_OpeningCredits.luac
ren NEW_OpeningCredits.luac NEW_OpeningCredits.lua
