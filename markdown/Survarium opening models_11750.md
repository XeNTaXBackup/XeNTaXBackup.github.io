## Post #1
- Username: ShooRuP
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Aug 03, 2014 1:08 am
- Post datetime: 2014-08-04T14:52:24+00:00
- Post Title: Survarium opening models

Hello everyone. Now i will tell you how to open file the game resurses.db Survarium. How to do it:
1. Downloading QuickBMS ([http://aluigi.altervista.org/papers/quickbms_0.5.29.zip](http://aluigi.altervista.org/papers/quickbms_0.5.29.zip))
2. Next, we need a script to QuickBMS ([http://aluigi.altervista.org/papers/bms ... varium.bms](http://aluigi.altervista.org/papers/bms/others/survarium.bms))
3. Game client. resurses.db file is here /Survarium/game/..
4. Script to import the files in 3ds max

Let's start!  Create a text document in the folder with QuickBMS. In a text document you want to insert the text of the script:


Run QuickBMS. In the first pop-up window, select the text document that is in the folder with the program. In the next pop-up window, select the file resurses.db games. (It is better to make a backup, just in case). In the last window you must choose where to save the files. If you've done everything correctly, will extract the file.


Now try to open the model in 3ds max with a script. Script opens only model from  "character". Weapons and all not even attempt to open, do not open. The script does not need any where to put, it can be opened from the desktop. Run 3DS max, press MAXScript => Run Script. Specify the path to the script. In the first pop-up window, you need to specify the file "export_propertis", it is in the folder with the desired model. Next you will ask for a file "bind_pose", sometimes it is in the folder with the model, but not always. 
Here's an example: models/character/human/base/base_character_boot.skinned_model/render... In this folder there is a file "bind_pose", in the following folder is not present. But one "bind_pose" for several models. And the last file that you want to specify "converted_model". It is with the file "export_propertis" in the same folder. Result:

Thank you for your attention!
[Survarium 3ds.rar](https://xentaxbackup.github.io/file/7638_Survarium 3ds.rar)
