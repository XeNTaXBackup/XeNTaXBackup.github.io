## Post #1
- Username: Sinnery32
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Jan 05, 2017 3:24 pm
- Post datetime: 2023-03-04T10:46:49+00:00
- Post Title: Army of Two: The Devil's Cartel.

Hello everyone, I need help.
Files taken from the ps3 version of the game ([https://drive.google.com/file/d/1i7xe0U ... sp=sharing](https://drive.google.com/file/d/1i7xe0Ujv8yAJa6Uva3zh5ekNtPGTwz7Q/view?usp=sharing)).
I used the "short" tutorial of the _zaramot_ wizard, but stopped at the fact that I have no idea how to unpack files with the .DAT extension.
I've been trying to get masks from this game for 3 months, so I ask for your help.
## Post #2
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-03-04T14:37:51+00:00
- Post Title: Army of Two: The Devil's Cartel.

> Reply from Sinnery32 ↑Sat Mar 04, 2023 6:46 pm at Sat Mar 04, 2023 6:46 pm
>
> ...I used the "short" tutorial of the _zaramot_ wizard, but stopped at the fact that I have no idea how to unpack files with the .DAT extension...
I checked the assets you posted, they are not extracted properly, what you need is the following set of scripts for proper extraction:
[https://github.com/NicknineTheEagle/Frostbite-Scripts](https://github.com/NicknineTheEagle/Frostbite-Scripts)
You need the Frostbite 2 set of scripts as the game was released by similar engine build as NFS The Run game.

Second, after extraction there is still no way to convert the assets as this game has never been supported as currently i am aware of by any reverser, unless I am wrong? Also, i have no clue what that "short tutorial of the _zaramot_ wizard" you used, either way your extracted assets are wrong.
## Post #3
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-03-04T16:10:50+00:00
- Post Title: Army of Two: The Devil's Cartel.

PS. No need to PM me for such things, keep it here so others can see and use the info to help themselves.

> Reply from Sinnery32 ↑Sat Mar 04, 2023 11:03 pm at Sat Mar 04, 2023 11:03 pm
>
> ...I wanted to ask about the tool that you threw me ...
how to use them?
First install python 3 64-bit software.
You download the master zip from the github link above, inside the 'frostbite2" folder you open up "dumper.py" file by right clicking on it and select "Edit with IDLE" and choose the python 64-bit version.
On lines 19 and 20 you edit these:

```
targetDirectory = r"E:\GameRips\NFS\NFSTR\pc\dump"
```

"gameDirectory" line is the path to the game assets, the root folder from where you extracted the PS3 PKG game files, where "Data" folder is located.
"targetDirectory" line is where you want the game files to be extracted.
once you have edited that on your keyboard click F5 it asks you to save the file, click ok then the script will run and extract the game assets for you.
## Post #4
- Username: Sinnery32
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Jan 05, 2017 3:24 pm
- Post datetime: 2023-03-13T18:24:03+00:00
- Post Title: Army of Two: The Devil's Cartel.

my friend and I managed to unpack the "blueprintbundle" file, now the question arises how to open the files ....
_ [https://drive.google.com/file/d/1CoOny7 ... share_link](https://drive.google.com/file/d/1CoOny7UaZnqVchyMPKgEUdzO0oMgYDpZ/view?usp=share_link) _
