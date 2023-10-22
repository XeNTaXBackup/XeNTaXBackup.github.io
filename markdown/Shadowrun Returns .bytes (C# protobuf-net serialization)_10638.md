## Post #1
- Username: dubh
- Rank: n00b
- Number of posts: 13
- Joined date: Mon May 23, 2011 4:34 pm
- Post datetime: 2013-07-28T01:30:01+00:00
- Post Title: Shadowrun Returns *.bytes (C# protobuf-net serialization)

Shadowrun Returns has a ton of serialized files that govern abilities, items, props, scripts, character sheets, AI rules, and much more. All of these files have a .bytes extension. Here's what gibbed had to say about these files:

> Reply from gibbed
>
> Someone was asking me about this on IRC, so I'll repeat (somewhat) what I told them. I don't have time to work on this myself, however, it is very possible to easily edit this data because it's a Unity game, which means their (compiled) C# code is exposed to the world.

All of the *.bytes files are simple binary protobuf blobs. In particular, they use protobuf-net.

In Shadowrun_Data\Managed, there is a .NET assembly named ShadowrunDTO.dll (DTO is probably "Data transfer object"). This assembly contains all of the types (or most) serialized to and from files using protobuf in the game.

For example, *.ab.bytes maps to isogame.AbilityDef, *.item.bytes maps to isogame.ItemDef, and so on.

One could easily write a tool that dynamically loads ShadowrunDTO.dll from a user's game directory and invoke protobuf-net to deserialize data, then straight up dump it to an editable file, perhaps using .NET's XmlSerializer. Later, read the human editable data and serialize it back out to a binary blob, again using protobuf-net.

Sadly protobuf-net does not support TextFormat. You could probably get around this by manually writing a protobuf definition for all of the data you are interested in, and writing a C++/Java tool to dump to TextFormat, if so desired. This also means the game needs protobuf binary blobs, it will not support TextFormat.I'm a novice with C#, but I tried to write a simple application that follows gibbed's logic. I failed and I've given up. I'm much better with hacking and adapting existing code. Anyway, gibbed says that such an application would be trivial to write for someone with more experience.

Anyone interested in trying their hand?
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-08-02T15:58:43+00:00
- Post Title: Shadowrun Returns *.bytes (C# protobuf-net serialization)

I have steam version and in game included editor. You can try it for editing .bytes files.

[Screen](http://imageshack.us/a/img7/7750/lyat.png)
