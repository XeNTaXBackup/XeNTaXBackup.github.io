## Post #1
- Username: Dartfeld
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 21, 2022 7:30 pm
- Post datetime: 2022-08-03T13:41:07+00:00
- Post Title: "Captain Earth: Mind Labyrinth" PSVita character .dat file

Hi, I wanted to extract all the resources from this game, which were in obscure GPDA .dat files, after extracting virtually everything using quickBMS and noesis for conversion, what's left are (I assume) the characters full portraits, but after extracting the script_charactor.dat file  I'm left with another set of .dat files that are not GPDA anymore. Inside each file with hex what I can only get is a "list.dat" string, so not a clue what I can do to extract this one. I guess what this file contains is a group of files (because with the character small portraits was something like this, but in a GPDA containter). Any help will be much appreciated!

Here you have one of the extracted files as a sample:
[DAI_1C.dat](https://mega.nz/file/atxUiQ4T#HgiYQkLowCaCzHB7EPKxtj_v1Gel1kX7ArdNs45uebo)
And here is the container file for all these:
[script_charactor.dat](https://mega.nz/file/jgADiJKI#pTPObW07WlrbmXFIy7krQE7K9xh_yIZIhsaOur7hveI)
To extract the files from the script_charactor I used this quickBMS script
[Accel World Kasoku no Chouten (PS3) - XeNTaX Forum](https://forum.xentax.com/viewtopic.php?t=10195)

EDIT: Found the solution! In the end, the new .dat file is not a .dat file at all! It ocurred to me as all the previous files extracted from GPDA were .gxt.gz to change the extension of the file, and it worked! Inside there is indeed a "list.dat" file that is another GPDA, and extracting this file...has the remaining gxt files! 

Conclusion: If anyone in the future find this, the only tools needed to extract everything are quickBMS with the script and noesis (or similar) for file conversion.
