## Post #1
- Username: ice
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 12, 2019 1:24 am
- Post datetime: 2022-04-29T14:21:03+00:00
- Post Title: Ares Chronicles (PC) - unpacking Unity asset bundles

Ares Chronicle is a korean game
Use unity3d engine
Official website：[https://ac.zlongame.co.kr/](https://ac.zlongame.co.kr/)
My unpacked PC version
The first layer uses very simple packets, I decompress the packets using quickbms according to the UnityFS header information





When I couldn't open it with Assetstudio. I found that the unpacked file in hxd was also encrypted. I tried to decompile the dll again, and found that the dll was not encrypted.





I wonder if I can make a decryption script based on the dll file information, I am not too familiar with quickbms？

I upload a few files and dlls that I unpacked for the first time for reference


thank you very much

[https://drive.google.com/file/d/1nmh4Lz ... sp=sharing](https://drive.google.com/file/d/1nmh4LzYjc48HNZcNsur_pUuqNc7hUJ4h/view?usp=sharing)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-04-29T23:58:50+00:00
- Post Title: Ares Chronicles (PC) - unpacking Unity asset bundles

Hi. What script did you use to unpack those "packets"? Can you link it here?

Is PC version of this game free2play? Does it require payment or kerean ID verification to play?
## Post #3
- Username: ice
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 12, 2019 1:24 am
- Post datetime: 2022-04-30T03:26:46+00:00
- Post Title: Ares Chronicles (PC) - unpacking Unity asset bundles

Yes, of course

```
    goto OFFSET
    get DUMMY long
    findloc NEXT_OFFSET string "UnityFS" 0 ""
    if NEXT_OFFSET == ""
        get SIZE asize
    else
        math SIZE = NEXT_OFFSET
    endif
    math SIZE -= OFFSET
    string Name p "%s_%08x.unity3d" aRCNAME OFFSET
log Name OFFSET SIZE
    math OFFSET = NEXT_OFFSET
while NEXT_OFFSET != ""
```


The game is free
I'll upload a PC client later
## Post #4
- Username: ice
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 12, 2019 1:24 am
- Post datetime: 2022-04-30T04:05:41+00:00
- Post Title: Ares Chronicles (PC) - unpacking Unity asset bundles

> Reply from ikskoks ↑Sat Apr 30, 2022 7:58 am at Sat Apr 30, 2022 7:58 am
>
> 
Hi. What script did you use to unpack those "packets"? Can you link it here?

Is PC version of this game free2play? Does it require payment or kerean ID verification to play?

I have uploaded the full PC game！
<link deleted by moderator - uploading full games is not allowed here>
## Post #5
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-04-30T09:30:57+00:00
- Post Title: Ares Chronicles (PC) - unpacking Unity asset bundles

Thanks. I'll take a look at those files and I'll let you know when I find something useful.
## Post #6
- Username: ice
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 12, 2019 1:24 am
- Post datetime: 2022-04-30T17:06:42+00:00
- Post Title: Ares Chronicles (PC) - unpacking Unity asset bundles

Thanks
## Post #7
- Username: ice
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 12, 2019 1:24 am
- Post datetime: 2022-05-07T13:52:30+00:00
- Post Title: Ares Chronicles (PC) - unpacking Unity asset bundles

> Reply from ikskoks ↑Sat Apr 30, 2022 7:58 am at Sat Apr 30, 2022 7:58 am
>
> 
Hi. What script did you use to unpack those "packets"? Can you link it here?

Is PC version of this game free2play? Does it require payment or kerean ID verification to play?

any base？
## Post #8
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-05-07T20:27:59+00:00
- Post Title: Ares Chronicles (PC) - unpacking Unity asset bundles

I think you meant "Any news?"   


And yes, there is some progress, but not much. I've discovered that in this case assets are handled by "Zeus Framework"
and main logic is probably in file \Zeus.Framework.Asset\AssetBundleLoader.cs from decompiled source code.

But I hadn't too much time to analyze this format in detail.
## Post #9
- Username: ice
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 12, 2019 1:24 am
- Post datetime: 2022-05-14T20:11:59+00:00
- Post Title: Ares Chronicles (PC) - unpacking Unity asset bundles

> Reply from ikskoks ↑Sun May 08, 2022 4:27 am at Sun May 08, 2022 4:27 am
>
> 
I think you meant "Any news?"   


And yes, there is some progress, but not much. I've discovered that in this case assets are handled by "Zeus Framework"
and main logic is probably in file \Zeus.Framework.Asset\AssetBundleLoader.cs from decompiled source code.

But I hadn't too much time to analyze this format in detail.
OK
## Post #10
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-05-21T12:21:50+00:00
- Post Title: Ares Chronicles (PC) - unpacking Unity asset bundles

I've had a look at this and these Asset Bundles have a custom structure as well as the usual XOR cipher protection. Unlike most games which have some in-game logic to decipher bundles before loading them, these devs have actually modified the Unity Engine (UnityPlayer.dll) to natively support their changes.

Their custom header is 32 bytes with the standard "UnityFS" signature followed by 6 big endian uint32 fields i.e.

```
 {
    char Signature[8]; // "UnityFS"
    uint Field1;
    uint Field2;
    uint Field3; // null byte
    uint Field4;
    uint Field5;
    uint Field6;
 }

```


These field values are generated by using some elaborate bit twiddling that shifts, swaps and transforms the normal size, (un)compressedBlocksInfoSize and flag field bits. An example of decoding this can be seen [here](https://github.com/barncastle/AresChroniclesDumper/blob/master/AresChroniclesDumper/BundleConverter.cs#L104). Additionally, the compressed block info has an XOR cipher that uses a static [key ](https://github.com/barncastle/AresChroniclesDumper/blob/master/AresChroniclesDumper/BundleConverter.cs#L9) which can also be found within the modified UnityPlayer.dll.

However, as this is a custom structure, it is not just a matter of reversing these changes. You also need to rebuild each file with a proper Unity standard Asset Bundle header for it to be usable by normal tools.

I've created a tool to do just that. It extracts and converts each bundle so it can be opened with AssetStudio (and possibly Unity - I've not tested). You can find it [here](https://github.com/barncastle/AresChroniclesDumper), with a compiled binary under Releases. The BundleConverter class also contains (bad) example code to convert normal bundles to this customised format.

Also FYI, the _vfileIndexV2.fb file contains the names and offsets of each file within the blobs. There are also more files in the "%userprofile%/AppData/LocalLow/PerfectWorld" folder which is where updates and hotfixes get stored.
