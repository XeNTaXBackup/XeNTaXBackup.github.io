## Post #1
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-12-17T09:19:23+00:00
- Post Title: Releasing JaederStorm Source Component

I decided to release JaederStorm source, (the main pre-scanner for
jaedernaub), as i have been slacky on updates lately, too much other things to do, but jaeder naub isnt dead  , im mainly releasing it for both educational purposes and so people can make their own optimizations to
the prescanner to speed it up for their own purposes.

this version is the version used in JaederNaub 2.0.6c release.

[http://ihateui.com/jaederstorm_source.zip](http://ihateui.com/jaederstorm_source.zip)

For example, all File detections are by default detected by Jaeder Storm,
its actually the GUI program that later filters out the findings.

So, for the hardcore user you could disable any damn format you dont want
by cutting out the identifier code. or optimize it somehow, do whatever you want 

too bad its very badly documented (and cluttered), because i didnt think it would be released in this state, but overall it should be pretty selfexplanatory what the program does, atleast in the in the actual scannerloop.

Compile with Freebasic! preferable newest version.
also happy for suggestions on how to speed up the scanning further.

Cheers!!!!
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-12-17T09:29:21+00:00
- Post Title: Releasing JaederStorm Source Component

Cool  

Here's an alternative link in case the other dies. 

[http://www.xentax.com/uploads/author/mr ... source.zip](http://www.xentax.com/uploads/author/mrmouse/jaederstorm_source.zip)
## Post #3
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-12-17T09:30:45+00:00
- Post Title: Releasing JaederStorm Source Component

I cant say no too mirrors  thnx mousie!
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-12-17T09:32:18+00:00
- Post Title: Releasing JaederStorm Source Component

> Reply from Strobe
>
> I cant say no too mirrors  thnx mousie!

One thing, though, it might be an idea to include at least a readme.txt to tell the user what is it, who dunnit, and what to do to compile it.
## Post #5
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-12-17T09:44:53+00:00
- Post Title: Releasing JaederStorm Source Component

Readme.txt fixed in the zip now =P
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-12-17T09:51:52+00:00
- Post Title: Releasing JaederStorm Source Component

Good! Mirrored!
## Post #7
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-11T21:40:31+00:00
- Post Title: Releasing JaederStorm Source Component

What is the purpose of the first loop? Why do you use asm there?
So you simply compare the data with all signatures? Why is it yet fast?

We had a discussion about scanning algorithms some time ago here:
[viewtopic.php?f=22&t=2861](http://forum.xentax.com/viewtopic.php?f=22&t=2861)

I also asked in the other thread, but you've never answered it:
[viewtopic.php?p=23640#p23640](http://forum.xentax.com/viewtopic.php?p=23640#p23640)
## Post #8
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2008-04-02T14:57:06+00:00
- Post Title: Releasing JaederStorm Source Component

Im sorry for my absence of the forums right now! 

Do you mean this loop?

```

    Value=Peek(Integer,(Memory+Scanner))
    asm
        mov byte ptr [detected],0
        mov eax,[value]
         
        cmp eax, 1179011410 
        je foundfile
        cmp eax, 542327876
        je foundfile
        cmp eax, 1179207242
        je foundfile
        cmp eax, 944130375
        je foundfile
        cmp ax, 19778
        je foundfile
      
        mov byte ptr [detected],0
        'No More detections
        jmp short loldone 
        foundfile:
        mov byte ptr [detected],1
        mov ecx,[scanner]
        add ecx,3
        mov [scanner],ecx
       loldone:
    end asm
    '
    if detected=1 then Gosub StormListAdd
next scanner


```


thats the "UltraFast" Scanner for only a few formats. i decided to make it assembly optimized because
it was lots easier on just a fewer formats. but its super fast.

i had the idea to try to optimize the whole jaederstorm with only asm code but it took too long =P
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-04-02T19:35:22+00:00
- Post Title: Releasing JaederStorm Source Component

I love assembly.
## Post #10
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2008-04-03T04:34:08+00:00
- Post Title: Releasing JaederStorm Source Component

Thats perfect! now you recode the prescanner in full assembly and totally optimized
for ultra speed so i can sit back and eat popcorn instead =D !!!
*preferably quadcore optimized aswell*
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-04-03T06:08:23+00:00
- Post Title: Releasing JaederStorm Source Component

And steal your show? No sir!
## Post #12
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2008-04-03T06:09:40+00:00
- Post Title: Releasing JaederStorm Source Component

Damnit =(((

im getting lazy lately!
## Post #13
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-04-03T06:48:45+00:00
- Post Title: Releasing JaederStorm Source Component

The key to better performance is better algorithms, not simply doing everything in asm
## Post #14
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2008-04-03T06:53:35+00:00
- Post Title: Releasing JaederStorm Source Component

the only actual optimization in the scanner i have currently is that it will detect
slack data, for big ISO files that have large chunks of unused space.

that has proven to be a very good implementation, as it can skip up to 500mbs of slack space in 1 second 

other than that, not yet!
