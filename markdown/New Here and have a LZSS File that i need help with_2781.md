## Post #1
- Username: griffinpower
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Sep 11, 2007 10:54 pm
- Post datetime: 2007-09-12T02:06:01+00:00
- Post Title: New Here and have a LZSS File that i need help with

Hi just wanted to take a moment to say hey first off... this is my first post here and although its not a game related file I am having trouble getting this file decompressed. 


I have been using a file called Decode.exe that was used previously to uncompress it (by someone else) but it is not working for me.  SO now I am resorting to trying to figure out the word lenght/offset etc.. of the LZSS compression in this file. 


Any help is grealty appreciated!!!!!  
[symblotables.zip](https://xentaxbackup.github.io/file/1335_symblotables.zip)
## Post #2
- Username: griffinpower
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Sep 11, 2007 10:54 pm
- Post datetime: 2007-09-14T14:13:59+00:00
- Post Title: New Here and have a LZSS File that i need help with

So I am working on a script to handle this and I am getting an error upon compile in VS2005 C++.. hoping someone can tell me what is wrong here.

Sucks being such a programming noob!  


The error is Error C3861: 'toupper':identifier not found


```
	FILE *infile,*outfile;
	unsigned long newsize=0;
	time_t time1,time2;
	fpos_t filesize=0;
	void *srcmem,*destmem;
	printf("\nSimple LZSS implementation v1.0, by Jeremy Collake");
	printf("\nWritten for demonstrative/learning purposes only.");
	printf("\nhttp://www.collakesoftware.com");
	printf("\n---------------------------------------------------");
	if(argc!=4) {
		printf("\nInvalid parameters.");
		printf("\nUsage: LZSS [c|d] inputfile outputfile\n");
		return 1;
	}	
	if (toupper(argv[1][0])=='C') {
		printf("\nCompression mode.\n");

		if((infile=fopen(argv[2],"rb"))==NULL) {
			printf("\nError opening %s for input!",argv[2]);
			return 2;
		}				
		if((outfile=fopen(argv[3],"wb"))==NULL) {
			printf("\nError opening %s for output!",argv[3]);
			return 3;
		}
```
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2007-09-24T16:44:01+00:00
- Post Title: New Here and have a LZSS File that i need help with

to toupper problem can be resolved with #include <ctype.h>

Anyway I have a lzss uncompression function on my website which could be helpful to you:

[http://aluigi.org/mytoolz/unlzss.h](http://aluigi.org/mytoolz/unlzss.h)
## Post #4
- Username: griffinpower
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Sep 11, 2007 10:54 pm
- Post datetime: 2007-09-26T20:26:19+00:00
- Post Title: New Here and have a LZSS File that i need help with

Awesome!!  Thank you. I will give that a try and see what I come up with.
## Post #5
- Username: griffinpower
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Sep 11, 2007 10:54 pm
- Post datetime: 2007-10-24T18:31:06+00:00
- Post Title: New Here and have a LZSS File that i need help with

still having issues... tried the utility you had on your site and it works to a degree but still leaves it garbled. 


If possible can someone look at this and tell me if for sure it is LZSS and not another variation of the LZ family. I would greatly appreciate it.
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-11-01T01:40:34+00:00
- Post Title: New Here and have a LZSS File that i need help with

Deniz Oezmen is LZSS pro
## Post #7
- Username: griffinpower
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Sep 11, 2007 10:54 pm
- Post datetime: 2007-11-06T20:04:17+00:00
- Post Title: New Here and have a LZSS File that i need help with

> Reply from Rheini
>
> Deniz Oezmen is LZSS pro

Thank you for the suggestion. I have PM'd him on this!  THanks again!
