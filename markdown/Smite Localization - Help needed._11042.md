## Post #1
- Username: migs
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 13, 2013 1:51 pm
- Post datetime: 2013-12-14T04:45:04+00:00
- Post Title: Smite Localization - Help needed.

HI! I'm pretty new to files research and game hacks, and I'm glad that the first game I started to mess with is Smite, because it uses pretty simple encoding.
Basically what I want to do, is to be able to localize the game to any language (not specific - it's just interesting thing to learn). I'll tell you what I have done so far, and where I'm stuck. Hope someone can help me.
So, the game is built with "Unreal Engine 3", and the localization folders are existing as they should be in "Localization" folder. The game is using the INT folder, and even when I've tried to change the language in the config file - it doesn't work. So, there are few *.int files in UCS-2 encoding with plain text, that can be translated to any language, and will be displayed in the game only of you change the "GFxUI.int" file to use the only Unicode font from the game. This is fine, but most of the texts are located in "Lang_INT.dat" file, and that file is compressed somehow. There are many plain texts in there, and you can edit that text in any HEX editor, but I created a little program to help me with that (source(C#) in attachment).



The program is basically replaces HEX editor, but a little bit more comfortable. It runs byte by byte and reading only the plain text. It can save the file as it was, but with translations, and it can save the file as project, to manage the translation later.
The first problem, is that somehow, I think that my solution is pretty bad. There are many not readable characters, and I want to know why they are there, and what they represent, not just take the readable text. Second of all, the replacement can work only if the translation have the exact amount of characters as the original, so I would be glad to now how and where to search the validation process of file size and structure, so may be I could change it into the size chosen by me.
The second problem is the fonts for this file. As I've seen so far, the game not using any font from the "GFxUI.int" to display the text from that ".dat" file. So if I give him the translation in Cyrillic, it would be displayed as question marks. As for the file - it saved correctly, and you can find Cyrillic text in there.

I hope there is some one experienced with UE3 (or any other one) who can help me to learn and to solve this two problems.
I attached an archive with the source code of my tool and the original ".dat" file.

P.S.
Sorry for my English, by the way. I don't have much time to practice with it.
[SmiteTranslation.7z](https://xentaxbackup.github.io/file/6839_SmiteTranslation.7z)
