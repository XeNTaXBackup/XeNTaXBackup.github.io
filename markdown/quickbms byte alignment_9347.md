## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-24T21:10:04+00:00
- Post Title: quickbms byte alignment

Lol byte alignment has always gotten me.

The archive I'm working with stores null-terminated strings that are byte-aligned to the nearest 4 bytes.

So if the string is 9 chars (including the null-byte), it will take up 12 bytes to store.
If it takes 8 chars, it just takes 8 bytes.

The current way of parsing is just to save the current position, read the string, save the current position, do math to get the string length, and then read some extra bytes to cover the alignment.

Is there a better way?
## Post #2
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-07-24T23:00:01+00:00
- Post Title: quickbms byte alignment

Wow, that's a retarded way to store strings; it offers absolutely no space savings over just saving the byte length of the string (and since, on average, the string field will overrun the actual string length, it ends up using *more* space in most cases).
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-24T23:50:17+00:00
- Post Title: quickbms byte alignment

QuickBMS doesn't have anything to read byte-aligned strings?
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-25T01:47:45+00:00
- Post Title: quickbms byte alignment

> Reply from Dinoguy1000
>
> Wow, that's a retarded way to store strings; it offers absolutely no space savings over just saving the byte length of the string (and since, on average, the string field will overrun the actual string length, it ends up using *more* space in most cases).

They're just losing at most 3 bytes per string it's cool.
The retarded part is when they're duplicating the string for no seemingly good reason so that in every entry the same string appears twice
## Post #5
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-25T02:08:38+00:00
- Post Title: quickbms byte alignment

you would be surprised how bad some games are coded... how inefficient or silly they sometimes do things. for example, saints row third, all spaceship models use a vertex format that has 0xFF 0x00 0x00 0x00 for weights and 0x00 0xFF 0xFF 0xFF for bone indices. Takes 20,000 vertices and that's 40 KB of waste for something where all points are equally weighted and there is only one bone. Why use bones and weights at all? Why not just use another vertex format instead?
## Post #6
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-07-25T02:40:30+00:00
- Post Title: quickbms byte alignment

> Reply from howfie
>
> you would be surprised how bad some games are coded... how inefficient or silly they sometimes do things.
Not really, game development is a very weird world. For instance, I don't know about modern games, but back when memory constraints were super-tight, it apparently wasn't all that unusual for a senior/experienced developer to make the game allocate a block of memory that never got used and that the rest of the dev team didn't know about, so that if the deadline was looming and the team couldn't get memory usage under the target, said dev could just comment out the allocation for that block of memory and poof, the game meets the memory target and can ship on time (and of course the rest of the dev team would then hold that dev in awe for fixing something in five minutes that the rest of them had spent days or weeks on in vain, but it's not like that was ever a reason for using that technique...[/snipe]).

> Reply from finale00
>
> Dinoguy1000 wrote:Wow, that's a retarded way to store strings; it offers absolutely no space savings over just saving the byte length of the string (and since, on average, the string field will overrun the actual string length, it ends up using *more* space in most cases).

They're just losing at most 3 bytes per string it's cool.
Until you consider the total number of strings and the average length of each string. If a game has 10,000 strings at an average length of 25 bytes per string (pulled those figures out of my ass, so they probably don't reflect reality in any way), that means that, on average, each string requires 29 bytes of storage space (28 bytes for the string itself in 4-byte blocks, and one byte for the number of blocks); this adds up to 290k space required to store the strings. If a byte length format is used to store them instead, average length per string drops to 26 bytes (25 for the string and 1 for the string length), or 260k overall - a reduction of 30k in size, or over 10% less used space.

Of course, then you have devs turning around and doing stupid things like duplicating every string, which completely destroys any savings that might be gained from optimizing the storage format.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-25T03:28:25+00:00
- Post Title: quickbms byte alignment

Ok so I did some math.

```

```


```
math strlen = END
math strlen -= BEGIN

# modulus 4
math rem = nameLen
math rem %= 4

# now put it all together
math pad = 4
math pad -= rem1
math pad %= 4

```


And that gives me my padding that I should add. 7 commands to evaluate that simple expression!

 

Maybe I am not breaking down the expression properly.
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-25T16:08:32+00:00
- Post Title: quickbms byte alignment

isn't the Padding command enough for this job?
padding 4

note that the alignment calculation is made from offset 0.
the math command has the 'x' operator that does alignment works, for example:
math TMP = 7
math TMP x= 4
print "%TMP%"
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-27T01:12:47+00:00
- Post Title: quickbms byte alignment

Oh.

Lol that makes things easier
