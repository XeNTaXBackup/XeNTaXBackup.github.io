## Post #1
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2021-11-25T19:05:09+00:00
- Post Title: AssetStudio import function

Hello.

I'd like to translate 60Parsecs but I stumbled upon a problem.

I managed to find file with in-game text in game files. Using AssetStudio I export MonoBehaviour file where the text is and it asked me for Assembly files, so I selected 'Manage' folder and it gave me the entire script. So I just exported this file, I can edit it but how do I put it back?

I guess I need to reverse that process so again somehow use Assembly files to convert it back into MonoBehaviour and import it in asset archive. But how do I do that?

Thank you for any answer.

EDIT
-------------------------
Nevermind. I figured it out 

[](https://ibb.co/GsvRzKY)
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-11-25T20:36:15+00:00
- Post Title: AssetStudio import function

> Nevermind. I figured it out

Can you share your solution for others?
## Post #3
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2021-11-25T20:59:28+00:00
- Post Title: AssetStudio import function

Used software:

Asset Bundle Extractor  (UABE) v2.2 or later
Text editor


1. Open UABE
2. File - Open - resources.assets
3. Look for file with Path ID 179 (size in bytes 11 144 008)
4. Select this file and then click on Export Dump
5. Click on Yes in a pop-up window
6. Copy this file name Assembly-CSharp-firstpass.dll
7. Now back to UABE, find and open this folder ...\Steam\Steamapps\Common\60 Parsecs!\60Parsecs_Data\Managed
8. Paste the copied file name in the 'File name' and click on 'Open'
9. Repeat few times until command line opens and then wait.
10. Now it will ask you where you want your UABE text dump to be saved.
11. Open the file and edit with text editor. (It's HUUUUGE btw) Do not change anything about the script itself ofc, just translate your language.


How to Import back:

1. Repeat steps 1.-3. from before
2. Click on Import Dump, find and double click on the file you exported and edited and wait until this symbol - * - will show up under 'Modified' clumn.
3. File - Save and save your new archive. (You cannot overwrite the one you have opened. You will have to rename it and delete the original one later.)
