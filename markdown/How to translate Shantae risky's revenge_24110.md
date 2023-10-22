## Post #1
- Username: Evilangel
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jun 25, 2021 1:45 pm
- Post datetime: 2021-06-25T06:02:08+00:00
- Post Title: How to translate Shantae risky's revenge

Hi everyone, im new here, im pretty basic on computer stuff and windows basics.

I want to translate that game, same "foward point" kind as similar ported games to pc like ducktales and other shantae games.

A friend of mine gave me the extracted .pak files with many folders and files with .anb .lua .typ .an8 

I'm just interested in find the text files, any tools to explore those files? i just don't want to translate but learn how to extract them for future stuff. I want to translate Okami in the future... but this one for now...

This game its only on english, multi on wii, oh btw i want to translate it in spanish, and the wii version already has it but not the pc port. 

No spam intention or anything, this is the link with the unpacked .pak files nade by my friend if someone want to take a look. 
[https://krakenfiles.com/view/oVRTXGHQ31/file.html](https://krakenfiles.com/view/oVRTXGHQ31/file.html)

Oh and.. nice to meet you all.
## Post #2
- Username: Evilangel
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-06-25T07:32:06+00:00
- Post Title: How to translate Shantae risky's revenge

Hi, text is inside those two files:
\data\global.pak.temp\global_shantaetext.loctext
\data\global.pak.temp\global_shantaecredits.loctext

[https://i.imgur.com/FL73ELq.png](https://i.imgur.com/FL73ELq.png)

And tools for export and import are here:
[https://drive.google.com/drive/folders/ ... xS6ipd1VCQ](https://drive.google.com/drive/folders/0B7LaUGSR3677MFlBRlpJT2c3Uk0?resourcekey=0-badkNeKanpwTxS6ipd1VCQ)
You just need to compile them with AutoIt.
## Post #3
- Username: Evilangel
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jun 25, 2021 1:45 pm
- Post datetime: 2021-06-25T21:57:25+00:00
- Post Title: How to translate Shantae risky's revenge

thank you maaaan! Poland women are the most beautiful and loyal in the world!
## Post #4
- Username: Evilangel
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jun 25, 2021 1:45 pm
- Post datetime: 2021-06-25T22:53:33+00:00
- Post Title: How to translate Shantae risky's revenge

Question: (to learn) all those game-name files are like a dictionary of codes to read similar games, right? just to know.
## Post #5
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-06-26T08:22:46+00:00
- Post Title: How to translate Shantae risky's revenge

> Reply from Evilangel ↑Sat Jun 26, 2021 6:53 am at Sat Jun 26, 2021 6:53 am
>
> 
Question: (to learn) all those game-name files are like a dictionary of codes to read similar games, right? just to know.

Yeah, something like that. These are just source codes of the programs written by swuforce from zenhax forum for translating specifig games.
If you'll search hard enough, you could even find compiled versions on zenhax.
## Post #6
- Username: Evilangel
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jun 25, 2021 1:45 pm
- Post datetime: 2021-06-26T16:29:05+00:00
- Post Title: How to translate Shantae risky's revenge

Nice!
## Post #7
- Username: Evilangel
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jun 25, 2021 1:45 pm
- Post datetime: 2021-07-03T03:11:15+00:00
- Post Title: How to translate Shantae risky's revenge

Sup man. I'm about to start (i wish i could earlier but etc life sucks) 

so yeah now that i have the text files and learning by my own reading some stuff i want to ask you:

how do i pack the loctext files into a .pack file again? 

You see my language (spanish) use few extra words to describe stuff and also use characters like Ñ or ó so I need to test it to see if those characters or lenght of words affects the game.
## Post #8
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-03T09:50:47+00:00
- Post Title: How to translate Shantae risky's revenge

> how do i pack the loctext files into a .pack file again?
There are some tools available, but I'm not sure if they have any support for Shantae games, so you need to check it yourself.
Here are the links:
[https://github.com/artlavrov/paktools/](https://github.com/artlavrov/paktools/)
[viewtopic.php?t=10687](https://forum.xentax.com/viewtopic.php?t=10687)
## Post #9
- Username: Evilangel
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jun 25, 2021 1:45 pm
- Post datetime: 2021-09-29T21:51:44+00:00
- Post Title: How to translate Shantae risky's revenge

Hi there, long time not visiting the site, for some reason my internet service didnt allow me to load the website, and i dont wanted to use proxies, last time i did it i was banned in other site.

Anyway... about this shantae project i have some troubles.

Game: Shantae Risky's revenge wayforward "pc port".

Objective: translate to spanish

Tools: 

>im using DuckTalesTools.exe to extract (and pack) .loctext files from global.pak

>im using the shantaeriskysrevenge_export.au3  (import) to extract the text files from .loctext

Using the .au3 i export the .loctext, there is a file.text to translate.

I tested some words using ñ , " ; ¿? etc symbols, then i imported the file again using .au3 to a .loctext BUT the size its different. WHen i pack this into the global.pak <- then copy it to the game folder it crashes with a message "dump was not created"*

And even the size its still different when i export and import everything without doing any change with the same crash error. What to do?
## Post #10
- Username: Evilangel
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-09-29T22:13:08+00:00
- Post Title: How to translate Shantae risky's revenge

No idea, maybe wrong encoding? You could try to contact tool's author to get some help.
## Post #11
- Username: Evilangel
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jun 25, 2021 1:45 pm
- Post datetime: 2021-09-29T22:20:57+00:00
- Post Title: How to translate Shantae risky's revenge

Will do, thanks fren.
