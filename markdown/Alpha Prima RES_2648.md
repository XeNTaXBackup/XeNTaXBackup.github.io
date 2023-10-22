## Post #1
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2007-06-08T16:06:12+00:00
- Post Title: Alpha Prima RES

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2007-06-14T15:19:09+00:00
- Post Title: Alpha Prima RES

i'm afraid its a bit xoring method but not a single xor value.

well...it dont bring more to help.
## Post #3
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2007-06-14T15:27:57+00:00
- Post Title: Alpha Prima RES

xor? dammit...
## Post #4
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2007-07-10T15:11:00+00:00
- Post Title: Alpha Prima RES

nothing new on this?
## Post #5
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-10T21:23:53+00:00
- Post Title: Alpha Prima RES

for non-trivial encryption disassemble the exe.
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-10T22:52:02+00:00
- Post Title: Alpha Prima RES

I don't know if this is indeed a XOR method. This could also be a table encryption (at least for the filenames that is). Just look a the filenames, it might be they have a table for each valid character in a filename and use that to encrypt it.
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-11T21:49:40+00:00
- Post Title: Alpha Prima RES

LOL I figured it out, it's a funny encryption method. Let me get back to you later with a RES->NORMAL ZIP converter.  I must be insane to do this type of riddles.
## Post #8
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-11T21:52:29+00:00
- Post Title: Alpha Prima RES

You figured out the encryption method just by looking at the file?
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-11T23:08:05+00:00
- Post Title: Alpha Prima RES

> Reply from Rheini
>
> You figured out the encryption method just by looking at the file?

No, I looked at the executable.
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-12T09:44:01+00:00
- Post Title: Alpha Prima RES

ok, here's a list of the files in the dat02.res, I wrote a little lister to test the decryption method. 

```
SCRIPTS/
SCRIPTS/animset.h
SCRIPTS/class_creature/
SCRIPTS/class_creature/ai.h
SCRIPTS/class_creature/ai2.h
SCRIPTS/class_creature/boss.h
SCRIPTS/class_creature/humanoids.h
SCRIPTS/class_creature/npc.h
SCRIPTS/class_creature/robots.h
SCRIPTS/class_func.h
SCRIPTS/class_info.h
SCRIPTS/class_info_cutscene.h
SCRIPTS/class_item.h
SCRIPTS/class_item_weapon.h
SCRIPTS/class_light.h
SCRIPTS/class_misc_model.h
SCRIPTS/class_misc_physics_model.h
SCRIPTS/class_misc_physics_pack.h
SCRIPTS/class_particle.h
SCRIPTS/class_shot.h
SCRIPTS/class_trigger.h
SCRIPTS/console.h
SCRIPTS/definitions/
SCRIPTS/definitions/anim.h
SCRIPTS/definitions/animset.h
SCRIPTS/definitions/gameplay.h
SCRIPTS/definitions/globals.h
SCRIPTS/definitions/items.h
SCRIPTS/definitions/items_def.h
SCRIPTS/definitions/keys.h
SCRIPTS/definitions/shoteffects.h
SCRIPTS/definitions/sounds.h
SCRIPTS/definitions/soundsets.h
SCRIPTS/definitions/speechset.h
SCRIPTS/definitions/strings.h
SCRIPTS/editor.h
SCRIPTS/editor_links.h
SCRIPTS/editor_main.c
SCRIPTS/editor_path.h
SCRIPTS/func_display.h
SCRIPTS/hud.h
SCRIPTS/menu.h
SCRIPTS/music_player.h
SCRIPTS/player/
SCRIPTS/player/interface.h
SCRIPTS/player/player.h
SCRIPTS/proto.h
SCRIPTS/pviewer.h
SCRIPTS/script.c
SCRIPTS/shaders.h
SCRIPTS/soundset.h
SCRIPTS/super.h
SCRIPTS/super2.h
SCRIPTS/super_actor.h
SCRIPTS/viewer.h
strings.xml

```


As you can see, it works.  Now for a real converter.
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-12T10:52:21+00:00
- Post Title: Alpha Prima RES

The encryption method for the filenames is as follows:

```
// Demystified by M.W.Zuurman (Mr.Mouse/Xentax)
// 
// General idea:
//
// 1. The encryption XORs the characters in the strings with a seed value 
// 2. The seed value is the ascii-code of a letter picked from the encryption string 'insanity' 
//
// The method to pick the right character from the encryption string is:
//
// 1. Take the position of the character to be XORed (starting from 0)
// 2. AND this value with 7 
// 3. Look up the character in the encryption string that is at this position
// 4. XOR the character in the original string with the ASCII value of that encryption character
// 5. Loop this until the whole string is encrypted
//
// In raw useless code: 
//
// Declare and assign the following variables:
int Count ; // counter to loop through each character in the original string (OString)
int Lookup ; // Lookup value to get the character from the encryption string 'insanity' (EString)
int SSize ; // the size of the original string 

while (Count < SSize) {
Lookup = Count AND 7;
DString[Count] = OString[Count] XOR EString[Lookup] ;
Count += 1 ;
}

// That should be it in schematic code. 
// Note that the filenames will never be long enough for the 'AND 7' method to fail getting a number between 0 and 7.

```
## Post #12
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-12T11:06:24+00:00
- Post Title: Alpha Prima RES

> Reply from Mr.Mouse
>
> // Note that the filenames will never be long enough for the 'AND 7' method to fail getting a number between 0 and 7.
Nice encryption method 
What do you mean with "will never be long enough"? ANDing a number with 7 always gives you a value between 0 and 7.
Is every string encrypted individually or is it a block encryption?
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-12T11:38:11+00:00
- Post Title: Alpha Prima RES

Yes, I was referring to variable conversion types. Never mind.  

Each string is encrypted individually.  I gave away a bit of the method last night when I said: "I must be insane to do this type of riddles.".
## Post #14
- Username: saurav
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-12T14:15:08+00:00
- Post Title: Alpha Prima RES

It's amazing what you can find on the internet these days. Found this command line driven tool on a Russian site. It's by Xplorer and will do that for which I wanted to create a new program.

[http://www.xentax.com/uploads/author/mr ... es2zip.zip](http://www.xentax.com/uploads/author/mrmouse/xplorers_res2zip.zip)

This will correct the res file and make it a zip archive again.
## Post #15
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2007-07-18T15:29:29+00:00
- Post Title: Alpha Prima RES

amazing but not easy to find...well...you rock
## Post #16
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2007-08-12T23:56:10+00:00
- Post Title: 

i can't say nothing more than thank you very much
