## Post #1
- Username: francoiscoiscois
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat May 06, 2006 8:02 pm
- Post datetime: 2006-05-06T12:20:40+00:00
- Post Title: convert 3D file format

Hallo everybody

problem 
After I have extracted the file from there archives "tomb raider " for example or "oblivion"...   with "Dragon UnPACKer" "game extractor" or other game unpacker
How can I convert the 3D file format and texture to be enable to work with in 3DSmax or other 3D package and make my modification.
There are great tools like Milkshape but many file format aren't intergrated  and cannot be convert.     
I also tried to import serious sam 2 file (.mdl) extracted from Dragon UnPACKer in Milkshake and have an error message.

Is there a wizzard tool to convert 3D and texture game format to common format like .obj .ASE   .....   
Or How do you do???
Please help me help me I'm diing   !!!AHHHHHHH!!!!
## Post #2
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2006-05-06T13:36:38+00:00
- Post Title: convert 3D file format

would be nice to convert all objects game to usable formats
## Post #3
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-05-07T12:55:13+00:00
- Post Title: convert 3D file format

Many converters available. So are the 3D formats  
[http://www.3dlinks.com/links.cfm?catego ... egoryid=11](http://www.3dlinks.com/links.cfm?categoryid=1&subcategoryid=11)
## Post #4
- Username: francoiscoiscois
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat May 06, 2006 8:02 pm
- Post datetime: 2006-05-12T18:16:41+00:00
- Post Title: convert 3D file format

Thank for your link Xela
There are alot of converter hier
## Post #5
- Username: OneOneSeven
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Jul 16, 2006 1:54 pm
- Post datetime: 2006-07-16T06:25:40+00:00
- Post Title: convert 3D file format

There are a couple of good general-purpose conversion tools out there, the best of which are probably Ultimate Unwrap3d and Milkshape3d. (unfortunately, I have neither -_-) For the most part, I'd recommend doing a Google search with the extension and the name of the game you got it from. More than occasionally, developers will re-use an extension or modify the general format slightly.
## Post #6
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-08-26T05:22:05+00:00
- Post Title: convert 3D file format

I decided to refresh this post with question as follows: which commonly used 3D format is in your opinion perhaps the simpliest and easiest to read and understand? 

By that I mean if one was to attempt to write a converter from the format currently under investigation, but if and when finally fully understood, to which popular format one should try to translate it?
## Post #7
- Username: mirex
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon May 15, 2006 6:16 pm
- Post datetime: 2006-08-28T11:44:36+00:00
- Post Title: convert 3D file format

Hi
from my experiences with file formats I know that none I have encountered so far was suitable for everything. If you don't want to loose some data you usually need to keep them in their original format 

Formats which I liked most are .ASE ( 3D Studio max ascii format ) and .LWO ( Lightwave object ), probably because they both support per-point-vertex colouring and texturing.

LWO format is binary and quite hard to understand, so I recommend .ASE because its in text format and is quite readable.
## Post #8
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-08-29T01:03:56+00:00
- Post Title: convert 3D file format

Glad that *.ASE wins your recommendation. It is definetely easy to read and besides resides in 3dSMax. Thanks.
## Post #9
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-08-29T01:07:27+00:00
- Post Title: convert 3D file format

And since you are good on formats.    
Any idea where I can find some informations how to convert binary *.x to text. 

[viewtopic.php?t=1788](http://forum.xentax.com/viewtopic.php?t=1788)

PS. In that thread linked above I searched GameDev article to find this:
"The .X File format can be either in plain text or in binary. This is given in the header of the file. We will look into the text format. The binary format will be addressed in the fifth chapter."
But no chapter #5 was found.
## Post #10
- Username: OneOneSeven
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Jul 16, 2006 1:54 pm
- Post datetime: 2006-08-29T19:49:46+00:00
- Post Title: convert 3D file format

While we're on that sort of thing, the 'easiest' format to understand would be the basic ASCII. Just a bunch of numbers (vertex coords )
## Post #11
- Username: mirex
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon May 15, 2006 6:16 pm
- Post datetime: 2006-09-05T07:43:45+00:00
- Post Title: convert 3D file format

I hope that software called "Deep exploration" can convert binary X into ascii as it can handle many file formats. If on the other hand you want to know how to do it in your program you need a file format description, which can be found in the DirectX sdk AFAIK ... it can be probably downloaded at [http://msdn.microsoft.com/directx/](http://msdn.microsoft.com/directx/)

I'll try to search my home computer, maybe I have some cut-off from the documentation there.
## Post #12
- Username: Skyline
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Jan 03, 2007 10:22 am
- Post datetime: 2007-01-03T02:26:19+00:00
- Post Title: convert 3D file format

It's been a while since this topic has been replied to, but i thought I'd add my 2 cents.
Deep Ex has a very large file conversion library, is easy to use and is amongst the most stable.
Those bonuses offset it's price, which I happily paid.
It's been able to convert binary to x very nicely.
On one occasion I can recal, it reversed the normals of all the polygons, but that was easily fixed.
