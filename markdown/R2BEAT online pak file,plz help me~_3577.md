## Post #1
- Username: kensou
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jul 11, 2009 5:20 am
- Post datetime: 2009-07-11T09:36:07+00:00
- Post Title: R2BEAT online pak file,plz help me~

this game's pak file comtype by lz77.
here is a link to download a little r2beat's pak file 
[http://www.yourfilelink.com/get.php?fid=501200](http://www.yourfilelink.com/get.php?fid=501200)


end of the file,can see a byte 0x12,is idstring
before 4 bytes are FILES
before 4 bytes are FILELISTOFFSET
goto FILELISTOFFSET
get filenamelen byte
get filetype byte(filetype= 0x01 is a file,filetype = 0x02 is a folder) 
get OFFSET long
get ZSIZE long
get SIZE long
getdstring filename FILENAMELEN

this is my bms code ,but can not extract the pak file.plz help me
sorry for my english-_-!

```
savepos OFFSET
math OFFSET -= 1
goto OFFSET
get FILETYPE byte
math OFFSET -= 4
goto OFFSET
get FILES long
math OFFSET -= 4
goto OFFSET
get LISTOFFSET long
goto LISTOFFSET

for i = 0 < FILES
get FNAMELEN byte
get FILESTYPE byte
MATH FILNAMELEN += 1
get OFFSET long
get ZSIZE long
get SIZE long
getdstring NAME FNAMELEN
clog NAME OFFSET ZSIZE SIZE
next i
```
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-07-11T10:05:36+00:00
- Post Title: R2BEAT online pak file,plz help me~

the error was a variable used with a different name (FNAMELEN and FILNAMELEN) so I have adjusted the bms script but the problem is that the compression algorithm is not lzss.

```
goto -1
get FILETYPE byte
goto -5
get FILES long
goto -9
get LISTOFFSET long
goto LISTOFFSET

for i = 0 < FILES
    get FNAMELEN byte
    get TYPE byte
    math FNAMELEN += 1
    get OFFSET long
    get ZSIZE long
    get SIZE long
    getdstring NAME FNAMELEN
    if TYPE != 2
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
## Post #3
- Username: kensou
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jul 11, 2009 5:20 am
- Post datetime: 2009-07-11T10:26:15+00:00
- Post Title: R2BEAT online pak file,plz help me~

thx for your reply.
but i have a question,lzss=lz77?
## Post #4
- Username: kensou
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jul 11, 2009 5:20 am
- Post datetime: 2009-07-11T10:33:05+00:00
- Post Title: R2BEAT online pak file,plz help me~

here is a c++ code for extrator that pak file.
it seems use lz77 compress.

```
#include<string>
#include<cstring>
#include<vector>
#include <fstream>
#include <iostream>
using namespace std;
#define DIRECTORY_NAME 2
#define FILE_NAME 1
struct codedFile
{
	char fileNameLen;
	char fileType;
	unsigned long offsetInPAK;
	unsigned long codedLen;
	unsigned long originLen;
	string fileName;
};
ifstream infile;
int main(int argc, char* argv[])
{
	//读入pak文件
	void decode(const codedFile& theFile,const char * path);
	infile.open(argv[1],ios::in|ios::binary);
	char charBuffer;			//字节缓冲
	codedFile tempCF;			//codedFile结构缓冲
	long fileNum;				//解压后的文件夹+文件个数
	long codedFileGOffset;				//codedFile组所在的偏移位置
	vector<codedFile> codedFileG;
	infile.seekg(-1,ios::end );	//读取最后一个字节
	infile.get(charBuffer);
	if(charBuffer==0x12)			//标记来的吧
	{
		cout<<"The PAK can be decoded..."<<endl;
		infile.seekg(-5,ios::end );	//从倒数第五个字节开始读双字，为fileNum
		infile.read((char *)&fileNum,4);
		infile.seekg(-9,ios::end );	//从倒数第9个字节开始读双字，为codedFile组所在的偏移位置
		infile.read((char *)&codedFileGOffset,4);
		infile.seekg(codedFileGOffset,ios::beg );  //指针移动到codedFile组所在的偏移位置
		for(int i=0;i<fileNum;i++)			//读取codedFile进codeFileG
		{
			//不读文件名的起始地址
			infile.read ((char *)&tempCF.fileNameLen,1);	
			infile.read ((char *)&tempCF.fileType ,1);
			infile.read ((char *)&tempCF.offsetInPAK,4);
			infile.read ((char *)&tempCF.codedLen,4);
			infile.read ((char *)&tempCF.originLen,4);
			//读取文件名
			tempCF.fileName="";
			for(int j=0;j<=tempCF.fileNameLen ;j++)
			{
				infile.get(charBuffer);
				if(charBuffer=='/') charBuffer='\\';
				tempCF.fileName+=charBuffer;

			}
			codedFileG.push_back(tempCF);
		}
		/*
		for(int i=0;i<fileNum;i++)
		{
			cout<<codedFileG[i].fileName<<endl;
		}
		*/
		for(int i=0;i<fileNum;i++)
		{
			cout<<"Reading "<<argv[2]<<codedFileG[i].fileName<<endl;
			decode(codedFileG[i],argv[2]);
			cout<<"OK!!"<<endl;
		}

	}
	else cout<<"The PAK can't be decoded"<<endl;
	infile.close ();
	return 0;
}

void decode(const codedFile& theFile,const char * path)
{
	vector<char> textBuffer;
	int r=0;							//缓冲字节区内指针
	char outFileName[255];
	strcpy(outFileName,path);
	strcat(outFileName,theFile.fileName .c_str ());
	if(theFile.fileType == FILE_NAME)
	{
		infile.seekg(theFile.offsetInPAK ,ios::beg );
		//真正解码开始……………………………………
		int readLen=0;
		//readLen=(int)infile.tellg ()-theFile.offsetInPAK +2;
		while(textBuffer.size ()<theFile.originLen && readLen<theFile.codedLen-1 )
		{
			char codeInfo;			//储存加密标记字节
			infile.get(codeInfo);
			readLen++;
			for(int i=0;i<8;i++)
			{
				char codeFlag=codeInfo&0x1;	//记录是否加密的标记位，0=未加密，1=加密
				char charBuffer;					//字节缓冲
				if(codeFlag==0)				//未加密处理过程：直接拷贝原文
				{
					//if(!infile.eof())
					//{
						if(readLen==theFile.codedLen) goto endit;
						
						infile.get(charBuffer);
						readLen++;
						//////////outfile.put(charBuffer);
						
						//buffer[r++]=charBuffer;
						textBuffer.push_back(charBuffer);
						r++;
						
					//}
				}
				else						//加密处理过程
				{
					//if(!infile.eof())
					//{
						if(readLen==theFile.codedLen) goto endit;
						short int codePair;			//加密组合，高4位代表长度，低12位代表偏移量
						infile.read((char *)&codePair,2);
						readLen+=2;
						short int len=((codePair>>12)&0xf)+2;			//长度
						short int offset=codePair&0xfff;			//偏移量
						for(int j=0;j<len;j++)
						{
							charBuffer=textBuffer[r-offset];
							//charBuffer=buffer[r-offset];
							///////////outfile.put(charBuffer);
							//buffer[r++]=charBuffer;
							textBuffer.push_back(charBuffer);
							r++;
						}
					//}
				}
				codeInfo>>=1;
			}//end of for
			
		}//end of while
endit:		ofstream outfile;
		outfile.open(outFileName,ios::out|ios::binary);
		vector<char>::iterator textBufferI;
		cout<<"Extracting "<<outFileName<<endl;
		for(textBufferI=textBuffer.begin ();textBufferI!=textBuffer.end();textBufferI++)
		{
			outfile.put(*textBufferI);
		}
		outfile.close();
	}//end of if
	else			//文件夹
	{
		char commandLine[265]="md ";
		strcat(commandLine,outFileName);
		system(commandLine);
	}
}
```
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-07-11T10:43:19+00:00
- Post Title: R2BEAT online pak file,plz help me~

the compression algorithms are ever a chaos.
anyway plus or less yes, as far as I know, lzss is also known as lz77.
the problem are the derived algorithms like visible on [http://datacompression.info/LZSS.shtml](http://datacompression.info/LZSS.shtml) which creates confusion so you must be 100% sure of the algorithm (which by my tests performed on the files is none of those supported by quickbms).

for example the decode() function used in that c++ code is different than the classical and new lzss code.
## Post #6
- Username: kensou
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jul 11, 2009 5:20 am
- Post datetime: 2009-07-11T10:47:21+00:00
- Post Title: R2BEAT online pak file,plz help me~

> Reply from Bugtest
>
> the compression algorithms are ever a chaos.
anyway plus or less yes, as far as I know, lzss is also known as lz77.
the problem are the derived algorithms like visible on http://datacompression.info/LZSS.shtml which creates confusion so you must be 100% sure of the algorithm (which by my tests performed on the files is none of those supported by quickbms).

for example the decode() function used in that c++ code is different than the classical and new lzss code.

i see,
so,this pak can not unpack use quickbms.
thx again.
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-07-11T11:21:39+00:00
- Post Title: R2BEAT online pak file,plz help me~

it's not the most wonderful script of the world but it does the job :)

```
get FILETYPE byte
goto -5
get FILES long
goto -9
get LISTOFFSET long
goto LISTOFFSET

for MYFILES = 0 < FILES
    get FNAMELEN byte
    get TYPE byte
    math FNAMELEN += 1
    get OFFSET long
    get ZSIZE long
    get SIZE long
    getdstring NAME FNAMELEN

    if TYPE == 1
        if SIZE == ZSIZE
            log NAME OFFSET SIZE
        else
            log MEMORY_FILE OFFSET ZSIZE
            log MEMORY_FILE2 0 SIZE     # blah, assign memory

            set readlen long 0
            set r long 0
            for readlen = readlen < ZSIZE
                get codeinfo byte MEMORY_FILE
                math readlen += 1
                for i = 0 < 8
                    if codeinfo & 1
                        if readlen >= ZSIZE
                            break
                        endif
                        get codepair short MEMORY_FILE
                        math readlen += 2
                        set len long codepair
                        math len >>= 12
                        math len &= 0xf
                        math len += 2
                        math codepair &= 0xfff      # offset
                        for j = 0 < len
                            set tmp long r
                            math tmp -= codepair    # offset
                            getvarchr charbuffer MEMORY_FILE2 tmp
                            putvarchr MEMORY_FILE2 r charbuffer
                            math r += 1
                        next j
                    else
                        if readlen >= ZSIZE
                            break
                        endif
                        get charbuffer byte MEMORY_FILE
                        math readlen += 1
                        putvarchr MEMORY_FILE2 r charbuffer
                        math r += 1
                    endif
                    math codeinfo >>= 1
                next i
            next

            log NAME 0 SIZE MEMORY_FILE2
        endif
    endif
next MYFILES
```
## Post #8
- Username: kensou
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jul 11, 2009 5:20 am
- Post datetime: 2009-07-11T11:33:44+00:00
- Post Title: R2BEAT online pak file,plz help me~

it works!thx a lot....
but it not perfect,the end of a extractor file have a text "-1"
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-07-11T12:27:54+00:00
- Post Title: R2BEAT online pak file,plz help me~

the extracted files are identical to those obtained with the C++ code you pasted, so they are ok.

P.S.: eh eh eh I guess that mr.mouse will scream when he will see how you quoted in the previous post :)
