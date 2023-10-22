## Post #1
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2014-07-10T13:27:16+00:00
- Post Title: Starship Troopers .SBM Filetype

Hoping someone will know how to extract/convert the sbm to another usable filetype. I've tried what I know with no luck. Here's one of the files.
[https://www.sendspace.com/file/7gjyt5](https://www.sendspace.com/file/7gjyt5)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-07-10T19:31:25+00:00
- Post Title: Starship Troopers .SBM Filetype

using hex2obj (view link in my sig):



AIModel_grunt.JPG (217.39 KiB) Viewed 129 times



address of DWORD vertex count: 8 bytes before vertices start address (1st submesh: 0x26D). DWORD face indices count: 8 bytes before startaddress of faceindices (1st SM: 0x1F5F1)
## Post #3
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2014-07-10T20:50:06+00:00
- Post Title: Starship Troopers .SBM Filetype

Not sure I understand that do I need to change the values in the Hex2OBJ program or does it do that automatically?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-07-10T21:54:50+00:00
- Post Title: Starship Troopers .SBM Filetype

> Reply from Nintendude
>
> do I need to change the values in the Hex2OBJ program or does it do that automatically?I dream that dream every night...    

nope, it doesn't. you'll have to enter the values manually and they vary for every submesh.
Guess you made a typo: vertices start address is 26D, not 260

btw, the model I sent you contains the first submesh (SM) only. You'll have to get the other SMs for yourself.
VBsize and UVpos not to be changed, but addresses and count for go1 and go3 button.
## Post #5
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2014-07-11T06:52:49+00:00
- Post Title: Starship Troopers .SBM Filetype

> Reply from Nintendude
>
> Not sure I understand that do I need to change the values in the Hex2OBJ program or does it do that automatically?

Just use the 3D Object Converter that supports this format 3 years ago:
[http://3doc.i3dconverter.com/](http://3doc.i3dconverter.com/)
## Post #6
- Username: SoldierTODD
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Oct 25, 2014 5:15 am
- Post datetime: 2014-10-25T08:20:57+00:00
- Post Title: Starship Troopers .SBM Filetype

I beg your pardon. 
I need to import the model beetles (arachnid), along with the animation, how to do?

P.S. Sorry for my English. I use a translator.
## Post #7
- Username: SoldierTODD
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Oct 25, 2014 5:15 am
- Post datetime: 2014-10-27T13:13:45+00:00
- Post Title: Starship Troopers .SBM Filetype

I need animation. 
Someone could write a script to import models to the skeleton and animation? 
Script to import from the shooter Starship Troopers or strategy Starship Troopers: Terran Ascendancy.
