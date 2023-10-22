## Post #1
- Username: dijotp
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jun 20, 2009 9:47 pm
- Post datetime: 2010-11-01T23:11:07+00:00
- Post Title: Emergency 2012

Hi.

Someone could help me decrypt Emergency 2012 files. Here are some example files:
[http://netload.in/dateiOJmsMVT04z/emergency2012.rar.htm](http://netload.in/dateiOJmsMVT04z/emergency2012.rar.htm)

Thanks.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-11-01T23:22:25+00:00
- Post Title: Emergency 2012

sure this is easy but next time just use a free site like sendspace or mediafire.
Here is a quickbms script all the files you sent me only contain one file so this may not work on every file.

```
get files long
get size long
get null long
get unk01 long
get zsize asize
math zsize - 0x14
get name filename
get ext EXTENSION
string name + .
string name + ext
clog name 0x14 zsize size

```
## Post #3
- Username: dijotp
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jun 20, 2009 9:47 pm
- Post datetime: 2010-11-02T00:43:41+00:00
- Post Title: Emergency 2012

> Reply from chrrox
>
> sure this is easy but next time just use a free site like sendspace or mediafire.
Here is a quickbms script all the files you sent me only contain one file so this may not work on every file.
Code: Select allget idstring long
get files long
get size long
get null long
get unk01 long
get zsize asize
math zsize - 0x14
get name filename
get ext EXTENSION
string name + .
string name + ext
clog name 0x14 zsize size

Run great!!!
Thank you very much.
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-11-02T09:45:46+00:00
- Post Title: Emergency 2012

As a side note, since the 4.4.0 update you should be able to run QuickBMS scripts from MultiEx Commander as well. Gives you another interface possibility.
## Post #5
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2010-11-03T16:33:27+00:00
- Post Title: Emergency 2012

I unpacked the xml file, how can I repack it?
## Post #6
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2010-11-09T21:23:38+00:00
- Post Title: Emergency 2012

> Reply from qabRieL
>
> I unpacked the xml file, how can I repack it?
## Post #7
- Username: bhrun
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Mar 20, 2010 8:20 pm
- Post datetime: 2010-11-10T12:21:45+00:00
- Post Title: Emergency 2012

The game runs without repack it.

Just rename the file xxxx.xml.xml to xxxx.xml

Works fine
## Post #8
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2010-11-10T16:50:30+00:00
- Post Title: Emergency 2012

> Reply from bhrun
>
> The game runs without repack it.

Just rename the file xxxx.xml.xml to xxxx.xml

Works fine
Thanks, man. It works fine.
