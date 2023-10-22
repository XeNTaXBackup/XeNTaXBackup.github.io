## Post #1
- Username: warrantyvoider
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 03, 2016 9:13 pm
- Post datetime: 2018-01-22T14:49:25+00:00
- Post Title: Goldeneye N64 eep savegame editor

Update: its done now 
[](https://www.youtube.com/watch?v=bIUE1aNff40)

download at: [https://github.com/zeroKilo/GE64SaveEditorWV](https://github.com/zeroKilo/GE64SaveEditorWV)









I started to reverse the format for goldeneye's internal save format, as I have an everdrive I can simply test what changes. I already found out how and where times are saved (10bit values, one after another for a given difficulty), has anyone information about how the hashes are made?

greetz WV
[GE64SaveEditor.zip](https://xentaxbackup.github.io/file/13829_GE64SaveEditor.zip)
## Post #2
- Username: warrantyvoider
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 03, 2016 9:13 pm
- Post datetime: 2018-01-22T14:52:55+00:00
- Post Title: Goldeneye N64 eep savegame editor

here some example savegames, I can only attach one zip per post, sry
[Save.zip](https://xentaxbackup.github.io/file/13830_Save.zip)
## Post #3
- Username: warrantyvoider
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 03, 2016 9:13 pm
- Post datetime: 2018-01-22T19:30:28+00:00
- Post Title: Goldeneye N64 eep savegame editor

[https://pastebin.com/EzGqRN7G](https://pastebin.com/EzGqRN7G)

reads all times now!

interestingly 10bit * 20 times = 200 bit needed; 
200 bit / 8 bitPerByte = 25 bytes! (0x19)

thats why the offsets are 0x19 far apart!
(in bytes)
Offset Agent Time : 0x12
Offset Secret Agent Time : 0x2B
Offset 00 Agent Time : 0x44

so for one slot, the structure definition would be:

```
{
  byte[8] hash; //???
  ushort unk1;
  ushort unk2;
  ushort unk3;
  uint cheatflags;
  bit10[20] timeAgent;
  bit10[20] timeSAgent;
  bit10[20] time00Agent;
  byte[3] leftover;
}
```


and for an entire savegame:

```
{
  byte[32] header;
  slot[5] times;
}
```


greetz WV

PS: 17:03 should be the longest possible time (0x3ff = 1023 sec)
## Post #4
- Username: warrantyvoider
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 03, 2016 9:13 pm
- Post datetime: 2018-01-23T07:23:10+00:00
- Post Title: Goldeneye N64 eep savegame editor

[https://pastebin.com/BzRVPvHS](https://pastebin.com/BzRVPvHS)

```
CODE:80015F40 3C 09 1F C0 35 29 07 C0                 li      $t1, 0x1FC007C0  # Load Immediate
CODE:80015F48 3C 0A A4 80                             lui     $t2, 0xA480      # Load Upper Immediate
#actual write to eeprom
CODE:80015F4C AD 49 00 10                             sw      $t1, 0xA4800010  # Store Word
```


learning new stuff all the time! I think I found the spot where the actual write of eeprom (if no save exists yet) is done. eeproms are accessed linewise, that means 8 bytes at a time and this function is called 64 times = 512 byte

to do this, I got the source of project64, compiled it, ran it in interpreter mode, set a breakpoint on the eeprom command for writing to it, then looked up the actual opcode (AD 49 00 10), stepped the cpu and noted the very next opcode (8F AB 00 18). with these two "magic" numbers I found a single hit in goldeneye's rom, at 0x80015F4C !

well, research continues... 

EDIT1: lol, just noticed, im stupid, the cpu has an PROGRAM_COUNTER member, it told me it was at 0x70015f4c, well ignoring the upper part, I could have just seen the XXX15F4C and replace the XXX with 800... damn^^

EDIT2: well, this function is also used for reading, as its meant to be a call, "writing" the arguments makes sense:

```
        //...
        ReadFrom(&Command[4], Command[3]);
        break;
    case 5: //Write to Eeprom
        //...
        WriteTo(&Command[4], Command[3]);
        break;
```

so for one call the arguments asks for a write and somehow contain the data for it, and for another call it may ask for a read and provides a resultbuffer, dunno, maybe it uses special register, not sure (havent figured out arg passing yet)
## Post #5
- Username: warrantyvoider
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 03, 2016 9:13 pm
- Post datetime: 2018-01-24T20:31:58+00:00
- Post Title: Goldeneye N64 eep savegame editor

well not much news, I just used the visual studio debugger to step the cpu and trace where the call came from, sofar I got:

CODE:80015ED0             eeprom_access: //the function I first found, does one write access / 8 bytes
CODE:80015340             eeprom_access2://calls above function twice, does at least one write access with it
CODE:80015960             eeprom_access3://calls above function multiple times, writes all 64 lines, I guess from some buffer in RAM
CODE:8000C808             eeprom_access4://calls above function once

it would be alot nicer if I could start the rom paused and use the normal debugger included... btw, to write memory into eeprom you have to DMA a command buffer(64 byte I think) into PIF RAM, so that it sees the eeprom command and decodes it (first 4 bytes zero, then 2 unknown bytes 0x0a and 0x01, then that its a write access 0x05, then the line nr starting with 0x00, goes until 0x3F, then 8 bytes of data to write) which in turn does the actual writing to eeprom (at least thats how the emulator does it)
## Post #6
- Username: warrantyvoider
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 03, 2016 9:13 pm
- Post datetime: 2018-01-26T17:40:50+00:00
- Post Title: Goldeneye N64 eep savegame editor

just a little update on this:


I traced the calls back 3 caller functions (by stepping through every subfunction), one way leads to eeprom_access as write access and one as read access

greetz
## Post #7
- Username: warrantyvoider
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 03, 2016 9:13 pm
- Post datetime: 2018-01-28T14:24:20+00:00
- Post Title: Goldeneye N64 eep savegame editor

more updates:

CODE:80051EC0             readSaveGame
CODE:800CF530             makeHash

the hash is made with a seed as input, which is reused on next call of it, thats why different slots with the same data have different hashes, anyone wanna help me reverse that function? im already delving into it^^

greetz
## Post #8
- Username: warrantyvoider
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 03, 2016 9:13 pm
- Post datetime: 2018-01-28T15:24:24+00:00
- Post Title: Goldeneye N64 eep savegame editor

ok nvm, I think I solved it^^



here the hashfunction in C#:

```
{
    uint seedLo = 0x3108B3C1;
    uint seedHi = 0x8F809F47;
    uint s1 = 0;
    UInt64 resultHi = 0;
    UInt64 resultLo = 0;
    for (int i = 0; i < data.Length; i++)
    {
        byte t8 = data[i];
        uint t9 = s1 & 0xF;
        uint t0 = (uint)(t8 << (byte)t9);
        uint t7 = t0 + seedLo;
        uint t6 = t0 >> 31;
        if (t7 < seedLo)
            t6++;
        t6 += seedHi;
        seedHi = t6;
        seedLo = t7;
        UInt64 newSeed = SubHash(seedHi, seedLo);
        s1 += 7;
        resultHi ^= (uint)newSeed;
        seedLo = (uint)newSeed;
        seedHi = (uint)(newSeed >> 32);
    }
    for (int i = data.Length - 1; i >= 0; i--)
    {
        byte t8 = data[i];
        uint t9 = s1 & 0xF;
        uint t0 = (uint)(t8 << (byte)t9);
        uint t7 = t0 + seedLo;
        uint t6 = t0 >> 31;
        if (t7 < seedLo)
            t6++;
        t6 += seedHi;
        seedHi = t6;
        seedLo = t7;
        UInt64 newSeed = SubHash(seedHi, seedLo);
        s1 += 3;
        resultLo ^= (uint)newSeed;
        seedLo = (uint)newSeed;
        seedHi = (uint)(newSeed >> 32);
    }
    return resultHi<<32 | resultLo;
}

static UInt64 SubHash(uint hi, uint lo)
{
    UInt64 a3 = (UInt64)hi << 32 | lo;
    UInt64 a2 = a3 << 63;
    UInt64 a1 = a3 << 31;
    a2 = a2 >> 31;
    a1 = a1 >> 32;
    a3 = a3 << 44;
    a2 |= a1;
    a3 = a3 >> 32;
    a2 ^= a3;
    a3 = a2 >> 20;
    a3 &= 0xFFF;
    a3 ^= a2;
    return a3;
}
```

   

greetz
## Post #9
- Username: warrantyvoider
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 03, 2016 9:13 pm
- Post datetime: 2018-01-28T19:00:46+00:00
- Post Title: Goldeneye N64 eep savegame editor

ok, all done now, edited the first post with the links, see y'all

greetz
## Post #10
- Username: warrantyvoider
- Rank: beginner
- Number of posts: 20
- Joined date: Tue May 03, 2016 9:13 pm
- Post datetime: 2018-01-29T14:09:44+00:00
- Post Title: Goldeneye N64 eep savegame editor

to the "unknown" parts, they probably store some additional settings you can set with bonds watch.

previously unknown2 = volume sliders! (higher/left byte = music volume, lower/right byte = fx volume, 0..255, not visible in new tool, unk3 is now unk2)
and here the list of cheat flags for the cheat value:

```
40000000 No Radar [Multi]
20000000 Turbo Mode
10000000 2x Rocket L.
08000000 2x Grenade L.
04000000 DK Mode
02000000 Invincible
01000000 Paintball
00800000 Infinite Ammo
00400000 2x Hunting Knife
00200000 Silver PP7
00100000 Slow Animation
00080000 Enemy Rockets
00040000 Bond Invisible
00020000 Fast Animation
00010000 2x Throwing Knife
00000800 All Guns
00000400 2x Laser
00000200 Gold PP7
00000100 2x RC-P90
```

so I added better GUI for that, will upload the new version once I get home



greetz

EDIT: now on github
## Post #11
- Username: iGuyC
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 16, 2019 9:13 pm
- Post datetime: 2019-08-16T13:26:54+00:00
- Post Title: Goldeneye N64 eep savegame editor

Hey this is great work, thank you very much for this.

I'm not interested in editing, but want to be able to read times.

I use an emulator called 1964 which is modded and uses plugins in such a way that GE007 can be played with a keyboard and mouse at 1080p and 60fps.

I notice from your YouTube video that your EEP files are 1KB, however the ones that 1964 produce are 2KB.

I'm wondering if this might be the reason why your reader doesn't seem to be able to load them? There aren't any errors, but after opening the file, the window remains blank - no slots are displayed.

This is a screenshot of the data:
1964eep.PNG

This was a clean save file, but one slot has played and completed Dam Agent and Dam Secret Agent.

I can send you a copy of the save if it helps, do you think this is fixable?
## Post #12
- Username: iGuyC
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 16, 2019 9:13 pm
- Post datetime: 2019-08-16T13:51:49+00:00
- Post Title: Goldeneye N64 eep savegame editor

Just spotted the image being missing for some reason.

Will try again.



1964eep.PNG (35.5 KiB) Viewed 42 times
