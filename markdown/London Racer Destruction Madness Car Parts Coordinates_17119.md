## Post #1
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-10-10T23:05:31+00:00
- Post Title: London Racer: Destruction Madness Car Parts Coordinates

Hi all,i have extracted models from that game but offsets for car parts in CNT files,and i dont know how to read them,what metrics and etc.
I can place it in 3ds max by myself but im lazy to doing it with all cars from that game  



Here blue is a car part name,yellow unknown value(if I change it, then nothing will change in the game),green and red move like on screenshot from game.

Link to all files of that car: 

[https://mega.nz/#!BplySZTT!lKzXq8-XUO9H ... OB9KNVZ01M](https://mega.nz/#!BplySZTT!lKzXq8-XUO9HMlUAG5m90mgwDXgKOLkG2OB9KNVZ01M)

And topic about models from that game:

[https://forum.xentax.com/viewtopic.php?f=16&t=16232](https://forum.xentax.com/viewtopic.php?f=16&t=16232)

I hope someone can help.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-10-11T10:59:04+00:00
- Post Title: London Racer: Destruction Madness Car Parts Coordinates

> Reply from dropoff
>
> Hi all,i have extracted models from that game but offsets for car parts in CNT files,and i dont know how to read them,what metrics and etc.so you would like to leave the annoying part of analysing to the audience?  In my experience that doesn't work, usually.

Noone likes to start from scratch to help out others; so it's up to you to put in more efforts.
Why not give the carbody.cnt file a structure? For example there's 21 times the string "MODL".

You need to provide more infos than just colouring some random values (they are random, aren't they?).

> I can place it in 3ds max by myselfwouldn't that require the parameters you're asking for?  
(Tell/show us more, please.)

> but im lazy to doing itthat's me, too
## Post #3
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-10-11T11:28:46+00:00
- Post Title: London Racer: Destruction Madness Car Parts Coordinates

> Reply from shakotay2
>
> so you would like to leave the annoying part of analysing to the audience?  In my experience that doesn't work, usually.
Maybe i need to do more researches here,but im hit a wall,im found parameters that i needed,but i dont know how to read them,and seems like developers leave decrypted version of that file in folder CAR.TXT,but still i dont know what metrics of that coordinates.

> Reply from shakotay2
>
> Noone likes to start from scratch to help out others; so it's up to you to put in more efforts.
Why not give the carbody.cnt file a structure? For example there's 21 times the string "MODL"

Sorry,im new to analyse files,and idk how to do this properly.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-10-11T14:46:55+00:00
- Post Title: London Racer: Destruction Madness Car Parts Coordinates

> Reply from dropoff
>
> im found parameters that i needed,but i dont know how to read themyou're speaking in riddles, want to keep things secret?  (edit: correction, see my note at the end)
well, from what I see here:



classiccoupe.jpg (171.9 KiB) Viewed 56 times


I'd guess you're missing the offsets for the parts, don't you?
Then you need to learn how to read floats from a binary file. That's not too hard.

If you can't do it by coding, search for a hex editor that can display data as floats.

Or you could use hex2obj with the .cnt file, addr 0x768, simply negate the 1.31.

edit: well, see, you were on the right track, my apologies  ,
you simply marked the floats in a unusual way: C4 17 65 3F (for the boot) is one float in IEEE754 floating point format
