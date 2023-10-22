## Post #1
- Username: daukun
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 02, 2010 3:08 am
- Post datetime: 2014-12-26T06:37:54+00:00
- Post Title: Resources to get started?

Hello there!

I recently taught myself basic coding (started with classic C and then iterated to some object oriented languages like Objective-C and PHP) and now that I understand some of the basics I would like to get in depth with a language more related to games like C# or C++ but I'm kind lost on where to start. Are there any design patterns, beginner terminology, I should look up first? 

Most of the work I've done has been related to the MvC design pattern (for websites and apps) and I have also worked with some frameworks. Learning the syntax of C and read code was relatively easy but understanding the logic behind of why the code is written in a certain way is what broke my head most of the time. I don't want to carry that over to this stage of my learning process. 

Any tips, direction?
Thanks!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-26T15:00:49+00:00
- Post Title: Resources to get started?

> Reply from daukun
>
> Hello there!

I recently taught myself basic codingHi,
that's what I did ages ago and it's the worst thing you can ever do, imho.  
(But I guess you used a Programmer's Guide to C or whatever?)

If not then buy a good book or - if you've access to a university library, search there.
(I nether used one - but there might be good inet tutorials, too.) 

> Any tips, direction?
>
> Thanks!
If you're using Visual Studio (express is free) I would suggest to investigate here:
[http://www.codeguru.com/](http://www.codeguru.com/)
Chose any project of your interest, try to understand the code and maybe change/improve it.

You might start with a simple one like recursively scanning a drive directory for filenames.

cheers
## Post #3
- Username: daukun
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 02, 2010 3:08 am
- Post datetime: 2014-12-26T17:59:21+00:00
- Post Title: Resources to get started?

Thanks for your reply!

Haha yeah it was not an easy road to follow lol.

Hmm thanks for your suggestions, I don't know how I didn't came across with that site. I was actually going to read an old book of design patterns by the gang of four but going through the reviews I found out that it's way too outdated?  On a more related search I found this one "3D Graphics for Game Programming by 3D Graphics for Game Programming. Seems like a really good book.

Looking by how the scripts are written, most of the things I can identify are loops, iterations to get paths, filenames, etc. Besides that, most of them read like greek to me lol.

May I ask how you got started reverse engineering game file formats?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-26T18:40:26+00:00
- Post Title: Resources to get started?

> Reply from daukun
>
> I was actually going to read an old book of design patterns by the gang of four but going through the reviews I found out that it's way too outdated?Don't know it - but some basic principles never change. And sometimes old books shed a light on how we got to the place where 3D development is nowadays.

> May I ask how you got started reverse engineering game file formats?I'm pretty sure it was when stumbling over a wavefront obj file. I imported it into a 3D software (guess it was blender).

But I had to realize that games use binary files instead of obj.
Since I always hated "black boxes" I tried to transform these black boxed binaries into something understandable like obj.

And well, there was no book to read and I coded my own IEEE754 floating point conversion routine   
because I didn't know that you can do it in C as simple as this:

float *pFloat ;

pFloat = (float*) pFileBuffer ;
fprintf( stream, "%f ", *pFloat) ;
## Post #5
- Username: daukun
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun May 02, 2010 3:08 am
- Post datetime: 2014-12-28T18:56:41+00:00
- Post Title: Resources to get started?

Oh I see, well that pretty much what I was thinking on my head.  But before trying to understand how these blackboxes works, it would be advisable to understand how a simple obj works?
