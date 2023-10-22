## Post #1
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2016-02-18T15:23:24+00:00
- Post Title: Anyone want to dust off Simcity 2000? Looking for assistance

Hey everyone,

I started a few personal projects, one of those involves writing a library to read *.SC2 files, or Simcity 2000 city save files. There's already a [huge text file](http://djm.cc/simcity-2000-info.txt) documenting it, although some mysteries remain. As you can see [here](http://wiki.xentax.com/index.php?title=Simcity_2000_Special_Edition#SC2), I started to move some of that document to the wiki, and it got... A little messy. 

Here's the deal: I'd like to fully understand the ALTM, or Altitude map section of the file. What's known right now is that it is uncompressed, 32768 bytes of data. Each tile in a city is represented by two bytes. As far as it's known right now, the first byte or eight bits go unused. The following three bits supposedly have something to do with water. The remaining five bits represent the altitude of the tile, as a multiple of 50 feet. I'd like to focus in on the three bits that may or may not have to do with water.

As you can tell by the wiki, I spent quite a bit of time researching and testing it, only to end up more confused. Raising and lowering a title with respect to its neighbors, then adding a pond, seemed to flip these three bits in an inconsistent manner. I don't know if they actually represent something else, or are there for an unimplemented feature. I think I'm on the verge of cracking the game open with a disassembler to see what the heck it's doing with the memory.

If anyone is familiar with the game, or would like to get familiar with the game, I'd love to have your help in getting to the bottom of this. It's about time we figured out how this game saves its data
## Post #2
- Username: Ambren786
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 09, 2019 7:49 pm
- Post datetime: 2019-01-09T12:00:40+00:00
- Post Title: Anyone want to dust off Simcity 2000? Looking for assistance

Last month Dave Amos, a former land use planner and now PhD candidate at UC Berkeley, in the process of acquiring his City and Regional Planning degree, decided to blow the dust off SimCity 2000 and see how much his practical knowledge applies to the 25-year-old game.
thanks
## Post #3
- Username: tgp1994
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Mar 28, 2010 11:10 am
- Post datetime: 2019-01-09T17:48:24+00:00
- Post Title: Anyone want to dust off Simcity 2000? Looking for assistance

> Reply from Ambren786
>
> Last month Dave Amos, a former land use planner and now PhD candidate at UC Berkeley, in the process of acquiring his City and Regional Planning degree, decided to blow the dust off SimCity 2000 and see how much his practical knowledge applies to the 25-year-old game.
thanks

Hi Ambren,

Thank you for the heads up, a lot has changed since I made that post! I'm pretty sure there's an open source browser remake of SC2K out there right now with full support for loading city files, so when I'm back on this project I'll have to take a look at that.
## Post #4
- Username: Ambren786
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 09, 2019 7:49 pm
- Post datetime: 2019-01-15T07:20:39+00:00
- Post Title: Anyone want to dust off Simcity 2000? Looking for assistance

welcom 

[https://www.shutterstock.com/image-vect ... 4eUag-1-74](https://www.shutterstock.com/image-vector/wolf-vector-logo-front-1261851487?src=MgtpJHWbwOyikpJ8D4eUag-1-74)
