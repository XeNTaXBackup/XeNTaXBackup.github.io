## Post #1
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-01-14T02:58:44+00:00
- Post Title: Dark Souls Reverse Engineering

Hi everybody, first time posting on these forums ^-^v
I have a bit of history of reverse engineering video games, using tools such as IDA, ollydbg, various hex editors, and visual studio (to write my tools). I finally got around to trying my hand at Dark Souls, and I see that there's a few folks on these forums that are pretty knowledgeable on the file formats used by the game.

I'm interested in chatting with anybody who's got some experience inside Dark Souls' code. Being that I've only started a little while ago, I have very little of the executable documented yet, so I'm hoping I might be able to get some notes from somebody to help me avoid having to rediscover what's already been discovered.

Specifically, I'm interested in data pertaining to IDA - does anybody have experience loading Dark Souls into IDA? I'd love to get some function names/offsets to save me some time! I'm particularly interested in the file access code, such as reading archives, accessing subarchives, decompressing data, and deserializing individual file data.

As a side note/disclaimer: I know that there's already threads available here that provide scripts for extracting the files, etc.. That's not what I'm looking for- I want to poke inside the assembly of the executable itself.
## Post #2
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-01-27T23:43:11+00:00
- Post Title: Dark Souls Reverse Engineering

Who wants to do some repacking?   

[](http://imageshack.us/photo/my-images/841/2013012700001p.jpg/)

(WIP)
## Post #3
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-01-28T07:21:03+00:00
- Post Title: Dark Souls Reverse Engineering

I would like to localize this game. However on X360....
## Post #4
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-02-16T01:12:45+00:00
- Post Title: Dark Souls Reverse Engineering

So to help really get down to the nitty gritty of how these archives work (specifically to help with re-creating them), I've started mapping of a bunch of the code.

Some general comments about what I've noticed, and am working on:

I've run some of my scripts against the executable to get a partial view of the class hierarchy via the RTTI and virtual file tables- this has shown me a lot of their internal class names, as well as some of the internal class hierarchy, and also has shown me that they're using some of the classes from the std namespace.
The lack of supporting DLLs and a few other pieces of info in the code have lead me to believe that they've statically linked some of the more useful IO classes from std (such as stdi::basic_filebuf), and I've been spending some time mapping out the code of some of these classes to give me a good foothold for really sinking my teeth into the deserialization routines employed by Dark Souls.

Has anybody else done any of this before? Or has experience and wants to help out? This kinda stuff is always more fun when there's somebody to bounce ideas/information off of. ^-^
## Post #5
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-05-12T20:55:25+00:00
- Post Title: Dark Souls Reverse Engineering

I've finally managed to find some more useful areas inside the binary. This makes me quite happy, as it was becoming more of a chore I didn't want to do, rather than a hobby I wanted to pursue, trying to just get to the point where I'm looking at code I actually care about. This'll help a lot with my understanding of how Dark Souls manages memory, so I can simulate that same model in my application.

For anybody who's interested, the code I'm dealing with is inside the DLBinder5FileDevice and DLBinder5FileOperator classes, and one of the interesting functions I found was at offset text:0x00BDAF50 (in IDA Pro). I'm calling this function CalculateHashForFilename. It's just a simple function that takes a filename and converts it into the hash used inside the archive files. In the case of the bhd5 files, they ONLY store hashes, but the other internal archives store the filename as well.

This validates my suspicions that those are the classes I want to focus on, and it also gives me a pretty good building block to work with while extending my assembly definitions into other interesting areas. Because of finding this function, I've got a few other interesting functions, but I haven't finished mapping them yet.

I'm pretty exciting going forward now, so I won't be putting off further reverse engineering of the game anymore, for the foreseeable future.
## Post #6
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-06-19T05:41:08+00:00
- Post Title: Dark Souls Reverse Engineering

So I've found some interesting structures for how the game handles file lookups. Based on how the data is structured in ram, and how the code accesses it (and by the data that's stored in it), I can only describe this discovery as a recursive lookup table for internal file paths.

It's basically a list of pairs of strings similar to the following:

* "dvdroot", "game:/"
* "game", "system:/"
* "material", "dvdroot:/testdata/"
* "system", "C:\Program Files (x86)\Steam\steamapps\common\Dark Souls Prepare to Die Edition\DATA\"

So what I surmise is the case, is that an asset can request a file at a location such as material:/mydata.dat, and the lookup table checks for what material (everything before the colon) is associated with. In this case, dvdroot:/testdata/. So now it has dvdroot:/testdata/mydata.dat. It then recurses into checking again for what dvdroot is associated with- this time it's game:/, so now it has game:/testdata/mydata.dat. Now it checks for game's association: system:/, so it's now got system:/testdata/mydata.dat. And finally it checks for system's association, which gives it C:\Program Files (x86)\Steam\steamapps\common\Dark Souls Prepare to Die Edition\DATA\testdata/mydata.dat. At this point, there is no C value (everything before the colon) in the lookup table, so it stops recursing.

