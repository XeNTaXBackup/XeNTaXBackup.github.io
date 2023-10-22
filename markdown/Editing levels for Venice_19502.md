## Post #1
- Username: bizzybody
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Jan 02, 2008 4:54 pm
- Post datetime: 2019-02-16T01:13:01+00:00
- Post Title: Editing levels for "Venice"?

AKA Venice Deluxe [https://en.wikipedia.org/wiki/Venice_(video_game)](https://en.wikipedia.org/wiki/Venice_%28video_game%29)

It comes with 71 levels. Once you beat the regular game you can play Flood mode where the same levels are played but with the water level steadily increasing. There's also an endless survival mode. Periodically through regular and flood modes are trick shots, which can be revisited later.

The levels are obviously constructed from a variety of tiles and other stock elements.

config.xml has a bunch of settings that look like they'd be interesting to fiddle with, and it references a bunch of other XML files for the levels, all of which are most likely in the 30+ megabyte main.pak

Unpacking main.pak should give access to the level xml files to be able to make new levels and if needed repack to a replacement main.pak

Figuring out how the survival mode produces an endless stream of a level without making any weird looking or impossible to hit stuff might be tapped for producing random regular levels to modify for playability.
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2019-02-19T04:23:51+00:00
- Post Title: Editing levels for "Venice"?

Just a hint: main.pak is XOR'ed with 0xF7
