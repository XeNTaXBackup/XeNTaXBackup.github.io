## Post #1
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-03-23T16:54:56+00:00
- Post Title: [Solved]Gundam UC tpf file

Hello everyone!
I have some textures in .tpf format impossible to preview or convert in .dds.
I try to preview tpf files with TextureFinder and don't work.
Dark Souls's tpf and Gundam UC's tpf are very different from each other.
Somebody help me! Please.
Here's some sample files as well.
[http://www.mediafire.com/?bg0ifca33li392a](http://www.mediafire.com/?bg0ifca33li392a)
## Post #2
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-03-25T13:24:35+00:00
- Post Title: [Solved]Gundam UC tpf file

Is anyone interested in tpf files?
Here is TPF source by Allen

```
char[4]           Idstring          //"TPF "
dword            ImageFileSizeTotal    //所有图像的大小的总和 Total all image file size
dword            ImageFileNumber       //图像数量
dword            unknown           //0x02030200
}
struct TPF_Index{
dword            OffsetImageStart
dword            ImageFileSize
byte               DXT               //如果=0，则是DXT1. 如果=5，则是DXT5。
byte               Null
word              unknown.
word              Width 
word              Height
dword[2]        Null
dword            OffsetImageName
dword            Unknown           //=1，则有下面的值，=0，则没有
*dword          Unknown
*dword          Unknown
*float             Unknown
}
struct Image_Header{
char[4]          Idstring          //"DCP "
char[4]          UnkName           //"EDGE "
dword            HeaderSize           //0x00000020
dword            unknown           //0x9000000
dword            unknown           //0x00100000
dword[2]        Null
dword            unknown           //0x00100100
}
Struct Image
Char[4]          Idstring          //"DCS "
word              NumberImagePart2
word              Unknown
dword            ImageDataSize     //size of image data
dword            Null
<Image data>                       //Image Data Start
} 
struct DAC{                          //DAC是一个索引表
Char[4]          Idstring          //"DCA "
dword            ImageIndexChunkLength
struct EGDT
{
char[4]           Idstring              //"EgdT"
dword            unknown            //0x10000
dword            EgdT_HeaderSize       //0x20
dword            EachImageIndexSize  //0x10
dword            RawBufferSize            //0x00010000
dword            ImageIndexTableSize  
dword            ImageIndexTableNumber  //索引表数量
dword            unknown           //0x00100000
}
Struct ImageIndex
{
dword            Null
dword            offsetImagePart   //base on Image Data Start
dword            ImagePartSize
dword            Compression Flag  //alway 0x1
}
}

```
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-25T15:40:08+00:00
- Post Title: [Solved]Gundam UC tpf file

What's the compression flag for
