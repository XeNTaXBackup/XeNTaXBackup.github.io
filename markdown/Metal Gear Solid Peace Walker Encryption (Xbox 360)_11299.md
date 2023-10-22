## Post #1
- Username: mojobojo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 26, 2011 3:25 am
- Post datetime: 2014-03-10T14:23:40+00:00
- Post Title: Metal Gear Solid Peace Walker Encryption (Xbox 360)

Well a friend asked me to take a look at this encryption method and got more than I bargained for. I ended up copying around 7k lines of assembly into a separate xbox 360 application. There is no way I am going to reverse this much assembly without asking around to make sure this is not something I can find a library for. I just remembered about this forum so thought I would drop by and give it a shot here to see if someone knows. Right now I have the encryption and decryption routines isolated into __asm blocks. Decryption works, I could not get encryption working fully but all the code to do it is there. Looking to see if someone has any insight on this and maybe can recognize this strange encryption. If you have the xbox 360 sdk you can compile and run this code yourself.

Here is the code, I warn you though its a lot of powerpc assembly.
[https://www.dropbox.com/s/qn1yaiqtezw1zb9/MGSPW.rar](https://www.dropbox.com/s/qn1yaiqtezw1zb9/MGSPW.rar)

Alternatively you can view it online.
[https://github.com/mojobojo/PublicXboxS ... GSPW/MGSPW](https://github.com/mojobojo/PublicXboxStuff/tree/master/Applications/Xbox/MGSPW/MGSPW)

Here is a couple of saves too.
[https://www.dropbox.com/s/rmai38xdi9na5ts/mgssaves.rar](https://www.dropbox.com/s/rmai38xdi9na5ts/mgssaves.rar)
