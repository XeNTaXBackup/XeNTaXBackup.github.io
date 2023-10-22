## Post #1
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-11-08T15:22:52+00:00
- Post Title: Excel in Hex hunt.

Excel can be a pretty nifty tool to convert Xex to Dec with the macro function  like =HEX2DEC. This one, as the name indicates,  will convert hex to decimal in Little Endian byte order.  I was wondering though if there was some other spreadsheet function for floats ?
## Post #2
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2007-01-07T00:27:12+00:00
- Post Title: Excel in Hex hunt.

Going through my old posts and try update what I have learned since I posted the question. About that Excel thing  maybe someone may find this helpful: 
[http://digilander.libero.it/foxes/xnumber_review_20.htm](http://digilander.libero.it/foxes/xnumber_review_20.htm)
I thought I 'd share.
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-01-13T21:12:01+00:00
- Post Title: Excel in Hex hunt.

Why don't you simply use a hex editor?
## Post #4
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2007-01-18T12:10:04+00:00
- Post Title: Excel in Hex hunt.

> Why don't you simply use a hex editor?
I was looking for spredsheet type conversion floats in one column and DEC values in another. Translating many floating point  coordinates of vertices.
but ....
For now I DO, as  no other option really found.  List of them for some of the models gets to be pretty loooong.
## Post #5
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2007-01-20T00:18:36+00:00
- Post Title: Excel in Hex hunt.

Depends on the format of the floating point.  You do know, that unlike, integers, there are many different floating point formats.  Perhaps you mean a specific IEEE format?
## Post #6
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2007-01-26T20:01:21+00:00
- Post Title: Excel in Hex hunt.

Sorry did not notice this earlier...
I know that there are different floating point formats , but since I am self learner not much beyond that:

3d 25 a7 40 = 5.22329569 e+000

What format would that be?
## Post #7
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2007-01-27T18:19:51+00:00
- Post Title: Excel in Hex hunt.

Single Precision 32-Bit IEEE 754 Format

[http://en.wikipedia.org/wiki/IEEE_754](http://en.wikipedia.org/wiki/IEEE_754)
## Post #8
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2007-03-15T02:19:11+00:00
- Post Title: Excel in Hex hunt.

I know its no Excel support forum, but maybe by chance someone from this community wuld be willing and able to help me sort out this perhaps pretty basic Excel task. 

I have bunch of of numbers formated with 6 decimal places. I need to round each of them (up or down) to closest 1/8th (0.125)  increment:
16.277790 = 16. 250000
18.745009= 18.750000

Call me thick, but I cannot figure how to do it   .
## Post #9
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-03-15T02:43:37+00:00
- Post Title: Excel in Hex hunt.

That sounds like something you would use a macro for. Unfortunately, I have no idea how to make or use macros, but a quick Google search should turn up some tutorials...
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-03-15T07:50:08+00:00
- Post Title: Excel in Hex hunt.

Nah, it's in Excel:

You can do this :

[http://j-walk.com/ss/excel/usertips/tip011.htm](http://j-walk.com/ss/excel/usertips/tip011.htm)

Or you can do this:

> Round to a Chosen Multiple
>
> 
>
> There is another round function in Excel that will round a number to the multiple we specify. This function is called MROUND. It is not available by default, so you need to go to Tools>Add-ins and check Analysis Toolpak.
>
> 
>
> =MROUND(22.5,10) will result in a value of 20
>
> 
>
> =MROUND(22.5,5) will result in a value of 25

In your case, you'd write MROUND(16.277790;0.125)

If you have Excel 2007 this function is in by deafult I believe. 

I have attached a test sheet that does this. Check it.
[test.xls](https://xentaxbackup.github.io/file/1091_test.xls)
## Post #11
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2007-03-15T11:50:12+00:00
- Post Title: Excel in Hex hunt.

Thanks Mr. Mouse and DinoGuy1K, 
=MROUND function would do nicely. Very nicely.
