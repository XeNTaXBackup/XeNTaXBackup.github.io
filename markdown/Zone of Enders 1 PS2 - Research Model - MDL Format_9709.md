## Post #1
- Username: denetsu
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 05, 2010 2:03 pm
- Post datetime: 2012-10-03T21:26:24+00:00
- Post Title: Zone of Enders 1 PS2 - Research Model - MDL Format

Good for all. At this moment I am investigating (practicing a bit) file format for the game Zone of Enders (the first) for PS2. I've been able to locate the bytes of the models. HOWEVER for more I try to separate the bytes and get patterns, I find it very difficult to get a consistent pattern of 3 floating numbers.

This is what I have been able to achieve so far.


[ZOE_jehuty.rar](https://xentaxbackup.github.io/file/5876_ZOE_jehuty.rar)
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-10-05T09:11:24+00:00
- Post Title: Zone of Enders 1 PS2 - Research Model - MDL Format

Did you manually extract the file through hex? It looks like the end has parts of another model.

It needs to be extracted properly, i already figured some stuff out already but it's useless with just 1 sample.
## Post #3
- Username: denetsu
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 05, 2010 2:03 pm
- Post datetime: 2012-10-05T13:10:40+00:00
- Post Title: Zone of Enders 1 PS2 - Research Model - MDL Format

Yes. 

First, i was digging through the ram extracted by emulator PCSX2 in the savestate, but the strange thing is that after the name of many models (which could be seen on the screen at the time I made the catch) you could find the word init.pak (this not hapened in the ISO). It was as if they were group by a package or something. HOWEVER, I realized that digging in the ISO, you could find models not encrypted nor compressed. Just need to open the ISO with the hex editor and search all terminations. mdl.

Attach guess what is one of complete models. After the last byte begins the name of the next model.

Attached is an example with 3 models (in theory).

Ah! And the model viewer or extracter it's no problem. I can do it easily if i figure out the bytes order.
[ZOE_3_MODELS_ISO.rar](https://xentaxbackup.github.io/file/5879_ZOE_3_MODELS_ISO.rar)
## Post #4
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-10-06T12:21:17+00:00
- Post Title: Zone of Enders 1 PS2 - Research Model - MDL Format

Great news,I hope finally this format will be converted properly....for Zoe and Zoe 2 maybe
## Post #5
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-10-08T23:54:32+00:00
- Post Title: Zone of Enders 1 PS2 - Research Model - MDL Format

What are you doing? You said that the .mdl files are all separate in the .ISO so upload them, why have you just pasted 3 models into a .bin file that's just useless. If you want this to work you need the original files all unpacked. You're just confusing people by providing the wrong files.
## Post #6
- Username: denetsu
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 05, 2010 2:03 pm
- Post datetime: 2012-10-09T00:15:32+00:00
- Post Title: Zone of Enders 1 PS2 - Research Model - MDL Format

> Reply from C00L12345
>
> What are you doing? You said that the .mdl files are all separate in the .ISO so upload them, why have you just pasted 3 models into a .bin file that's just useless. If you want this to work you need the original files all unpacked. You're just confusing people by providing the wrong files.

No sorry, i guess I explained wrong. The files are not separated physically in the ISO, even more, the only way to explore is to hexadecimal level. If you extract the contents of the ISO manually (eg with winrar) you will not find anything useful. You asked me a file with more examples. So I put a post with three consecutive files in a row within a BIN file. In the first post you have one model alone.

In what else I can help you?
