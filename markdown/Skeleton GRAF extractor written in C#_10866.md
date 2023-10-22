## Post #1
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-10-13T02:24:22+00:00
- Post Title: Skeleton GRAF extractor written in C#

This is the extractor template I commonly use for many of my extractors. I'm much of a noob when it comes to BMS scripts, and for myself it's easier editing a couple lines of C# code than to write a BMS script. Also, for complicated formats, such as ones with complex directory trees and custom compression routines, I need a bit more power than what QuickBMS provides. So here is a source code project for a command line GRAF extractor (much like the ones I released) that can accommodate the "directory" type archive pattern with a few lines added, and can be easily expanded for other types of GRAF and for custom encryption and compression routines.
[GrafExtractorSkeleton.zip](https://xentaxbackup.github.io/file/6826_GrafExtractorSkeleton.zip)
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-10-13T08:44:26+00:00
- Post Title: Skeleton GRAF extractor written in C#

Nice work man

Let me post something useful I use most of the time in my programs


Basically you pass it a stream a signature (byte array) a mask string and it will return the position in the stream if locates the pattern. Very useful

Example

\x56\x8B\xF1\x8B\x86\xBC\x00\x00\x00\xC1\xE8\x1B\xA8\x01\x0F\x85\x9A\x00\x00\x00
xxx?????????????????

Credits to the master131 for the masking method 

```
	/// 2nd method to sigscan
	/// </summary>
	/// <param name="stream"></param>
	/// <param name="pattern"></param>
	/// <returns></returns>
	/// <remarks></remarks>
	public long FindPattern(Stream stream, byte[] pattern, string mask)
	{
		if (stream == null || pattern == null)
		{
			return -1;
		}
		if (mask.Length != pattern.Length)
		{
			return -1;
		}
		if (!stream.CanSeek || pattern.Length > stream.Length)
		{
			return -1;
		}

		BinaryReader br = new BinaryReader(stream);
		byte[] buffer = br.ReadBytes(Convert.ToInt32(stream.Length));
		int index = 0;
		for (int i = 0; i < buffer.Length; i++)
		{
			if (buffer[i] == pattern[index] || mask[index] == '?')
			{
				index += 1;
				if (index == pattern.Length)
				{
					return i - (pattern.Length - 1);
				}
			}
			else
			{
				index = 0;
			}
		}
		return -1;
	}


```
## Post #3
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-12-06T16:40:39+00:00
- Post Title: Skeleton GRAF extractor written in C#

I fixed an error with the zero-terminated string reading function. New version is in the first post.
