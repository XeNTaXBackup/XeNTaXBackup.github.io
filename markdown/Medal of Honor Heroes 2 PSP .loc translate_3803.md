## Post #1
- Username: zakos
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Feb 15, 2008 3:59 am
- Post datetime: 2009-10-24T17:02:50+00:00
- Post Title: Medal of Honor Heroes 2 PSP .loc /translate/

Could you please look at the *.loc and *.idx files from Medal of Honor Heroes 2 - I think they contain the texts from the game
[mohh2.zip](https://xentaxbackup.github.io/file/2477_mohh2.zip)
## Post #2
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2009-10-24T21:39:42+00:00
- Post Title: Medal of Honor Heroes 2 PSP .loc /translate/

eng_us.loc definitely contain text strings. They are also UNICODE one (2 bytes).
## Post #3
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-10-24T22:26:25+00:00
- Post Title: Medal of Honor Heroes 2 PSP .loc /translate/

eng_us.loc looks like a very simple string table format.

First there's a LOCH section:

```
{
   char magic[4]; // "LOCH"
   uint32_t size;
   uint32_t unk1; // 0
   uint32_t unk2; // 1.
   uint32_t unk3; // 20.
}

```


Then a LOCL section:

```
{
   char magic[4]; // "LOCL"
   uint32_t size;
   uint32_t unk1; // 0
   uint32_t nStrings;
   uint32_t stringPtr[nStrings]; // Pointers to little endian unicode strings, relative to the start of the LOCL section
}

```
## Post #4
- Username: zakos
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Feb 15, 2008 3:59 am
- Post datetime: 2009-10-25T09:40:15+00:00
- Post Title: Medal of Honor Heroes 2 PSP .loc /translate/

Thank you very much,but how can i use this code,what you wrote?
## Post #5
- Username: BANDIT
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Sep 13, 2011 4:19 am
- Post datetime: 2018-06-14T11:22:47+00:00
- Post Title: Medal of Honor Heroes 2 PSP .loc /translate/

For *.loc files use this tool - [https://www89.zippyshare.com/v/ioMiFdsj/file.html](https://www89.zippyshare.com/v/ioMiFdsj/file.html)