This particular example ends with an absolute hard drive path, but the vast majority of them actually end with something such as dvdbnd0:/chr/, which I speculate is a virtual path into the archive file itself.

The full list, as it exists when you first arrive at firelink shrine (I'm not sure if it ever changes..)

```
animation	dvdroot:/testdata/
breakobj	dvdbnd0:/map/breakobj/
breakobj_dlc	breakobj:/
cap_EnvLightMap	capture:/EnvLightmap/
cap_breakobj	capture:/breakobj/
cap_dbgrep	capture:/dbgreport/
cap_event	capture:/event/
cap_mapstudio	capture:/mapstudio/
cap_param	capture:/param/
cap_scrshot	capture:/screenshot/
capture		N:/FRPG/data/CAPTURE/
chr		dvdbnd0:/chr/
chranibnd	dvdbnd0:/chr/
chranibnd_dlc	chranibnd:/
chresd		dvdbnd0:/chr/
chresdpatch	dvdbnd0:/chr/
chrflver	dvdbnd0:/chr/
chrhkx		dvdbnd0:/chr/
chrtpf		dvdbnd0:/chr/
config		dvdroot:/
dbgai		interroot:/script/ai/
dbgscript	interroot:/script/
debug		game:/
dvdroot		game:/
event		dvdbnd2:/event/
eventpatch	dvdbnd2:/event/
facegen		dvdbnd1:/facegen/
ffx		interroot:/sfx/effects/
ffxbnd		dvdbnd0:/sfx/
ffxbndpatch	dvdbnd0:/sfx/
ffxdebug	interroot:/sfx/debug/
ffxlua		interroot:/sfx/lua/
ffxmodel	interroot:/sfx/model/
ffxtex		interroot:/sfx/tex/
fmod		dvdbnd1:/sound/
fmod_dlc	fmod:/
font		dvdbnd1:/font/
game		system:/
interroot	N:/FRPG/data/INTERROOT_win32/
item		dvdbnd0:/item/
loadlist	dvdroot:/testdata/
luascript	dvdbnd2:/script/
luascriptpatch	dvdbnd2:/script/
map		dvdbnd0:/map/
map_dlc		map:/
mapflver	dvdbnd0:/map/
maphkx		dvdbnd0:/map/
mappatch	dvdbnd0:/map/
maptpf		dvdbnd0:/map/
maptpf_dlc	maptpf:/
material	dvdroot:/testdata/
menu		dvdbnd1:/menu/
menuesd		dvdbnd1:/menu/
menuesd_dlc	menuesd:/
menutex_dlc	menutexture:/
menutexpatch	dvdbnd1:/menu/
menutexture	dvdbnd1:/menu/
model		dvdroot:/testdata/
moveu		dvdroot:/moveu/
movjp		dvdroot:/movjp/
movna		dvdroot:/movna/
movww		dvdroot:/movww/
msb		dvdbnd0:/map/mapstudio/
msg		dvdbnd3:/msg/
msgpatch	dvdbnd3:/msg/
mtd		dvdbnd1:/mtd/
mtd_dlc		mtd:/
navimesh	dvdbnd0:/map/
obj		dvdbnd1:/obj/
objanibnd	dvdbnd1:/obj/
objflver	dvdbnd1:/obj/
objhkx		dvdbnd1:/obj/
objtpf		dvdbnd1:/obj/
other		dvdbnd1:/other/
other_dlc	other:/
param		dvdbnd3:/param/
paramdef	dvdbnd3:/paramdef/
parampatch	dvdbnd3:/param/
parts		dvdbnd1:/parts/
remo		dvdbnd0:/remo/
remobnd_dlc	remo:/
replay		capture:/Replay/
shader		dvdbnd1:/shader/
sndchr		dvdbnd1:/sound/
sndchr_dlc	sndchr:/
sndmap		dvdbnd1:/sound/
sndmap_dlc	sndmap:/
sndremo		dvdbnd1:/sound/
sndremo_dlc	sndremo:/
sound		dvdbnd1:/sound/
sound_dlc	sound:/
talkscript	dvdbnd2:/script/talk/
talkscriptpatch	dvdbnd2:/script/talk/
texture		dvdroot:/testdata/

```
## Post #7
- Username: heisecaibao
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon May 26, 2014 5:12 pm
- Post datetime: 2014-05-27T11:49:11+00:00
- Post Title: Dark Souls Reverse Engineering

> Reply from nyxo
>
> Who wants to do some repacking?   



(WIP)
Hi nyxo
I want to change the character animation, you tool support?
