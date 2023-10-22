## Post #1
- Username: dung251997
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat May 06, 2017 6:22 pm
- Post datetime: 2017-05-06T10:29:30+00:00
- Post Title: Why I can't unpack a pak file ?

Today I want to unpack a pak file of game "Dead Cells". name "res.pak" but I tried much time with many application like winrar, 7zip, pak exploer,..... (apps can unpack file .pak) but all of them fail. Can you give me a solution :v I want to translate it.....

Dead cells is a new game and it's a beta version. Plz
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2017-05-06T17:06:31+00:00
- Post Title: Why I can't unpack a pak file ?

For unpacking you can use this QuickBMS script.

```
# By Allen
#2015-9-1 Evoland 2 .pak

idstring "PAK\0"
get DataOffset long
get fileSize long
get dummy short 
get numFolder long
for i = 0 < numFolder
    set folderName string ""
    CallFunction unpack 0 folderName
next i

StartFunction unpack folderName
    get namelen byte
    getdstring name namelen    
    get type byte
    if type == 0
        get offset long
        get size long
        get dummy long
        math offset += Dataoffset
        set fname string FolderName
        string fname += /
        string fname += name
        log fname offset size
    elif type == 1
        string folderName += /
        string folderName += name        
        get numEntry long
        for j = 0 < numEntry
            set folderName2 string folderName
            CallFunction unpack 0 folderName2
        next j
    endif
EndFunction

```
## Post #3
- Username: dung251997
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat May 06, 2017 6:22 pm
- Post datetime: 2017-05-06T18:58:53+00:00
- Post Title: Why I can't unpack a pak file ?

> Reply from merlinsvk
>
> For unpacking you can use this QuickBMS script.
Code: Select all#script for quickbms
# By Allen
#2015-9-1 Evoland 2 .pak

idstring "PAK\0"
get DataOffset long
get fileSize long
get dummy short 
get numFolder long
for i = 0 < numFolder
    set folderName string ""
    CallFunction unpack 0 folderName
next i

StartFunction unpack folderName
    get namelen byte
    getdstring name namelen    
    get type byte
    if type == 0
        get offset long
        get size long
        get dummy long
        math offset += Dataoffset
        set fname string FolderName
        string fname += /
        string fname += name
        log fname offset size
    elif type == 1
        string folderName += /
        string folderName += name        
        get numEntry long
        for j = 0 < numEntry
            set folderName2 string folderName
            CallFunction unpack 0 folderName2
        next j
    endif
EndFunction

Do you know how to unpack a file have extension .grd ? quickbms can do it ??
## Post #4
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2017-05-06T22:33:42+00:00
- Post Title: Why I can't unpack a pak file ?

deadcells.grd seems like some sort of compiled scripts file to me. So there is nothing to unpack.
## Post #5
- Username: dung251997
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat May 06, 2017 6:22 pm
- Post datetime: 2017-05-07T09:02:25+00:00
- Post Title: Why I can't unpack a pak file ?

> Reply from merlinsvk
>
> deadcells.grd seems like some sort of compiled scripts file to me. So there is nothing to unpack.
Ok, thanks, so final question :v how can I repack that file @@
## Post #6
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2017-05-07T09:14:34+00:00
- Post Title: Why I can't unpack a pak file ?

Try reimport mode of QuickBMS. But modified files can't be bigger than original. 
If you have bigger files, then you will need proper repacker.
## Post #7
- Username: dung251997
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat May 06, 2017 6:22 pm
- Post datetime: 2017-05-07T10:36:58+00:00
- Post Title: Why I can't unpack a pak file ?

> Reply from merlinsvk
>
> Try reimport mode of QuickBMS. But modified files can't be bigger than original. 
If you have bigger files, then you will need proper repacker.

Do you have script to reimport that file :v
## Post #8
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2017-05-07T12:51:51+00:00
- Post Title: Why I can't unpack a pak file ?

It's the same script. It should be good for reimporting, but I didn't test it though.
## Post #9
- Username: dung251997
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat May 06, 2017 6:22 pm
- Post datetime: 2017-05-07T12:53:55+00:00
- Post Title: Why I can't unpack a pak file ?

> Reply from merlinsvk
>
> It's the same script. It should be good for reimporting, but I didn't test it though.

It's not work for me T.T

Error like this [http://imgur.com/a/qd44w](http://imgur.com/a/qd44w)
## Post #10
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2017-05-07T16:46:28+00:00
- Post Title: Why I can't unpack a pak file ?

[It works](http://imgur.com/Xsl62rn).

```
quickbms.exe -r -w bms.txt res.pak text
```


Where "text" is folder with unpacked files/folders.
## Post #11
- Username: Adolfok3
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Aug 11, 2014 2:13 am
- Post datetime: 2017-05-21T14:15:47+00:00
- Post Title: Why I can't unpack a pak file ?

> Reply from merlinsvk
>
> It works.
Code: Select allquickbms.exe -r -w bms.txt res.pak text

Where "text" is folder with unpacked files/folders.

Which file did you edit? I edited all the language files and it made no difference in the game ...
## Post #12
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2017-05-21T17:34:12+00:00
- Post Title: Why I can't unpack a pak file ?

I don't remember, I've already deleted that game.
## Post #13
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2017-05-23T17:53:23+00:00
- Post Title: Why I can't unpack a pak file ?

So it was lang\main.en.mo. If you did't see any changes, your text file was probably not imported back into res.pak.
