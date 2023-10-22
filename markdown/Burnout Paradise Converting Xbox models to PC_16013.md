## Post #1
- Username: DGIorio
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 11, 2016 6:12 am
- Post datetime: 2017-03-17T23:05:15+00:00
- Post Title: Burnout Paradise: Converting Xbox models to PC

Hi guys,
I'm converting some Burnout cars from Xbox version of the game to PC version, but I need help converting the model because it has differents index and vertex list (but it is similar).

The index list in the xbox version is formed by triangle strips, however the PC versions just use triangles. I managed to convert it using the program hex2obj (by shakotay), and getting the index from the obj. And then converting it to hexadecimal. To convert the index list to hexadecimal I build a program (in MatLab) that write it in a .txt file, but the whole process take a long time.

The real problem is in the vertex list, because the UV coordinates and other things are different in which version. PC uses float (32 bits) and Xbox uses half float (16 bits). The 'x,y,z' coordinates are in big endian float in Xbox and PC it is little endian float.

Can someone help me converting half float to float? I tried to make a program, but I just know Fortran and MatLab hehehe.
There are example files attached at the post.

Images of my best result: [http://imgur.com/a/wysUO](http://imgur.com/a/wysUO)


(If someone would like to build a program to direct convert a full model from Xbox to PC I would like to help)
[Examples.rar](https://xentaxbackup.github.io/file/12651_Examples.rar)
