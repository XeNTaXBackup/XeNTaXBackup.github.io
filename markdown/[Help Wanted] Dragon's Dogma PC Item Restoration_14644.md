## Post #1
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2016-07-18T16:50:33+00:00
- Post Title: [Help Wanted] Dragon's Dogma PC Item Restoration

Greetings.

As some of you may know, Dragon's Dogma PC port is a very solid port of the console version, but there were a few cuts made to it much to the dismay of some people.
Those cuts include the intro song and two item sets that were present in the console version.
The intro song had already been restored through modding by a different person, but a friend of mine has been working on restoring those two cut item sets, namely the Berserk armors and weapons that are present in console versions but not on PC.

He made a decent progress with researching the files, finding item tables and even some initial testing with converting the models of those items to the PC version's format but he is unable to actually add the items themselves to the game (even though most of their data including stats, icons and description still being there!).

As such we'd like to request help of anyone who may have any ideas regarding how to get those things actually enabled. Chances are these are locked somewhere in the exe, but my friend ain't good with assembly so that is out of his league.

Here's an infographic he made regarding what has to be done:
[](http://i.imgur.com/wMO9U38.jpg)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-07-19T21:20:13+00:00
- Post Title: [Help Wanted] Dragon's Dogma PC Item Restoration

Old-school mods! Whoop.

How have you verified the files are never loaded? They may be in memory in multiple places - can you modify existing items?

Also does this game have its own scripting language? Any logic in data anywhere?
## Post #3
- Username: SlowpokeVG
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 17, 2015 3:30 pm
- Post datetime: 2016-07-20T13:51:24+00:00
- Post Title: [Help Wanted] Dragon's Dogma PC Item Restoration

> Reply from WRS
>
> Old-school mods! Whoop.

How have you verified the files are never loaded? They may be in memory in multiple places - can you modify existing items?

Also does this game have its own scripting language? Any logic in data anywhere?

File with item info is in memory, since it contains information about all weapons and items.
When I change, for example, weight of an item in that file, after re-loading it gets changed in game.
Said file also contains right info about cut items, such as type of item and weight, but neither game, nor cheatengine script don't check that info and game outputs a placeholder info instead (cheatengine doesn't update info and shows up previous value instead, and not a placeholder). Game retrieves item description and item name with no problems.
I believe cheatengine uses same information as a game, to decide whether or not it should check item weight and class, but I don't know neither ASM, nor how cheatengine scripts work, so I can't find it.
Item resources, such as model are not loaded in memory, they get loaded on demand.

FluffyQuack, who made an unpacker for MT Framework games, said that game scripts usually have XFS format, but I couldn't find them, or anything that looks like scripts.

I doubt game stores info about which items to "disable" in .exe, but I don't even know from which file game can get it, so looking in game memory for a file sounds like a good idea. At least to me.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-07-20T15:22:57+00:00
- Post Title: [Help Wanted] Dragon's Dogma PC Item Restoration

This is the same engine used for Resident Evil 5. I more familiar with the older MTFramework engine but still, most of the concepts in terms of in-game guis are the same.

It could be that there's a file defining properties for which thumbnails of each items are shown in the menus. Each entry should have their own unique name which corresponds to a pre-defined string within the executable. Perhaps jumping to the region which loads these strings will lead to clues as to how they've been disabled in the menus. Alternatively, it's possible there's an array of item ids stored in the memory which would need to be altered. 

I hope it helps.
Cheers.
## Post #5
- Username: atom0s
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Sep 27, 2014 4:19 pm
- Post datetime: 2016-07-20T19:37:20+00:00
- Post Title: [Help Wanted] Dragon's Dogma PC Item Restoration

Removed. (Find this info on my personal site or on Zenhax.)
## Post #6
- Username: atom0s
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Sep 27, 2014 4:19 pm
- Post datetime: 2016-07-20T20:11:54+00:00
- Post Title: [Help Wanted] Dragon's Dogma PC Item Restoration

Removed. (Find this info on my personal site or on Zenhax.)
## Post #7
- Username: SlowpokeVG
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 17, 2015 3:30 pm
- Post datetime: 2016-07-24T23:44:46+00:00
- Post Title: [Help Wanted] Dragon's Dogma PC Item Restoration

> Reply from atom0s
>
> Just peeked at the game for a minute. In terms of where the item list is loaded, here is a direct pointer:
[[[ddda.exe+14F6434]+110]+60]

This will point to the itemList.itl after the game loads it. If you want to look at how the game loads it, you can find that in:
Code: Select allint __usercall sub_45CEF0@<eax>(int a1@<esi>)

You can unpack the games main exe with my Steamless project here:
https://gitlab.com/atom0s/Steamless

This will let you fully analyze the game executable without the protection in place. 

Overall it looks like the file is just loaded directly, so the limitations could be a bitmask preventing the items from working properly or a block in another function that limits the item ids range or something. I've never played the game so I'm not sure how things work in terms of the item system and such to know what to look for directly. But maybe this bit of info can help.

Thank you for that program, but after almost a week of searching I couldn't find anything that could prevent game from looking into that part of a memory. Looks like I'm very bad at assembler.

