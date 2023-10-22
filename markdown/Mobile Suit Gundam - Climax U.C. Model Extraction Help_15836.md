## Post #1
- Username: lohengram
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 31, 2015 5:16 pm
- Post datetime: 2017-02-05T17:42:45+00:00
- Post Title: Mobile Suit Gundam - Climax U.C. Model Extraction Help

Hey Everyone,

Wanted a few models out of Mobile Suit Gundam - Climax U.C. anyone have a good method for accomplishing that? I have it broken down to the fpk files but got stuck there. If anyone can help me get the files out of the fpk or even models I would be grateful.

[http://www.mediafire.com/file/e1ksi26xvmn87y9/szb0.fpk](http://www.mediafire.com/file/e1ksi26xvmn87y9/szb0.fpk)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-02-05T18:42:21+00:00
- Post Title: Mobile Suit Gundam - Climax U.C. Model Extraction Help

1719 vertices from 0x73D64 build some line.

v -11.322868 -11.193009 -10.762479 
v -10.552279 -10.546121 -10.173987 
v -10.173955 -10.042491 -10.014354 
v -9.943300 -9.925982 -9.894806 
...
v -0.000065 0.000002 0.000046 
v 0.000109 0.000132 0.000185 
v 0.000220 0.000267 0.000331 
v 0.000499 0.000811 0.000878 
...
v 9.519199 9.559419 9.579540 
v 9.615817 9.689540 9.796847 
v 9.798254 9.823747 10.000000 
v 10.134120 10.211040 10.216042 


The rest up to 0x79824, too:

v 40.000000 70.000000 100.000000 
v 110.000000 120.000000 150.000000 
v 160.000000 170.000000 180.000000 
v 185.000000 190.000000 200.000000 
v 250.000000 280.000000 300.000000 
v 330.000000 350.000000 370.000000 
v 400.000000 420.000000 450.000000 
v 460.000000 470.000000 480.000000 
v 485.000000 490.000000 500.000000 
...
v 11760.000000 11800.000000 11820.000000 
v 11830.000000 11850.000000 11900.000000 
v 11920.000000 11930.000000 11950.000000 

(just increasing values)

Some assumed animation data, point cloud here (copy 6 lines into an empty text file, rename it to whatever.h2o, use with hex2obj, view link in my sig):
0x5F83C 501
Vb1
12 99
0x6364 35
020000
0x0 255



szb0-fpk_.JPG (89.95 KiB) Viewed 75 times
## Post #3
- Username: lohengram
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 31, 2015 5:16 pm
- Post datetime: 2017-02-13T07:27:36+00:00
- Post Title: Mobile Suit Gundam - Climax U.C. Model Extraction Help

Hello shakotay2,

Thank you for your help sorry for the late reply. I had to have a friend give me a crash course in Hexadecimal so I could begin to understand the tool. I created the h20 file that you suggest and loaded it into the program. 

The part where I get confused is do I load the file and use the settings provided by the file or do I need to work my way thru the file like you have done in the tutorial and change the data in the program. 

Sorry to bother you more I am just a total noob at this so a bit confused. On the bright side now understand how hexademical is determined and how it works.
