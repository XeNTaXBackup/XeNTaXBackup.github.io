## Post #1
- Username: Blue Mantis
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Feb 05, 2015 10:35 am
- Post datetime: 2015-04-03T16:41:50+00:00
- Post Title: 24: The Game - Audio Extraction?

PlayStation 2 game
The ISO contents:





I don't know if you've worked with this format before. I only want the audio because I imagine there are a few tracks at least that aren't present in the game's soundtrack. If you think you can work with this format (GAMEDATA.1, I don't know much about PS2) I will upload that file for you, thanks.
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-04-03T18:34:42+00:00
- Post Title: 24: The Game - Audio Extraction?

The 989SND.IRX makes me think that it uses the 989 sound driver. The same one that Jak & Daxter and Sly Cooper and the Thievius Raccoonus used which is an audio bank with instrument samples and a midi file of some description.

If it is using this sound driver as a sequencer like those other two games, then it's impossible to do anything with it as no one fully worked out the driver.
## Post #3
- Username: Blue Mantis
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Feb 05, 2015 10:35 am
- Post datetime: 2015-04-03T23:29:43+00:00
- Post Title: 24: The Game - Audio Extraction?

This is some text I found in 989SND.IRX file:

```
      Index: %d
          BlockPtr = 0x%8.8x
       Block Name = %s
           BlockID = %c%c%c%c
               Sound = 0x%8.8x
      Sound Index = %d
  	  Next Grain = %d
       start tick = %d
           Num Streams = %d
         Queued Stream = 0x%8.8x
          Head Stream = 0x%8.8x
  Stream Start Sector = %d
     VAG data consumed = %d
    ERROR... stream doesn't point to this handler!
   98snd: ReleaseSRAMMutex by thread that doesn't own it!!
    
Free SPU Block at -> %u (0x%x) size -> %d

    989snd: LockMasterTick called with interrupts disabled (0x%8.8x)!!!
            Mutex thread = 0x%8.8x
         Our Thread   = 0x%8.8x
      Tick Owner list:
            current = %d
          [%d] = 0x%8.8x
         VAlloc Owner : 0x%8.8x
    Sound System Tick locked out for 2 seconds.
         gLockMasterTick: %d
   989snd: Cd has been busy reading %s for 10 seconds.
    a vag   data    WOW! doubling voice is allocated 1!
    WOW! doubling voice is allocated 2!
    snd_StopAllStreams: ERROR! tried 5 times to stopp all streams!
 989snd: Error starting VAG! Killinig stream (0x%8.8x)
  989snd: CDRead with 0 sectors (1)!
 989snd: CDRead with 0 sectors (2)!
 989snd: CDRead with 0 sectors (3)!
 snd_KickDataRead: sceCdRead returned 0 but sceCdGetError returned SCECdErNo!
    989snd: snd_GetStreamDataFromCD... stdio get data and IOPbuffer wrong. Patching.
  989snd: CDRead with 0 sectors (4)!
 989snd: Got "gOddCdError" Code was %d
```


This suggests that it probably is using that sound driver. That's a shame. Perhaps I'll see if it's possible to disable the sounds in the game itself and record the music that way. (A bit primitive, but it might work.)
