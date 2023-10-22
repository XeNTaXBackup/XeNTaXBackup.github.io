## Post #1
- Username: kaspar
- Rank: n00b
- Number of posts: 15
- Joined date: Wed May 04, 2011 1:43 am
- Post datetime: 2012-10-22T16:40:49+00:00
- Post Title: FF8 - G.F. NPC and Terrain/City Models

I'm not sure about this but FF8 still keeps some secrets models hidden somewhere and i hope that what I'm about to post can be usefull somehow..

G.F. Models (Siren Shiva Eden Carbuncle.. etc) NPC and Terrain / City Models still can't be viewed or extracted whith any tool (but if i missed it plz tell me!) so I tried to extract them whith another method but my success was only 66,66666666% v.v

Here some screens:


Balamb:




Quezacotl (in different poses during animation):









I used 3d ripper DX  epsx and 3ds max for this but the problem is that the what you see is just flat (there is no depth at all..)



If anyone think these flat 3D screens can be helpful to understand any still mysterious file format of the game just ask me and I'll be happy to help!

Just 1 more thing..

Whith same tool i extracted some textures from the Balamb Garden ground model (i'm quite sure) and other from battle 3d enviroments..

here some examples:








I extracted lot of things whith other tool but i'm quite sure i'd never seen these textures before..

I'm quite sure that G.F. models are hidden inside some magic related files.. for example i found some Quetzacotl related textures in the mag115 file..so probably from same file 3d model and animation can be extracted too..
## Post #2
- Username: kaspar
- Rank: n00b
- Number of posts: 15
- Joined date: Wed May 04, 2011 1:43 am
- Post datetime: 2012-10-25T10:48:18+00:00
- Post Title: FF8 - G.F. NPC and Terrain/City Models

after some days of research this is what i was able to find out :

The World textures are contained in the world/dat/wmsetit.obj and textl.obj files.. here some samples:

in textl.obj i found 20 textures file containing world/city textures like these:



and nothing else

In wmsetit there were a lot of textures :
many smaller versions of textl file textures like this:


the world map:

All(not sure) vehicles textures (included, gardens, airship, cars, trains and ships) like these:






In same folder there is a file which seems not containing textures and maybe containing 3d models:
-wmx.obj (30.060 kb)

If anyone has info about it please let me know.
## Post #3
- Username: kaspar
- Rank: n00b
- Number of posts: 15
- Joined date: Wed May 04, 2011 1:43 am
- Post datetime: 2013-03-20T18:21:59+00:00
- Post Title: FF8 - G.F. NPC and Terrain/City Models

Ok Here's an update about the npc models.
Seems that datas about them is contained in Field files.

Just an example..
FIELD.FS contains all the background ambients files so let's extract it:
Let's take the ballroom file:
bgpaty_1.fs (783kb)

If we extract it (using noesis) we obtain many files and between them we'll find the 2 biggest files that are:
bgpaty.mim (428kb) which contains all the background images
chara.one (323kb) which is supposed to contain npc data

From chara.one I'd been able to extract 2 textures:

This should be the waitress who appear in the ballroom

I'm not 100% sure but this should be the dish whith the glasses

I searched something about chara.one files and I found this interesting topic on Qhimm forum..
Unfortunately I'm not a programmer so I don't know what to do whith those infos..but maybe someone could use them to create an extracting tool or a cool script for noesis for example
