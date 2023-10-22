## Post #1
- Username: PhillipGamer3264
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Aug 14, 2016 11:32 am
- Post datetime: 2017-06-20T20:33:37+00:00
- Post Title: Paper Mario: TTYD sprite help

This file is called ''a_mario'' and ''a_mario-''

[https://www.mediafire.com/?kx6783p44qvj3d6](https://www.mediafire.com/?kx6783p44qvj3d6)

can we extract this sprite plz?
## Post #2
- Username: Acewell
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2017-06-21T12:26:12+00:00
- Post Title: Paper Mario: TTYD sprite help

Here is partially guessed file format of a_mario:

```

//header
4 bytes - size of header
64 bytes - name + padding
64 bytes - name + padding
64 bytes - compilation date + padding

4 bytes - 1
4 bytes - 5
4 bytes - 5
224 bytes - ?


//animation entries (168 bytes)
64 bytes - animation name
104 bytes - ?

...

//table of filepaths (starting from 18764, 150 files)
number of files *
{
	64 bytes - filepath + padding
}

...

//group entries (starting from 38628, 59 entries)
64 bytes - name + padding
24 bytes - ?
number of entries *
{
	60 bytes - name + padding
	4 bytes - graphics offset
}


//graphics data (graphics data starts from offset 42492, right after header)
number of group entries *
{
	x bytes - file data
}




```


It's not any help with extraction, but it may help someone with writing tool for that files.
## Post #3
- Username: PhillipGamer3264
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Aug 14, 2016 11:32 am
- Post datetime: 2017-06-26T18:01:59+00:00
- Post Title: Paper Mario: TTYD sprite help

> Reply from ikskoks
>
> Here is partially guessed file format of a_mario:
Code: Select allbig endian

//header
4 bytes - size of header
64 bytes - name + padding
64 bytes - name + padding
64 bytes - compilation date + padding

4 bytes - 1
4 bytes - 5
4 bytes - 5
224 bytes - ?


//animation entries (168 bytes)
64 bytes - animation name
104 bytes - ?

...

//table of filepaths (starting from 18764, 150 files)
number of files *
{
	64 bytes - filepath + padding
}

...

//group entries (starting from 38628, 59 entries)
64 bytes - name + padding
24 bytes - ?
number of entries *
{
	60 bytes - name + padding
	4 bytes - graphics offset
}


//graphics data (graphics data starts from offset 42492, right after header)
number of group entries *
{
	x bytes - file data
}





It's not any help with extraction, but it may help someone with writing tool for that files.

i extract this file to rename this .tpl file to .tga file but, Open with Paint.NET to extract .PNG Files
