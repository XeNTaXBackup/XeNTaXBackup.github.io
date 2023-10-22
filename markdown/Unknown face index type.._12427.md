## Post #1
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-12-26T02:47:00+00:00
- Post Title: Unknown face index type..

I'm writing a MaxScript for a relatively simple format, but I can't figure out how to get the faces.
[http://pastebin.com/1KjEw8TV](http://pastebin.com/1KjEw8TV)
That's what they look like when I log them.
I attached the script and some samples.


 MH_SKN.7z
(210.8 KiB) Downloaded 29 times



I must add that they match with the vertex IDs in the weights section.
## Post #2
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-12-26T07:00:17+00:00
- Post Title: Unknown face index type..

Add one to the faces when you are reading them.

```
	f1 = (readlong f)+1
	tu = readfloat f
	tv = (readfloat f)*-1
	f2 = (readlong f)+1
	tu = readfloat f
	tv = (readfloat f)*-1
	f3 = (readlong f)+1
	tu = readfloat f
	tv = (readfloat f)*-1
	print (((("f ")+f1 as string)+(" ")+f2 as string)+(" ")+f3 as string)
	append UV_Array [tu,tv,0]
 	append Face_Array [f1,f2,f3]
)
```


MaxScript array indexes are one-based not zero-based.

--MDA
## Post #3
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-12-26T13:02:28+00:00
- Post Title: Unknown face index type..

> Reply from MichaelDarkAngel
>
> Add one to the faces when you are reading them.
Code: Select allfor x = 1 to DataCount do (
	f1 = (readlong f)+1
	tu = readfloat f
	tv = (readfloat f)*-1
	f2 = (readlong f)+1
	tu = readfloat f
	tv = (readfloat f)*-1
	f3 = (readlong f)+1
	tu = readfloat f
	tv = (readfloat f)*-1
	print (((("f ")+f1 as string)+(" ")+f2 as string)+(" ")+f3 as string)
	append UV_Array [tu,tv,0]
 	append Face_Array [f1,f2,f3]
)

MaxScript array indexes are one-based not zero-based.

--MDA
Ah silly me, it was late and for some reason I keep forgetting the simplest of things!
Thank you.
