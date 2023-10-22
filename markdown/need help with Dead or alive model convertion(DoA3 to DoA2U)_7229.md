## Post #1
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2011-08-24T07:00:45+00:00
- Post Title: need help with Dead or alive model convertion(DoA3 to DoA2U)

hi everybody. 
I made a conversion tool for models from doa3 to doa2u. but because i do lack knowledge on some values(badly i can't reverse "greed explorer"), it's shitty and work's wrong. if there's someone that can help me, please do it...

i found that both doa3 and doau contains the same test stage(a hexagon with different types of walls). researching this stage was very helpful and my converter converts it perfectly  (i also made a program that's looking in all models of the game, for what values can take a certain variable)


bellow is an image, with the same "OBJ" represented in doau and doa3 xpr, that shows my conversion method:

from what i found:
 - green and yellow parts are copied directly
 - gray are constant
 - about uncolored values, in doau OBJ, i don't know shit, and i use the same values
 - and purple(which is the amount of vectors) is calculated(incorrectly most times) like this:

for(each doa3vector) doa3allVectors += doa3vector + 4;
//and right after this "for" i do this
doa2vector = doa3allVectors - 4;


also if you ask me, i can share more information i have. please help
## Post #2
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-08-24T09:39:50+00:00
- Post Title: need help with Dead or alive model convertion(DoA3 to DoA2U)

umm well some of them maybe help [Dead or Alive tools [download]](http://forum.xentax.com/viewtopic.php?f=16&t=6392&hilit=Dead+or+alive)
