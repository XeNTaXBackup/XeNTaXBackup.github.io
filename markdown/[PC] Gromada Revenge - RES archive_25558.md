## Post #1
- Username: aurismat
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 27, 2022 6:33 pm
- Post datetime: 2022-06-27T16:47:43+00:00
- Post Title: [PC] Gromada: Revenge - RES archive

Hi XeNTaX forum! Sorry if I have put my question/help request in an incorrect topic, if I have done so please let me know.

Anyway, onto the topic. I really want to figure out how to unpack the assets of an old abandonware game by Buka Entertainment called Gromada: Revenge.
Only file that would make sense as the assets file(spritesheets etc.) is the largest one in the game's root directory - fw.res, and so far I've been stumped on it. I've tried extracting it using multiple programs from the XentaxWiki list found [here](https://wiki.xentax.com/index.php/Extraction_tools) Other files look like map data and game logic scripts written very similarly to C.
I was hoping someone with more knowledge about games of this age would be able to point me in the right direction unpacking this game's assets.

For those who want to take a crack at it, you should be able to find it in Internet Archive with relative ease.

(apologies to the moderation team for posting a link to the full game)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-06-27T21:49:07+00:00
- Post Title: [PC] Gromada: Revenge - RES archive

Hi, I've checked this game. There are two files in the main directory - fw.res and fw.ini.

INI file contains only those numbers:



screenshot000103.png (4.21 KiB) Viewed 52 times


I'm not sure what is it used for...

As for fw.res, it can be split to multiple entries and I've created a script to do this:
[https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/Gromada%20Revenge/Gromada_Revenge_RES_script.bms)

And new article has been added to the wiki for this format:
[http://wiki.xentax.com/index.php/Gromada_Revenge_RES](http://wiki.xentax.com/index.php/Gromada_Revenge_RES)

Most files have entry type 33 and this is probably some compressed data.
I've seen also other types, e.g. type 34 seems to be WAV file, but I couldn't play it properly in Winamp.
## Post #3
- Username: aurismat
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 27, 2022 6:33 pm
- Post datetime: 2022-06-28T06:45:09+00:00
- Post Title: [PC] Gromada: Revenge - RES archive

What a legend! That's most definetely a start. 

> Reply from ikskoks ↑Tue Jun 28, 2022 5:49 am at Tue Jun 28, 2022 5:49 am
>
> 
I've seen also other types, e.g. type 34 seems to be WAV file, but I couldn't play it properly in Winamp.
I've punched the only type 34 file into Audacity as raw Unsigned 8-bit PCM with the following settings and got what seems the SFX for the game. 



Untitled.png (6.37 KiB) Viewed 44 times


However, I am hearing some sort of clicking in between stitched audio clips. Might be just the audio file header data.

However, I was under the impression that this game also had some soundtrack which would be played mid-game along with it. I'll need to get a WinXP VM set up for this to verify, maybe my Windows 10 install is missing some codecs or is just too new outright or something. A thought occurred while I was discussing this with a friend who got me hooked on Gromada - might be a separate partition on the CD that stores the music.
