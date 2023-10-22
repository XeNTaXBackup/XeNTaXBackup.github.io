## Post #1
- Username: avarshinah
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 15, 2011 8:59 am
- Post datetime: 2011-03-15T01:22:07+00:00
- Post Title: Left Behind: ROTA .pak files

I got the new Left Behind game and I'm trying to extract files from the sound.pak file. This is really bugging me because I managed to do it with the previous instalment, but can't remember how the heck I did it!

I saw a couple of other threads on this forum from a few years ago about LB: Eternal Forces saying that the .pak files were basically XORed .zip files?

[viewtopic.php?f=11&t=2234&p=19315](http://forum.xentax.com/viewtopic.php?f=11&t=2234&p=19315)
[viewtopic.php?f=10&t=2346&p=19220](http://forum.xentax.com/viewtopic.php?f=10&t=2346&p=19220)

However, I'm either doing something wrong (likely, because I've never done this before and I'm basically messing around in the dark because I don't understand any of it) or there's something different about the LB: ROTA files. 

I've got a variety of .pak extractors and decompression software, none of which is working. I also have a couple of hex editors (UltraEdit and FlexHex) but don't really know how to XOR. FlexHex has a 'bitwise' edit function so I tried using that to XOR everything to 0x8c (from what I could understand) but then I saved the file and it still wouldn't open.

I've got Aluigi's XOR tool but it won't run at all for some reason.

Also have QuickBMS, if that's any help, but no idea what I'm doing with it.

If someone could give a total n00b step-by-step instructions on how to XOR in UltraEdit and/or FlexHex, or tell me if there's some special way of getting Aluigi's XOR tool to run, I'd be incredibly grateful! In the meantime I'm in the process of uploading the .pak file but it's taking a while so I thought I'd ask this in the meantime.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-15T09:12:30+00:00
- Post Title: Left Behind: ROTA .pak files

xor.exe is a command-line tool so if you double click on it is normal that it doesn't work :)
while for quickbms you can use the following script:

```
get NAME basename
string NAME += ".zip"
filexor 0x8c
log NAME 0 SIZE
```
## Post #3
- Username: avarshinah
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 15, 2011 8:59 am
- Post datetime: 2011-03-15T11:19:16+00:00
- Post Title: Left Behind: ROTA .pak files

Ohhh that explains it. Thanks, I managed to get your XOR program to work, no problem   and it did the trick!
