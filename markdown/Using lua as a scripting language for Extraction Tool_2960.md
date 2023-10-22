## Post #1
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-03-06T09:46:19+00:00
- Post Title: Using lua as a scripting language for Extraction Tool?

Still wondering if lua would be a good scripting language for a game archive extraction tool.
The engine could provide functions like GetByte(),GetInt(),GetString(),... (-> just like MultiEx does it) to get data from the archive file and something along the lines of AddFile(), AddFolder(),... (which the engine would use to create an intern tree which will then be displayed to the user, if the archive format doesn't support directories, there is only one root folder "/")

The advantage is that you have a powerful programming language for your needs. This makes it possible to also support encryption and compression.

What do you think?
## Post #2
- Username: SiENcE
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Jun 13, 2007 3:41 pm
- Post datetime: 2008-03-06T11:05:31+00:00
- Post Title: Using lua as a scripting language for Extraction Tool?

Lua is slow when using binary operation. Lua 5.1.3 speeds up some things but it's better todo this in cpp. Don't understand me wrong, lua is fast, but not for binary operations using large files.
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-03-06T11:14:37+00:00
- Post Title: Using lua as a scripting language for Extraction Tool?

What do you exactly mean? Passing data to lua via those Get* functions? Reading files directly in lua? Operations like bit shift and the like?
## Post #4
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2008-03-16T18:50:41+00:00
- Post Title: Using lua as a scripting language for Extraction Tool?

Na, doesn't sound like a good idea.  There is actually another idea on the drawing board.
## Post #5
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-03-16T22:00:26+00:00
- Post Title: Using lua as a scripting language for Extraction Tool?

> Reply from Rahly
>
> Na, doesn't sound like a good idea.  There is actually another idea on the drawing board.
btw this is no proposal for MultiEx, I wanna write my own little unpacking tool
## Post #6
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2009-04-23T17:49:58+00:00
- Post Title: Using lua as a scripting language for Extraction Tool?

> Reply from Rheini
>
> Still wondering if lua would be a good scripting language for a game archive extraction tool.
The engine could provide functions like GetByte(),GetInt(),GetString(),... (-> just like MultiEx does it) to get data from the archive file and something along the lines of AddFile(), AddFolder(),... (which the engine would use to create an intern tree which will then be displayed to the user, if the archive format doesn't support directories, there is only one root folder "/")

The advantage is that you have a powerful programming language for your needs. This makes it possible to also support encryption and compression.

What do you think?

Hi  I got same idea a few weeks ago, and now when I was listing code section I saw you thread 

Did you managed to make any scripting language for extracting files ? or tool that uses lua ? I'm thinking about making this tool too, with record support (struct) and other stuff...
## Post #7
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-04-23T18:36:47+00:00
- Post Title: Using lua as a scripting language for Extraction Tool?

Don't have much time, thus I didn't come far.
I started out by adding binary operators (<<, >>, & etc) and integer division to lua 5.1.4 which should be completed.
Still need to work on the LuaLib for D (an OO wrapper for the D programming language).
## Post #8
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2009-04-23T18:52:40+00:00
- Post Title: Using lua as a scripting language for Extraction Tool?

I'm not too familiar with lua  so I'm thinking about writing language from zero, and it will be written in Object Pascal or C++ (I dont have any experience with D language, sorry
## Post #9
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-04-23T22:08:36+00:00
- Post Title: Using lua as a scripting language for Extraction Tool?

it's your choice 
but writing a new and *stable* scripting language is hard.
btw, try D, it's worth it
## Post #10
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-06T12:30:13+00:00
- Post Title: Using lua as a scripting language for Extraction Tool?

Probably a language similar to 010 Editor's one is most appropriate.

```
{
    char[4] magic;
    uint      version;
    ...
}
```
