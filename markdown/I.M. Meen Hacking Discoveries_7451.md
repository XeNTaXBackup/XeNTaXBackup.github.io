## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-10-03T00:04:36+00:00
- Post Title: I.M. Meen Hacking Discoveries

Well, thought I'd put this is Code Talk as it does involve some of its game code. I've decided to put this up for anyone interested in hacking I.M.Meen for any purpose. Bear in mind that when it went to Chill Manor, OBJECTS.DEF was encrypted or changed to a binary format and IMAGES.IMG was given further information that is as of yet, aside from the raw wall textures, nonconvertible. The new information is for dealing with textures and images that exceed 64x64 but are otherwise the same. I refer to these as Version 2 IMG format.

RES###.LAB contents:

3D##.WAV - World sounds, such as doors opening, buttons, and kids rescued sounds.
BUZZER.WAV - Incorrect mark on grammar puzzle
CLICK.WAV - Used in grammar puzzles
ES##.WAV - Enemy sounds
ESHIT.WAV - Enemy hit you
FX##.WAV - General effect sounds
PW##.WAV - Spell and player attack sounds

CUBES1.DEF - Assuming dealing with walls.
FLOOR1.DEF - Assuming dealing with floor textures.
MAZE1.DEF - Assuming dealing with object placement. Object identification as of yet unknown.
OBJECTS.DEF - Defines all actors in the game in an easy-to-understand text code. Example below

```
// CHARACTERS
//
//
//   Generic Actor's parameters:
//
//   image, (set up automatically by image base builder)
//   dead_phases, dead_init, dead_image, dead_delay, dead_sound, life_power,
//   attack_phases, attack_init, attack_phase, attack_delay, attack_sound,
//   move_phases, move_init, move_delay, move_step,
//   delay_between_attack, (def8)
//   approach_dist, (def6 in cell quarters)
//   freq_change_course, (def16)
//   hit_image (def0)
//
//   for all actors & bullets
//   after right parenthesis:
//
//   delay_factor (def0), 
//   hit_power (def1)
//

Dragon		   (100,
		    21, 14, -1, 0, 0, 4,
		    4, 7, 0, 1, 8,
		    4, 0, 1,
		    10,
		    11,      // specific: dead_ready_image,
		    2, 3, 2, // specific: dead_1phases, dead_1repeat, dead_1delay
		    0, 5, 0
		    );

Gargoyle	   (144,
		    16, 37, 53, 0, 0, 3,
		    4, 17, 0, 1, 7,
		    4, 1, 2,
		    4,
		    4, 24, 1, // specific: fly_total, fly_init, fly_delay
		    16,       // specific: fly_step
		    0, 3, 0
		    );


Ghost		   (198,
		    6, 23, -1, 0, 0, 2,
		    5, 15, 0, 3, 10,
		    6, 0, 1,
		    8,
		    3, 12, 10,  // near attack  (phases, init, sound)
		    0, 6, 8);

GhostGold   :Ghost (29,
		    6, 23, -1, 0, 0, 2,
		    5, 15, 0, 3, 10,
		    6, 0, 1,
		    8,
		    3, 20, 10, // near attack
		    0, 6, 8);

Gnome		   (98,
		    11, 15, 26, 0, 16, 2,
		    5, 9, 3, 1, 24,
		    4, 1, 0,
		    8,
		    15, 2, 7,  // specific: jump_init, jump_total1, jump_total2
		    16, 4, 8),,5,8,11;
```

SKY1.DEF - Thinking relates to ceiling textures
SOUNDDAT.DEF - Defines sounds used in this level.
STARTPOS.DEF - Start position is assigned in unknown manner of:
#,
#,
#,
Originally I thought this was X, Y, and Z but having a number in the Z position makes no sense as everything is on the same level, there is no op or down as the ceiling only goes so high (64).
Level 6 is, for example:

```
6,
90,

```


FLOOR.IMG - Floor textures
GAME_SCR.PCX - HUD, and contains the game's palette (the game apparently takes the PCX palette as the game palette, altering it changes ingame colors).
IMAGES.IMG - Wall textures, doors, and sprites are contained here, sprites are encoded with masking values that have been cracked thanks to MortoQuiba and WRS.
SKY.IMG - Ceiling textures
STARTSCR.PCX - Level title screen

Others are the animated cel files (ANI), SC## are these. PRC and BMF files serve unknown purposes.

The CMP files are uncracked and seem to have the same masking style as IMAGES.IMG but seem to have the addition of using a Color Lookup Table (CLT) as opposed to running from raw encoding. As of yet there is no method of conversion.

Further discoveries:

MAZE1.DEF assumption was correct, it does place objects and enemies, additionally it also assigns a routine or behavior of the actors, such as to wander/patrol which, as far as I know, was not present in Doom1/2 making some enemies actively seeking targets rather than standing around.
## Post #2
- Username: YoshiOG1
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Oct 16, 2011 2:30 am
- Post datetime: 2011-12-02T20:42:07+00:00
- Post Title: I.M. Meen Hacking Discoveries

About the start position coordinates, I think that Z might represent the direction that the player is facing, which is most likely measured in degrees.

I wonder if someone could crack the code of the mapping of the LAB files, so that we can hack more easily.
Maybe if someone could develop a program to mod the maps, the program could be like AdvanceMap, but for I. M. Meen instead of Pokémon.

Another thing:
If you're going to change OBJECTS.DEF and re-import all the files back into an existing LAB file using QuickBMS, then OBJECTS.DEF needs to have the same file size as it did before you changed it.  Well, at least I think that's the way it works.
