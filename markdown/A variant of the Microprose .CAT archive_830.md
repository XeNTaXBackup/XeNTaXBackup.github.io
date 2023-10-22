## Post #1
- Username: NosyBody
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-01T02:24:17+00:00
- Post Title: A variant of the Microprose .CAT archive

Hello Mr. Mouse..
Cool place you have here. I've only just heard of your utilities, and I am mighty impressed.

Here's one for you: Microprose used a CAT file archive for Transport Tycoon, (which I see you support). However they also used a different format archive with the CAT extension for their M1 Tank Platoon 2 and Gunship! simulation titles.

As far as I can tell, it does not use a file list, but rather the path/name of the resource within the CAT is hashed, and the hash value is used to lookup the resource. The sneaky bit is, we need the plain text string for the path/name, and while I have access to known contents, I can't access unknowns. Which is a whole heckuva lot, in round numbers.

I have some documentation on the hash algorithm. Any interest in helping us reach the Unknown Lands? 

cheers
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-02T11:52:37+00:00
- Post Title: A variant of the Microprose .CAT archive

Hi! 

Thanks for the kind words. I will need to get a hold of these CAT files first, before I can say anything about it's format. I'll download a demo of these games, if I can find them.
## Post #3
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-02T13:07:17+00:00
- Post Title: A variant of the Microprose .CAT archive

Hi back!

If you had time to take a look at them, that would be fantastic! 

Yopu can get the Gunship! demo here (18MB):

[http://www.atari.com/us/demos/](http://www.atari.com/us/demos/) 

The exisiting CAT extraftor can be found ehre, under "File Stuff"
[http://www.simwarrior.com/gunship/gsdev.html](http://www.simwarrior.com/gunship/gsdev.html)

It works fine, but is limited to known path/filename strings. I can provide mroe details about the algorithm if you are interested.

Thanks again!

cheer
NB
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-02T13:08:39+00:00
- Post Title: A variant of the Microprose .CAT archive

Sure, I'm interested.
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-03T14:25:17+00:00
- Post Title: A variant of the Microprose .CAT archive

Well, after looking through some c-code I have found enough. I can encode the string names. There's a catch though as the original encoding does not ensure unique codes and fixes itself by asserting after convulsion. 

I will see what I can find.
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-04T09:08:00+00:00
- Post Title: A variant of the Microprose .CAT archive

Okay, so the files in my demo version are all 

"images\somename.someextension" in images1.cat

"textures\somename.someextension" in images.cat

I can tell, because the encryption code is xx xx xx 04 (which would be the case if you would Xor the character 'i' with 'm' and then shift the 4-byte value left 24 times, as is done in the encoding. 

If you would do this with 't' and 'e' you would get xx xx xx 11. This I can find in images.cat only. 11 is a hexadecimal value, by the way. 

In the exe file of the demo there are only few string entries that go "textures\blahblah" and a little more that go "images\blahblah". 

I can track these down in the cat archives, using the INTEGER (2-byte) part of the 4-byte value you get after encoding of a string to a 4-byte value. The source I saw did check whether codes would be identical for different strings, and ask the catmaker to change one of the filenames, so I reckon you can trace all files down, using the integer part. There's a catch i don't quite understand yet, the 3rd byte of the 4-byte value is incrementing in the archive. As if there's a counter running in the encoding while saving in the archive , but I don't see this in the source code. Oh well, perhaps we only need the integer part anyway. 

So, you should find all string entries that go "images\blah" or "textures\blah" in the executable (use WinDASM to show you al lstring entries in an executable). Then I could write a program that will point out to you where to find them in the cat.
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-07T23:51:33+00:00
- Post Title: A variant of the Microprose .CAT archive

Well, I'm still not sure about this format, I can't find all the filenames (I have less known filenames that I can encode, then there are codes in the archives), but at least you will be able to extract any and all files in these archives, nameless. Just run MultiEx Commander, and start the webupdate of it. You can now open Gunship! .cat files. 

NOTE: Switch OFF the check "File Info Ascending" option in Options. 
Or else you will get the "Corrupted file info" message!
## Post #8
- Username: NosyBody
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-15T13:47:33+00:00
- Post Title: A variant of the Microprose .CAT archive

WOW! More brilliant work! Thank you!   

I've been away most of the week, and have only had a few minutes to play with this. It looks very cool so far.

It doesn't seem to be exposing any of the non-graphic files in the CAT, though. (BTW, MPS used mainly PCX files, but also used extensions like PCA, and PCB for transparancy and/or Alpha layer files. But they are all PCX format.) 

But I think I'm beginning to understand why the code bits aren't extracting as whole files: Could it be possible that all the tantalizing bits of code in the CAT files are just fragments which were later overwritten by the graphics files added to the CAT later?

This would be unfortunate news,  but any information is worth having, even if it isn't what was hoped for.  

I'm going to explore this mroe. But thank for your effort on this Mr. Mouse. Your generous help clearly has benefitted many peopel.

cheers
NB
