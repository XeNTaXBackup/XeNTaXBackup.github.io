## Post #1
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2016-10-30T23:52:43+00:00
- Post Title: Burnout 3 .BGV format

Dear forums,

 I know that a quick BMS script was written for this game sometime ago but it cannot completely decode the vehicles of this marvelous game. Bellow is a sample file for one of the cars. what is know is that some of the vertex data is in the .BGV file but what comes out of the extraction is missing a lot that should come with a full decoding. thank you for your time.

[https://www.mediafire.com/?10h6xbl7ejzp3re](https://www.mediafire.com/?10h6xbl7ejzp3re)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-11-03T13:14:26+00:00
- Post Title: Burnout 3 .BGV format

not sure which bms script you're talking about, maybe Burnout3BGVto3ds.bms

So there were times  when I struggled with funny scripts containg things like
"foxcount, fivfiv, werefox, fafterafter, Snake, Dragon" but now I'm too old for wasting my time with such.  

Quickest approach I could think of would be to convert the 3ds file to obj, with groups.

Dividing it into submeshes with 750 faces each gives such:



car5_750.JPG (84.23 KiB) Viewed 282 times



Maybe not the best solution but since I didn't find uvs in the 3ds file (no serious search, though)
it may not be worth to take pains.
## Post #3
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2016-11-03T13:40:57+00:00
- Post Title: Burnout 3 .BGV format

> Reply from shakotay2
>
> not sure which bms script you're talking about, maybe Burnout3BGVto3ds.bms

So there were times  when I struggled with funny scripts containg things like
"foxcount, fivfiv, werefox, fafterafter, Snake, Dragon" but now I'm too old for wasting my time with such.  

Quickest approach I could think of would be to convert the 3ds file to obj, with groups.

Dividing it into submeshes with 750 faces each gives such:
car5_750.JPG

Maybe not the best solution but since I didn't find uvs in the 3ds file (no serious search, though)
it may not be worth to take pains.

 hmmm interesting and yeah I that is the script I was using with my son (we are both hugh burnout fans) I'll take your advice to heart and he and I shall continue working with what we can get. I thank you for taking the time to check it out. it's much appreciated.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-11-03T15:34:43+00:00
- Post Title: Burnout 3 .BGV format

edit: not to confuse late time readers  
I loaded the CAR5.BGV.1.3ds into hex2obj here!

The .3ds resulted from extracting [PS2] CAR5.BGV with Burnout3BGVto3ds.bms, created by FurryFan, afaik.

with this said:
to find the start addresses of the submeshes in the .3ds file you  might try out hex2obj
(pay attention to the 2 in the red circle which simply means that two zero bytes in the face indices list are being skipped for each 3-index-face)

The white arrow points to the assumed 2nd submesh (SM). I didn't care for it.

To find the 3rd submesh you need to calculated as this:
next face indices address: 0x2247C + (1500 x 3 x 4) = 0x2247C + 0x4650 = 0x26ACC (parenthesis values are decimal)
which reveals a vertex count of 2322.

Effectively 357 vertices are being displayed (since we don't start from FI=1 but 1966).



car5_3ds.JPG (191.57 KiB) Viewed 279 times


You can increase the FIs' count of the 3rd SM to 2500 and watch whether the chassis SM  "improves" or another submesh "floats in".

btw: I did a typo, it's 1500 x 2 x 4 (because we have word indices) so you have to recalculate the FIs' start address for the 3rd submesh


btw: the script is very similar to WildArms3eememoryto3ds.BMS so it should be possible to get uvs, too
(the latter script didn't provide uvs by default, though, iirc).
