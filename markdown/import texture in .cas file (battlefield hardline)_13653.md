## Post #1
- Username: A20Group
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Nov 28, 2014 12:36 am
- Post datetime: 2015-12-10T14:41:38+00:00
- Post Title: import texture in .cas file (battlefield hardline)

Hi to all
i am export all texture and ebx file and mesh and .... from battlefield hardline with FrankElstner scripts
now i want reimport a texture in .cas file
for example
season_1_thumb_07.dds file  There is in cas_06.cas with  SHA1: 953eb4d9df3dc8222e11147445a558996549bd28
now I want to replace edited texture with hex But I can not find the original texture Code
After research, I realized the files were compressed with LZ77
I need a way or a program for compression texture with LZ77 To then be able replace edited texture.
I picked up LZ77.dll from FrankElstner scripts and I uploaded for you It might help you out
[http://upload.a20game.com/images/nyekk9 ... eyb390.rar](http://upload.a20game.com/images/nyekk90q1zmkpbeyb390.rar)
Many thanks that you have read the text
I am waiting for your response
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-12T07:12:35+00:00
- Post Title: import texture in .cas file (battlefield hardline)

try this one for battlefield 4

[http://captainsplexx.github.io/FrostBite3Editor/](http://captainsplexx.github.io/FrostBite3Editor/)
## Post #3
- Username: A20Group
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Nov 28, 2014 12:36 am
- Post datetime: 2015-12-17T12:57:20+00:00
- Post Title: import texture in .cas file (battlefield hardline)

> Reply from daemon1
>
> try this one for battlefield 4

http://captainsplexx.github.io/FrostBite3Editor/

thank you for FrostBite3Editor Program but i want a program that can compress any files by LZ77 algoritm (with DLL that i put above)
i'm wait for your help
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-17T15:22:57+00:00
- Post Title: import texture in .cas file (battlefield hardline)

> Reply from A20Group
>
> i want a program that can compress any files by LZ77 algoritm (with DLL that i put above

That dll CAN'T compress files. That is dll Frank wrote ONLY to decompress. And this is not standard algorithm, this is custom compression based on LZ77. You need to write a new compression program yourself.
## Post #5
- Username: A20Group
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Nov 28, 2014 12:36 am
- Post datetime: 2016-01-02T10:27:42+00:00
- Post Title: import texture in .cas file (battlefield hardline)

> Reply from daemon1
>
> A20Group wrote:i want a program that can compress any files by LZ77 algoritm (with DLL that i put above

That dll CAN'T compress files. That is dll Frank wrote ONLY to decompress. And this is not standard algorithm, this is custom compression based on LZ77. You need to write a new compression program yourself.

Now there is no way that I would replace a texture
For example I decompress cas files then replace a texture With hex Or any other way
That did not do anything?
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-01-04T20:14:06+00:00
- Post Title: import texture in .cas file (battlefield hardline)

FrostBite3Editor can replace textures by making "paches" to the game files. Have you tried it?
