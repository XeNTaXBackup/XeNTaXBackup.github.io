## Post #1
- Username: Wakka387
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 02, 2015 2:06 pm
- Post datetime: 2015-05-14T13:44:29+00:00
- Post Title: MGD Format (Activision)

Curious if anyone knows anything about the MGD file format that was used by activision back when they made the True Crimes series?




Here are the files

[https://db.tt/NwobaJ1H](https://db.tt/NwobaJ1H)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-14T17:04:39+00:00
- Post Title: MGD Format (Activision)

test.mgd looks like a huge map file:


test_mgd.JPG (106.41 KiB) Viewed 152 times
## Post #3
- Username: Wakka387
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 02, 2015 2:06 pm
- Post datetime: 2015-05-15T15:54:55+00:00
- Post Title: MGD Format (Activision)

> Reply from shakotay2
>
> test.mgd looks like a huge map file:test_mgd.JPG
hmm... any way to access it? like, load it into 3DS Max?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-16T02:51:48+00:00
- Post Title: MGD Format (Activision)

> Reply from ss4gogeta0
>
> shakotay2 wrote:test.mgd looks like a huge map file:test_mgd.JPG
hmm... any way to access it? like, load it into 3DS Max?what do you want to achieve?
You can display the maps as point clouds using hex2obj.
Afaik the 3DSmax obj exporter doesn't like obj files without face indices.
## Post #5
- Username: Wakka387
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 02, 2015 2:06 pm
- Post datetime: 2015-05-16T06:32:15+00:00
- Post Title: MGD Format (Activision)

> Reply from shakotay2
>
> ss4gogeta0 wrote:shakotay2 wrote:test.mgd looks like a huge map file:test_mgd.JPG
hmm... any way to access it? like, load it into 3DS Max?what do you want to achieve?
You can display the maps as point clouds using hex2obj.
Afaik the 3DSmax obj exporter doesn't like obj files without face indices.
all the data for the map should be in the folder I had uploaded. the map itself, all the textures for it, co-ordinates and so forth. each of the files should have pieces that can be used to construct the full LA City... the only issue for me is that I don't know how to access the files and extract the information. which is why I came here 

Textures



Street names & such (rather useless at the moment I guess)



the reason I asked if it could be imported into a 3D modelling software is because I plan to import it into GTA SA (while a friend of mine wants to import it into GTA IV)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-16T08:22:15+00:00
- Post Title: MGD Format (Activision)

> Reply from ss4gogeta0
>
> [..] each of the files should have pieces that can be used to construct the full LA City... the only issue for me is that I don't know how to access the files and extract the information. which is why I came hereThis will require some fiddeling. I showed you what I could find in a 5 minutes job but sadly I don't have the time to dig deeper.

> the reason I asked if it could be imported into a 3D modelling software is because I plan to import it into GTA SA (while a friend of mine wants to import it into GTA IV)Same as above. I could have tried to apply some guessed face indices but the maps are way too big to know where to start with the vertices belonging to them.
## Post #7
- Username: Wakka387
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 02, 2015 2:06 pm
- Post datetime: 2015-05-19T00:23:54+00:00
- Post Title: MGD Format (Activision)

> Reply from shakotay2
>
> ss4gogeta0 wrote:[..] each of the files should have pieces that can be used to construct the full LA City... the only issue for me is that I don't know how to access the files and extract the information. which is why I came here This will require some fiddeling. I showed you what I could find in a 5 minutes job but sadly I don't have the time to dig deeper.
the reason I asked if it could be imported into a 3D modelling software is because I plan to import it into GTA SA (while a friend of mine wants to import it into GTA IV)Same as above. I could have tried to apply some guessed face indices but the maps are way too big to know where to start with the vertices belonging to them.
its cool, I hope someone with more free time can look deeper into the files and extract it.

well college is going to be done soon so hopefully some willing volunteers witll show up
## Post #8
- Username: Wakka387
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 02, 2015 2:06 pm
- Post datetime: 2015-06-02T01:56:19+00:00
- Post Title: MGD Format (Activision)

bumping this because I am still interested in trying to atleast extract the map for use with a GTA mod. 

anyone willing to help a wayward soul?
## Post #9
- Username: Wakka387
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Apr 02, 2015 2:06 pm
- Post datetime: 2015-10-24T23:44:44+00:00
- Post Title: MGD Format (Activision)

regarding most of the TC:LA files. I have been doin a bit of research and compiled a list of the formats in the city folder.

EPP = Edit Pad Pro. Street names and such

EPM = MPE Data Encryption? Destiny MPE

EXT = Textures

IDX = Subtitles?

RES = Possibly Textures?

MGD = Possible CAD file. contains the Map
