## Post #1
- Username: Blast Processing
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 04, 2012 2:04 am
- Post datetime: 2012-12-04T14:01:38+00:00
- Post Title: Pokédex for iOS - BIN Files

Hi. Recently I purchased the new [Pokédex for iOS app](https://itunes.apple.com/jp/app/pokemon-tu-jian-for-ios/id573135437?mt=8) from the Japanese app store with the intention of trying to extract the 3D graphics for fun, until I ran into archive issues that have me stumped.

Most of the data is stored in two files: arcbin0r.bin (22.8MB) and arcbin5r.bin (413MB), the larger of which has to hold most of the data for the Pokémon models, though I can't guess as to what is in the smaller one. I couldn't discern any obvious data from both BIN files in a hex editor, just seemingly random characters like so:



I assume this means that the data is compressed or encrypted in some way that means I can't just go in and look for where files would start and end. Unfortunately the app requires iOS6 to run and I don't own any devices that can jailbreak iOS6, so I can't do anything while data is loaded into memory. The only information I could find was in the main executable file which included function names and libraries.

Unfortunately I am not very experienced with data compression or encryption methods, so I don't really know where to go from here in an attempt to extract individual files from the archives.
## Post #2
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2012-12-13T05:18:46+00:00
- Post Title: Pokédex for iOS - BIN Files

Apparently those two files have a form of AES-128 encryption judging by the strings in the glview file. Which means it's not gonna be easy to decypher.
## Post #3
- Username: barracuda
- Rank: beginner
- Number of posts: 30
- Joined date: Sat Nov 24, 2012 9:15 pm
- Post datetime: 2012-12-13T09:48:07+00:00
- Post Title: Pokédex for iOS - BIN Files

Depends on how well the key is hidden in the executable.
