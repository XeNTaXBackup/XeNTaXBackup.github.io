## Post #1
- Username: PenneyM19
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Apr 07, 2019 6:14 am
- Post datetime: 2021-07-19T18:13:00+00:00
- Post Title: SpongeBob's Truth or Square Possible DDS Texture Format (Wii)

Hello   

I have recently made a basic level editor for SpongeBob's Truth or Square, and it is capable of extracting files and editing some files of the game. Now, I know what the texture files are, and they do not have names or a file extension, but looking at them in a hex editor, they seem to be headerless DDS files, but I've tried many raw data texture editors and texture tools for this stuff, and I get nothing. I'm sure these are the texture files because other games from this same studio have these same kind of texture files but they are viewable in those games. So, if anyone can help me figure out what these are, thank you so much!     

Thanks!

I have attached the unknown texture file here in a zip file.


 Unknown_Texture_PossibleDDS.zip
the unknown texture file that could be a dds file. (9.39 KiB) Downloaded 28 times
## Post #2
- Username: PenneyM19
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Apr 07, 2019 6:14 am
- Post datetime: 2021-07-20T21:15:45+00:00
- Post Title: SpongeBob's Truth or Square Possible DDS Texture Format (Wii)

OK, using Dolphin Emulator's format overlay feature, the textures are CMPR formatted with DXT1, but I cannot figure out how to decompress and open them, nor even open them in general, as I've searched everywhere for how, but I can't figure it out.
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-21T07:23:00+00:00
- Post Title: SpongeBob's Truth or Square Possible DDS Texture Format (Wii)

It seems that your sample is a TPL file with 32 bytes extra header.
[http://wiki.tockdom.com/wiki/TPL_(File_Format)](http://wiki.tockdom.com/wiki/TPL_%28File_Format%29)

So you can for example use Hex Workshop to delete 32 bytes from the beginning of the file
and you can save it as file with *.tpl extension. [https://i.imgur.com/jfTUzQU.png](https://i.imgur.com/jfTUzQU.png)

Then you can install any tool from the wiki article above, for example BrawlBox [https://github.com/libertyernie/brawltools/releases](https://github.com/libertyernie/brawltools/releases)
and then open your new TPL file with it [https://i.imgur.com/cHh23Ub.png](https://i.imgur.com/cHh23Ub.png)
## Post #4
- Username: PenneyM19
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Apr 07, 2019 6:14 am
- Post datetime: 2021-07-21T10:08:14+00:00
- Post Title: SpongeBob's Truth or Square Possible DDS Texture Format (Wii)

Wow, this works! Thank you so much!
## Post #5
- Username: PenneyM19
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Apr 07, 2019 6:14 am
- Post datetime: 2021-08-10T15:41:18+00:00
- Post Title: SpongeBob's Truth or Square Possible DDS Texture Format (Wii)

The Wii textures work when removing the extra header and renaming it to .tpl, so thanks! But now I'm looking at the Xbox 360 version of the game and the textures seem to be a completely different format, and I wonder if you or anyone else can help with these now. I have attached a sample of the 360 version of the unknown texture format.


 X360_ToS_TextureFileSample.zip
(130.21 KiB) Downloaded 20 times



Thanks for the help!
## Post #6
- Username: lilyampykidXeNTaXalt
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 28, 2021 5:11 am
- Post datetime: 2021-08-28T16:27:11+00:00
- Post Title: SpongeBob's Truth or Square Possible DDS Texture Format (Wii)

I've also got a texture that I got to have help with, so I'm sorry for off-topic and spam. I promise I won't do it again.
P.S. I'm not just necrobumping, I am looking
Here's an unknown texture sample I need help with:


 3rdunknowntosformat.zip
(12.33 KiB) Downloaded 19 times


I am unable to get that .HO file cracked, so I hope it gets cracked someday too.
