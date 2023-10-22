## Post #1
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-10-19T07:56:42+00:00
- Post Title: I am Setsuna *.font_raw

Does anyone can make 010 template for raw files?
Samples. [https://www.sendspace.com/file/ayq6cl](https://www.sendspace.com/file/ayq6cl)

```
295B8 = 5AC + EE9(# of glyphs) * 2C  = 5AC + 2900C
```
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-10-19T22:00:00+00:00
- Post Title: I am Setsuna *.font_raw

I don't have a copy of the 010 Editor but I think this should work:

```
    struct HEADER {
        int     v0;
        float   v1;
        float   v2;
        int     v3;
        int     v4;
        int     v5;
        int     v6;
        int     v7;
        int     v8;
        int     numCharacters;
    } header;

    struct CHARACTER {
        int     id;
        float   x;
        float   y;
        float   width;
        float   height;
        float   xoffset;
        float   yoffset;
        float   v7;
        float   v8;
        float   xadvance;
        float   page;
    } character[ file.header.numCharacters ];

} file;
```
## Post #3
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-10-20T06:46:40+00:00
- Post Title: I am Setsuna *.font_raw

> Reply from herbert3000
>
> I don't have a copy of the 010 Editor but I think this should work:

Thank you. However, is it also including kernings?

```
kerning first=40  second=106 amount=3   
kerning first=8221 second=46  amount=-1  
kerning first=44  second=8217 amount=-3  
kerning first=44  second=8221 amount=-2  
kerning first=8221 second=44  amount=-1  
...etc
```
## Post #4
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-10-20T08:30:50+00:00
- Post Title: I am Setsuna *.font_raw

> Reply from adol365
>
> Thank you. However, is it also including kernings?
No, I don't think there's any kerning info in the raw file.
