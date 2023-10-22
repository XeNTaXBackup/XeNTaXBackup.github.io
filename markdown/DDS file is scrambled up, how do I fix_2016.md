## Post #1
- Username: daddio
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 01, 2006 1:59 pm
- Post datetime: 2006-08-01T06:06:43+00:00
- Post Title: DDS file is scrambled up, how do I fix?

I have a DDS image that is scrambled somehow. It was unpacked from a XPR file. Any clue how to unscramble the image? I can't load the DDS file as attachment here for you to work with but will attach as a JPG if that would help.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-08-01T07:28:02+00:00
- Post Title: DDS file is scrambled up, how do I fix?

> Reply from daddio
>
> I have a DDS image that is scrambled somehow. It was unpacked from a XPR file. Any clue how to unscramble the image? I can't load the DDS file as attachment here for you to work with but will attach as a JPG if that would help.

Why not zip it first and then attach it?

Also, you may want to read this: [viewtopic.php?t=1048&highlight=xpr](http://forum.xentax.com/viewtopic.php?t=1048&highlight=xpr)

The DDS files have missing headers, if I'm not mistaken. You can replace / add them yourself.
## Post #3
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2006-08-01T15:05:10+00:00
- Post Title: DDS file is scrambled up, how do I fix?

> Reply from daddio
>
> I have a DDS image that is scrambled somehow. It was unpacked from a XPR file. Any clue how to unscramble the image? I can't load the DDS file as attachment here for you to work with but will attach as a JPG if that would help.
This sounds like an image for an Xbox game, since it is the most common platform to do it to DDS files, but I would bet that the DDS file is swizzled.  There are a few threads at Xbox Scene that explain swizzled DDS images.  There are no programs made, just to unswizzle/reswizzle DDS files, they are usually part of other programs that also extract the DDS files.  It's mainly trial and error on finding the correct swizzle algorithm that is being used on the DDS file, but they all follow a similar pattern.  Hope this has helped you some.
## Post #4
- Username: daddio
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 01, 2006 1:59 pm
- Post datetime: 2006-08-01T19:39:42+00:00
- Post Title: DDS file is scrambled up, how do I fix?

I'm sure your correct. its a Forza image file. The rar is too large to attach from here. I will try to find a site to upload it to and post a link to the orignal file.
## Post #5
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2006-08-09T06:55:53+00:00
- Post Title: DDS file is scrambled up, how do I fix?

Here's a code algorithm for xbox swizzle and unswizzle


```
{
	if(SegWidth == 2 && SegHeight == 2)
	{
       ((byte *)WriteArray)[WriteOffset                ] = ((byte *)ReadArray)[ReadOffset + 0];
       ((byte *)WriteArray)[WriteOffset + 1            ] = ((byte *)ReadArray)[ReadOffset + 1];
       ((byte *)WriteArray)[WriteOffset + DataWidth    ] = ((byte *)ReadArray)[ReadOffset + 2];
       ((byte *)WriteArray)[WriteOffset + DataWidth + 1] = ((byte *)ReadArray)[ReadOffset + 3];
	   ReadOffset += 4;
	}
	else
	{
		UnSwizzle(ReadArray, WriteArray, ReadOffset, WriteOffset, SegWidth/2, SegHeight/2, DataWidth);
		UnSwizzle(ReadArray, WriteArray, ReadOffset, WriteOffset + SegWidth/2, SegWidth/2, SegHeight/2, DataWidth);
		UnSwizzle(ReadArray, WriteArray, ReadOffset, WriteOffset + DataWidth*(SegHeight/2), SegWidth/2, SegHeight/2, DataWidth);
		UnSwizzle(ReadArray, WriteArray, ReadOffset, WriteOffset + DataWidth*(SegHeight/2) + SegWidth/2, SegWidth/2, SegHeight/2, DataWidth);
	}
}

void Swizzle(void *WriteArray, void *ReadArray, unsigned long int &WriteOffset, unsigned long int ReadOffset, unsigned long int SegWidth, unsigned long int SegHeight, unsigned long int DataWidth)
{
	if(SegWidth == 2 && SegHeight == 2)
	{
       ((byte *)WriteArray)[WriteOffset                ] = ((byte *)ReadArray)[ReadOffset + 0];
       ((byte *)WriteArray)[WriteOffset + 1            ] = ((byte *)ReadArray)[ReadOffset + 1];
       ((byte *)WriteArray)[WriteOffset + 2            ] = ((byte *)ReadArray)[ReadOffset + DataWidth];
       ((byte *)WriteArray)[WriteOffset + 3            ] = ((byte *)ReadArray)[ReadOffset + DataWidth + 1];
	   WriteOffset += 4;
	}
	else
	{
		Swizzle(WriteArray, ReadArray, WriteOffset, ReadOffset, SegWidth/2, SegHeight/2, DataWidth);
		Swizzle(WriteArray, ReadArray, WriteOffset, ReadOffset + SegWidth/2, SegWidth/2, SegHeight/2, DataWidth);
		Swizzle(WriteArray, ReadArray, WriteOffset, ReadOffset + DataWidth*(SegHeight/2), SegWidth/2, SegHeight/2, DataWidth);
		Swizzle(WriteArray, ReadArray, WriteOffset, ReadOffset + DataWidth*(SegHeight/2) + SegWidth/2, SegWidth/2, SegHeight/2, DataWidth);
	}
}

```
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-08-09T07:54:34+00:00
- Post Title: DDS file is scrambled up, how do I fix?

Nice one !