Here's a code from that Cheat Engine script, can anybody, please, tell me what prevents it from checking that part of memory? I hope that will bring me closer to adding items back.
[http://pastebin.com/NPBg42zU](http://pastebin.com/NPBg42zU)
## Post #8
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2016-08-01T22:10:05+00:00
- Post Title: [Help Wanted] Dragon's Dogma PC Item Restoration

Bumping for interest.

We really need a hand with this, so if anyone has ideas please do help us.
## Post #9
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-08-01T22:59:41+00:00
- Post Title: [Help Wanted] Dragon's Dogma PC Item Restoration

> Reply from Panzah
>
> Bumping for interest.

We really need a hand with this, so if anyone has ideas please do help us.

can you upload itemList.itl? i don't have the game either but want to take a look at the format anyway.

also (silly question), but what ids are you assigning new items? on the nexusmod page, the item list has a suspicious "used" value of 1902 which could easily be the max/count/total size of an enum table in the exe.

edit this is the item id list linked on the mod page - [http://pastebin.com/E7x4B2u9](http://pastebin.com/E7x4B2u9)
## Post #10
- Username: SlowpokeVG
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 17, 2015 3:30 pm
- Post datetime: 2016-08-01T23:19:58+00:00
- Post Title: [Help Wanted] Dragon's Dogma PC Item Restoration

> Reply from WRS
>
> 
can you upload itemList.itl? i don't have the game either but want to take a look at the format anyway.

also (silly question), but what ids are you assigning new items? on the nexusmod page, the item list has a suspicious "used" value of 1902 which could easily be the max/count/total size of an enum table in the exe.

edit this is the item id list linked on the mod page - http://pastebin.com/E7x4B2u9

Uploaded file from all platforms (PC, Xbox360 and PS3), but it's a simple format with a list of all items and parameters assigned to it.
I don't see anything that separates 'unused' items from usable in it, only stuff like weight and type of item.

I didn't change file ID, game allows me to spawn these weapons and armor in inventory by their old IDs.
For example, 549 Thousandlimbs and 550 White Hawk's Talon.
[item.zip](https://xentaxbackup.github.io/file/11448_item.zip)
## Post #11
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-08-01T23:23:11+00:00
- Post Title: [Help Wanted] Dragon's Dogma PC Item Restoration

just having a look at the save format which seems to serialize inventory items like this:

```
<s16 name="data.mNum" value="0"/>
<s16 name="data.mItemNo" value="-1"/>
<u32 name="data.mFlag" value="0"/>
<u16 name="data.mChgNum" value="0"/>
<u16 name="data.mDay1" value="0"/>
<u16 name="data.mDay2" value="0"/>
<u16 name="data.mDay3" value="0"/>
<s8 name="data.mMutationPool" value="0"/>
<s8 name="data.mOwnerId" value="0"/>
<u32 name="data.mKey" value="0"/>
</class>

```


will see what i make of your file



edit

hmm "itemList x360.itl" isn't useful at all!

where is the weight?
"Crossed Cinquedea" itemid 312 has a value of 0.18, but fir "Thousandlimbs" itemid 549 this value is 0.51  


edit 2

no luck with trying to locate the stats. currently trying to pair swords (here: [http://dragonsdogma.wikia.com/wiki/Swords](http://dragonsdogma.wikia.com/wiki/Swords)) with their ids (here: [http://pastebin.com/E7x4B2u9](http://pastebin.com/E7x4B2u9)).

not much luck. got this so far:

```

struct{
  uint32 Magic <format=hex>;
  uint32 Unknown;
  uint32 EntryCount;
  uint32 Unused;
}Header;

local uint EntrySize = (FileSize()-sizeof(Header))/Header.EntryCount;

//LittleEndian();

union{
  ubyte raw[EntrySize];

  struct{
    uint32 Unknown[16];
    int32 Un2;
    float Un3_f;
    int32 Un4;
    int32 Un5;
    int32 ItemID;
// 549 Thousandlimbs
// 312 Crossed Cinquedea
// 707	Devil's Nail XX
// 451 Almace 0.81
// 531 Cursed Bite
// 532 Cursed Light
    float Un7_f;
  }Item;

}Data[Header.EntryCount] <optimize=false>;


```
## Post #12
- Username: SlowpokeVG
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Nov 17, 2015 3:30 pm
- Post datetime: 2016-08-02T00:11:50+00:00
- Post Title: [Help Wanted] Dragon's Dogma PC Item Restoration

> Reply from WRS
>
> 
i can't find the "Crossed Cinquedea" itemid 312 in "itemList x360.itl". where is the weight for example? the closest value is 0.18, but for "Thousandlimbs" itemid 549 this value is 0.51
312 in HEX is 138, multiply in by 8 and you'll get 9C0, file starts with id hex value 7, so add 7 to 9C0 and search for 09C7, it'll appear at 9C4C.
(I may be wrong, but position in file appears to be same as position in PC file, so maybe it's a right way of searching for ID in xbox file)

Weight is at 9BD4, with float value 40351EB8 = 2.83.

Pardon me, when I made pic in first post, I thought weight appears after ID value, but it's actually before it.
