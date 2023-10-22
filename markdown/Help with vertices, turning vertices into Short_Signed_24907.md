## Post #1
- Username: TheYellowFlash26
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 02, 2022 12:48 pm
- Post datetime: 2022-01-02T05:09:31+00:00
- Post Title: Help with vertices, turning vertices into Short_Signed

Hi everyone, I came to ask for help with a Model of a game that I'm studying the Models and I'm aiming to be able to modify them, and I recently came across these vertices of the Short_Signed type, which are 2 bytes in 2 bytes (from what I understand ), the real question is that I wanted to know how to take the vertices I can see in the OBJ and transform them back into Short_Signed, I can even identify where each vertex is but I don't know what I calculate I have to do to transform them back for Short_Signed, I'll send a sample file.


Sample file: [https://drive.google.com/file/d/1E_ulWI ... sp=sharing](https://drive.google.com/file/d/1E_ulWISkNJxnRyq8jAw5q14QhEZBwnBq/view?usp=sharing)


Well, first of all, I'm going to talk about what I've discovered so far about these Models, in the Offset 0x20 it has the vertex count, in case this file is 0x18, which converting from 24, so this box contains 24 vertices. Each vertex is divided by 3 pieces of 2 bytes, 0x2, 0x2, 0x2 = 0x6, which I assume is X, Y, Z. 

Offset 0x24/Vertice 1:

24 FE = X
DC 01 = Y
00 00 = Z


Before you ask if this box has faces the answer is no, this game uses a modeling system they don't store faces in the file, they are automatically generated in the game itself. But that's whoever knows how to convert or any idea to help me I'm grateful in advance, thank you
## Post #2
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2022-01-02T08:13:57+00:00
- Post Title: Help with vertices, turning vertices into Short_Signed

When games use short signed for positions, they retrieve the value by dividing by the max absolute value so 32767. However as you can see this only allows values between -1 and 1. So either games are fine with that or they have an additionnal scale/bias pair to scale and offset the values. Sometimes these are determined using the bounding box info or other data. So the final formula ends up being :

position = (short)/32767 * scale + bias

If you don't have these scale and bias vectors then you just need to grab your position, multiply by 32767, round it (there are several to round, most games I dealt with use the round half away from 0 [https://en.wikipedia.org/wiki/Rounding# ... _from_zero](https://en.wikipedia.org/wiki/Rounding#Round_half_away_from_zero) ).
## Post #3
- Username: TheYellowFlash26
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 02, 2022 12:48 pm
- Post datetime: 2022-01-02T15:51:10+00:00
- Post Title: Help with vertices, turning vertices into Short_Signed

As I didn't understand, what I understood was that in 0x24FE the 0xFE is equivalent to -1, 0xFD is -2, FC is -3 etc...

I don't know how this 0x24FE gave -1.8594 converted
