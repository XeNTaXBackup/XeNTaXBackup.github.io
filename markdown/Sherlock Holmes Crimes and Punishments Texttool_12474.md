## Post #1
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2015-01-07T01:27:14+00:00
- Post Title: Sherlock Holmes Crimes and Punishments Texttool

Can anyone please have a look on this files : 

 Sherlock Holmes Crimes and Punishments Text.rar
(82.61 KiB) Downloaded 120 times




I found those files when I unpack upk file, I will send all text file in private. Hope anyone can make a texttool for this game. Thanks!
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-01-07T21:10:22+00:00
- Post Title: Sherlock Holmes Crimes and Punishments Texttool

not a lot of data to go on here - any complete loose text files you could share?

roughly this:

```
//--- 010 Editor v6.0 Binary Template
//--------------------------------------

typedef uint32 u32;
typedef uint64 u64;

u32 unknown_1;

struct entry
{
    u64 a;
    u64 id; // ??
    u64 total_str_size; // length of len + str:
    u32 len;
    char str[len];
};

entry e1, e2, e3;

```
## Post #3
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-01-07T21:55:17+00:00
- Post Title: Sherlock Holmes Crimes and Punishments Texttool

missing headers!
## Post #4
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2015-01-08T23:47:57+00:00
- Post Title: Sherlock Holmes Crimes and Punishments Texttool

> Reply from WRS
>
> not a lot of data to go on here - any complete loose text files you could share?

roughly this:
Code: Select all//--------------------------------------
//--- 010 Editor v6.0 Binary Template
//--------------------------------------

typedef uint32 u32;
typedef uint64 u64;

u32 unknown_1;

struct entry
{
    u64 a;
    u64 id; // ??
    u64 total_str_size; // length of len + str:
    u32 len;
    char str[len];
};

entry e1, e2, e3;

Thanks! I sent pm for you!
## Post #5
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-01-09T20:04:34+00:00
- Post Title: Sherlock Holmes Crimes and Punishments Texttool

didn't realize this game was unreal engine 3 - the file structure of this engine is a complete mess

there is no central locale table. instead, any strings are 'inlined' where they are needed - so strings are all over the place

sorry i can't help with this
## Post #6
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2015-01-10T07:49:25+00:00
- Post Title: Sherlock Holmes Crimes and Punishments Texttool

> Reply from WRS
>
> didn't realize this game was unreal engine 3 - the file structure of this engine is a complete mess

there is no central locale table. instead, any strings are 'inlined' where they are needed - so strings are all over the place

sorry i can't help with this

Thanks! Anyway, thanks for your quick reply!
## Post #7
- Username: desert32
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 19, 2014 4:55 am
- Post datetime: 2015-04-18T19:35:03+00:00
- Post Title: Sherlock Holmes Crimes and Punishments Texttool

I can't .xxx files repack please help me
