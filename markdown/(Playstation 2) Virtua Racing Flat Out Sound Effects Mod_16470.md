## Post #1
- Username: DaroDaroDaro
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 29, 2017 7:37 pm
- Post datetime: 2017-06-29T11:49:21+00:00
- Post Title: (Playstation 2) Virtua Racing Flat Out Sound Effects Mod

Hello Everyone: 

I'm new here, so I apologize in advance if I failed to observe any forum-specific rules by posting in this manner.
I'm trying to remove a specific sound effect (of tires screeching) in Virtua Racing Flat Out for the PS2, which is almost game-breaking in its nature. To see what I mean, feel free to play a few seconds of this video: [https://www.youtube.com/watch?v=kqK8hjJcc7Q](https://www.youtube.com/watch?v=kqK8hjJcc7Q) . The sound can be heard any time the car is turning, making an unbearable mess of sound. 

The sound effect itself is bundled with a bunch of other sound effects. It's inside a file less than a megabyte in size, named "SE01.BD", which has a companion file with an "HD" extension. I want to edit this sound effect and replace it with silence, so the game will still have something to playback, but I haven't been able to pull this off correctly. Can anyone give me some pointers? I feel like this should be an easy enough task and I've been missing something. 

Thanks for any help you can provide!
## Post #2
- Username: DaroDaroDaro
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 29, 2017 7:37 pm
- Post datetime: 2017-06-30T11:42:23+00:00
- Post Title: (Playstation 2) Virtua Racing Flat Out Sound Effects Mod

Posting to let you know that I've found a working solution to this issue: The .HD file contains a lot of settings for each one of the samples contained in the .BD file. One of the values is, easy enough, sample volume. In this case it was set to 7F, and by hex editing that value to 00 and rebuilding the ISO with the modified .HD file, Virtua Racing Flat Out is now a whole lot easier on the ears. I might try setting that value to something lower than 7F but higher than 00 to hear if the sfx becomes enjoyable at lower volumes. But for now I'll consider this a win. Hope it helps, cheers!
## Post #3
- Username: Hellr0t
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 20, 2020 2:03 am
- Post datetime: 2020-05-19T20:57:07+00:00
- Post Title: (Playstation 2) Virtua Racing Flat Out Sound Effects Mod

Hello! I'm so sorry for necroing this thread, but unfortunately, the solution isn't clear. I too am extremely annoyed by the sound, but love the game.

Has anyone figured out how to do what OP did exactly, as in, set that particular sound's volume to zero? I understand you need to change its HEX value from 7F to 00 in the SE01.HD file, but there's over 100 strings using this value, so it's not clear which one corresponds to the screeching tire sound. Unfortunately, OP didn't mention what exact files or strings need to be looked for.

Could anyone please help with this? I'm a total noob in these matters... Thanks!

EDIT

Alright, I got it! After unsuccessfully trying using Cheat Engine to figure out whether there's a value in the game's memory that calls for the tire screeching sound I could force to 0, I've decided to try hex-editing the SE01.HD file the hard way.

I changed any values that were set to 7F to 00 in bulk until the desired effect worked in-game, then narrowed it down. So here is a brief how-to:

1. We need to use Hex Editing software to open the game's SE01.HD file, which can be found in the SOUND folder. "HxD" is a free program that can be used.

2. Scroll down to offset 000008E0. The value we need to change is in the 0E column, and is set to 7F by default.

3. Change the value from 7F to 00.

4. Save the file, rebuild the ISO and play.

Thanks so much to OP, the game can actually be enjoyed! I have no idea why anyone would approve that constantly screech noise that can last the entire race, but good thing it can be muted.

Unfortunately, I couldn't find any value that would just make the sound quieter, but one can live without it imo
