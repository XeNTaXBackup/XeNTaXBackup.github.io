## Post #1
- Username: MarcoBabo
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 08, 2023 7:48 pm
- Post datetime: 2023-02-08T11:54:40+00:00
- Post Title: The Wolf Among Us - Special Characters

Hi guys,

This is my first time here! I'm translating The Wolf Among Us and I'd like to ask you how to make the special characters (áàãâç etc.) appear in game. For example: I translate the sentence "It won't happen again" to "Não vai voltar a acontecer" and in game it displays "Nao" instead of "Não". How can I fix this?

Also, is it possible to change the subtitles font?

Thanks!
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-02-08T19:57:20+00:00
- Post Title: The Wolf Among Us - Special Characters

You can do it with TTG Tools [https://github.com/pashok6798/TTG_Tools](https://github.com/pashok6798/TTG_Tools)

You can even find some tutorials explaining how to translate Telltale games, e.g. [https://ikskoks.pl/poradnik-4-edycja-gier-telltale/](https://ikskoks.pl/poradnik-4-edycja-gier-telltale/)
## Post #3
- Username: MarcoBabo
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 08, 2023 7:48 pm
- Post datetime: 2023-02-08T20:46:44+00:00
- Post Title: The Wolf Among Us - Special Characters

I can do both? I'm already using TTG to translate the game and I noticed it has a Font Editor but I don't quite understand it.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-02-08T21:11:50+00:00
- Post Title: The Wolf Among Us - Special Characters

Yes, you can do both. Just play with the tool, try to add some new characters or replace existing ones.
## Post #5
- Username: MarcoBabo
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 08, 2023 7:48 pm
- Post datetime: 2023-02-08T21:14:14+00:00
- Post Title: The Wolf Among Us - Special Characters

Sorry, but how do I add new characters?
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-02-08T21:44:50+00:00
- Post Title: The Wolf Among Us - Special Characters

> Reply from MarcoBabo ↑Thu Feb 09, 2023 5:14 am at Thu Feb 09, 2023 5:14 am
>
> 
Sorry, but how do I add new characters?

# Add new coordinates #
1. Open Font Editor
2. Go to File > Open
3. Choose .font file and open it
4. Right click on the table and choose "Export coordinates".
5. Save file, e.g. "C:\Users\User\Desktop\Gotham Light_60.fnt"
6. Open .fnt file in Notepad++.
7. Add new row with correct ID, then adjust coordinates for your new character
8. Add +1 to "chars count" in line 5
9. Save .fnt file
10. In Font Editor right click on the table and choose option "Import Coordinates".
11. Save .font file


# Add new char on DDS image #
1. Open Font Editor
2. Go to File > Open
3. Choose .font file and open it
4. Right click on the table and choose "Export texture"
5. Save DDS file, e.g. "C:\Users\User\Desktop\MenuBodyLarge_0.dds"
6. Edit DDS file in GIMP and save it
7. In Font Editor right click on the table and choose "Import Texture".
8. Save .font file


Here are some fonts from Batman, you can practice on them ---> [download/file.php?id=11518](https://forum.xentax.com/download/file.php?id=11518)


If this method doesn't work, then the only option would be to replace already existing characters.
## Post #7
- Username: MarcoBabo
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 08, 2023 7:48 pm
- Post datetime: 2023-02-08T21:47:32+00:00
- Post Title: The Wolf Among Us - Special Characters

Thanks for your time! I'll try that when I get home!
## Post #8
- Username: MarcoBabo
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 08, 2023 7:48 pm
- Post datetime: 2023-02-09T00:31:31+00:00
- Post Title: The Wolf Among Us - Special Characters

Where are the .font files? I only got .LANDB files.
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-02-09T07:35:51+00:00
- Post Title: The Wolf Among Us - Special Characters

> Reply from MarcoBabo ↑Thu Feb 09, 2023 8:31 am at Thu Feb 09, 2023 8:31 am
>
> 
Where are the .font files? I only got .LANDB files.

I don't know. You have to extract ALL .ttarch archives and find some .font files in one of them.
## Post #10
- Username: MarcoBabo
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 08, 2023 7:48 pm
- Post datetime: 2023-02-09T07:41:27+00:00
- Post Title: The Wolf Among Us - Special Characters

Thanks for your help!
