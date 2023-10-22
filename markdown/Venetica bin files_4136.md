## Post #1
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2010-02-13T10:03:46+00:00
- Post Title: Venetica bin files

Hi,

This bin files contains an lua script. 
I don't know how to extract it? But i suppose the game can load the extracted lua scripts.

[http://www.sendspace.com/file/mc6rw6](http://www.sendspace.com/file/mc6rw6)
[http://www.sendspace.com/file/ig0hfp](http://www.sendspace.com/file/ig0hfp)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-13T10:38:36+00:00
- Post Title: Venetica bin files

copied from an old post of mine:
"it's a precompiled lua script so you need a decompiler to read it (well it's not like the original lua file but it's better than nothing):
[http://lua-users.org/wiki/LuaTools](http://lua-users.org/wiki/LuaTools)

section "Assembler / Disassembler / Bytecodes"
I have tried with this luadec and works, while the others listed there had some problems"
## Post #3
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2010-04-29T20:19:51+00:00
- Post Title: Venetica bin files

aluigi,
I assume you are referring to LuaDec 5.1.

Venetica uses a newer build of lua (5.1.4?), thus LuaDec 5.1 cannot decompile it properly.
Just check the output and search for "confused about"...

PS:
VENETICA\media\levels.dat, shared.dat and shared_preview.dat are ZIP files containing a bunch of BIN files as well - those are not LUA files.
