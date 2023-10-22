## Post #1
- Username: shorewake
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Feb 16, 2023 9:37 am
- Post datetime: 2023-07-29T00:57:58+00:00
- Post Title: Hana to Taiyou to Ame to (.bin) PS2

Is there any QuickBMS script for Hana to Taiyou to Ame to (Flower Sun and Rain) .bin files? Most scripts I've tried already didn't work. Thanks, Samples: [https://www.mediafire.com/file/216x0cav ... s.zip/file](https://www.mediafire.com/file/216x0cav9yu0eta/FSR+Samples.zip/file)
## Post #2
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2023-07-29T15:55:07+00:00
- Post Title: Hana to Taiyou to Ame to (.bin) PS2

BMS script for your sample:

```

IDstring "LF"
get FILES short
for i = 0 < FILES
	get OFFSET long
	get SIZE long
	math OFFSET * 0x800
	string NAME p "FILE%04d." i
	log NAME OFFSET SIZE
next i

```
