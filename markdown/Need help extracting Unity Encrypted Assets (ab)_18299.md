## Post #1
- Username: sleepeatrepeat
- Rank: n00b
- Number of posts: 11
- Joined date: Wed May 16, 2018 1:57 pm
- Post datetime: 2018-06-30T12:48:00+00:00
- Post Title: Need help extracting Unity Encrypted Assets (*ab)

it's from an android japanese game called Abyss Horizon, can anyone tell me how to extract these files?
it is an Encrypted Unity Assets files in the form of (.ab), any help is appreciated!  thanks in advance  

[Battle.ab](https://drive.google.com/uc?id=1n5nXpH7frF4OWCHS4iF-4gaEESDWcA_v)

[Map.ab](https://drive.google.com/uc?id=1Q6G60dA2Yqljebqo-l_EteHvuEq1WgNV)
## Post #2
- Username: sleepeatrepeat
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-06-30T23:32:31+00:00
- Post Title: Need help extracting Unity Encrypted Assets (*ab)

only 0x1000 bytes of each file are encrypted.
the first 0x20 of the encrypted bytes are encrypted with a xor key of 0xA6.
this model 
 
is file AssetBundles/models/boats/130070.ab

the key for each file is not static for the 0xFE0 bytes
[mapconstconfig.7z](https://xentaxbackup.github.io/file/14534_mapconstconfig.7z)
## Post #3
- Username: sleepeatrepeat
- Rank: n00b
- Number of posts: 11
- Joined date: Wed May 16, 2018 1:57 pm
- Post datetime: 2018-07-01T09:23:19+00:00
- Post Title: Need help extracting Unity Encrypted Assets (*ab)

> Reply from chrrox
>
> only 0x1000 bytes of each file are encrypted.
the first 0x20 of the encrypted bytes are encrypted with a xor key of 0xA6.
this model 
 
is file AssetBundles/models/boats/130070.ab

the key for each file is not static for the 0xFE0 bytes

Could you explain how to decrypt them?  i'm not familiar with this kind of thing and can't do anything with your explanation (i'm dumb) lol.

thanks in advance
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-07-01T10:05:58+00:00
- Post Title: Need help extracting Unity Encrypted Assets (*ab)

I can't decrypt that section not sure what the key is.
## Post #5
- Username: sleepeatrepeat
- Rank: n00b
- Number of posts: 11
- Joined date: Wed May 16, 2018 1:57 pm
- Post datetime: 2018-07-01T10:12:45+00:00
- Post Title: Need help extracting Unity Encrypted Assets (*ab)

> Reply from chrrox
>
> I can't decrypt that section not sure what the key is.

but how did you get that unity3d file?
im using assetstudio to open up 130070.ab file but it doesn't load anything.
## Post #6
- Username: sleepeatrepeat
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-07-01T10:13:28+00:00
- Post Title: Need help extracting Unity Encrypted Assets (*ab)

dumped from ram.
## Post #7
- Username: sleepeatrepeat
- Rank: n00b
- Number of posts: 11
- Joined date: Wed May 16, 2018 1:57 pm
- Post datetime: 2018-07-01T10:15:16+00:00
- Post Title: Need help extracting Unity Encrypted Assets (*ab)

> Reply from chrrox
>
> dumped from ram.

ahh i see, well thanks for the answer i really appreciate it.
cheers man.
## Post #8
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2018-07-01T11:22:23+00:00
- Post Title: Need help extracting Unity Encrypted Assets (*ab)

> Reply from chrrox
>
> dumped from ram.

Hi chrrox, could you show me how to dump files from ram on Android device? I want to have a look in some files in this game  Thank you
