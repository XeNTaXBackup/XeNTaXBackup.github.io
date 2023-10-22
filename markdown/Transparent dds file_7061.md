## Post #1
- Username: meandme
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 24, 2011 10:24 am
- Post datetime: 2011-07-27T08:46:37+00:00
- Post Title: Transparent dds file

is there anyway to make a transparent dds file ( in ether Dxt or 32bit )?

I'm trying to make a glass walls in a model I'm doing but it ether comes out Black or White.
the programs I'm using are photoshop cs4 with 3ds max.
## Post #2
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-07-27T09:12:58+00:00
- Post Title: Transparent dds file

maybe,Is it so "Alpha Channel"?
I can not explain to you because i dont have Photoshop...
I atached two sample dds files.

(edit)
Excuse me,Would you use "NVIDIA Plug-ins"？
I found "NVIDIA Plug-ins for Adobe Photoshop" plugin has issue.
You will use "DirectX Texture Tool" in "DirectX SDK".
[http://msdn.microsoft.com/En-us/directx/aa937788.aspx](http://msdn.microsoft.com/En-us/directx/aa937788.aspx)

or try this.(but this is japanese plugin)
[http://www.apras.net/blog/?p=334](http://www.apras.net/blog/?p=334)
[sampledds.rar](https://xentaxbackup.github.io/file/4545_sampledds.rar)
## Post #3
- Username: meandme
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 24, 2011 10:24 am
- Post datetime: 2011-07-27T20:34:46+00:00
- Post Title: Transparent dds file

> Reply from porimac
>
> maybe,Is it so "Alpha Channel"?
I can not explain to you because i dont have Photoshop...
I atached two sample dds files.

(edit)
Excuse me,Would you use "NVIDIA Plug-ins"？
I found "NVIDIA Plug-ins for Adobe Photoshop" plugin has issue.
You will use "DirectX Texture Tool" in "DirectX SDK".
http://msdn.microsoft.com/En-us/directx/aa937788.aspx

or try this.(but this is japanese plugin)
http://www.apras.net/blog/?p=334

Thanks for the reply

About the sample files only one file opened with me witch was the one with the HI picture, the blank one was black and didn't work.

Yes about nevidia plug-ins i use it and I'm trying the directx texture that you suggested at the moment.
## Post #4
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-07-27T20:54:08+00:00
- Post Title: Transparent dds file

> About the sample files only one file opened with me witch was the one with the HI picture, the blank one was black and didn't work.
It is a meaning of a comparison each other. 
However, the explanation did not suffice, sorry. 

But I believed that ur problem is solved, If you use "DirectX Texture Tool".
Plz check it.
[http://msdn.microsoft.com/en-us/library ... 10%29.aspx](http://msdn.microsoft.com/en-us/library/bb197345%28v=xnagamestudio.10%29.aspx)
## Post #5
- Username: meandme
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 24, 2011 10:24 am
- Post datetime: 2011-08-04T04:52:23+00:00
- Post Title: Transparent dds file

> Reply from porimac
>
> About the sample files only one file opened with me witch was the one with the HI picture, the blank one was black and didn't work.
It is a meaning of a comparison each other. 
However, the explanation did not suffice, sorry. 

But I believed that ur problem is solved, If you use "DirectX Texture Tool".
Plz check it.
http://msdn.microsoft.com/en-us/library ... 10%29.aspx

Thanks for the reply and sorry for not responding sooner
Anyway I don't quite understand how to do it with Directx Texture Tool I've tried the PNG file way but it didn't work, the bmp file on the other hand I really don't understand how to do the white and black pixel thing.
## Post #6
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-08-04T09:31:15+00:00
- Post Title: Transparent dds file

> Reply from meandme
>
> but it didn't work
oh ah, error? stucked? or BSOD??

I hope this helps, explain in some images. 
My vocabulary is too primitive to explain for you. 

He want Transparent texture. :/ 


Launch "DirectX Texture Tool". And select "New Texture" from file menu.


Make new blank texture as you want.


Select "Open Onto This Surface"


Apply image as you like.


Next, select "Open Onto Alpha Channel Of This Texture".


Open as grayscale image.


When they unite, it becomes like this. 


Save it as DDS extension.


TA-DA! His hope was realized!


or read once more that..
[http://msdn.microsoft.com/en-us/library ... 10%29.aspx](http://msdn.microsoft.com/en-us/library/bb197345%28v=xnagamestudio.10%29.aspx)
## Post #7
- Username: meandme
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 24, 2011 10:24 am
- Post datetime: 2011-08-06T00:26:02+00:00
- Post Title: Transparent dds file

Thank you very much for the reply.

Ya that what I was stuck on thank you for the tutorial really appreciate it.
