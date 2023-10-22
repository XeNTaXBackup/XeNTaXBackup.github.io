## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-02T22:52:17+00:00
- Post Title: C++ compiler

Looking for a C++ compiler that I can carry around with me on a thumb-drive so I can code anywhere. Should be able to use on windows without having to install extra things.

Recommendations?
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-09-03T01:26:47+00:00
- Post Title: C++ compiler

[Tiny C Compiler](http://bellard.org/tcc/)? =D
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-03T02:29:13+00:00
- Post Title: C++ compiler

I saw that one, but does it compile C++? It looks like it only does C.
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-09-03T03:27:01+00:00
- Post Title: C++ compiler

Aah, I somehow missed the "++". I don't know if it does handle C++, but it would surprise me if it did...
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-09-03T04:30:08+00:00
- Post Title: C++ compiler

A search for portable C++ compilers keeps leading me to Orwell DEV C++ Portable, have you tried this one yet? 

[http://sourceforge.net/projects/orwelld ... 0Releases/](http://sourceforge.net/projects/orwelldevcpp/files/Portable%20Releases/)
[http://orwelldevcpp.blogspot.com/](http://orwelldevcpp.blogspot.com/)
[http://portableapps.com/node/32477](http://portableapps.com/node/32477)


[pocketcpp](http://code.google.com/p/pocketcpp/) seems to be another viable option.
## Post #6
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2012-09-03T21:06:05+00:00
- Post Title: C++ compiler

sounds like a job for Eclipse and Mingw?  

or maybe DevCpp
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-09-04T01:54:23+00:00
- Post Title: C++ compiler

Mingw and eclipse are awesome if you don't mind not having the latest gcc. They are always more than a few versions behind. Also comes with Fortran and Ada if you want that aerospace job lol.
## Post #8
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-09-04T02:06:07+00:00
- Post Title: C++ compiler

You could also install Linux on your flash drive and install a more recent gcc depending on the distro. I used to do this until fedora started using gnome 3. What the fuck were they thinking? That PC's should use tablet operating systems lol?
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-04T02:13:39+00:00
- Post Title: C++ compiler

What's the difference between different versions of the compiler?
Is it something that someone that has barely ever touched C++ should be concerned with? lol
## Post #10
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-09-04T02:32:08+00:00
- Post Title: C++ compiler

Features from the upcoming c++ draft standard are slowly being implemented by vendors. To get these features you must use latest version of any c++ compiler. Last I used mingw g++ I still had to write shared_array<object<int>   > instead of shared_array<object<int>>. If you are fussy about latest features I wouldn't use mingw.
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-04T02:57:34+00:00
- Post Title: C++ compiler

...spacing matters in certain place?
lol I thought it was just python that was crazy about white-space.
## Post #12
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-09-04T03:29:34+00:00
- Post Title: C++ compiler

Yeah, ambiguity between bitwise right shift operator >> and nested template argument template<int x = 5 >> 2>. Standard has now said for years the extra space is not required but only latest gcc has this. But other than the lack of latest features mingw is awesome.
## Post #13
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2012-09-04T21:11:29+00:00
- Post Title: C++ compiler

You could switch to COBOL, everyone loves COBOL
