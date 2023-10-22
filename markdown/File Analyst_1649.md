## Post #1
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-12-29T21:54:10+00:00
- Post Title: File Analyst

New program I'm working on, first screen shot, build 0.0.0.70.



This is just the hex viewer for now.  more information on features later.
## Post #2
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-12-29T21:58:57+00:00
- Post Title: File Analyst

Nice   wait news
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-30T02:26:20+00:00
- Post Title: File Analyst

Looking good  Can I ask what the purpose of this program is? Is it going to primarily function as a hex editor, or do you have some other ideas for what you want it to do.

Keep up the good work!

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #4
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2005-12-30T02:43:05+00:00
- Post Title: File Analyst

Been talking about Mr. Mouse about it over IM.  Its going to be a file analysis program. Highlighting sections through the hexeditor, you can flag parts, give them variable names, build structures apply them to the file, allow you to drag out parts of a file to work with them individually apply compression or decompression filters on them.  Since a lot of people use HexWorkshop, including myself, i wanted to have a similar look, so i've been working on the hex viewer to get it to look/feel similar.  Of course, this is only the 70th build .  Perhaps when its done, it could have a MexScript export.  Basically it allows you to debug or create new binary file formats.
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-30T03:13:40+00:00
- Post Title: File Analyst

Cool cool, I thought that was your intention - I just wan't sure if I was reading too much into it or not. Guess not  

It sounds really good - certainly something that would be benificial - so I hope you continue working on it.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-12-30T15:22:33+00:00
- Post Title: File Analyst

Indeed. Looking good
## Post #7
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-01-01T03:21:18+00:00
- Post Title: File Analyst

Im also very interested in testing/using this one,
and for some real great stuff would be calculating options
for blocks. like XORing until found a certain string, or ROR/ROL
etc etc for common encryption detection, that would make this
tool extremely usefull. =)

ive made one own of this kinda tool, but it was for the amiga
i think i called it "The Machine". but now im too lazy and sticking
with other hexeditors =X
## Post #8
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-01-01T04:58:02+00:00
- Post Title: File Analyst

Excellent Rahly ..... Waiting public version
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-01T07:26:20+00:00
- Post Title: File Analyst

> Reply from Strobe
>
> Im also very interested in testing/using this one,
and for some real great stuff would be calculating options
for blocks. like XORing until found a certain string, or ROR/ROL
etc etc for common encryption detection, that would make this
tool extremely usefull. =)

ive made one own of this kinda tool, but it was for the amiga
i think i called it "The Machine". but now im too lazy and sticking
with other hexeditors =X

Those features sound very usefull indeed. 

Perhaps I need to make some adaptations to Mex script, but our idea is to use the File Analyst in close association with the script. It might also be that a whole new method of processing is needed, I once started work on MultiEx 4 (the script processor) with a new method in mind, but I lacked time to finish it.
## Post #10
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-01-02T07:43:25+00:00
- Post Title: File Analyst

finished the hex viewers highlighting, almost the final piece
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2006-01-02T21:04:14+00:00
- Post Title: File Analyst

Rahly: will this tool be open source and portable to other platforms other than Win32?

About the question of Strobe, making that type of program (search using xor, plus, less and other operations) is very simple but how many programs use these simple types of encoding and how we know what keyword to search?

A good idea could be the creation of a tool which emulates what "we think" when we try to understand the file formats... cool 8-)
## Post #12
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-01-03T06:46:20+00:00
- Post Title: File Analyst

There is ofcourse no way one can know what to search for,
so you simply have to search for commonly used headers
, like "RIFF", "JFIF", "DDS |" etc in order to make something out
of the file.
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-03T06:49:40+00:00
- Post Title: File Analyst

> Reply from Bugtest
>
> Rahly: will this tool be open source and portable to other platforms other than Win32?

About the question of Strobe, making that type of program (search using xor, plus, less and other operations) is very simple but how many programs use these simple types of encoding and how we know what keyword to search?

A good idea could be the creation of a tool which emulates what "we think" when we try to understand the file formats... cool

The latter was the idea of the EUREKA project I started (see other thread in the Code Talk forum). We never worked any further on it though. (Time).
## Post #14
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-01-03T08:57:09+00:00
- Post Title: File Analyst

"but how many programs use these simple types of encoding"

actually, i dont know =O

but there seems to be a couple of games atleast that have used XORs.
## Post #15
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-01-04T17:33:12+00:00
- Post Title: File Analyst

Adding a plugin system also, plugins should be allowed to create new menu items, also new project options, as well as to add to global preferences.  I'm going for a options look similar to winamps, only plugin configurable.
## Post #16
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-01-13T19:29:00+00:00
- Post Title: 

which do you think is better, multiple windows? or all in one, like VS or VS.NET?
## Post #17
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-01-14T05:42:56+00:00
- Post Title: 

Quick question... Do you plan on adding file compare? I'm not sure about all of you guys, but I find I use it alot...
## Post #18
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2006-01-14T13:10:20+00:00
- Post Title: 

> Reply from Rahly
>
> which do you think is better, multiple windows? or all in one, like VS or VS.NET?
All in one, I'd say.
## Post #19
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-15T10:20:23+00:00
- Post Title: 

If you can do all-in-one - do it  . Another good thing, which is half the reason why I wrote my own little hex viewing program ages ago, would be the ability to display 2 ( or more? ) files at the same time. For example, my program has a split down the middle so it can show 2 files (or the same file twice) on the left and right. If you were to do this, I would definately rate this highly 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #20
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-15T11:47:28+00:00
- Post Title: 

> Reply from Rahly
>
> which do you think is better, multiple windows? or all in one, like VS or VS.NET?

I think multiple windows would also work for me. Especially if I can run other programs at the same time on screen. It's a matter of taste, I guess. I don't mind switching between windows. But all in one is okay as well. I started on MexCom 4 from scratch once, and it had multiple windows, and you could drag stuff from one window to the other. Never finished it though.
## Post #21
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-02-17T13:16:40+00:00
- Post Title: 

I am really very noob here , so forgive my perhaps naive question. Is there any utility which could split file into "intuitively" recognisable chunks. I usually use graphic interpretation of the hex content in Axe Hex Editor.  So I can see from the graphic patterns whenever  there is a bitmap or other graphic in it. I can see now and can recognise a sound file. My only prob with Axe that row width cannot be adjusted with an arrow key in one fluid movement , but that is minor. 

Is there anything like this to do it better? Are there any other tricks of the trade available in this particualry area ? Or tool to split into sensible and integral file chunks? Thank you.
## Post #22
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-02-17T15:47:23+00:00
- Post Title: 

I guess I am answering my question myself, but appears that there is no "free lunch". This site and it's main tutorial DGTEF is the answer. That and some of the threads here too. Still, if there are any other hints - appreciate.
