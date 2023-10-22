## Post #1
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2020-11-14T22:14:24+00:00
- Post Title: Giana Sisters : Twisted Dreams - Owltimate Edition .pak files

I extracted the rom file of Giana Sisters : Twisted Dreams - Owltimate Edition and came across with many pak files.
Usually, using helldorado.bms QuickBMS script works for extracting Twisted Dreams pak files, but this time it didn't worked because the pak files from Owltimate Edition use the RPMC compression.
I tried to use [http://aluigi.altervista.org/bms/topgun.bms](http://aluigi.altervista.org/bms/topgun.bms), but it didn't worked either.

Here's an sample file : [http://www.mediafire.com/file/ljvydxwch ... s.zip/file](http://www.mediafire.com/file/ljvydxwch1it7mf/animations.zip/file)
Helps would be very appreciated!
## Post #2
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2020-11-20T20:02:00+00:00
- Post Title: Giana Sisters : Twisted Dreams - Owltimate Edition .pak files

Any one interested? because maybe writing a QuickBMS script by basing it from topgun.bms and helldorado.bms could make it possible.
## Post #3
- Username: GianaSistersFan64
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-11-21T21:27:59+00:00
- Post Title: Giana Sisters : Twisted Dreams - Owltimate Edition .pak files

Ok, I think that I have figured that out. 
Here you can see tool and documentation [https://github.com/bartlomiejduda/Tools ... d%20Dreams](https://github.com/bartlomiejduda/Tools/tree/master/NEW%20Tools/Giana%20Sisters%20Twisted%20Dreams)

This tool decompress gzip compressed blocks and creates SBPACK archive
which can be later unpacked with [http://aluigi.zenhax.com/bms/helldorado.bms](http://aluigi.zenhax.com/bms/helldorado.bms)
using "r" option.

I will also update Xentax Wiki later. 


Edit: Ok, I have updated wiki [http://wiki.xentax.com/index.php/Giana_ ... Dreams_PAK](http://wiki.xentax.com/index.php/Giana_Sisters:_Twisted_Dreams_PAK)
## Post #4
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2020-11-21T23:03:28+00:00
- Post Title: Giana Sisters : Twisted Dreams - Owltimate Edition .pak files

> Reply from ikskoks ↑Sun Nov 22, 2020 5:27 am at Sun Nov 22, 2020 5:27 am
>
> 
Ok, I think that I have figured that out. 
Here you can see tool and documentation https://github.com/bartlomiejduda/Tools ... d%20Dreams

This tool decompress gzip compressed blocks and creates SBPACK archive
which can be later unpacked with http://aluigi.zenhax.com/bms/helldorado.bms
using "r" option.

I will also update Xentax Wiki later. 


Edit: Ok, I have updated wiki http://wiki.xentax.com/index.php/Giana_ ... Dreams_PAK

Can you tell me how do i use the python script? i tried to figure out but i can't.
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-11-21T23:29:28+00:00
- Post Title: Giana Sisters : Twisted Dreams - Owltimate Edition .pak files

Of course, here is the instruction:

1. Install Python 3
2. Change paths at the end of the script
3. Run script in Python using cmd or some IDE like "Wing IDE"

```
python script.py
```


Also this may be helpful [https://www.google.com/search?client=fi ... hon+script](https://www.google.com/search?client=firefox-b-d&q=how+to+run+python+script)
## Post #6
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2020-11-21T23:37:43+00:00
- Post Title: Giana Sisters : Twisted Dreams - Owltimate Edition .pak files

> Reply from ikskoks ↑Sun Nov 22, 2020 7:29 am at Sun Nov 22, 2020 7:29 am
>
> 
Of course, here is the instruction:

1. Install Python 3
2. Change paths at the end of the script
3. Run script in Python using cmd or some IDE like "Wing IDE"
Code: Select allpython script.py

Also this may be helpful https://www.google.com/search?client=fi ... hon+script

When i try it, it gives me this error :

```
SyntaxError: (unicode error) 'unicodeescape' codec can't decode bytes in position 2-3: truncated \UXXXXXXXX escape
```
## Post #7
- Username: GianaSistersFan64
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-11-21T23:41:55+00:00
- Post Title: Giana Sisters : Twisted Dreams - Owltimate Edition .pak files

You may have wrong paths defined. You need to use double backslash "\\", for example:

```
C:\\Users\\SomeUser\\Desktop\\PAK\\animations.pak
```
## Post #8
- Username: GianaSistersFan64
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Jul 21, 2020 11:48 pm
- Post datetime: 2020-11-22T00:28:57+00:00
- Post Title: Giana Sisters : Twisted Dreams - Owltimate Edition .pak files

> Reply from ikskoks ↑Sun Nov 22, 2020 7:41 am at Sun Nov 22, 2020 7:41 am
>
> 
You may have wrong paths defined. You need to use double backslash "\\", for example:
Code: Select allC:\\Users\\SomeUser\\Desktop\\PAK\\animations.pak

It's worked! Thank you so much
## Post #9
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2020-11-22T02:00:48+00:00
- Post Title: Giana Sisters : Twisted Dreams - Owltimate Edition .pak files

Here is bms script, which is doing the same thing (converts pak to sbpack).


 giana_sisters_td_pak.zip
(420 Bytes) Downloaded 24 times
