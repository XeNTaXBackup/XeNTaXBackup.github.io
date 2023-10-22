## Post #1
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-02-06T09:56:10+00:00
- Post Title: Xbox 360 XD3 ISO format

HI all,

I was wonder if anyone can write quickbms script or any cmd tool to extract and replace files/file from Xbox 360 ISO format. I know there is a tool allready but i need command line tool capable to do it. Please anyone who can help it would be lovely. If anyone is interest i can also provide a complete iso but only if someone really want to try. Otherwise i can provide only a cut of it as it is 7GB size.

Thx in advance.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-06T11:42:14+00:00
- Post Title: Xbox 360 XD3 ISO format

what is the point in replacing a file in an iso?
if you modify the disc it will be flagged as corrupt and wont boot.
## Post #3
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-02-06T11:49:26+00:00
- Post Title: Xbox 360 XD3 ISO format

> Reply from michalss
>
> HI all,

I was wonder if anyone can write quickbms script or any cmd tool to extract and replace files/file from Xbox 360 ISO format. I know there is a tool allready but i need command line tool capable to do it. Please anyone who can help it would be lovely. If anyone is interest i can also provide a complete iso but only if someone really want to try. Otherwise i can provide only a cut of it as it is 7GB size.

Thx in advance.

And if you generate by yourself an updated iso, and make a patch? The size of the patch will be as big as the changed data, and you can use patch tool from CMD. (for example: xdelta3)
## Post #4
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-02-06T11:56:51+00:00
- Post Title: Xbox 360 XD3 ISO format

> Reply from chrrox
>
> what is the point in replacing a file in an iso?
if you modify the disc it will be flagged as corrupt and wont boot.

Point is to replace Localization files from ISO. Dont care about flagget or w/e. I'm doing it for years and it works but PPL are noobs and dont know how exactly to use XboxBrowser apps. Thats why i want to write interface GUI to do it, but problem is that any cmd tool does not exist yet. You can also image it as custom installer language files into ISO.
## Post #5
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-02-06T11:57:35+00:00
- Post Title: Xbox 360 XD3 ISO format

> Reply from evin
>
> michalss wrote:HI all,

I was wonder if anyone can write quickbms script or any cmd tool to extract and replace files/file from Xbox 360 ISO format. I know there is a tool allready but i need command line tool capable to do it. Please anyone who can help it would be lovely. If anyone is interest i can also provide a complete iso but only if someone really want to try. Otherwise i can provide only a cut of it as it is 7GB size.

Thx in advance.

And if you generate by yourself an updated iso, and make a patch? The size of the patch will be as big as the changed data, and you can use patch tool from CMD. (for example: xdelta3)

Also dont need mod any update files. All i need it something what would be able to replace file from ISO with exact the same size as original ofcourse.
## Post #6
- Username: maurocio
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jan 27, 2010 3:45 am
- Post datetime: 2012-02-07T07:22:03+00:00
- Post Title: Xbox 360 XD3 ISO format

If you need reemplace files for same size or minor, you can use xbox backup creator that have a reemplace option.
## Post #7
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-02-07T07:44:13+00:00
- Post Title: Xbox 360 XD3 ISO format

> Reply from maurocio
>
> If you need reemplace files for same size or minor, you can use xbox backup creator that have a reemplace option.

Did u even read my post ?
## Post #8
- Username: maurocio
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jan 27, 2010 3:45 am
- Post datetime: 2012-02-07T09:49:11+00:00
- Post Title: Xbox 360 XD3 ISO format

> Reply from michalss
>
> Did u even read my post ?

Yes, men!!!

If you prefer create a program for reimport take a look source code from extract-xiso v2.7.0, maybe would be easy to implement on this a import option on this program.
[extract-xiso.rar](https://xentaxbackup.github.io/file/5042_extract-xiso.rar)
## Post #9
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-02-07T10:18:04+00:00
- Post Title: Xbox 360 XD3 ISO format

Well i know allready this but problem is that language  I can't write in C++.... 

I even know the original dev for this but he told me this:

"
	It's not easily done.  The xISO format is designed for writing onto a DVD so there aren't any available sectors like you'd find on a hard drive.  Everything in the original ISO is tightly packed.  The proper way to do this is to unpack the ISO completely to your hard drive, replace the file, then repack the ISO.  This ensures the resultant file is again tightly packed for writing to DVD.

	If you're just changing a few bytes in a particular file but not modifying its size, the extract xiso source has some debug code for printing out sector offsets of various files.  In that case you'd just find where in the ISO your file lives and patch the file using a hex editor.  You can't change the size doing it this way though.

	I'd recommend writing a shell script or similar to take the first approach though if you want to automate the file replacement process.

"

Anyone could help me out please ? I just need to do replace same size, same filename, just different contents!
## Post #10
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-07T10:59:11+00:00
- Post Title: Xbox 360 XD3 ISO format

Translate c+ + to another language you know like python. Same thing. All programming languages are limited by what we can do with slr and lalr grammars. Same shit just different syntax. Don't let it stop you just because it is written in another language!
## Post #11
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-02-07T11:05:05+00:00
- Post Title: Xbox 360 XD3 ISO format

Well this is nonsence if you dont know what the code does how would u to put it into different language.
## Post #12
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-02-11T08:54:20+00:00
- Post Title: Xbox 360 XD3 ISO format

please anyone ?
## Post #13
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2012-02-12T17:59:52+00:00
- Post Title: Xbox 360 XD3 ISO format

Why don't you create a new console app in Visual Studio, and then make a reference to the C++ code?  Then you can call things in the C++ project in your own app.  It's very easy to do, a quick Google search will give you tons of tutorials on doing that.  It's easier to do this when using C# code in VB code, or vice versa, but it is possible to use C++ in those other languages as well with the correct calls, but I'm assuming you probably only know VB.

This is how I make a lot of my programs.  I have a lot of code in C++, but the main program GUI is done in C#, for its simplicity, but the actual code to do things is all in C++.
## Post #14
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T18:28:56+00:00
- Post Title: Xbox 360 XD3 ISO format

> Reply from michalss
>
> Well this is nonsence if you dont know what the code does how would u to put it into different language.

I guess it's time to learn a new language.....
## Post #15
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-12T18:48:51+00:00
- Post Title: Xbox 360 XD3 ISO format

I don't even think that code applies, it was written for like the original xbox. And it does look hard; I wouldn't want to touch that code even though I know C++. There's a lot of file systems crap in there, stuff like AVL tree code. Best thing to do would probably ask the guys at xbox-scene.
## Post #16
- Username: xman2000
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-02-12T19:05:08+00:00
- Post Title: Re: Xbox 360 XD3 ISO format

It is for X360 iso format, but it will only extract the files. However in the debug mode there is something what could identify the file on the base of offset in binary. But still C++ is a barrier for me . I ofcourse know also C# and VB.Net. I could use it as DLL and load it to assembly but still it is missing the important functionality what i ever wanted, replace file!
