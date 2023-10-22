## Post #1
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-08-05T01:01:22+00:00
- Post Title: [Request] Kingdom Hearts 2 BMS

I have found a code online which, if implemented, can extract all of the 3D models from Kingdom Hearts 2, including the ones Yaz0r's tool can't extract. The problem is, it's in C# or something and I only know how to extract files from games with QuickBMS. So, can someone convert the following code to BMS script?

int calcHash(char *FileName)
{
	int x, FileHash = -1;
	for (unsigned int i = 0; i < strlen(FileName); i++ )
	{
		x = 7;
		FileHash ^= FileName << 24;
		do
		{
			if ( FileHash >= 0 )
			{
				FileHash *= 2;
			}
			else
			{
				FileHash *= 2;
				FileHash ^= 0x4C11DB7;
			}
			x--;
		}
		while ( x >= 0 );
	}
	return -1 - FileHash;
}
## Post #2
- Username: yaz0r
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Sep 23, 2010 4:32 pm
- Post datetime: 2010-09-23T08:36:05+00:00
- Post Title: [Request] Kingdom Hearts 2 BMS

That's just the code to compute the hash key (md5 in fact) for a given file name. That doesn't give you the actual filename itself.
