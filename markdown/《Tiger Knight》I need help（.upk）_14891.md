## Post #1
- Username: m545891031
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Jul 21, 2016 4:04 am
- Post datetime: 2016-08-19T11:00:25+00:00
- Post Title: 《Tiger Knight》I need help（.upk）

《Tiger Knight》 is a "and《Mount & Blade》 similar instant pass game
Game model is great, but I can't use UDK to extract them.
Is there any tools to extract it? I need help
Game:[http://steamcommunity.com/sharedfiles/f ... =230422589](http://steamcommunity.com/sharedfiles/filedetails/?id=230422589)


 upk.zip
(181.7 KiB) Downloaded 38 times
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-08-19T15:38:49+00:00
- Post Title: 《Tiger Knight》I need help（.upk）

Looks like part of the header is XORed.
## Post #3
- Username: m545891031
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Jul 21, 2016 4:04 am
- Post datetime: 2016-08-20T09:54:46+00:00
- Post Title: 《Tiger Knight》I need help（.upk）

> Reply from Gh0stBlade
>
> Looks like part of the header is XORed.
Yes, you have successfully extract?
## Post #4
- Username: m545891031
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Jul 21, 2016 4:04 am
- Post datetime: 2016-08-29T18:51:44+00:00
- Post Title: 《Tiger Knight》I need help（.upk）

> Reply from m545891031
>
> Gh0stBlade wrote:Looks like part of the header is XORed.
Yes, you have successfully extract?

Can someone help me to look at these files?
## Post #5
- Username: ysjysj734
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Mar 26, 2023 11:01 pm
- Post datetime: 2023-05-29T00:11:21+00:00
- Post Title: 《Tiger Knight》I need help（.upk）

Is there a way to extract it
## Post #6
- Username: nhatvpo
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Jul 12, 2015 5:41 pm
- Post datetime: 2023-05-29T06:52:02+00:00
- Post Title: 《Tiger Knight》I need help（.upk）

i think it mean no  nice armor to mod game but
## Post #7
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2023-05-29T11:21:11+00:00
- Post Title: 《Tiger Knight》I need help（.upk）

It is a simple xor, but the subsequent data format differs from standard UE3. Compressed?
I don't know how to decompress it, as I can't find any magic about compression.
## Post #8
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-05-29T13:14:07+00:00
- Post Title: 《Tiger Knight》I need help（.upk）

It's standard UE3, they're just xoring data on per variable basis, which causing xor to shift on strings. Attached script should work for most packages, except those with only single asset insluded (header format would be different there).

Result: [https://imgur.com/q4uVT4w](https://imgur.com/q4uVT4w)



 tiger_knight_upk.zip
(443 Bytes) Downloaded 28 times
## Post #9
- Username: ysjysj734
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Mar 26, 2023 11:01 pm
- Post datetime: 2023-05-30T03:11:26+00:00
- Post Title: 《Tiger Knight》I need help（.upk）

This is really great. Thank you for providing the script
