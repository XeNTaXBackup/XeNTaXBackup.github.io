## Post #1
- Username: carnage
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Jun 26, 2012 10:21 pm
- Post datetime: 2012-06-26T16:04:50+00:00
- Post Title: Tool Extraci/Import Scripts RE 5 and CLoS

Friends programmers come here asking for your help in two games if possible.
I know this script to extract the text from the Castlevania Lord of Shadows

[quote] idstring BFPK
get long version
files get long
savepos TMP
for i = 0 <files
goto TMP
get long nSize
getdstring name nSize
get size long
get offset long
savepos TMP
goto offset
get zsize long
savepos OFFSET
if size == zsize
log name offset zsize
else
clog name size offset zsize
endif
goto TMP
next i
[/ quote]

Extracted everything right, but I am not knowing add the files back, I have to create another script to reimport?

The other question is about the Resident Evil 5, our friend Caws member of our group of translations Monkey's Traduções, completed the tool for the extraction of protests for the PS3 version though, the guy disappeared from the map no longer has the news and Caws all documentation of the tool is only what is lost here in the forum.
I would appreciate if someone can edit the file's read for the Xbox 360 version.

I appreciate the cooperation of all friends.
