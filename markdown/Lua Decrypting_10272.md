## Post #1
- Username: just2good
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Dec 01, 2011 3:04 am
- Post datetime: 2013-03-26T10:11:29+00:00
- Post Title: Lua Decrypting

Was wondering if anyone could help with decrypting a .lua for editing.

I tried using Chunkspy but it is unable to decrypt a 51 chunk file.

The lua is for a game called Warframe btw.

I attached the .lua below.
[LightFX.rar](https://xentaxbackup.github.io/file/6290_LightFX.rar)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-27T20:27:15+00:00
- Post Title: Lua Decrypting

This LUA not encrypted.. Just compiled in binary format. If you need decompile - ByteCode only.
## Post #3
- Username: just2good
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Dec 01, 2011 3:04 am
- Post datetime: 2013-03-28T13:18:07+00:00
- Post Title: Lua Decrypting

I tried decompiling using Luadec51 but I get file is not a valid luac file, tried renaming it to luac and nothing, tried using other versions including an updated and modified version by a new author and still nothing.


Can you clarify a bit on what you mean please?
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-28T18:15:37+00:00
- Post Title: Lua Decrypting

> Reply from just2good
>
> I tried decompiling using Luadec51 but I get file is not a valid luac file, tried renaming it to luac and nothing, tried using other versions including an updated and modified version by a new author and still nothing.

Can you clarify a bit on what you mean please?
LuaDec, in its current form, is not a complete decompiler. It does succeed in decompiling most of the Lua constructs, so it could be used as a tool to aid in retrieving lost sources.

The situations where LuaDec "get it wrong" are usually related to deciding whether a sequence of relational constructs including TEST operators are part of an assignment or an if construct. Also, the "single pass" nature of the symbolic interpreter fails at some corner cases where there simply is not enough information in the sequence of operator/jump pairs to identify what are the "then" and "else" addresses. This is an example of such a case: 

Original Code:

```
while x do
   if ((x==2) and y) or ((x==3) and 1) or 0
   then
      a = 1
   do break end
      a = 2
   else
      a = 3
   do break end
      a = 4
   end
   a = 5
end
```

ByteCode

```
2       [3]     JMP             0 16    ; to 19
3       [4]     EQ              0 1 250 ; - 2
4       [4]     JMP             0 2     ; to 7
5       [4]     TEST            2 2 1
6       [4]     JMP             0 5     ; to 12
7       [4]     EQ              0 1 251 ; - 3
8       [4]     JMP             0 3     ; to 12
9       [4]     LOADK           3 2     ; 1
10      [4]     TEST            3 3 1
11      [4]     JMP             0 0     ; to 12
12      [6]     LOADK           0 2     ; 1
13      [7]     JMP             0 7     ; to 21
14      [8]     LOADK           0 0     ; 2
15      [8]     JMP             0 3     ; to 19
16      [10]    LOADK           0 1     ; 3
17      [11]    JMP             0 3     ; to 21
18      [12]    LOADK           0 4     ; 4
19      [3]     TEST            1 1 1
20      [3]     JMP             0 -18   ; to 3
21      [14]    RETURN          0 1 0
```


You need learn LUA language first. Without knowledge you do nothing.

btw: LuaDec project discontinued.

More info [here](http://luadec.luaforge.net/)
## Post #5
- Username: just2good
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Dec 01, 2011 3:04 am
- Post datetime: 2013-03-28T18:43:25+00:00
- Post Title: Lua Decrypting

> Reply from Ekey
>
> just2good wrote:I tried decompiling using Luadec51 but I get file is not a valid luac file, tried renaming it to luac and nothing, tried using other versions including an updated and modified version by a new author and still nothing.

Can you clarify a bit on what you mean please?
LuaDec, in its current form, is not a complete decompiler. It does succeed in decompiling most of the Lua constructs, so it could be used as a tool to aid in retrieving lost sources.

The situations where LuaDec "get it wrong" are usually related to deciding whether a sequence of relational constructs including TEST operators are part of an assignment or an if construct. Also, the "single pass" nature of the symbolic interpreter fails at some corner cases where there simply is not enough information in the sequence of operator/jump pairs to identify what are the "then" and "else" addresses. This is an example of such a case: 

Original Code:
Code: Select alllocal a, x, y
while x do
   if ((x==2) and y) or ((x==3) and 1) or 0
   then
      a = 1
   do break end
      a = 2
   else
      a = 3
   do break end
      a = 4
   end
   a = 5
end
ByteCode
Code: Select all1       [2]     LOADNIL         0 2 0
2       [3]     JMP             0 16    ; to 19
3       [4]     EQ              0 1 250 ; - 2
4       [4]     JMP             0 2     ; to 7
5       [4]     TEST            2 2 1
6       [4]     JMP             0 5     ; to 12
7       [4]     EQ              0 1 251 ; - 3
8       [4]     JMP             0 3     ; to 12
9       [4]     LOADK           3 2     ; 1
10      [4]     TEST            3 3 1
11      [4]     JMP             0 0     ; to 12
12      [6]     LOADK           0 2     ; 1
13      [7]     JMP             0 7     ; to 21
14      [8]     LOADK           0 0     ; 2
15      [8]     JMP             0 3     ; to 19
16      [10]    LOADK           0 1     ; 3
17      [11]    JMP             0 3     ; to 21
18      [12]    LOADK           0 4     ; 4
19      [3]     TEST            1 1 1
20      [3]     JMP             0 -18   ; to 3
21      [14]    RETURN          0 1 0

You need learn LUA language first. Without knowledge you do nothing.

btw: LuaDec project discontinued.

More info here

Yeah I tried LuaDec51 as well as the one that was picked up by another person that updates his frequently.

Also I'll be completely honest, I do want to learn lua, it is definitely one of things I will eventually learn however I am a very lazy person and can't multilearn. (if thats even a word)
Currently trying to learn C++ and still only in the early stages.

I was wondering, only if you wouldn't mind, if you could make me a decompiler/compiler for this certain type of lua file as you seem very knowledgeable when it comes to these things. I would greatly appreciate it if you could! If not that is completely okay and I understand.

Thanks a bunch for the help btw! Nice knowing that there is a real pro when it comes to these things.
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-28T20:08:30+00:00
- Post Title: Lua Decrypting

Well i have 3 different dissasemblers for lua and dont work. Likely game used newest version LUA. LuaDec can't recognize opcodes from new version. Have to wait for an update to LuaDec with new instructions, opcodes ect.
If game used LuaJIT you can watch my old [video](http://www20.zippyshare.com/v/34753967/file.html) tutorial how decompile lua's (Example Target: Legend of Grimrock). Used method ByteCode <=> Compare.
## Post #7
- Username: just2good
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Dec 01, 2011 3:04 am
- Post datetime: 2013-03-28T21:35:40+00:00
- Post Title: Lua Decrypting

> Reply from Ekey
>
> Well i have 3 different dissasemblers for lua and dont work. Likely game used newest version LUA. LuaDec can't recognize opcodes from new version. Have to wait for an update to LuaDec with new instructions, opcodes ect.
If game used LuaJIT you can watch my old video tutorial how decompile lua's (Example Target: Legend of Grimrock). Used method ByteCode <=> Compare.
I did read something about a new version of lua or something released either yesterday or a few days before, I'll have to read that again if i could ever find it. Also your tutorial was one of the first things I found while searching and I compiled latest version of luajit to no avail. There is an updated luadec51 somewhere updated by someone else since the original creator stopped developing on it. I think its called luatool ill have to check when I get back from work.
