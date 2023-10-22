## Post #1
- Username: Gogeta
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 06, 2023 4:03 pm
- Post datetime: 2023-09-06T09:56:16+00:00
- Post Title: Chrono Cross's Altered TIM Format

Right now I'm working on an Altered TIM to PNG Converter for the PC Version of Chrono Cross. I already wwrote my own extraction and repacking tool for the prd archives, that holds all the battle textures as altered Tim files.
The extraction and repacking scripts seems to work right. It extracts the prd file and the TIM Files it extracts are readable via tools like timviewer or tim2view and the repacker could reopacking the files back to prd archive and the Game didn't crashed when loading the modded textures.

As I want to make upscaled mods possible for the Game I need to upscale the tim files. The problem is that first it would be good to convert the TIM files to PNG for also preserving the alpha. Now that there's no real Tim to PNG converter out in the wild. I used tim2view, which can do it but it's somewhat a pain in the ass and it foten crashed for no appearnt reasons.
I tried writting my own converter but the Problem is that the TIM formats for the battle stuff are stored in an altered TIM Format, where I tried using the resource here: [https://www.chronocompendium.com/Term/TIM_Textures.html](https://www.chronocompendium.com/Term/TIM_Textures.html) Sadly, as I'm not a profesional Coder it's not working right. The image itself is pulled out, but the CLUT is completely wrong.

Afterwards I of course need to convert the PNG back to the altered TIM Format. Sadly the TIM File that my script generates using the PNG files are not readable at all and I think it's not handling the CLUT and Image Data correctly.

Is there anyone who has knowledge of that altered TIM Format and can help me out with the converter? Everything else should be duoable with my extraction and repacking script.

I've attached a 7zip containing one of the altered TIM Files.
Any help is really much appreciated! 
[bg_03.prd.069.bt02.tim.7z](https://xentaxbackup.github.io/file/24317_bg_03.prd.069.bt02.tim.7z)
## Post #2
- Username: piken
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 25, 2021 9:55 pm
- Post datetime: 2023-09-17T11:09:09+00:00
- Post Title: Chrono Cross's Altered TIM Format

> it's not working right. The image itself is pulled out, but the CLUT is completely wrong.

Although I have no knowledge of the TIM format itself, just opening the file with a raw viewer, we can see the palette starts at 0x0014 with 2-byte palette entries (in increasing bit index order: red x 5 bits, green x 5 bits, blue x 5 bits, transparent x 1). Whenever faced with a problem like this, you can try modifying one of the entries to a specific value which will help debugging (e.g. like palette entry 0 to solid red via tim2view, which helps iron out of channel swapping or bit count issues).
[Chrono Cross's Altered TIM Format topic=27177 bg_03.prd.069.bt02.png](https://xentaxbackup.github.io/file/24355_Chrono Cross's Altered TIM Format topic=27177 bg_03.prd.069.bt02.png)
