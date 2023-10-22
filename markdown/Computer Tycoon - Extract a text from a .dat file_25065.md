## Post #1
- Username: goodhour
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Feb 18, 2022 4:04 am
- Post datetime: 2022-02-18T17:50:24+00:00
- Post Title: Computer Tycoon - Extract a text from a .dat file

could someone help me to understand how to extract the text in this file?

[https://drive.google.com/file/d/1ai7xlN ... sp=sharing](https://drive.google.com/file/d/1ai7xlNQfiYE6erQnM8FwHvbjejgg27mk/view?usp=sharing)

And once extracted edit a text file and reassemble it in the same format?
It should contain the localization text, but I have no idea how to extract files of this format
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-02-18T22:04:35+00:00
- Post Title: Computer Tycoon - Extract a text from a .dat file

It is a metadata file from some Unity game. It doesn't contain any text, it only has names for C# functions etc.

To find text, you should really try total commander method first
[https://ikskoks.pl/searching-text-strin ... commander/](https://ikskoks.pl/searching-text-strings-using-total-commander/)
and then use UnityEx or AssetStudio on some asset files you will find.

Also - what is the name of the game this file comes from?
## Post #3
- Username: goodhour
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Feb 18, 2022 4:04 am
- Post datetime: 2022-02-19T02:16:39+00:00
- Post Title: Computer Tycoon - Extract a text from a .dat file

In the meantime, thank you for your response....
I used the method you mentioned (in particular both total commander and DnGrep) to search for various texts of the translation and the programs always bring me back to this file and not as I thought to .asset files
I'll post you the images for a text search (but it's the same for anything you search)
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-02-19T13:28:26+00:00
- Post Title: Computer Tycoon - Extract a text from a .dat file

Ok, it seems you are right. 
I have double checked it and some texts for this game are stored in global-metadata.dat file as you said in the first post.
Text is usually stored in assets files, so it's something new for me.

I don't have any working solutions for you, but maybe it's worth to check projects linked below.
It will be a good starting point.
[https://github.com/nevermoe/unity_metadata_loader](https://github.com/nevermoe/unity_metadata_loader)
[https://github.com/djkaty/Il2CppInspector](https://github.com/djkaty/Il2CppInspector)


Edit: Oh, check this as well 
[https://github.com/JeremieCHN/MetaDataStringEditor](https://github.com/JeremieCHN/MetaDataStringEditor)
## Post #5
- Username: goodhour
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Feb 18, 2022 4:04 am
- Post datetime: 2022-02-24T16:09:49+00:00
- Post Title: Computer Tycoon - Extract a text from a .dat file

Thanks for the reply!
I didn't understand how the utilities you suggested work....
Or rather from what little I understand, I might be able to extract the text, but then how do I reassemble it into the same file?
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-02-24T21:03:58+00:00
- Post Title: Computer Tycoon - Extract a text from a .dat file

I'm not sure. I haven't used those tools.
