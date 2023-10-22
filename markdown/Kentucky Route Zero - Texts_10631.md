## Post #1
- Username: Crybio
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Dec 25, 2010 11:54 pm
- Post datetime: 2013-07-24T08:49:59+00:00
- Post Title: Kentucky Route Zero - Texts

Hello!!

I'd like to translate this wonderful game into ITALIAN language, but i've some problems..
First of all, I used the "UnityAssetsExplorer" to extract all I can do from the main folder.

1 - I replace a text contained in one of the assets files (with "Notepad++"), then I rebuild the Assets file (with "UnityAssetsExplorer"), but in the game that text doesn't appear! The game works fine, but that text doesn't appear!

2- I cannot find some texts, like the menu texts (Quit, Back to Game, etc.), or the object names (for example, when you put the mouse cursor on an object)...

Someone can help me? Thanks so much!!
## Post #2
- Username: Rion
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Jul 08, 2011 4:14 am
- Post datetime: 2013-07-25T13:33:16+00:00
- Post Title: Kentucky Route Zero - Texts

This is also the case with Anna EE and other Unity-based games. UAE v1.2 can only extract files from .assets, but cannot reimport them all - only DDS textures, if I recall correctly.
## Post #3
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2013-07-25T15:11:21+00:00
- Post Title: Kentucky Route Zero - Texts

looks this [viewtopic.php?f=10&t=10085&hilit=unity+text&start=30](http://forum.xentax.com/viewtopic.php?f=10&t=10085&hilit=unity+text&start=30) for text string.

And which file do you have edit ?
## Post #4
- Username: Crybio
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Dec 25, 2010 11:54 pm
- Post datetime: 2013-07-25T17:43:31+00:00
- Post Title: Kentucky Route Zero - Texts

Thanks for your answers!!

I discovered that if I use the same number of characters as the original file (with Notepad++), then there is no problem, but unfortunately it is a big problem in the adaptation phase of the dialogues..

I edited the "sharedassets5/GasStationDogLook.49" file, that contains:

"(An old hound in a straw hat. Both have seen better days.)"

it's the first sentence of the game, when you click on the dog!
## Post #5
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2013-08-20T14:46:56+00:00
- Post Title: Kentucky Route Zero - Texts

You need to download reflector looks at links i give you there are tuts.
## Post #6
- Username: Smash15195
- Rank: beginner
- Number of posts: 24
- Joined date: Fri Apr 08, 2011 4:35 am
- Post datetime: 2013-10-06T13:55:08+00:00
- Post Title: Kentucky Route Zero - Texts

Hi,

I'm interrest to translate this game. You know what files needs to be extract ?

Your italian translation works ? or nor ? 

Thanks
## Post #7
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2013-10-09T15:46:05+00:00
- Post Title: Kentucky Route Zero - Texts

> Reply from Crybio
>
> Thanks for your answers!!

I discovered that if I use the same number of characters as the original file (with Notepad++), then there is no problem, but unfortunately it is a big problem in the adaptation phase of the dialogues..

I edited the "sharedassets5/GasStationDogLook.49" file, that contains:

"(An old hound in a straw hat. Both have seen better days.)"

it's the first sentence of the game, when you click on the dog!
You could upload this file to me analyze it?
## Post #8
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2013-10-10T22:43:45+00:00
- Post Title: Kentucky Route Zero - Texts

I write here because this method maybe works with this game, but right now the only one i know it might be working is Anna EE, because it has a simple xml file.
You can make a Quickbms script to reimport the xml, but it works only if the file size is not bigger than original, so check which text file is the biggest ( as i see its the russian )
Open Anna EEs resources.assets with Unity Assets Explorer, find the strings_ru.xml ( or other biggest ) and check the OFFSET and SIZE columns, than make a script.

```
set offset 93436636            #this is the biggest files offset
set size 261355                #and size
log name offset size

```

Save this to reimport.bms and use Quickbms to reimport your file. In game you must swith the language you use for reimport.
Im not sure this will work properly, but you can give it a try.

Edit
Look like this game is different. But you can try this.
Use [barracuda's DisUnity](http://forum.xentax.com/viewtopic.php?f=33&t=10739) to extract the assets files. Text are in TextAsset folder. Make sure you edit them in utf8 encoding.
Then use this tool: [http://www.sendspace.com/file/x4jen3](http://www.sendspace.com/file/x4jen3), to put edited txt files at end of archive.
