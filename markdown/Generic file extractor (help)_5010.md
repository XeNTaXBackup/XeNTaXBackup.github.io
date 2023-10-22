## Post #1
- Username: Digitkel
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 12, 2010 5:01 am
- Post datetime: 2010-09-11T21:53:56+00:00
- Post Title: Generic file extractor (help)

Hello I'm trying to extract data from what has been referred to as a "chunked archive", A container holding multiple instances of a certain type of file. 

These files have a signature at the begining,  I'll use RIFF as an example. Wav files first 4 bytes are RIFF which is 0x52 0x49 0x46 0x46 in hex. I want to seach for a hex string and get the offset, then find the end of the chunk and extract. Then find the next instance. The chunks are seperated by large groups of zeros, 0x00  0x00 etc in hex. The signature isn't RIFF it may use nonprintable characters that's why I want to search for the hex values.

I've been trying to write a bms script for this but can't seem to get it right, I think I should use FindLoc but I'm not sure I've looked at alot of examples, and guides but I still haven't figured BMS out yet. 
Could someone help me out and write a script to do this, and maybe comment the lines, so I can figure out what's happening?

I'd also like some help writing some code to do this, also commented if possible. I would like to be able to slightly modify the code to use it for different files, basically a generic extractor that searches for hex bytes. I've been looking for some c or cpp code that does this but haven't been able to find it yet. 

It would also help if it supported large files - 2gb+. Any help would be appreciated.
## Post #2
- Username: Digitkel
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 12, 2010 5:01 am
- Post datetime: 2010-09-16T00:04:04+00:00
- Post Title: Generic file extractor (help)

I have been trying to base my extractor on this code. I can't figure out the how to search for 0x00 in hex. can someone help me? 

```
#include "string.h"
#include "malloc.h"
#define DDS_MAGIC "DDS "
int ipos[10240];
int iposind=0;
int tfilelen;
char* TransBuf=NULL;
int main(int argc, char** argv){
int i,r;
FILE* sFile=NULL;
FILE* tFile=NULL;
char ifn[256];
char ofn[256];
char qc;
if (argc !=2){
printf("usage: %s filename\n",argv[0]);
return 0;
}
strcpy(ifn,argv[1]);
sFile=fopen(argv[1],"rb");
fseek(sFile,0,SEEK_END);
tfilelen=ftell(sFile);
fseek(sFile,0,SEEK_SET);
TransBuf=(char*)malloc(tfilelen);
for(i=0,r=0;r<tfilelen;){
/* read the file in */
i=fread(TransBuf+r,1,tfilelen-r,sFile);
if(i>0)r+=i;
}
qc=DDS_MAGIC[0];
for(i=0;i<tfilelen;i++){
if(TransBuf[i]!=qc)continue;
if(strncmp(DDS_MAGIC,TransBuf+i,4)==0){
ipos[iposind]=i;
iposind++;
}
}
ipos[iposind]=tfilelen;
for(i=0;i<iposind;i++){
char* s;
int l;
int j;
s=TransBuf+ipos[i];
l=ipos[i+1]-ipos[i];
if(l<4)continue; /* don't write out dds files with no data*/
/* write each dds segment to it's own file */
sprintf(ofn,"%s_%d.dds",ifn,i);
tFile=fopen(ofn,"w+b");
for(j=0,r=0;r<l;){
j=fwrite(s+j,1,l-r,tFile);
if(j>0)r+=j;
}
fclose(tFile);
}
printf("extracted %d chunks\n",i);
return 0;
}
```
## Post #3
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-09-16T23:55:59+00:00
- Post Title: Generic file extractor (help)

> Reply from Digitkel
>
> I have been trying to base my extractor on this code. I can't figure out the how to search for 0x00 in hex. can someone help me?Change strncmp to memcmp and then modify DDS_MAGIC to what you're searching for e.g. "A\x00B\x00" would search for A, 0x00, B, 0x00.
## Post #4
- Username: Digitkel
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 12, 2010 5:01 am
- Post datetime: 2010-09-17T01:06:03+00:00
- Post Title: Generic file extractor (help)

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-09-17T22:39:47+00:00
- Post Title: Generic file extractor (help)

If that's what you're trying to do than you don't need to modify DDS_MAGIC. Here's the previous code modified to do what (I think) you described. I'm too lazy to explain it right now but feel free to ask.

```
#include "string.h"
#include "malloc.h"
#define DDS_MAGIC "DDS "
int ipos[10240];
int iposind=0;
int tfilelen;
char* TransBuf=NULL;
int main(int argc, char** argv) {
    int i,r;
    FILE* sFile=NULL;
    FILE* tFile=NULL;
    char ifn[256];
    char ofn[256];
    char qc;
    if (argc !=2) {
        printf("usage: %s filename\n",argv[0]);
        return 0;
    }
    strcpy(ifn,argv[1]);
    sFile=fopen(argv[1],"rb");
    fseek(sFile,0,SEEK_END);
    tfilelen=ftell(sFile);
    fseek(sFile,0,SEEK_SET);
    TransBuf=(char*)malloc(tfilelen);
    for (i=0,r=0; r<tfilelen;) {
        /* read the file in */
        i=fread(TransBuf+r,1,tfilelen-r,sFile);
        if (i>0)r+=i;
    }
    qc=DDS_MAGIC[0];
    for (i=0; i<tfilelen; i++) {
        if (TransBuf[i]!=qc)continue;
        if (strncmp(DDS_MAGIC,TransBuf+i,4)==0) {
            ipos[iposind]=i;
            iposind++;
        }
    }
    ipos[iposind]=tfilelen;
    for (i=0; i<iposind; i++) {
        char* s;
        int l;
        int j;
        int lastWasNull; /* The to vars were added for the code below. */
        int firstLastNull;
        s=TransBuf+ipos[i];
        l=ipos[i+1]-ipos[i];
        if (l<4)continue; /* don't write out dds files with no data*/
        /* write each dds segment to it's own file */
        sprintf(ofn,"%s_%d.dds",ifn,i);
        tFile=fopen(ofn,"w+b");

        /* We want to find the length of this chunk without all the nulls on the end. */
        lastWasNull = 0;
        firstLastNull = l;
        for (j=0; j<l; j++) {
            if (s[j] == 0) {
                if (lastWasNull == 0) {
                    firstLastNull = j;
                    lastWasNull = 1;
                }
            } else {
                lastWasNull = 0;
            }
        }
        l = firstLastNull;
        /* End modified code. */

        for (j=0,r=0; r<l;) {
            j=fwrite(s+j,1,l-r,tFile);
            if (j>0)r+=j;
        }
        fclose(tFile);
    }
    printf("extracted %d chunks\n",i);
    return 0;
}

```
## Post #6
- Username: Digitkel
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 12, 2010 5:01 am
- Post datetime: 2010-09-17T23:15:12+00:00
- Post Title: Generic file extractor (help)

