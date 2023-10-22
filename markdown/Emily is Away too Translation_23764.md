## Post #1
- Username: Rain
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Apr 20, 2021 4:34 am
- Post datetime: 2021-04-19T20:53:21+00:00
- Post Title: Emily is Away too Translation

Heyah! So, I'm here to ask for help with a problem that i'm encountering while trying to translate the game Emily is Away too for Pt-Br. I'm a brazillian, and i'm very fluently to english, but, my language uses a lot of accents in words, and for that reason, I have a problem with invalid characters in the game.

I'm using the program dnSpy to translate the entire game code and to export/import the Assembly-CSharp.dll. In the ChatValues class i could find a public static that has ValidCodeCharacters on it. It's probably for display or call measures, so, ever if i tries to add a character to it, won't work. So, the problem is that ~^´`° and others characters like these get an type of red X on it, meaning that it's an invalid character. I don't know if i'll need to change the font or edit it, so that can be compatible with the characters, and even if that's the way to solve it, i don't know how to do it.

So, if you know how to solve my problems, please help me below, i really want to finish the translation for this game because i love it, and people of my country deserves to fully enjoy it. Any help would be appreciated, i just want to fix that god damn invalid characters error.
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-04-19T21:00:25+00:00
- Post Title: Emily is Away too Translation

You could also try to replace already existing characters if you have enough unused letters in the font file.
I see that this game is on Unity engine, so you need find font file first using tools like AssetStudio etc.
## Post #3
- Username: Rain
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Apr 20, 2021 4:34 am
- Post datetime: 2021-04-19T23:23:31+00:00
- Post Title: Emily is Away too Translation

> Reply from ikskoks ↑Tue Apr 20, 2021 5:00 am at Tue Apr 20, 2021 5:00 am
>
> 
You could also try to replace already existing characters if you have enough unused letters in the font file.
I see that this game is on Unity engine, so you need find font file first using tools like AssetStudio etc.

Gonna try that, but, i don't know how i should do it, could you give me a help? 

