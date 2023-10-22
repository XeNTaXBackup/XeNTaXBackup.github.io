## Post #1
- Username: phunmoiblackpeony
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 10, 2019 10:14 am
- Post datetime: 2019-05-10T02:16:01+00:00
- Post Title: Editing levels for "Venice"?

It comes with 71 levels. Once you beat the regular game you can play Flood mode where the same levels are played but with the water level steadily increasing. There's also an endless survival mode. Periodically through regular and flood modes are trick shots, which can be revisited later.

The levels are obviously constructed from a variety of tiles and other stock elements.

config.xml has a bunch of settings that look like they'd be interesting to fiddle with, and it references a bunch of other XML files for the levels, all of which are most likely in the 30+ megabyte main.pak

Unpacking main.pak should give access to the level xml files to be able to make new levels and if needed repack to a replacement main.pak

Figuring out how the survival mode produces an endless stream of a level without making any weird looking or impossible to hit stuff might be tapped for producing random regular levels to modify for playability.
