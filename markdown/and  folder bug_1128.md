## Post #1
- Username: Visirot
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-03-23T10:26:39+00:00
- Post Title: ":" and "*" folder bug

Hi

Just to tell there is a slight bug in the main mc.mrf file, that crashes mexbinder when you try to extract all the bms files.
That's because they are extracted in folders that have the name of the game/format, and a couple of them have illegal characters.
These are "Star Trek : BOTF" because ":" is not allowed in a folder, and there is another one that is "Lemmings *.xxx" (don't remind the extension) that crash the global extraction with a 'error 76 folder not ound" or alike. 
This can be easily corrected by hex editing the mc.mrf and replacing the : and * with a space.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-03-23T11:23:21+00:00
- Post Title: ":" and "*" folder bug

Thank you. This error has been noticed earlier and is already fixed. The new version of MexBinder is waiting to be released with a new version of MultiEx Commander.
