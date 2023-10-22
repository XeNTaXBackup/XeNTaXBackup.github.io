## Post #1
- Username: Karan Vess
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 23, 2016 7:30 am
- Post datetime: 2016-01-22T23:47:55+00:00
- Post Title: Dragon's Dogma PC files

Hey!
Short story in a nutshell, I'm trying to do a modelswap and stuff doesn't work because the game is trying to open a file I don't want it to open because it results in a crash.
I tracked the game accessing another file when equipping the piece in question but when extracting it I only get a texture file that is half the size of the actual file itself, so I'm thinking there's a list of files in there that tells the game what files should be present. Problem is, I have no idea how to continue from here, I have no coding experience whatsoever. Can anyone help me?

Here's the files in question:
The file the game reads when equipping:
[https://www.dropbox.com/s/loarm5o1s9p4i ... D.arc?dl=0](https://www.dropbox.com/s/loarm5o1s9p4i6m/item0763_b_ID.arc?dl=0)
The piece of equippment:
[https://www.dropbox.com/s/r1dyxggtin6ek ... 4.arc?dl=0](https://www.dropbox.com/s/r1dyxggtin6ekvf/f_a_helm7004.arc?dl=0)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-24T13:31:40+00:00
- Post Title: Dragon's Dogma PC files

> Reply from Karan Vess
>
> Hey!
Short story in a nutshell, I'm trying to do a modelswap and stuff doesn't work because the game is trying to open a file I don't want it to open because it results in a crash.
I tracked the game accessing another file when equipping the piece in question but when extracting it I only get a texture file that is half the size of the actual file itself, [...]Wasting lifetime on following your confusing story? Doubt, that anyone will.

> I tracked the game accessing another fileWhat does that mean exactly? Did you use a file monitor? Or a debugger, attached to the game's exe?

> so I'm thinking there's a list of files in there that tells the game what files should be presentassumed this is true the file monitor (or process monitor) should display those filenames in case the game accesses them
## Post #3
- Username: Karan Vess
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 23, 2016 7:30 am
- Post datetime: 2016-01-24T18:05:13+00:00
- Post Title: Dragon's Dogma PC files

> What does that mean exactly? Did you use a file monitor? Or a debugger, attached to the game's exe?
I used a process monitor.

```
assumed this is true the file monitor (or process monitor) should display those filenames in case the game accesses them
```

That's the thing, the arc file is an archive, consists of multiple files: .dwm, .mod, .mrl, etc
What I'm guessing is, that the file the game reads has something that says "archive xy consists of: file.dwm, file.mod, file.mrl, etc". But I have no way to check that. If it is like that I want a way to remove file.dwm from that list.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-24T18:38:58+00:00
- Post Title: Dragon's Dogma PC files

that was better but I needed to uncompress item0763_b_ID.arc to fully understand what you meant: there's a 17 kB .tex file contained.

Did you notice that there's 32 kB of zeroes in that arc?
So it's a little bit unlikely that there's other files contained in there.

This might be worth a try: just copy then rename a valid .dwm to "thiswillnotcrash".dwm (using the name of the .dwm file that causes a crash of course).
## Post #5
- Username: Karan Vess
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 23, 2016 7:30 am
- Post datetime: 2016-01-24T21:10:31+00:00
- Post Title: Dragon's Dogma PC files

> Just copy then rename a valid .dwm to "thiswillnotcrash".dwm (using the name of the .dwm file that causes a crash of course).
I already tried that with different dwms. Some work, some don't. But they all end up causing physics glitches to some extend if they don't crash the game, so I came to the conclusion that dwm files contain physics bones or whatever it's called. Gear that doesn't have any moving parts doesn't have dwm files in it. The original file is something that has moving parts and so has a dwm file, the file I want to replace it with doesn't.
