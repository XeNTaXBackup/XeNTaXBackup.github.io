## Post #1
- Username: inspiredgurl
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 01, 2011 5:07 am
- Post datetime: 2012-03-14T17:52:28+00:00
- Post Title: DW7 textures error

I'm trying to view textures and get offzip to extract the files but I keep getting this error

[](http://imageshack.us/photo/my-images/560/errorjq.png/)

Uploaded with [ImageShack.us](http://imageshack.us)

am i doing something wrong?
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-03-14T18:01:18+00:00
- Post Title: DW7 textures error

You have a c:/c:/. I would just put offzip in the usrdir and cd into that dir so you can use relative paths instead.
## Post #3
- Username: inspiredgurl
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 01, 2011 5:07 am
- Post datetime: 2012-03-15T00:35:08+00:00
- Post Title: DW7 textures error

Thanks but now how to make my textures show in 3ds max? I read about a dds plugin but i'm no expert at 3ds max. 
Any help is appreciated. 

[](http://imageshack.us/photo/my-images/339/textureerror.png/)

Uploaded with [ImageShack.us](http://imageshack.us)
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-03-15T08:12:24+00:00
- Post Title: DW7 textures error

DW7 requires manual texturing. 3DS Max requires no DDS plugin. Basically you do something like this:

Select model.
Press 'M' to bring up material editor.
Select Maps section.
Click on None button next to Diffuse Color.
Select Bitmap.
Select OK.
Find the texture.
Select Open.
Back at Material Editor window click Assign Material to Selection button (third button from left).
## Post #5
- Username: inspiredgurl
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 01, 2011 5:07 am
- Post datetime: 2012-03-15T21:17:12+00:00
- Post Title: DW7 textures error

> Reply from howfie
>
> DW7 requires manual texturing. 3DS Max requires no DDS plugin. Basically you do something like this:

Select model.
Press 'M' to bring up material editor.
Select Maps section.
Click on None button next to Diffuse Color.
Select Bitmap.
Select OK.
Find the texture.
Select Open.
Back at Material Editor window click Assign Material to Selection button (third button from left).

Thanks for the tip. I tried your method and this is what I got:

[](http://imageshack.us/photo/my-images/861/textureerrors.png/)

Uploaded with [ImageShack.us](http://imageshack.us)
## Post #6
- Username: inspiredgurl
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 01, 2011 5:07 am
- Post datetime: 2012-03-16T17:18:17+00:00
- Post Title: DW7 textures error

i even activated the materials (standard realistic) in the view port. 
the result came out as the above picture.
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-03-16T18:48:17+00:00
- Post Title: DW7 textures error

Looks like wrong texture was applied. The model should have a uvw modifier. Check it out. Make sure the uvs jive with the image you want to apply. If I recall right dw7 just creates a list of textures and you must guess which textures go on which models. Model also uses multiple map channels. Your pic shows using map channel 1. Look at uvw modifier to see which channels are matched up with which images. Uv mapping is typically a full 40 pages in a book on 3ds max. You can see in your images the number of options is frightening lol. Don't be afraid to get a book on 3ds max and read the section on materials. The steps to do what you want to do are lengthy. Dw7 really is a pain in the ass game. As is all dw games.
