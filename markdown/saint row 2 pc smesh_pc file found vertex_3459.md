## Post #1
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2009-05-03T10:36:23+00:00
- Post Title: saint row 2 pc smesh_pc file found vertex

Hi,
i make some search on saint row 2 files and i found the vertex somebody can look on these files i need to know where is the face hexadecimal section PLEASE (my nickname is dany in Saint row 2 forum)

[http://community.saintsrow.com/viewtopi ... 37&t=28748](http://community.saintsrow.com/viewtopic.php?f=37&t=28748)


 saint row2 model weapons.zip
(26.38 KiB) Downloaded 36 times
## Post #2
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2009-05-08T03:15:28+00:00
- Post Title: saint row 2 pc smesh_pc file found vertex

Very interesting! could you tell me the offset in this file to the vertex data? I'll see if I can find the face index.

Edit:
Never mind. from what I can see it seems like the face index is RIGHT below the vertices. its the "data" you speak of in the saints row forums.

XYZ
Data <- this seems to be the face index.

it is formed of 16bit integers. atm I don't know anything else since I can't figure out the header of the file.

Header:
12 bytes. some sort of signature.
int16 some sort of counter
int16 another counter

Strange data follows.. some sort of obfuscated number or something. after that is in plain text the texture file names.

again more strange numbers and more plain text.
this chunks of strange numbers with plain text seem to be linked to the 2 int16s of the header.

after that there are more chunks with a mixture of floats and something else.  and finaly the vertex and face chunks.
