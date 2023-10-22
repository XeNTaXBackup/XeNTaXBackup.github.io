## Post #1
- Username: UtkuGARIP
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Feb 28, 2017 8:53 am
- Post datetime: 2023-02-14T16:44:57+00:00
- Post Title: I can't find texts in old Unity games

Hi everyone

Lately, I can't find the text files in many Unity 2019 (or even older) games. All I want to do is translate them for my language, I don't understand why game makers go to so much trouble and try to block them.
The attached picture is the result of the game "Sailwind" filtered with "Filter -> TextAsset" after opening all the files in the "Sailwind_Data" folder.



image.png (11.13 KiB) Viewed 93 times


Can you help me how to access the texts of these and other plays?
## Post #2
- Username: UtkuGARIP
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-02-15T22:23:59+00:00
- Post Title: I can't find texts in old Unity games

Always first thing to try should be total commander method [https://ikskoks.pl/searching-text-strin ... commander/](https://ikskoks.pl/searching-text-strings-using-total-commander/)
Try this on decompressed files as well!

Not all language files are text files... some (many?) are binary files. And it is standard practice in game development.
Not always keeping translations as text files is effective in game development - noone is hiding text from you (or at least not always   ).


As for your "Sailwind" case, some texts are stored in "\Sailwind_Data\Managed\Assembly-CSharp.dll".
For example, after decompilation with dotPeek, you will see hint texts in "Assembly-CSharp\Hints.cs" file.

Check out this example --> [https://i.imgur.com/Zw2wf9i.png](https://i.imgur.com/Zw2wf9i.png)

More tools can be found here [http://wiki.xentax.com/index.php/List_of_Unity_Tools](http://wiki.xentax.com/index.php/List_of_Unity_Tools)
