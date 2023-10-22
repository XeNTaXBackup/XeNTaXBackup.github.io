## Post #1
- Username: Bolek
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu May 20, 2004 2:11 am
- Post datetime: 2004-05-19T18:15:42+00:00
- Post Title: Hidden & Dangerous2

Mr. Mouse i writted beta unpacker. Some files are extracting good but some not :/ Can you help me ??? I can send you all my knowladge about this format. One last step to end this but need your help  Plaease !!!!!! 
Writte on this forum whot you think about it.
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-20T05:30:13+00:00
- Post Title: Hidden & Dangerous2

Sure. I'll help where I can, just post me the details of the things you have figured out and the things you still haven't.
## Post #3
- Username: Bolek
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu May 20, 2004 2:11 am
- Post datetime: 2004-05-20T13:05:47+00:00
- Post Title: Hidden & Dangerous2

First of all sorry for my English 
Ok here we go: It's no secret so i will post it here:

The H&D2 files are coded so first of all we must know how encode it.
To encode rhe file we will need two DWORD Keys. Every *.dta file have difrent keys.

I give you keys for Sounds.dta:
         Key1 = 2368300490;
         Key2 = 1340625158;

Ok now we need encode function:
void Decrypt(char* pBuffer, DWORD cbBuffer, DWORD Key1, DWORD Key2) {
	// First loop: process whole 64bit sequences.
	__int64*        pLongLong = (__int64*) pBuffer;
	DWORD    cLongLong = cbBuffer / 8;

	for (; cLongLong; --cLongLong, ++pLongLong){
		DWORD*  pLong = ((DWORD*) pLongLong);
		DWORD   ulong;

		ulong = *pLong;
		*pLong = ~((~ulong) ^ Key2);                      
		++pLong;                       
		ulong = *pLong;
		*pLong = ~((~ulong) ^ Key1);
	}

	// Second loop: process remaining bytes.       
	unsigned char*         pByte = ((unsigned char*) pLongLong);
	DWORD  cBytes = cbBuffer % 8;
	DWORD  keys[2] = { Key2, Key1 };
	unsigned char*         pKey = ((unsigned char*) keys);

	for (; cBytes; --cBytes, ++pByte, ++pKey) {
		unsigned char byte = *pByte;
		unsigned char key = *pKey;               
		*pByte = (unsigned char)(~((~byte) ^ key));
	}
}

Dont worry  just copy it to your program  First parameter is a pointer to data witch will be encoded secound is the size of this data.  DWORD Key1, DWORD Key2 are ouer keys.

Ok  Now we can go with the file format:


- First 4 bytes its a file signature so we skip it
- Next we have Header:

	typedef struct tBASEHEADER {
	DWORD uiNumFiles;                // Number of files in *.dta
	DWORD uiOffsetToTable;         // Offset to file info table
	DWORD uiSizeOfTable;           // Size of table in bytes
	DWORD uiUnknow;                 // ??
                 };

we read this Header but when we readed it we must Encode it.
Example:
Decrypt(Header ,sizeof(tBASEHEADER), 2368300490, 1340625158);
// Keys 2368300490, 1340625158 are to Sounds.dta
Now we can chect example number of files in *.dta 


Ok  Now we seek file to uiOffsetToTable and we have:

           typedef struct tBASEFILEINFO {
	DWORD uiUnknow;           // ??
	DWORD uiOffset;             // Offset to File Header
	DWORD uiUnknow2;         // ??
                char  strFileName[16];     // This isn't real name 
            };

in uiOffsetToTable we have structures no one structure so w must create a  dynamic table:
tBASEFILEINFO FileInfos[ Header->uiNumFiles ];

now we read FileInfos   and when we read it all we must decode it:
Decrypt(FileInfos ,uiSizeOfTable, 2368300490, 1340625158);

Ok  Now we have offsets to files in DTA 

Eatch offset bring as to this structure:

        typedef struct tBASEFILEHEADER {
	DWORD uiUnknow;            // ??
	DWORD uiUnknow2;          // ??
	DWORD uiUnknow3;          // ??
	DWORD uiUnknow4;          // ??
	DWORD uiFileSize;            // Propably Size of File
                DWORD uiUnknow5;          // Propably Number of parts
	unsigned char byLenght;    // Lenght of file name
	char szUnknow6[7];          // ??
        };

We read this structure and we decoding it with description function 
Next we have file name:
char filename[ byLenght ];  we read it and we decoding it with description function 

Ok and next comes file data  but it is so difficult :/

Data are stored in parts 
Part look like this:
             WORD wPartSize;
             WORD wUnknow;
This two values we dont decoding. 

And now we read Data:
char Data[wPartSize];

And we looping it so many times whit is parts number value;

And here is my problem :/ Some files are unpacking good and some not :/
Propabli when we discripted char Data[wPartSize];  we must throw out first byte :/ Meaby not ?    

Please Help me  I thing you will make it 
Do you understand all of it ??
## Post #4
- Username: Bolek
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu May 20, 2004 2:11 am
- Post datetime: 2004-05-21T11:20:44+00:00
- Post Title: Hidden & Dangerous2

Mr. Mouse you take it  ??
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-21T11:26:41+00:00
- Post Title: Hidden & Dangerous2

Yes, I will take a good look at it. I will have to have these archives (for instance the sounds.dat) first. 
Then I will have to recreate the process you describe. 
It will take time.
## Post #6
- Username: Bolek
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu May 20, 2004 2:11 am
- Post datetime: 2004-05-21T12:57:41+00:00
- Post Title: Hidden & Dangerous2

Mr. Mouse thank you.
## Post #7
- Username: Bolek
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu May 20, 2004 2:11 am
- Post datetime: 2004-05-28T15:28:45+00:00
- Post Title: Hidden & Dangerous2

Mr. Mouse some news ??