BIG Thanks Zench that worked like a charm.

Now for added flexiblity how about changing "DDS_MAGIC" to a variable and allow the user to input a 4 byte hex value. "DDS " would be 44445320. And then use that in the variable.

That's the reason I was trying to figure the hex part out.
## Post #7
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-09-17T23:46:39+00:00
- Post Title: Generic file extractor (help)

> Reply from Digitkel
>
> Now for added flexiblity how about changing "DDS_MAGIC" to a variable and allow the user to input a 4 byte hex value. "DDS " would be 44445320. And then use that in the variable.Well I'm not going to write all your code for you  

I'll give you a hint though...

char magic[4]; /* Was DDS_MAGIC */

int valueFromHex;
sscanf(inputString, "%2x", &valueFromHex); /* Grab a 2-character hex value from inputString. */

magic[0] = valueFromHex; /* Assign this value as the first byte of the magic. */

...
## Post #8
- Username: Digitkel
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 12, 2010 5:01 am
- Post datetime: 2010-09-18T00:54:02+00:00
- Post Title: Generic file extractor (help)

ok that is very understandable, I might be able to get that part. 
Many thanks again for all the help, I probably couldn't have did it without your help. 

I have a question about your loop though. How is it determining what's a null?

Upon further testing it doesn't work corectly in some cases. Say there are some non 0x00 characters in between the end of data, and the next instance of the magic number.

I should have put a couple in the test file but wasn't thinking. Data in the test file is represented by x and y, and the data always ends before 0x00's

since you know that loop very well   atleast help me with that part.
## Post #9
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-09-18T01:38:34+00:00
- Post Title: Generic file extractor (help)

Small oversight on my part:

```
lastWasNull = 0;
firstLastNull = l;
for (j=0; j<l; j++) {
    if (s[j] == 0) {
        if (lastWasNull == 0) {
            firstLastNull = j;
            lastWasNull = 1;
        }
    } else {
        lastWasNull = 0;
        firstLastNull = l; /* This line was added. */
    }
}
l = firstLastNull;
/* End modified code. */
```
It should work better now, if I understood you correctly.

> Reply from Digitkel
>
> I have a question about your loop though. How is it determining what's a null?The line:

```
if (s[j] == 0) {
```
s is chunk in memory.
## Post #10
- Username: Digitkel
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 12, 2010 5:01 am
- Post datetime: 2010-09-18T02:32:47+00:00
- Post Title: Generic file extractor (help)

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: Digitkel
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 12, 2010 5:01 am
- Post datetime: 2010-10-17T18:20:31+00:00
- Post Title: Generic file extractor (help)

Can anybody show me an example of reading the first 4 bytes of a file and put it into a variable say buffer1 and read the next 4 bytes and put that into buffer2?

Then print buffers as hex and dec just to make sure everything is working properly.

say we have an example test.txt that's 16 bytes in size with ascii characters a through p, the first four bytes should be abcd, that's 61626364 in hex and that's 1633837924 in dec.

Here's the cpp I started and got stuck, should use a different method?

```
#include <fstream>
using namespace std;

int main () {
  int length;
  char * buffer;

  ifstream is;
  is.open ("test.txt", ios::binary );

  // get length of file:
  is.seekg (0, ios::end);
  length = is.tellg();
  is.seekg (0, ios::beg);

  // allocate memory:
    buffer = new char [4];
    
    
  // read data:
  is.read (buffer,4);
  is.close();

  cout.write (buffer,4);
    
  delete[] buffer;
  return 0;
}

 
```
## Post #12
- Username: Digitkel
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Sep 12, 2010 5:01 am
- Post datetime: 2010-10-19T05:21:18+00:00
- Post Title: Generic file extractor (help)

I have a question about Data type ranges. Here's a small program that demostrates my problem. The value seems to be too big and it results in a negative number. How can I fix this? 

Here's some info on data type ranges, I hope I'm allowed to post links like this.  
[http://msdn.microsoft.com/en-us/library/s3f49ktz.aspx](http://msdn.microsoft.com/en-us/library/s3f49ktz.aspx)


```
#include <iostream>
using namespace std;

int main()
{
       
    long long number = 4123789456LL;   // added LL
   
    cout << "test Value " << number << endl; 
    printf("%d\n", number);                    // print Decimal
    printf("%x\n", number);                    // print Hex
       
    return 0;
}
```