Edit: There's too many fonts, i'm viewing with the Assets Studio and i don't know what one i should change, and how can i change, import and export it to fit the game with width and height. Also i could find that the main one should be Atlas, but, i don't know where i can start modifying it, or if i should do idk, all of then seems to have ~´^`°
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-04-20T07:17:19+00:00
- Post Title: Emily is Away too Translation

Simple answer is that you should change all of them to make it work. 

As for editing, that depends what is the format of the font. Is it DDS or TTF? Or something else?
Can you show some screenshots?

For export/import you can use tools like UnityEx or UnityAssetsExplorer.
## Post #5
- Username: Rain
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Apr 20, 2021 4:34 am
- Post datetime: 2021-04-20T11:09:15+00:00
- Post Title: Emily is Away too Translation

> Reply from ikskoks ↑Tue Apr 20, 2021 3:17 pm at Tue Apr 20, 2021 3:17 pm
>
> 
Simple answer is that you should change all of them to make it work. 

As for editing, that depends what is the format of the font. Is it DDS or TTF? Or something else?
Can you show some screenshots?

For export/import you can use tools like UnityEx or UnityAssetsExplorer.

So, i've packed away a lot of information on this imgur below, i could find some other things too and the font file.
[https://imgur.com/a/DZ4r59p](https://imgur.com/a/DZ4r59p)
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-04-20T17:14:44+00:00
- Post Title: Emily is Away too Translation

Well, to add new characters to TTF files you can use FontCreator from High-Logic [https://www.high-logic.com/font-editor/fontcreator](https://www.high-logic.com/font-editor/fontcreator)
For DDS files you can use GIMP [https://www.gimp.org/downloads/](https://www.gimp.org/downloads/)

Here is the tutorial for editing DDS/TTF fonts [https://ikskoks.pl/poradnik-8-edycja-cz ... -oraz-dds/](https://ikskoks.pl/poradnik-8-edycja-czcionek-w-formacie-ttf-oraz-dds/)

As for packing/unpacking you can use UnityEx as I said earlier.
## Post #7
- Username: Rain
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Apr 20, 2021 4:34 am
- Post datetime: 2021-04-20T17:39:12+00:00
- Post Title: Emily is Away too Translation

> Reply from ikskoks ↑Wed Apr 21, 2021 1:14 am at Wed Apr 21, 2021 1:14 am
>
> 
Well, to add new characters to TTF files you can use FontCreator from High-Logic https://www.high-logic.com/font-editor/fontcreator
For DDS files you can use GIMP https://www.gimp.org/downloads/

Here is the tutorial for editing DDS/TTF fonts https://ikskoks.pl/poradnik-8-edycja-cz ... -oraz-dds/

As for packing/unpacking you can use UnityEx as I said earlier.

K, really thank you! Also, you saw the imgur link that i sent? If yes, then, i'm doing it at the right way, or you can see another type of problem / way to solve it?
## Post #8
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-04-20T17:43:56+00:00
- Post Title: Emily is Away too Translation

Yeah, I saw it. For the TTF font and main DDS font everything should be easy to edit, but you may have some issues with additional DDS fonts, because there are not enough characters to replace as I saw on those screenshots - in that case I would just leave it as it is, because it is too much effort in my opinion to fix this.
## Post #9
- Username: Rain
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Apr 20, 2021 4:34 am
- Post datetime: 2021-04-20T21:38:58+00:00
- Post Title: Emily is Away too Translation

> Reply from ikskoks ↑Wed Apr 21, 2021 1:43 am at Wed Apr 21, 2021 1:43 am
>
> 
Yeah, I saw it. For the TTF font and main DDS font everything should be easy to edit, but you may have some issues with additional DDS fonts, because there are not enough characters to replace as I saw on those screenshots - in that case I would just leave it as it is, because it is too much effort in my opinion to fix this.

K, thanks a lot for your help!
## Post #10
- Username: Rain
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Apr 20, 2021 4:34 am
- Post datetime: 2021-04-20T22:00:33+00:00
- Post Title: Emily is Away too Translation

> Reply from ikskoks ↑Wed Apr 21, 2021 1:43 am at Wed Apr 21, 2021 1:43 am
>
> 
Yeah, I saw it. For the TTF font and main DDS font everything should be easy to edit, but you may have some issues with additional DDS fonts, because there are not enough characters to replace as I saw on those screenshots - in that case I would just leave it as it is, because it is too much effort in my opinion to fix this.

Ok, so, i've got now another problem, the .ttf font that the game is using has all the characters that my language uses, or Latin-1-Supplement. Now i don't know what i should do because, the forced square seems to be the main font used by the game, i'm gonna try edit the other fonts, but, i don't know what i should do now with the forced square.

[https://imgur.com/a/dyAQeQH](https://imgur.com/a/dyAQeQH)
## Post #11
- Username: Rain
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Apr 20, 2021 4:34 am
- Post datetime: 2021-04-20T22:36:59+00:00
- Post Title: Emily is Away too Translation

Also, how do i can insert characters at the dds fonts, because the width and height of the images are just too low. Also, even if i can insert another character, how do i make to it recognize that character is ê é or something like it? 

[https://imgur.com/a/smMvoVS](https://imgur.com/a/smMvoVS)
## Post #12
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-04-21T07:25:39+00:00
- Post Title: Emily is Away too Translation

> Also, how do i can insert characters at the dds fonts, because the width and height of the images are just too low. Also, even if i can insert another character, how do i make to it recognize that character is ê é or something like it?
I told you earlier that it is the issue which can't be solved so easily in most cases.
You have to either find the file with character mapping if it exist and edit it properly or try to debug the game  and figure out how the  characters are mapped.

Only easy solution is to ignore those fonts...

> the .ttf font that the game is using has all the characters that my language uses, or Latin-1-Supplement.

For me it just means that you're looking at the wrong font, but you can of course test that in game.
Try to make some changes and check if you can see something different in the game.
## Post #13
- Username: Rain
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Apr 20, 2021 4:34 am
- Post datetime: 2021-04-21T10:41:47+00:00
- Post Title: Emily is Away too Translation

> Reply from ikskoks ↑Wed Apr 21, 2021 3:25 pm at Wed Apr 21, 2021 3:25 pm
>
> 
Also, how do i can insert characters at the dds fonts, because the width and height of the images are just too low. Also, even if i can insert another character, how do i make to it recognize that character is ê é or something like it? 
I told you earlier that it is the issue which can't be solved so easily in most cases.
You have to either find the file with character mapping if it exist and edit it properly or try to debug the game  and figure out how the  characters are mapped.

Only easy solution is to ignore those fonts...
the .ttf font that the game is using has all the characters that my language uses, or Latin-1-Supplement.

For me it just means that you're looking at the wrong font, but you can of course test that in game.
Try to make some changes and see if you can see something different in the game.

Yeah, it sounds like it's the wrong font, btw seems that the game uses the DDS ones for the main characters, so now i'm out of ideas, like, the DDS is really the fonts that doesn't have the characters i want, and i could'nt find the files that maps the keys, but, later i'll check it even more, for now i'll try something else, but, i'm not sure what i should do with the DDS files.

Another question, so if i find the code or the way the games maps the bitmap, i can increase the amount of height/width and code myself to detect the new characters in a way that i want? Like, i'll increase the file height by 100 and then detect the character that i added, and so on.
## Post #14
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-04-21T11:12:32+00:00
- Post Title: Emily is Away too Translation

> Another question, so if i find the code or the way the games maps the bitmap, i can increase the amount of height/width and code myself to detect the new characters in a way that i want? Like, i'll increase the file height by 100 and then detect the character that i added, and so on.

That really depends on the game and it may not be as simple as you think. You would need to find this code (or mapping) first, understand it, reverse engineer it and then patch it in some way. That requires some good reverse engineering and programming skills.
## Post #15
- Username: Rain
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Apr 20, 2021 4:34 am
- Post datetime: 2021-04-21T13:51:44+00:00
- Post Title: Emily is Away too Translation

> Reply from ikskoks ↑Wed Apr 21, 2021 7:12 pm at Wed Apr 21, 2021 7:12 pm
>
> 
Another question, so if i find the code or the way the games maps the bitmap, i can increase the amount of height/width and code myself to detect the new characters in a way that i want? Like, i'll increase the file height by 100 and then detect the character that i added, and so on.

That really depends on the game and it may not be as simple as you think. You would need to find this code (or mapping) first, understand it, reverse engineer it and then patch it in some way. That requires some good reverse engineering and programming skills.

Damn, about reverse engineering i just know the basic of the basic, like, debugging and finding how i can do it will be a pain, idk if it'll be worth it, but, instead i'll just translate the game without the accents, would be confusing but better than nothing, really thanks for all the help that you gave me!
