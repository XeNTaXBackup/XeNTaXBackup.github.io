## Post #1
- Username: alininavcisi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 06, 2020 2:21 pm
- Post datetime: 2021-05-13T10:03:46+00:00
- Post Title: [Fantasy Tennis] Need help to add new material/texture to model file

Hello everyone. 

We are working on a game called "Fantasy Tennis" to add new content to game. This is private server, revived the game last months. You can reach community & download here : [https://www.jftse.com/](https://www.jftse.com/)

We are able to extract models to 3dsmax via excellent plugin called Fat Importer : [viewtopic.php?f=33&t=7901&sid=5547ae75a ... b0831fcabc](https://forum.xentax.com/viewtopic.php?f=33&t=7901&sid=5547ae75ae90b80bc63cbeb0831fcabc)

You can download plugin & model file here : [https://drive.google.com/file/d/1B4aelJ ... sp=sharing](https://drive.google.com/file/d/1B4aelJG_D7YINtNASmuV3Sv6MYyGuUjh/view?usp=sharing)
(2ec5ffbc is Fantasy Tennis script)


We can find costume name via search. Here C_Niki_DB is for Divinity costume. It's material name or mesh name, I don't know it. But If you look, you will see texture names called "MCommon_DB00, 01 etc". They are .dds texture file references and I am able to change them. Here example :



When I change existing line, everything works. For example, I have changed MCommon_DB00 to MCommon_DB04(It's texture file I made) and game works perfectly. But however, when I "insert" new texture reference like in first picture(red text), game crashes. Game checks texture count or offset somewhere. Because instead of inserting, I tried to remove one texture reference, samethings happen. 

We just want to add new texture reference so we can add new items to the game. Why do you think this crash is happening? And If the problem is offset or texture reference count, where can It be stored? And I tried to read FatImporter script, It's too much complicated I couldn't understand what's going on there. But If I would understand FatImporter script, It would be good.
