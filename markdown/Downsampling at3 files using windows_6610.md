## Post #1
- Username: cozy
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Dec 08, 2009 5:18 am
- Post datetime: 2011-05-13T22:33:56+00:00
- Post Title: Downsampling at3 files using windows

Tools needed:-
1.Sony sound forge 10 Pro (use google to get it)
2.Atrac3plus tool "see below"
3.UMDGen (use google to get it)

First you need to get your at3 files,use UmdGen to open your iso and get all your at3 files,use the extract option,and extract your at3 files see image below 



Now open the atrac3plus tool,and drag and drop your at3 files onto it,you will see your file names in the tool with all the bit rates etc..



You can see these files are looped and are at 192kbps stereo, so we are going to make them mono and 32kbps!
Now the SFaa3 button has a bit of colour on it,this meens we can convert these files to Sony sound forge files .aa3!
So press it and this will make a folder @SFaa3Atrac3Plus-Loop[Yes],but if your at3 have no loop then it will make another folder called
@SFaa3Atrac3Plus-Loop[No]remember this as when you have downsampled the files you must make them looped or not!.
Now you have a folder called @SFaa3Atrac3Plus-Loop[Yes] with .aa3 files with the same name as the original at3 files.
Now open Sony sound forge pro10:



And select Tools tab and them batch:



This will then pop up the batch tool select then select the add tab and add the aa3 files you made with the atrac3plus tool.



You will then see all the aa3 files.

Then select the save Tab option:-



Keep the name file name option as "same as source" and make a new folder called "yes" for the saved files to.(but if the files are not looped then make a folder "no")
Now select the convert to option keep the atrac audio option but select the custom button



And select the 32kbps mono,once you have selected that option then select the "run job"this will then downsample the aa3 files to a mono 32kbps in the yes folder.



Now open the atrc3plus tool again ,and now add the new aa3 files that you have downsampled from the folder "yes" or "no" if they are not loopded



As you can see the bit rate is now 32 kbps and mono and now the atrac3plus button has some colour,press the atrac3plus button and this will them convert the files to at3!!but if the files are non looped select the looped option to no looped,this will them produce a folder called @Atrac3Plus-Loop[Yes] or @Atrac3Plus-Loop[No] you can now add the new downsampled at3 file to your Psp iso...

Hope this will help you all

cozy
[Atrac3plus_tool.rar](https://xentaxbackup.github.io/file/4237_Atrac3plus_tool.rar)
## Post #2
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2011-07-01T12:06:00+00:00
- Post Title: Downsampling at3 files using windows

it does. been looking for a GUI tutorial on how to make At3-Wav for ages. thanks a lot D:
## Post #3
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2011-07-01T16:22:14+00:00
- Post Title: Downsampling at3 files using windows

Basically you do the same thing here except you save it as a uncompressed WAV instead of .AA3 using Sound Forge. Keep the channels and Hz rate the same though.
