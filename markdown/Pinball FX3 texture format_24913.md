## Post #1
- Username: BlackStarEOP
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 03, 2022 8:28 pm
- Post datetime: 2022-01-03T13:11:25+00:00
- Post Title: Pinball FX3 texture format

Hi guys, new to the forum with a question I hope you guys have some info/suggestions about 

Currently I'm working on parsing the textures from Pinball FX3 tables. I have used QuickBMS and the PXP format decoder to get all the files from the archive, but it doesn't stop there.
My entire C++ codebase for this thing is at [https://github.com/BlackStar-EoP/dmdwidget](https://github.com/BlackStar-EoP/dmdwidget) if you want to see what I've done so far (beware it's a bit more than just a ripper for these textures)

Screenshow from my tool:



fx3 texture.jpg (219.35 KiB) Viewed 36 times



What I have done here is import a texture file as is, and read 4 bytes as RGBA. As you can see the colors are totally incorrect. What I have tried so far is  every permutation of RGBA, combined with reversing bits, swapping nibbles and nothing I did has any decent results so far.

It seems the data is more or less uncompressed since I can clearly see things when opening a single file. It seems that it has some precalced mipmaps, but at the bottom of the file, there is this rainbow noise that follows the same pattern.

My hunch here is that somehow you have to combine the images to create the end-result. What is striking to me is how detailled everything looks ingame, but if you take a look at these textures, they are fairly low res (main playfields are 512x1024)

Does anyone have a clue how these textures are stored?
