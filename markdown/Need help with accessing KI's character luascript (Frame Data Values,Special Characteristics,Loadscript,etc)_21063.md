## Post #1
- Username: Kurome
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 01, 2019 4:23 pm
- Post datetime: 2019-09-02T02:48:10+00:00
- Post Title: Need help with accessing KI's character luascript (Frame Data Values,Special Characteristics,Loadscript,etc)

While looking through the files I extracted from the GLOBAL.PAK in Killer Instinct , I managed to find where the frame data for all the characters was located as well as the files used to determine certain properties like velocity and multipliers. The files used for the damage, velocity and multipliers had a ".9" file extension but were readable and editable in a normal text editor. The frame data also had this ".9" file extension and was readable just like the other file, but didn't actually affect frames/values or special characteristic about the moves. I believe that this was only used to show information through the "Attack Data" option in the game, which just shows you the values of a move's frame data. After looking through the folder a bit more, I found that there were XML files that had character names on them. These files were readable with a text editor and had a bunch of load information with directories to the various files of the character. While looking through it, I noticed that there was a line pointing to the specific character's load script. The load scripts to the characters were located in a directory named "luascript". When I accessed it, there was folder name "characterscript". This folder had the names of all the different characters, which contained not only the load the script that was being pointed to but a bunch of other files that had "seq" in them, followed by the types of moves of that character. (Normal, Special, Shadow, etc.). All of these were had the file extension ".58" and none of them were readable through a text editor. I tried a bunch of different programs to see if I could open it (3Ds Max, Havoc Preview Tools, Visual Studio, A bunch of different editors, etc.) but nothing was actually able to open the file or provide something that was comprehensible (Just a bunch of random numbers/letters/symbols, replacement characters, etc.). After trying all of this, I decided to run the game using something that could actively view the memory (I used CE for this) while the game was running. I decided to put the names of these files and their directories into the memory search function, but replaced the extension with something like ".lua". The search came up with a bunch of results; almost all of the files were being identified as lua files while the game was running. Additionally, the lua tables were all showing up and had their respective file directories as well as the actual scripting for the moves. They were all visibly written in lua code and had things such as special characteristics, the frame values and even developer comments of what each part of the script was doing. I'm very certain that these ".58" files contain the actual lua scripting to the moves of all characters.



Now we can get to the problem I've been having...



None of the files in the luascript directory were readable as is. I can't really figure out if they're encrypted or if something else is processing them and making them readable. None of the files have the extension of ".lua" in the game's folder. I tried changing the extension and seeing if they could be de-compiled, but they'd always give something like an "Invalid Signature" error. I'm wondering if there's a way to find out what's responsible for processing these files and if there's a way to change or revert them to a readable state and hopefully be able to change them back to their current state so the game can load them (Or if they just have some really tight security, Decrypt them to edit them and Re-Encrypt them so the game can load them).


I'm unable to actually upload the files since it said they weren't allowed, so I would need permission to send them to somebody or to temporarily change the extension so they'll upload. 


gameinfo/scriptdata

(This is where all the ".9" files and XML files were located. They followed a naming pattern, so I'll put an example of how they're labeled.)

a_charactername_movetype

(Damage values, multipliers and certain properties of the move)

Ex: a_gargos_autodbl

(Gargos' Autodoubles)

c_charactername.EventList

(These are the XML files that pointed me to the luascript folder that I mentioned earlier. They have information on other stuff too, like bone and attachment files.)

Ex: c_gargos.EventList

(The specified locations of different files for Gargos)


gameinfo/scriptdata/FrameData

(This is the folder that had the tables of the Frame Data of all the characters, but their only purpose is to show the player what the FrameData is, specifically with the "Attack Data" option. These files don't affect the actual moves. All these files have the extension of ".9")

KI_charactername_FrameDataAndMove_Datax

(The frame data about the character)

Ex: KI_Gargos_FrameDataAndMove

(Gargos' Frame Data)

gameinfo/luascript

(I'm pretty certain that this is the directory where the lua scripts for all the various characters is stored. The problem is that none of it is actually readable outside of the game running it. Each character has their own folder.)

gameinfo/luascript/characterscript

(The location of the characters and their folder

Ex: gameinfo/luascript/characterscript/gargos

(Gargos' lua scripts)

Then their are a bunch files with lua scripts to different things about the character

gameinfo/luascript/characterscript/charactername/charactername

(The character's have their own lua tables)

Ex:gameinfo/luascript/characterscript/gargos/Gargos

(Gargos' Lua Table)

gameinfo/luascript/characterscript/charactername/charactername_LoadScript

(The file that the EventList XML's specified as the LoadScripts for all the characters)

Ex: gameinfo/luascript/characterscript/gargos/Gargos_LoadScript

(Gargos' LoadScript)

gameinfo/luascript/characterscript/charactername/character_SeqCharacterAction

(The luascript of a character's specific action)

Ex: gameinfo/luascript/characterscript/gargos/Gargos_SeqSpecialAttack

(Gargos' Special Attacks)



As you can see, there's quite a lot going on between these files. The ".58" files are what I'm actually trying to get access to as something readable. These files were mentioned in the memory viewer I used and have all of the really technical stuff and appeared to be written in lua. These are what I want really access to and I'm really hoping that I can receive some help with doing so.
