## Post #1
- Username: Stallone
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Mar 12, 2020 5:24 am
- Post datetime: 2021-05-01T15:09:39+00:00
- Post Title: New Pokémon Snap [NSP]

Hi,

I am trying to export audio files from New Pokémon Snap. After spending a night trying to do so I come for help.

So far, I was able to partially dump the NSP I got, it gave me the Sounds folder with English and Japanese voices, and lots of sound effects and a few music tracks. The one effect I'm looking for (the annoying ringtone to make pokémon dance) doesn't seem to be there.

There are also bank files in the directory but I don't know how to use them or decrypt the files. Same goes with all the other folders that host models etc. they are wrapped in .drp format that I don't know how to use or dump/decrypt.

I'm really new to this, so if someone with Switch dumping experience could help me I would really appreciate it.

Thanks!
## Post #2
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2021-05-03T00:01:04+00:00
- Post Title: New Pokémon Snap [NSP]

You can try this: [https://github.com/kwsch/NewSnap/releases](https://github.com/kwsch/NewSnap/releases)
## Post #3
- Username: Stallone
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Mar 12, 2020 5:24 am
- Post datetime: 2021-05-03T23:25:28+00:00
- Post Title: New Pokémon Snap [NSP]

Thanks for the suggestion! Just tried it, didn't get any luck with this, it creates an empty -01 folder when trying to dump drpf file... And I provided the required dll from Warframe as mentionned on github so I don't know
## Post #4
- Username: bootyflute
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Feb 24, 2021 9:28 am
- Post datetime: 2021-05-10T18:22:01+00:00
- Post Title: New Pokémon Snap [NSP]

> Reply from Stallone ↑Tue May 04, 2021 7:25 am at Tue May 04, 2021 7:25 am
>
> 
Thanks for the suggestion! Just tried it, didn't get any luck with this, it creates an empty -01 folder when trying to dump drpf file... And I provided the required dll from Warframe as mentionned on github so I don't know

Sadly you can't just drag and drop the files for it to work, you have to use a .bat or command prompt command but it can do whole folders so thats helpful. 
1.cd to the folder you unpacked the extractor and runtime too, make sure you have the whole runtime version downloaded 
2. You should now be in the release folder directory in cmd should look something like C:\Users\YourUsername\Desktop\Release   (replace YourUsername with your actual username)
3. Type: NewSnap.App.exe -drp C:\Users\YourUsername\Desktop\PokemonSnap\nx\Pack\Characters\master (replace YourUsername with your actual username, and whatever your root pokemon snap location is)
4. Hit enter and it should run through all the folders making CH_001 and so on folders
Sorry if this wasn't detailed enough but if you can use some simple cmd commands it is pretty easy! For any other folders, just hit the up arrow and delete the last folder location and type or paste the next master folder you want to extract.
## Post #5
- Username: Stallone
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Mar 12, 2020 5:24 am
- Post datetime: 2021-05-15T12:32:10+00:00
- Post Title: New Pokémon Snap [NSP]

Sorry for the late reply, and thank you very much! I managed to use the program in cmd with your help. I got a couple more sound effects in .bnk extracted from .drp, but still no luck for the ONE i'm looking for... I'll wait more because there might be something more complicated that triggers it. I'll start with extracting all masters.

Thanks again
