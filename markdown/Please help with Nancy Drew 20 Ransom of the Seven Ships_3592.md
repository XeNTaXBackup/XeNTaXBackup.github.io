## Post #1
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-07-18T03:02:40+00:00
- Post Title: Please help with Nancy Drew 20 Ransom of the Seven Ships

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-18T11:50:55+00:00
- Post Title: Please help with Nancy Drew 20 Ransom of the Seven Ships

Here it is I did not extract the name table

```
set PNG string .png
set LUA string .lua
set XSHEET string .XSHEET
math FILES += 2341
goto 0x1C


for i = 0 < files
math NAME += 1
savepos START
goto START
getdstring NULL 0x2C
get SIZE long
savepos OFFSET
math COUNTER += 1
get TYPE long


if TYPE == 1196314761
string NAME += PNG
else if TYPE == 1635077147
string NAME += LUA
else if TYPE == 1162367832
string NAME += XSHEET
else
string NAME += UNK
string NAME += COUNTER
endif

log NAME OFFSET SIZE
math OFFSET += SIZE
goto OFFSET
savepos START
next i


#some name table I am not good at combining  these yet.
#goto 0x56EEF3B
#for j = 0 < files
#get ID long
#getdstring NAME 0x40

```
## Post #3
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-07-18T12:29:02+00:00
- Post Title: Please help with Nancy Drew 20 Ransom of the Seven Ships

Very thanks!
## Post #4
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-07-18T12:45:57+00:00
- Post Title: Please help with Nancy Drew 20 Ransom of the Seven Ships

But i need the real filename for the file.
Because i need to repack it.
Can you make another script?
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-18T13:42:30+00:00
- Post Title: Please help with Nancy Drew 20 Ransom of the Seven Ships

You don't need the name of the file to repack the file.
the files are not compressed just find your uncompressed file in that big archive and then just overwrite it with the new one.
what do you want to do mod the textures or lua files?
if you want to mod the textures there is an easier way than reinserting them into the archives.
just use tex mod to change the textures with that program very easy to use.
## Post #6
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-07-18T23:08:25+00:00
- Post Title: Please help with Nancy Drew 20 Ransom of the Seven Ships

I want to translate this game so i need repack it.
What is tex mod?
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-18T23:18:32+00:00
- Post Title: Please help with Nancy Drew 20 Ransom of the Seven Ships

kust follow this guide only use your game
[http://wiki.guildwars.com/wiki/Guide_to ... e_graphics](http://wiki.guildwars.com/wiki/Guide_to_modifying_in-game_graphics)
