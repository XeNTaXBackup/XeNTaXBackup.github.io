## Post #1
- Username: frogz2007
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Nov 10, 2014 9:13 am
- Post datetime: 2015-06-30T15:26:37+00:00
- Post Title: Monsters, Inc. (PS2) Guide to swapping models and animations

First and foremost, I have to thank FurryFan for teaching me how to do this. That aside, what you need is:

1. Hex editor (I prefer HxD)
2. Monsters, Inc. (Obviously)
3. UltraISO (or a program that can reimport and rebuild ISO files)
4. Text editor (preferred program is Notepad++)

Step 1. Open the ISO and navigate to the "levels" folder.
Step 2: Open up the "scareflr" folder (for the sake of this tutorial)
Step 3. Extract the "scareflr.LV2' and "scarelfr.WAD" file to your desktop (or any place where you can remember where you put it)
Step 4: Open the .LV2 file with Notepad++ and type in the search field "sully"
Step 5: Replace the resource name with "randall". This replaces the model and textures, but not the animations.
Step 6: Save the .LV2 file
Step 7: Open up the .WAD file in HxD (or whichever hex editor you want) and search for "sul_run".
Step 8: Replace "sul_run" with "ran_run" and then search for "ran_run" and replace that with "sul_run".
Step 9: Save the .WAD, and replace the existing .WAD and .LV2 files with the modified versions you just did, and save the ISO.
Step 10: Play the game, and if you did it right, Sully should now be Randall, and should use Randall's running animation!

Here is a list of all of the animations used by the game:

[https://www.dropbox.com/s/jburho1dys9ec ... S.rtf?dl=1](https://www.dropbox.com/s/jburho1dys9ecq9/MINC%20ANIMATIONS.rtf?dl=1)

Note: A few of the animations are completely unused by the game, so try and stick to the ones that are basic moves, such as run, walk, idle, etc...

And, keep in mind, make sure that if the animation name is longer than the other, make sure the name's offset ends with 0.
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-08-07T19:55:26+00:00
- Post Title: Monsters, Inc. (PS2) Guide to swapping models and animations

Thanks for taking the effort!
## Post #3
- Username: frogz2007
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Nov 10, 2014 9:13 am
- Post datetime: 2015-08-08T10:37:38+00:00
- Post Title: Monsters, Inc. (PS2) Guide to swapping models and animations

No problem. Though as I said, I know this stuff thanks to a good friend of mine on here named FurryFan.
