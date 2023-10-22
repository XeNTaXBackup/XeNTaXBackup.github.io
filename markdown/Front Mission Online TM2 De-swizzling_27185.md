## Post #1
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2023-09-08T18:09:56+00:00
- Post Title: Front Mission Online TM2 De-swizzling

While Game Graphics Studio can handle FMO's environmental and UI textures, none of its de-swizzling methods work for what I assume are the textures I actually need. While I grasp the general concept of swizzling, I have yet to find any information on how I'm supposed to decern what pattern is being used so I have something to work backwards from. Simply put, I'm staring at masses of pixels and don't know what to do next. Any help or suggestions would be greatly appreciated as, being a defunct MMO, dumping with PCSX2 is not an option. Furthermore, this is the last hurdle before I'm done with the PS2 Front Mission games.
[Example.7z](https://xentaxbackup.github.io/file/24321_Example.7z)
## Post #2
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2023-09-09T12:42:55+00:00
- Post Title: Front Mission Online TM2 De-swizzling

I think I found the solution in [this](https://gist.github.com/Fireboyd78/1546f5c86ebce52ce05e7837c697dc72), I just need to figure out how to use it.
## Post #3
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2023-09-10T12:53:00+00:00
- Post Title: Front Mission Online TM2 De-swizzling

Never mind, I think I figured out how to parse the file. Just need to reverse-engineer the script.
## Post #4
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2023-09-17T23:02:01+00:00
- Post Title: Front Mission Online TM2 De-swizzling

I reverse-engineered the script and it gives me the same result as Games Graphic Studio/Console Texture Explorer. I'm taking a look at Victor Suba's code now, though I'm not sure how to calculate the values that need to be passed into the read and write functions.
## Post #5
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2023-09-24T16:04:28+00:00
- Post Title: Front Mission Online TM2 De-swizzling

I managed to figure this out with the help of Discord, but the texture I need don't actually seem to be stored as TIM2s.
## Post #6
- Username: Greg
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Dec 15, 2015 12:47 pm
- Post datetime: 2023-09-26T20:28:08+00:00
- Post Title: Front Mission Online TM2 De-swizzling

Turns out I could extract everything I need from the PC version.
