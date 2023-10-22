## Post #1
- Username: RythusOmega
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Sep 20, 2014 11:05 pm
- Post datetime: 2021-07-03T04:06:45+00:00
- Post Title: Namco's "Flight Engine" DPL package container(Ace Combat)

(image embeds removed due to Imgur's recent ToS changes about inactive photos)

The fifth time in theory i make a post of this, as i did at previous times on other forums without my original nick to avoid legal issues of ACI begin active as a F2P service.

File Sample : [https://www.dropbox.com/s/hftxn4hilh9oi ... 0.PAC?dl=0](https://www.dropbox.com/s/hftxn4hilh9oiqw/DATA00.PAC?dl=0)

DPL is a header of package containers from the Ace Combat games made for the PS3/X360 era, the extension of those turns to be .PAC, which was used before for the PS2 games, but those got a more simple structure and were decompressed already by a friend of mine, one of the games makes uses of the ULZ encryption, used on the last PS1 game of the series. AC6 also introduces the .PAC extension, but heavily encrypted, by report of some users, tools for that may existed at some point.


the .PAC which stores the DPL containers, start to begin used on Ace Combat Assault Horizon for PS3 and X360, it was the first instance of this files to existing, a common misconception, is aside of the root .PAC files(DATA00 and DATA99, latter used for disclamer warning sprites), the "target" folder stores more types of .PAC files(ranging from DATA11, 12, 13, 20, etc...), the thing is, despite using .PAC extension, they are originally Criware's CRIYALLA packages, the famous CPK headers, which can store game files, but isn't used on the games case, the 1x range stores audio clips and music, when the 2x stores the video clips, which VGMtoolbox is recomended, as those don't use a conventional CPK structure, is also hardcoded, but extractable.



The games this type of container was featured, mostly are related with the Ace Combat series :
-Ace Combat Assault Horizon for PS3/X360(2011)
-Ace Combat Infinity, for PS3(Beta : 2013 / Final : 2014)
-MachStorm, an arcade title(2013)
*Assault Horizon Enhanced Edition for PC(2013), doesn't use DPL as their main container originally, instead, they use the QDF container, making easier by lacking complex encryption and begin documented, but a DPL file exists inside the internals for storing DLC content assets.

The main consensus of those type of files, turns to them begin strictly hardcoded in XOR, with a bit of deflate, with the time reaching in contact with a programmer who managed to decompress the PS2 games and AC6 at the last decade, said it was beyond his knowledge at decoding those, so honestly, i won't expect those begin extracted too early.

And yeah, mostly i'm not too worried either, seeing if people check this profile, recently i managed to extract some of the game files by memory dump, which was one of my main interrest since the begining, however, some files, mostly graphical assets, are totally abstent of the current version i had, clueless if turns they was server sided, or are hidden in the game files still, along that ACI isn't a playable game anymore, some gameplay assets would demand to the DPL begin extractable instead, as those aren't even preloaded on the memory cache.
[viewtopic.php?f=16&t=22230](https://forum.xentax.com/viewtopic.php?f=16&t=22230)
[https://zenhax.com/viewtopic.php?f=5&t=14942](https://zenhax.com/viewtopic.php?f=5&t=14942)
