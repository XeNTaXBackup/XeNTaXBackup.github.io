## Post #1
- Username: legendhavoc175
- Rank: beginner
- Number of posts: 29
- Joined date: Sat Sep 07, 2019 11:06 pm
- Post datetime: 2020-09-29T23:19:16+00:00
- Post Title: Can somebody help out with porting Far Cry 4's animations into Far Cry 5's format?

Ok, so Far Cry 5 still has a LOT of Far Cry 4's features leftover in the files. I've modded most of them back into the game, the animations are still there but HEAVILY downgraded. Low quality animations, some of them sporting broken animations with oddly varying frame rates. Far Cry 4's animations were absolutely stunning and greatly detailed, but the leftovers in Far Cry 5 are an incredibly broken shell of what they used to be. Some of the animations were "fixed", but still retain animation issues. Some other modders and I have looked into the files but have been unsuccessful in conversion. The only thing we could find was what the first byte of each .mab file did, the .mab files are the animation format for non-facial animations in the Far Cry series. The first byte is a version number, and while they are different between each Far Cry game, editing them isn't enough for a conversion. 

I have a list of the version numbers here.
Far Cry 3= "61"
Far Cry 3 Blood Dragon = "62"
Far Cry 4 ="81"
Far Cry Primal = "82"
Far Cry 5/ Far Cry New Dawn = B0

There is also a unique part of the .mab files from the Far Cry games before Far Cry 5,
they have these things called "markups". They essentially pull sounds and attach props and add particles/postFX.
Far Cry 5's .mab files don't have these. So, you would need to remove them from the .mab file.

here is an example of a .mab
this one in particular is from Far Cry 4

[https://drive.google.com/file/d/1Xczqkn ... sp=sharing](https://drive.google.com/file/d/1Xczqkn5zGwiJNMH1RRZ6SUW91DVA1Cqd/view?usp=sharing)

notice how this one has a filesize of 45kb

and now this one is from Far Cry 5

[https://drive.google.com/file/d/1HSBZbN ... sp=sharing](https://drive.google.com/file/d/1HSBZbNbvGlBkCTauIZ3yMCfhHDs9hDZQ/view?usp=sharing)

this one has a filesize of 7kb, not even three times the size of the original file from Far Cry 4.


There's no denying it, they're supposed to be the same animation, but the version in Far Cry 5 is awfully broken and has issues.

That's all the info I have on hand right now,

If someone can please help fix the awful animations from tainting the restored features that took quite a lot of work to implement, I'm sure everyone who mods Far Cry 5 and even plays it with mods will be extremely grateful!


Thanks, Legendhavoc175
## Post #2
- Username: ak79857
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jun 06, 2020 3:52 am
- Post datetime: 2022-04-25T20:35:08+00:00
- Post Title: Can somebody help out with porting Far Cry 4's animations into Far Cry 5's format?

Hi, and how to convert a .mab file to a file.bvh or how to import this file into 3ds max or maya?
