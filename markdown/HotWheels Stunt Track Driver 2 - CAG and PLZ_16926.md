## Post #1
- Username: Matsilagi
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Aug 31, 2014 12:39 pm
- Post datetime: 2017-08-26T17:11:31+00:00
- Post Title: HotWheels Stunt Track Driver 2 - CAG and PLZ

Im trying to rip this game's car models and textures to be used in other games (especifically ReVolt)

I've managed to get their meshes with dgVoodoo and NinjaRipper, but i lack the textures, in which i think its inside either one of those files
Do you guys think you can help me with it?

[https://mega.nz/#!vRxXUR6C!NVmtBESuvLM1 ... Lw_3QTndT4](https://mega.nz/#!vRxXUR6C!NVmtBESuvLM1AQFjEh7jHGtGEXQDw8UmnLw_3QTndT4) (cars.cag)

[https://mega.nz/#!6Vwx1IoC!Y9TvA_o2gD4B ... y51FkbgQBA](https://mega.nz/#!6Vwx1IoC!Y9TvA_o2gD4B8oXghNDad_8AqPJUSJrPBy51FkbgQBA) (win.plz)
## Post #2
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2017-08-27T15:37:25+00:00
- Post Title: HotWheels Stunt Track Driver 2 - CAG and PLZ

QuickBMS script to extract the CAG file:

```

for i = 0 < FCOUNT
	getdstring NAME 0x20
	get OFFSET long
	get SIZE long
	get FIVE long
	log NAME OFFSET SIZE
next i
```
## Post #3
- Username: Matsilagi
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Aug 31, 2014 12:39 pm
- Post datetime: 2017-08-28T04:01:56+00:00
- Post Title: HotWheels Stunt Track Driver 2 - CAG and PLZ

Thanks a lot! Just gotta find a way to open them
Even if its says they are simple TGA and LWO files, no programs can open them, but i'll see if i can figure that. Thanks for the extraction.
