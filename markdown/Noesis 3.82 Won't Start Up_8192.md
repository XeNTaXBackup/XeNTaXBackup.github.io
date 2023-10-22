## Post #1
- Username: dragicorn
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Sep 18, 2011 3:21 am
- Post datetime: 2012-02-05T20:21:47+00:00
- Post Title: Noesis 3.82 Won't Start Up

Today, I opened noesis just fine. I tried to open a couple of files, and it kept giving me incorrect parameter responses on .bin .cue and .img files.

Now, I click on the icon, and the mouse does a short wait, and then nothing happens. I tried Open, Run As, Run as Administrator, Compatability Mode, and Run this Program as Admin. Nothing makes it pop up. I restarted the computer, installed a fresh copy of Noesis, tried lower versions, and so forth.

Does an install of MagicIso have anything to make this problem happened, cause that was installed prior to the problems happening. I need Magic iso to extract .bin files and .img files.

EDIT: When starting up Noesis 373, I get an Import Error message, saying there is no module named Noesis_inc. What in the world is this?

New EDIT: Okay, the program does launch, but then quits. It appears it's run on 3887 MB of Read Disk (Ram). THAT'S A TON! So, I suspect the system's going to block this program due to the fact that the system has for some reason reserved 4 GB of 8 GB of Ram Space, and 3 other RAM is being used by programs and processes. I would upgrade my RAM to become 16 GB (max), but I am trying to save that money for an IPAD 3... plus... I'm fresh out of money anyway. Unless I can wipe my system's processing history of Neosis without a recovery, I am fresh out of luck! Unless...

Can someone recreate Neosis and rename the entire lines of the word "Noesis" it to "Total Model Viewer" or Something? I think my system would not recognize the program if it's named something entirely different... not just the program name but all of the scripts and plugins to it?

The reasoning behind this is that the system blocks everything "Noesis". So a different name might bypass this difficulty.

The system must had Super Heavy Processes. I dunno why it worked and then stopped working yesterday... maybe because when I was loading .bin and .cue files and this filetype I don't recognized that it got all Heavy Processing trying to decipher it/them.

I can wait, I got other activities to do besides look at models anyway.
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-02-26T22:14:43+00:00
- Post Title: Noesis 3.82 Won't Start Up

I don't know why you'd post a Noesis issue in the MultiEx Commander section, Noesis isn't related to MEX, and I never would've seen this if Mr.Mouse hadn't IM'd me the thread link. But in any case, Noesis never uses more than 50MB during startup. So something on your system is totally screwed up if it's eating anything more than that. Half of what you say sounds completely wrong and you must be confusing your terms as well, so it's hard to diagnose what's actually happening from this information you've provided. Sounds like you extracted Noesis incorrectly too, if the Python implementation can't find inc_noesis.py. And why are you using 3.73? It runs for you but 3.82 doesn't? Then something is definitely screwed up on your system.

Are you using the distribution from the official Noesis site? If you got it anywhere else, I don't vouch for whatever it is that you ran, and it could easily contain some form of virus/malware if you aren't getting it from the official site.
## Post #3
- Username: vayeate
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 23, 2016 8:46 am
- Post datetime: 2016-01-23T00:50:19+00:00
- Post Title: Noesis 3.82 Won't Start Up

> Reply from dragicorn
>
> Today, I opened noesis just fine. I tried to open a couple of files, and it kept giving me incorrect parameter responses on .bin .cue and .img files.

Does an install of MagicIso have anything to make this problem happened, cause that was installed prior to the problems happening. I need Magic iso to extract .bin files and .img files.

I know this thread is years old, but it's the top google result for "noesis won't start".  This is the answer. It's MagicIso. I was having Neosis show for a fraction of a second before closing. ProcessMonitor showed the last thing it did was access my virtual DVD drive before closing (I use Virtual CloneDrive, but same thing as MagicISO). Disabled the virtual drive, Neosis no longer crashes on boot.
