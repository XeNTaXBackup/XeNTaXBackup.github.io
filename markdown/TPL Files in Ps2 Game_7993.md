## Post #1
- Username: Gabriel Marques
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Feb 06, 2011 5:13 am
- Post datetime: 2012-01-05T12:01:23+00:00
- Post Title: TPL Files in Ps2 Game

Hello Guys!
I have a project to translate the game Saint Seiya for PS2.
99% is already complete,missing only edit a message and then save the game into my language.

I guess what I need are in archives .TPL , since they were the only file format in the game where you can not open for edit or view..  

Someone has already worked with this type of file?
Know a program to visualize the file or edit tpl files?
Please help us because now missing 1% to complete the project.

Thanks in advance,
Gabriel.
## Post #2
- Username: Gabriel Marques
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Feb 06, 2011 5:13 am
- Post datetime: 2012-01-07T16:04:15+00:00
- Post Title: TPL Files in Ps2 Game

Some information about the help they need on the texts of Kiki(Save Text):

In GAME ISO PAL in English, a part of the text is this: "Seiya, do you want to save ..."
If you find where and how it is stored snippets, is enough.

The texts that are easy to find (the ones we have translated) are loose (without compression) in files .Bin which in turn are released (uncompressed) in file .AFS These texts are encoded with "UTF16 Little Endian".

Thus, to find any text, just do a search on the entire AFS using this encoding. It ran several searches using two different software and always get the same results: find all the texts that we have already found, but find no talk of Kiki. This leads me to believe that the phrases are compressed Kiki somehow.
## Post #3
- Username: Gabriel Marques
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-01-12T02:46:59+00:00
- Post Title: TPL Files in Ps2 Game

The TPL files are just textures, Noesis can open them.
## Post #4
- Username: Gabriel Marques
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Feb 06, 2011 5:13 am
- Post datetime: 2012-01-13T09:57:27+00:00
- Post Title: TPL Files in Ps2 Game

> Reply from MrAdults
>
> The TPL files are just textures, Noesis can open them.
Thank you, but you could give more information about the Noesis?
Is a program? I could not find anywhere... 

EDIT: It is possible that these files contain a text save or the logo of the game?
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-13T18:06:37+00:00
- Post Title: TPL Files in Ps2 Game

They might if the game uses images to display them.
## Post #6
- Username: Gabriel Marques
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Feb 06, 2011 5:13 am
- Post datetime: 2012-01-13T20:52:57+00:00
- Post Title: TPL Files in Ps2 Game

YES!   Thank you guys! With your help we can view images with the program Noesis! And really was what we were.

With Noesis, we can view and extract the images that need to be edited, but can't insert it back into the file.TPL

Someone could tell us how to do this?
Now, you just need 0.5% to finish our project to translate the game! Thank you all once again!
## Post #7
- Username: Gabriel Marques
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-01-13T20:56:18+00:00
- Post Title: TPL Files in Ps2 Game

Noesis (as you've presumably found by now): [http://oasis.xentax.com/index.php?content=downloads](http://oasis.xentax.com/index.php?content=downloads)

It doesn't repack TPL files, and it should be noted that multiple textures are usually packed into TPL files. Source code is included for the Saint Seiya plugin, however. (see pluginsource.zip)
## Post #8
- Username: Gabriel Marques
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Feb 06, 2011 5:13 am
- Post datetime: 2012-01-13T21:11:29+00:00
- Post Title: TPL Files in Ps2 Game

> Reply from MrAdults
>
> Noesis (as you've presumably found by now): http://oasis.xentax.com/index.php?content=downloads

It doesn't repack TPL files, and it should be noted that multiple textures are usually packed into TPL files. Source code is included for the Saint Seiya plugin, however. (see pluginsource.zip)

Yes! I see the source code for saint seiya and could view the images to edit the logo. The program exports to PNG, where do the editing.
But what to put inside the .TPL again? how do I do?
## Post #9
- Username: Gabriel Marques
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Feb 06, 2011 5:13 am
- Post datetime: 2012-01-30T22:58:57+00:00
- Post Title: TPL Files in Ps2 Game

Some more information:

1 - Most programs to edit TPL files, are somehow related to the Nintendo Wii system. Some of these programs recognize and export the TPL file to other formats, but can not reenter a modified file in the container TPL.
When trying to execute the action you reinsert an image, a message appears that says "this program does not work with files of multiple texture"

2 - The program Game Graphic Studio opens some TPL file types similar structure (with extension FJF) but not the files that we need to edit.

Any information about editing these file types will be of great help to us.

Thanks in advance everyone!
## Post #10
- Username: ranma11
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 14, 2012 7:58 pm
- Post datetime: 2012-04-14T13:05:49+00:00
- Post Title: TPL Files in Ps2 Game

I have the same problem.Do you solved it?
## Post #11
- Username: gustavofarias
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 16, 2012 12:52 am
- Post datetime: 2012-04-14T14:14:49+00:00
- Post Title: TPL Files in Ps2 Game

> Reply from ranma11
>
> I have the same problem.Do you solved it?

Please refer to these two topics, they are about the same problem of opening TPL files, specially the compressed ones:

[viewtopic.php?p=66396#p66396](http://forum.xentax.com/viewtopic.php?p=66396#p66396)

[viewtopic.php?f=21&t=8251](http://forum.xentax.com/viewtopic.php?f=21&t=8251)

Maybe they can help you, or you can help us.
