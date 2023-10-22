## Post #1
- Username: sarzamin
- Rank: beginner
- Number of posts: 38
- Joined date: Fri Nov 19, 2010 10:19 pm
- Post datetime: 2013-09-12T17:11:49+00:00
- Post Title: Wargame Airland Battle

Hi guys

I use [this](https://bitbucket.org/nanomad/wargame-ee-dat-unpacker) tool to unpack WargameEE .dat files

It supports Wargame Airland Battle, but in extract an exception occurred when unpacker want to build a folder with illegal characters.

Is there any other rool to unpack this files?

Example file:

[http://www.4shared.com/archive/y40oSwnX/DataMap.html](http://www.4shared.com/archive/y40oSwnX/DataMap.html)

mirror:

[http://www.mediafire.com/download/rwc6j ... DataMap.7z](http://www.mediafire.com/download/rwc6jrc81po5cii/DataMap.7z)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-12T19:29:51+00:00
- Post Title: Wargame Airland Battle

All files extracted without any errors.
## Post #3
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2013-09-12T22:04:44+00:00
- Post Title: Wargame Airland Battle

\Wargame Airland Battle\Data\wargame\PC\2100001487\NDF_Win.dat, for example, cause BEX.
## Post #4
- Username: sarzamin
- Rank: beginner
- Number of posts: 38
- Joined date: Fri Nov 19, 2010 10:19 pm
- Post datetime: 2013-09-14T07:04:46+00:00
- Post Title: Wargame Airland Battle

Example files added.
## Post #5
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2013-09-16T02:32:19+00:00
- Post Title: Wargame Airland Battle

i make .dat unpacker on Lua (based on Wargame:EE DAT Unpacker) - [https://github.com/hhrhhr/Lua-utils-for-Wargame](https://github.com/hhrhhr/Lua-utils-for-Wargame) , works with both "European Escalation" and "Airland Battle".
## Post #6
- Username: sarzamin
- Rank: beginner
- Number of posts: 38
- Joined date: Fri Nov 19, 2010 10:19 pm
- Post datetime: 2013-09-16T06:44:54+00:00
- Post Title: Wargame Airland Battle

> Reply from hhrhhr
>
> i make .dat unpacker on Lua (based on Wargame:EE DAT Unpacker) - https://github.com/hhrhhr/Lua-utils-for-Wargame , works with both "European Escalation" and "Airland Battle".

Thank u so much

but, what about pack again?
## Post #7
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2013-09-16T12:39:07+00:00
- Post Title: Wargame Airland Battle

still doesn't.
## Post #8
- Username: SchnelleMeyer
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Feb 27, 2017 5:28 am
- Post datetime: 2020-11-27T15:00:15+00:00
- Post Title: Wargame Airland Battle

How do I run this unpacker? 

What are the instructions please?
## Post #9
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2020-11-27T15:18:33+00:00
- Post Title: Wargame Airland Battle

Click on the above link, you will be taken to github site. Read the instructions and follow them.
## Post #10
- Username: SchnelleMeyer
- Rank: beginner
- Number of posts: 27
- Joined date: Mon Feb 27, 2017 5:28 am
- Post datetime: 2021-01-03T20:25:40+00:00
- Post Title: Wargame Airland Battle

Thank you for your reply, but if you mean these instructions> 
Usage:
used LuaJIT 2.0.2 ([http://luajit.org](http://luajit.org))

unpack .dat (.ppk) files

  luajit unpack_wargame_dat.lua path_to_dat [output_dir]

I dont understand what to do at all.
Could you please explain me with some more details?
## Post #11
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2021-01-03T20:43:48+00:00
- Post Title: Wargame Airland Battle

I do not quite understand what exactly you do not understand. replace "path_to_dat" with the name of the required file, instead of "output_dir" - the name of the directory for unpacking.
