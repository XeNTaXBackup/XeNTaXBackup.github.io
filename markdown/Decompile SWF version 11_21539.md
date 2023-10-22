## Post #1
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2019-12-27T20:22:03+00:00
- Post Title: Decompile SWF version 11

The game in question is made by Gameloft, and the compiled SWF seem to be of version 11. The are a lot of UI's made of SWF, but they all seem to use library.swf and mainUI.swf files. The final goal I have in mind is to write my own UI but making it working as if it was the original. From what I understand, SWF files call game methods via some API, and I believe I can see the names in SWF file, but I'm not certain. I tried [JPEXS Decompiler](https://github.com/jindrapetrik/jpexs-decompile), but I don't have "Scripts" tree node in the result. Searching through the web only gives me very old results for old Flash version. Are there any up-to-date tools that can help me? Or what do I need to do/to research to achieve my goal?

Sample files: [https://www.mediafire.com/file/y4qyxhfk6279ksx](https://www.mediafire.com/file/y4qyxhfk6279ksx)
## Post #2
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2020-03-28T12:05:42+00:00
- Post Title: Decompile SWF version 11

Alright, so deciding to look into this again after a break, I was able to parse the SWF with [swf-parser](https://github.com/open-flash/swf-parser) lib, as well as 010 Editor SWF template from their repository, which turned out to have a bug that prevented me from parsing it at the time of the first post. 

Anyway, I was hoping to see the byte-code (ABC) somewhere in the SWF tags, but the samples I checked don't have it. Instead, they have a tag of type = 300, which contains a lot of binary data (see screenshot). Googling the first bytes seem to reveal that this tag should actually be a byte-code, however
if I use a disassembler tool like [Flazzy](https://github.com/ArachisH/Flazzy), it errors at runtime because either the code is invalid ABC, or it has some unsupported format. Any suggestions?
[swf.png](https://xentaxbackup.github.io/file/17823_swf.png)
## Post #3
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2020-03-28T21:55:49+00:00
- Post Title: Decompile SWF version 11

So this turned out to be the byte-code, however with the help of Flazzy I was able to figure out 

At 0x12 you can see that there are 5 params, and 0x1b tells us that 7 of them are optional, which is totally nonsense because

> ...The number of optional parameters is given by option_count, which must not be zero nor greater than the parameter_count... (from [official documentation, par. 4.5.1](https://www.adobe.com/content/dam/acom/en/devnet/pdf/avm2overview.pdf)).

Attached screenshot shows the method infos block (0x0 byte indicates methods count). Any ideas what's actually going on here?
[swf.png](https://xentaxbackup.github.io/file/17827_swf.png)
## Post #4
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2020-08-12T22:31:04+00:00
- Post Title: Decompile SWF version 11

Another round of playing around after some time and I've got some nice progress. Turns out that a few major structures are complying with the AVM2 specification: constants pool and method bodies. However methods bodies list required minor change:
1. There is no structs count field.
2. Method body structure has one extra field at the beginning - method index
3. First method body index _is_ the total structs count.

In the screenshot below the top green selection is constants pool , the bottom selection is method bodies, with the byte code in gray. The `0x2F` indicates amount of methods (as can be seen both at `0x04A8` and `0x06DF`).



automove.png (128.97 KiB) Viewed 67 times



The middle uncolored part on the left _should_ contain description for the following structs:
1. Methods info
2. Metadata
3. Instances info
4. Classes info
5. Scripts info

Still a lot, right? Now watch this: using the following (actually quite straightforward) struct I was able to parse the weird pattern in the bottom middle:

```
    EncodedU32 count <bgcolor=0x00FFFF>;
    EncodedU32 values[count.value] <bgcolor=0xDDDDDD>;
};

FSeek(0x585);
EncodedU32 count <bgcolor=0x00FF00>;

local int i;
for (i = 0; i < count; i++) {
    Test test;
}

```


Results you can see on the right side of the screenshot on top.

Given that this is a custom tag and that this structure is not similar to any of the missing ones, I assume some of the structs (like Metadata) was completely removed, but  How do I proceed with parsing the middle part?

Last but not least, if I were to parse the middle part as required, starting with Methods info, it would overlap the right Test structure.
## Post #5
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2020-08-12T23:18:57+00:00
- Post Title: Decompile SWF version 11

Almost solved! The `method_info` structures are actually still missing (at least in the form described by docs), but 2 bytes away I found unchanged `Instances` and `Classes` description, which you can see on screenshot.



automove almost.png (82.18 KiB) Viewed 65 times



The yellow `2F 00` are what were giving me troubles. `2F` is a count (probably of `methods_body` structs count) with a trailing zero padding (likely), followed by `Instances` in cyan and `Classes` in green. The orange part is unchanged `Scripts` definition.

The gray part is still unknown. I doubt it's anything like metadata, so my best bet is these are `method_info` structures which in docs is described as follows:

```
    u30          param_count
    u30          return_type
    u30          param_type[param_count]
    u30          name
    u8           flags
    option_info  options
    param_info   param_names
}

```


Guess I'm actually finally stuck again here
## Post #6
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2020-08-15T10:18:39+00:00
- Post Title: Decompile SWF version 11

Case solved! Turned out this structure is actually 95% compliant with official specs with some small changes.

First change is the order of structures. AVM2 specification states that the following order is expected:

```
ConstantsPool
Methods
Metadata
Instances
Classes
Scripts
MethodBodies

```

and the game SWF has following order:

```
ConstantsPool
UnknownCount <-- extra u30 field which seems to hold the same value as method count, but the usage is unknown
Metadata
Instances
Classes
Scripts
Methods
MethodBodies

```


Another difference applies to Method and MethodBody structs, where devs added data size field before the struct and after index field respectively.
