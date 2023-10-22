## Post #1
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2013-10-31T06:55:19+00:00
- Post Title: WWE 2k14 Save Data

I'm having some difficulty figuring out the save format this year. Some history on how the wwe save files work:

1. The is a file called chetc which the games reads and creates the save
2. The chetc file contains individual files containing information about each wrestler in the game (name, which show, height, attribute values, etc)
3. Each wrestler has a slot number assigned in the save file and wrestler info is created for each slot from the chetc. 

In previous years it was relatively easy to figure out but with wwe 2k14 some things have changed i.e.

1. The save file is zlib compressed (Fairly easy to uncompress)
2. The chetc files seem to be compressed or encrypted somehow as it is substantially smaller than last years files. It also doesn't contain the wrestlers names in a readable format). 
3. The save file wrestler info also seems to be compressed or encrypted as it also does not contain wrestler names. 

Here's what the chetc files look like comparitively:



Here's what the wrestler info files from the save look like comparitively (the labels say chetc data but it's actually a picture of the save data)




This file contains the chetc files and save wrestler infor files from both games: [http://www19.zippyshare.com/v/14322889/file.html](http://www19.zippyshare.com/v/14322889/file.html)

This file contains the entire save as well as a few more files from both years chetc to compare: 
[http://www35.zippyshare.com/v/87538925/file.html](http://www35.zippyshare.com/v/87538925/file.html)
## Post #2
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2013-11-19T11:34:32+00:00
- Post Title: WWE 2k14 Save Data

Not to worry guys. I figured it out. The save data isn't compressed, it contains references to the names contained in another file.
