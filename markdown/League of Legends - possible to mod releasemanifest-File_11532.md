## Post #1
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2014-05-22T21:31:59+00:00
- Post Title: League of Legends - possible to mod "releasemanifest"-File?

Hey Guys,

I want to ADD some files to the actual League of Legends Patch and It works till now.
But the Files will not be loaded because I have to modify the releasemanifest.

I uploaded the newest releasemanifest of the League of Legends - Client.
I hope someone could help me with it 

I think the structure COULD be like this, but I`m not sure about it.
[http://l3cdn.riotgames.com/releases/liv ... gemanifest](http://l3cdn.riotgames.com/releases/live/projects/lol_game_client/releases/0.0.0.233/packages/files/packagemanifest)

releasemanifest:
[https://mega.co.nz/#!VQwmXZCB!t8u1MKoid ... N3gGAW3Ojs](https://mega.co.nz/#!VQwmXZCB!t8u1MKoidI13YgFHcTLYQFOEMJhiBc7rqN3gGAW3Ojs)


If I'm able to modify this file, I`ll be able to add old maps and new scripts to this game 

Thank you to everyone who will try it
## Post #2
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2014-05-24T22:27:57+00:00
- Post Title: League of Legends - possible to mod "releasemanifest"-File?

We are looking for a way to add files entries to the 'releasemanifest' file of League Of Legends. 
Currently, "Skin Installer Ultimate" (a program which allows us to modify files in the game) contains a function which modify the size of some files entries in the 'releasemanifest' file (In fact, if we add a mod to SIU, some files of the mod can have a different size than the Riot files, so SIU has to modify the 'size' parameter of the modified file in the 'releasemanifest').
This function does modify the size of existing files, only. But what we are looking for is a way to ADD files entries in the 'releasemanifest' file (with also 'File Name', 'File Size' parameters).
The problem is that we do not know how to do! We know the file structure and the LGG's code helped us a lot. 
The part of the code which is the more interesting is "RelManDirectoryFile". It contains all the informations about the 3 types of things there are in the 'releasemanifestfile': StringList, FilesList and FoldersList.
This code is reading the file and is listing all of the file entries. That we have to know is to modify the vars which are stocked these informations and then create a function which re-write the 'releasemanifest' using the vars we have modified (including new files we want to add in the 'releasemanifest')
But the problem is that we're not enough skilled to do a program which would allow this feature.

This is the source of SIU 
[https://code.google.com/p/siu-lgg/sourc ... FRelManLib](https://code.google.com/p/siu-lgg/source/browse/#hg%2FThirdParty%2FRelManLib)


If we get it to work, we're really able to readd the old maps like "Old Twisted Treeline" or "Proving Ground" and play it in custom Games.
More things should be possible then, too!


It would be great if you can help us with it.
## Post #3
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2014-05-28T05:27:46+00:00
- Post Title: League of Legends - possible to mod "releasemanifest"-File?

After some tests, we're able to "replace" the maps, but there are some problems.
SummonersRift uses other files with other filenames and coordinates as Old Twisted Treeline.
That's the reason we have some bugs till now.
We're not able to add new/old files to the game (the files from OldTT that are not have the same filename as the files from SR will not loaded).

Now we need YOUR help to get the chance to play the old Maps again!
Old SR (Horrowing & Winter), Old Twisted Treeline & Proving Ground.

Here's a Screenshot of the (little bit buggy) old Twisted Treeline!
IMAGE-LINK

Thank you for your help
