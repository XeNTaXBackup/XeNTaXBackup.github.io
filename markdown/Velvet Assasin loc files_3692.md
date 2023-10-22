## Post #1
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2009-09-01T19:58:48+00:00
- Post Title: Velvet Assasin loc files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2009-11-18T00:34:35+00:00
- Post Title: Velvet Assasin loc files

Each .loc file has the following structure:

```
long signature 0x061c

>>for each file:
long sn_size
char string_name[sn_size]
long sv_size
wchar_t string_value[sv_size]

char container 'B'
```


String names look like:

> GAMEPLAY_EVENTS\DOOR_LOCKED
>
> GAMEPLAY_INTERACTIONS\ALARM_DESTROY
>
> KEYBOARD_LAYOUT\KEY_0

String values look like:

> The door is locked.|(no audio)|

Some strings values have other data:

> Anymore questions?|Snd/vox.fev;enemies/dialogues;nazi_dialogue_any_questions|

Some values are also multi-line.

Hope this helps.
## Post #3
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-11-18T15:25:13+00:00
- Post Title: Velvet Assasin loc files

```

```


This is the number of strings in the file.
## Post #4
- Username: Slaii
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jun 26, 2006 2:28 am
- Post datetime: 2009-11-22T09:20:22+00:00
- Post Title: Velvet Assasin loc files

Hi
Severals months ago I wrote simple text extractor and packer for these .loc files [.loc <-> .txt]

Extracting works fine, but there is little problem with packing back texts to .loc file - game crashes.

Anyway if you are still interested in this you can use/modify/whatever included source

It's coded in C++ as M$ Visual Studio solution, but you can use whatever IDE to compile it...
Comments are in Slovak language, but if you have at least a little C++ experience you can understand the code

Hope it helps...
[VelvetAssassin.zip](https://xentaxbackup.github.io/file/2542_VelvetAssassin.zip)
