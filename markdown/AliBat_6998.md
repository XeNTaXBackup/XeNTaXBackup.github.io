## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-18T01:45:37+00:00
- Post Title: AliBat

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-07-19T01:52:55+00:00
- Post Title: AliBat

sample file you posted doesn't look encrypted... u can see indeces at the bottom, among other stuff in the file as well. is that a full model file?
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-19T02:01:23+00:00
- Post Title: AliBat

looks like a very easy model format no encryption.
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-07-19T02:16:58+00:00
- Post Title: AliBat

yeah, i just looked through the vertex format... seems like a group of 8 floats (try loading data from 0xB4450 - 0xB0760), standard byte-order. multiple models per file.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-19T02:24:05+00:00
- Post Title: AliBat

No idea whether it's a full model or not.
There are only 8 files that aren't sounds, and 4 of them don't look like models.

PS: I just remembered I posted a decrypted model lol
## Post #6
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-07-19T02:33:06+00:00
- Post Title: AliBat

Of those 8 floats, first three are x, y, z.
after vertex list, beginning with Mex section appears to be triangle list indeces. Of the data I took, I was able to look at the points.
[sample.jpg](https://xentaxbackup.github.io/file/4508_sample.jpg)
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-19T02:35:40+00:00
- Post Title: AliBat

Hmmm nice.
I found some files which look like index files so I'll try to see if these are actually multiple files packed into one or not.

EDIT: it looks like all of the models are in the file (there's another with letter T, which contains a bunch of dds textures). Haven't found any files that indicate how they might be separated, so maybe the game just loads everything into memory? lol

Here are the files that I thought were weird, but it doesn't seem like anything to me (maybe I got the decryption key wrong).
[data.7z](https://xentaxbackup.github.io/file/4509_data.7z)
## Post #8
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-07-19T04:16:09+00:00
- Post Title: AliBat

yeah, the file is weird.
for example, i was looking at the model cGin.cGin_wingShape_006.
it appears in a 8230 byte section at 0x149A7E.
it appears again in a 8230 byte section at 0x19191A (exactly the same data too I think).
## Post #9
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-07-19T08:15:54+00:00
- Post Title: AliBat

Ah, some objects use a different vertex specification... the wing uses 15 floats per vertex!
[wing.jpg](https://xentaxbackup.github.io/file/4515_wing.jpg)
## Post #10
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-07-19T21:59:46+00:00
- Post Title: AliBat

Gin is in. Is there a dog or some thing in the game? There is something that looks like snoopy in this file lol.

```

bool read_object(ifstream& file, size_t base, const char* lsfile)
{
 // debug output
 bool debug = false;

 // move to base
 cout << "object base = " << base << endl;
 file.seekg(base, ios_base::beg);

 // read size of object
 unsigned int object_size;
 file.read((char*)&object_size, sizeof(object_size));
 cout << "object size = " << object_size << endl;

 // read name of object
 string object_name = "";
 for(;;) {
     char temp;
     file.read((char*)&temp, 1);
     if(temp != 0x00) object_name += temp;
     else break;
    }
 cout << "object name = " << object_name.c_str() << endl;

 // read 0x30 throw away characters
 while(file.peek() == 0x30) {
       char cx;
       file.read((char*)&cx, sizeof(cx));
      }

 // read a 4-byte variable
 float unknown01;
 file.read((char*)&unknown01, sizeof(unknown01));
 cout << "unknown01 = " << unknown01 << endl;

 // read a 4-byte variable
 float unknown02;
 file.read((char*)&unknown02, sizeof(unknown02));
 cout << "unknown02 = " << unknown02 << endl;

 // read a 4-byte variable
 float unknown03;
 file.read((char*)&unknown03, sizeof(unknown03));
 cout << "unknown03 = " << unknown03 << endl;

 // read a 4-byte variable
 float unknown04;
 file.read((char*)&unknown04, sizeof(unknown04));
 cout << "unknown04 = " << unknown04 << endl;

 // read a 4-byte variable
 unsigned int unknown05;
 file.read((char*)&unknown05, sizeof(unknown05));
 cout << "unknown05 = " << unknown05 << endl;

 // read a 4-byte variable
 unsigned int unknown06;
 file.read((char*)&unknown06, sizeof(unknown06));
 cout << "unknown06 = " << unknown06 << endl;

 // read a 4-byte variable
 unsigned int unknown07;
 file.read((char*)&unknown07, sizeof(unknown07));
 cout << "unknown07 = " << unknown07 << endl;

 // read number of vertices
 unsigned int n_vertices;
 file.read((char*)&n_vertices, sizeof(n_vertices));
 cout << "number of vertices = " << n_vertices << endl;
 
 // read vertex buffer
 size_t vertex_size = 15*4;
 size_t vertex_buffer_size = n_vertices*vertex_size;
 float* vertex_buffer_data = (float*)::operator new(vertex_buffer_size);
 file.read((char*)vertex_buffer_data, vertex_buffer_size);

 // vertex data is followed by two 0x00000001
 unsigned int fixed1;
 file.read((char*)&fixed1, sizeof(fixed1));
 if(fixed1 != 1) return error("After vertex data, expecting 0x00000001.");
 unsigned int fixed2;
 file.read((char*)&fixed2, sizeof(fixed2));
 if(fixed2 != 1) return error("After vertex data, expecting 0x00000001.");

 // read number of indeces
 unsigned int n_indices;
 file.read((char*)&n_indices, sizeof(n_indices));
 cout << "number of indices = " << n_indices << endl;

 // read index buffer
 size_t index_size = 2;
 size_t index_buffer_size = n_indices*index_size;
 unsigned short* index_buffer = (unsigned short*)::operator new(index_buffer_size);
 file.read((char*)index_buffer, index_buffer_size);

 // start lscript
 ofstream ofile(lsfile);
 ofile << "main" << endl;
 ofile << "{" << endl;
 ofile << " editbegin();" << endl;

 // save vertices
 size_t vertex_float_index = 0;
 for(size_t vertex_index = 0; vertex_index < n_vertices; vertex_index++)
    {
     // extract position
     float x = vertex_buffer_data[vertex_float_index++];
     float y = vertex_buffer_data[vertex_float_index++];
     float z = vertex_buffer_data[vertex_float_index++];
     ofile << " pointlist[" << (vertex_index + 1) << "]" << " = " << "addpoint(" << x << "," << y << "," << z << ");" << endl;

     // extract other crap
     float unknown_p01 = vertex_buffer_data[vertex_float_index++];
     float unknown_p02 = vertex_buffer_data[vertex_float_index++];
     float unknown_p03 = vertex_buffer_data[vertex_float_index++];
     float unknown_p04 = vertex_buffer_data[vertex_float_index++];
     float unknown_p05 = vertex_buffer_data[vertex_float_index++];
     float unknown_p06 = vertex_buffer_data[vertex_float_index++];
     float unknown_p07 = vertex_buffer_data[vertex_float_index++];
     float unknown_p08 = vertex_buffer_data[vertex_float_index++];
     float unknown_p09 = vertex_buffer_data[vertex_float_index++];
     float unknown_p10 = vertex_buffer_data[vertex_float_index++];
     float unknown_p11 = vertex_buffer_data[vertex_float_index++];
     float unknown_p12 = vertex_buffer_data[vertex_float_index++];

     // display debug data
     if(debug) {
        cout << "VERTEX_INDEX[" << vertex_index << "]" << endl;
        cout << x << endl;
        cout << y << endl;
        cout << z << endl;
        cout << unknown_p01 << endl;
        cout << unknown_p02 << endl;
        cout << unknown_p03 << endl;
        cout << unknown_p04 << endl;
        cout << unknown_p05 << endl;
        cout << unknown_p06 << endl;
        cout << unknown_p07 << endl;
        cout << unknown_p08 << endl;
        cout << unknown_p09 << endl;
        cout << unknown_p10 << endl;
        cout << unknown_p11 << endl;
        cout << unknown_p12 << endl;
        cout << endl;
       }
    }

 // save triangle strip
 size_t tristrip_index = 0;
 if(debug) cout << index_buffer[tristrip_index] << endl;
 unsigned short i0 = index_buffer[tristrip_index + 0] + 1;
 unsigned short i1 = index_buffer[tristrip_index + 1] + 1;
 unsigned short i2 = index_buffer[tristrip_index + 2] + 1;
 ofile << " addtriangle(pointlist[" << i0 << "], pointlist[" << i1 << "], pointlist[" << i2 << "]);" << endl;

 for(tristrip_index = 1; tristrip_index < n_indices - 2; tristrip_index++) {
     if(debug) cout << index_buffer[tristrip_index] << endl;
     unsigned short i0 = index_buffer[tristrip_index + 0] + 1;
     unsigned short i1 = index_buffer[tristrip_index + 1] + 1;
     unsigned short i2 = index_buffer[tristrip_index + 2] + 1;
     if(tristrip_index % 2) ofile << " addtriangle(pointlist[" << i0 << "], pointlist[" << i2 << "], pointlist[" << i1 << "]);" << endl;
     else ofile << " addtriangle(pointlist[" << i0 << "], pointlist[" << i1 << "], pointlist[" << i2 << "]);" << endl;
    }

 // end lscript
 ofile << " editend();" << endl;
 ofile << "}" << endl;

 return true;
}

// WINGS
// cGin.cGin_wingShape_006
// 15 floats per vertex
// 4 bytes per float
// 126 vertices
// 7560 total vertex bytes (0x1D88)
// 0x149A7A - 0x149A7D -> 0x2026 = 8230 (total object bytes)
// 0x149A7E - 0x149A94 -> name of object (16 bytes)
// 0x149A95 - 0x149A95 -> 0x00 (terminating null)
// 0x149A96 - 0x149A99 -> 0x40AA4BB6 = 5.32174205780029
// 0x149A9A - 0x149A9D -> 0x00000000 = 0.0
// 0x149A9E - 0x149AA1 -> 0x40E4FF4E = 7.15616512298584
// 0x149AA2 - 0x149AA5 -> 0xBF2A3A10 = -0.664948634399941
// 0x149AA6 - 0x149AA9 -> 0x00000001 = 1
// 0x149AAA - 0x149AAD -> 0x00000DC3 = 3523 = (13/195)
// 0x149AAE - 0x149AB1 -> 0x00000000 = 0
// 0x149AB2 - 0x149AB5 -> 0x0000007E = 126 (number of vertices)
// 0x149AB6 - 0x14B83D -> vertex data (7560 bytes)
// 0x14B83E - 0x14B841 -> 0x00000001 = 1
// 0x14B842 - 0x14B845 -> 0x00000001 = 1
// 0x14B846 - 0x14B849 -> 0x0125 = 293 (number of indeces)
// 0x14B84A - 0x14BA93 -> index data (293*2 bytes)
// 0x14BA94 - 0x14BA97 -> 0x00000000 fixed
// 0x14BA98 - 0x14BA9B -> 0x00000003 fixed
// 0x14BA9C - 0x14BA9F -> 0x00000000 fixed
// 0x14BAA0 -> next object

// BODY SHAPE
// cKun.c_KUN_bodyShape_001
// 0x2BFE08 - 0x2BFE0B = 0x0000A68E = 42,638 (total object bytes)
// 0x2BFE0C - 0x2BFE23 -> name of object (18 bytes)
// 0x2BFE24 - 0x2BFE24 -> 0x00 (terminating null)
// 0x2BFE25 - 0x2BFE27 -> 0x303030 (padding bytes?)
// 0x2BFE28 - 0x2BFE2B -> 0x3FCO0000 = 1.5
// 0x2BFE2C - 0x2BFE2F -> 0x00000000 = 0.0
// 0x2BFE30 - 0x2BFE33 -> 0x3FCO0000 = 1.5
// 0x2BFE34 - 0x2BFE37 -> 0x3E3457E2 = 0.176116496324539
// 0x2BFE38 - 0x2BFE3B -> 0x00000000 = 0
// 0x2BFE3C - 0x2BFE3F -> 0x00000DC3 = 3523 = (13/195)
// 0x2BFE40 - 0x2BFE43 -> 0x00000000 = 0
// 0x2BFE44 - 0x2BFE47 -> 0x00000287 = 647 (number of vertices)
// 0x2BFE48 - 0x2C95EB -> vertex data (15*4*647 bytes = 38820 bytes)
// 0x2C95EC - 0x2C95EF -> 0x00000001 = 1
// 0x2C95F0 - 0x2C95F3 -> 0x00000001 = 1
// 0x2C95F4 - 0x2C95F7 -> 0x00000749 = 1865 (number of indeces)
// 0x2C95F8 - 0x2CA489 -> index data (1865*2 bytes = 3730 bytes)
// 0x2CA48A - 0x2CA48D -> 0x00000000 = 0
// 0x2CA48E - 0x2CA491 -> 0x00000003 = 3
// 0x2CA492 - 0x2CA495 -> 0x00000000 = 0
// 0x2CA495 -> next object

int main(void)
{
 // open file
 ifstream file("bankM01_out.dat", ios::binary);
 if(!file) return error("Error opening file.");

 read_object(file, 0x1314D8, "cGin.cGin_handShape_001.ls"); 
 read_object(file, 0x139D7A, "cGin.cGin_skirtShape_002.ls"); 
 read_object(file, 0x13CBF4, "cGin.cGin_skirtShape_001.ls"); 
 read_object(file, 0x13E254, "cGin.cGin_skirtShape_003.ls"); 
 read_object(file, 0x13E5E0, "cGin.head_dressShape_004.ls"); 
 read_object(file, 0x13F5B6, "cGin.head_dressShape_002.ls"); 
 read_object(file, 0x13FE76, "cGin.head_dressShape_005.ls"); 
 read_object(file, 0x140506, "cGin.head_dressShape_006.ls"); 
 read_object(file, 0x141DDE, "cGin.cGin_headShape_007.ls"); 
 read_object(file, 0x149A7A, "cGin.cGin_wingShape_006.ls"); 
 read_object(file, 0x14BAA0, "cGin.cGin_dressShape_004.ls"); 
 read_object(file, 0x14D1F2, "cGin.cGin_dressShape_002.ls"); 
 read_object(file, 0x15372E, "cGin.cGin_dressShape_006.ls"); 
 read_object(file, 0x157E88, "cGin.cGin_hairShape_008.ls"); 
 read_object(file, 0x160522, "cGin.cGin_hairShape_009.ls");
 read_object(file, 0x1618F2, "cGin.cGin_blouseShape_005.ls");
 read_object(file, 0x161F84, "cGin.cGin_blouseShape_001.ls");
 read_object(file, 0x16B896, "cGin.cGin_legShape_010.ls");
 read_object(file, 0x170BFA, "cGin.cGin_legShape_011.ls");
 read_object(file, 0x173BB0, "cGin.cGin_legRozeShape_005.ls");

 // read_object(file, 0x2BFE08); // cKun.c_KUN_bodyShape_001

 file.close();

 return 0;
}


```

[gin.jpg](https://xentaxbackup.github.io/file/4516_gin.jpg)
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-19T23:39:04+00:00
- Post Title: AliBat

Yes, there is a cute fire-breathing dog
## Post #12
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-07-20T01:23:10+00:00
- Post Title: AliBat

got the archive that holds the textures in it too?
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-20T01:30:57+00:00
- Post Title: AliBat

It's pretty big, too much for my upload speed.
You might as well get the game (400 MB)
## Post #14
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-07-20T01:33:01+00:00
- Post Title: AliBat

ok, sure. can u save me some time and let me know what files they are in and the xor key for it?
## Post #15
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-20T01:47:53+00:00
- Post Title: AliBat

bankT01.dat, 0xFE2A5378
bankT01P.dat, 0x8756CBED
## Post #16
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-07-21T16:23:07+00:00
- Post Title: Re: AliBat

For bankT01P.dat I saw no TRUEVISION-XFILE TGA footers in there when I decrypted it. Try it with 0x12345678 instead . My  0x00000000 frequency analysis produced (in decimal):

271886706 is 0.000131181 % 0x00000000
305419896 is 0.142922 % 0x00000000
3989526151 is 0.606286 % 0x00000000

It is the second one that decrypts the file. The third one is the key that you provided. Mapped models coming soon! Thank goodness there are no DDS textures in that one.
## Post #17
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-21T16:25:55+00:00
- Post Title: Re: AliBat

That explains why the ones with P looked weird.

What did you use to get that?
## Post #18
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-07-21T16:32:47+00:00
- Post Title: Re: AliBat

With your help. Couldn't have done it without knowing it was a 4-byte xor key. The key is breaking early in the inner loop. TGA files contain a lot of 00000000's at the beginning of a file so if no 4-byte 0's occur in the first 100 dwords I exit. Took an hour to crack.

```

void main()
{
 DecryptFile(0x12345678);
}

void DecryptFile(void)
{
 cout << "Enter an input filename:" << endl;
 char filename1[64];
 cin.getline(filename1, 64);

 ifstream ifile(filename1, ios::binary);
 if(!ifile) { cout << "Could not open input file." << endl; return; }

 // get length of file
 ifile.seekg(0, ios::end);
 size_t filesize = ifile.tellg();
 ifile.seekg(0, ios::beg);

 unsigned int* buffer1 = (unsigned int*)::operator new(((filesize + 3)/4)*4);
 ifile.read((char*)buffer1, filesize);
 unsigned int n_dword = (filesize + 3)/4;
 cout << "Number of dwords = " << n_dword << endl;

 double max_percent = 0.0;
 for(unsigned int i = 0x10000000; i < UINT_MAX; i++)
    {
     unsigned int count = 0;
     for(size_t j = 0; j < n_dword; j++) {
         unsigned int result = buffer1[j] ^ i;
         if(result == 0) count++;
         if(j > 100 && count == 0) break;
        }
     double tmp_percent = (100.0*(double)count)/(double)n_dword;
     if(tmp_percent > max_percent) {
        max_percent = tmp_percent;
        cout << i << " is " << max_percent << " %" << endl;
       }
    }

 delete[] buffer1;
 buffer1 = 0;
}

```
## Post #19
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-21T17:26:46+00:00
- Post Title: Re: AliBat

Now all we need to do is figure out whether there's a way to separate the file into separate parts.
If each model is stored one after another, and you've figured out how to determine the size of a single model, then maybe we can use that information to split the data.

Like with the DDS textures, it would just be a matter of searching for the next occurrence of "DDS" or EOF and then just extract everything up to that point.

If you've decrypted the bankSHD files, does it store the directory structure?
Looking at bankSHD01, I see D8 8C B3 9A everywhere but when I used it, it didn't look like anything.
## Post #20
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-07-21T17:58:46+00:00
- Post Title: Re: AliBat

The texture file that contains only TGA files (the one with a P) was easy to extract all 52 player textures. The one that contains both TGA and DDS files is going to be harder since I need to know how big a DDS file is by looking at its header, and I don't know much about DDS files. But that's ok since all the player model textures are stored in the one with only TGA files. The following code extracts the TGAs from unencrypted bankT01P.dat file. I haven't taken a look at the other files yet.

```
#include<iomanip>
#include<fstream>
#include<string>
#include<strstream>
using namespace std;

void DecryptFile(void);
void DecryptFile(unsigned int value);
void LoadTGAFileList(void);
bool IsTGAFooter(const char* buffer, size_t index);

void main()
{
 //DecryptFile(0x12345678);
 LoadTGAFileList();
}

void DecryptFile(void)
{
 cout << "Enter an input filename:" << endl;
 char filename1[64];
 cin.getline(filename1, 64);

 ifstream ifile(filename1, ios::binary);
 if(!ifile) { cout << "Could not open input file." << endl; return; }

 // get length of file
 ifile.seekg(0, ios::end);
 size_t filesize = ifile.tellg();
 ifile.seekg(0, ios::beg);

 unsigned int* buffer1 = (unsigned int*)::operator new(((filesize + 3)/4)*4);
 ifile.read((char*)buffer1, filesize);
 unsigned int n_dword = (filesize + 3)/4;
 cout << "Number of dwords = " << n_dword << endl;

 double max_percent = 0.0;
 for(unsigned int i = 0x10000000; i < UINT_MAX; i++)
    {
     unsigned int count = 0;
     for(size_t j = 0; j < n_dword; j++) {
         unsigned int result = buffer1[j] ^ i;
         if(result == 0) count++;
         if(j > 100 && count == 0) break;
        }
     double tmp_percent = (100.0*(double)count)/(double)n_dword;
     if(tmp_percent > max_percent) {
        max_percent = tmp_percent;
        cout << i << " is " << max_percent << " %" << endl;
       }
    }

 delete[] buffer1;
 buffer1 = 0;
}

void DecryptFile(unsigned int value)
{
 cout << "Enter an input filename:" << endl;
 char filename1[64];
 cin.getline(filename1, 64);

 cout << "Enter an output filename:" << endl;
 char filename2[64];
 cin.getline(filename2, 64);

 ifstream ifile(filename1, ios::binary);
 if(!ifile) { cout << "Could not open input file." << endl; return; }

 ofstream ofile(filename2, ios::binary);
 if(!ofile) { cout << "Could not create output file." << endl; return; }

 for(;;) {
     unsigned int c1;
     ifile.read((char*)&c1, sizeof(c1));
     unsigned int c2 = c1 ^ value;
     ofile.write((char*)&c2,sizeof(c2));
     if(ifile.gcount() == 0 || ifile.bad()) break;
    }
}

void LoadTGAFileList(void)
{
 cout << "Enter an input filename:" << endl;
 char filename1[64];
 cin.getline(filename1, 64);

 ifstream ifile(filename1, ios::binary);
 if(!ifile) { cout << "Could not open input file." << endl; return; }

 // get length of file
 ifile.seekg(0, ios::end);
 size_t filesize = ifile.tellg();
 ifile.seekg(0, ios::beg);

 // read file data
 char* buffer = new char[filesize];
 ifile.read((char*)buffer, filesize);

 // read TGA files
 size_t count = 0;
 size_t p1 = 0;
 size_t p2 = 0;
 while(p2 < filesize)
      {
       if(IsTGAFooter(buffer, p2))
         {
          std::strstream sstream;
          sstream << count << ".tga" << ends;
          cout << "Saving " << sstream.str() << endl;
          ofstream ofile(sstream.str(), ios::binary);
          ofile.write((char*)(buffer + p1), p2 - p1 + 18);

          // start over
          p2 = p2 + 18;
          p1 = p2;
          count++;
         }
       else
          p2++;
      }

 delete[] buffer;
 buffer = 0;
}

bool IsTGAFooter(const char* buffer, size_t index)
{
 if(buffer[index +  0] != 0x54) return false;
 if(buffer[index +  1] != 0x52) return false;
 if(buffer[index +  2] != 0x55) return false;
 if(buffer[index +  3] != 0x45) return false;
 if(buffer[index +  4] != 0x56) return false;
 if(buffer[index +  5] != 0x49) return false;
 if(buffer[index +  6] != 0x53) return false;
 if(buffer[index +  7] != 0x49) return false;
 if(buffer[index +  8] != 0x4F) return false;
 if(buffer[index +  9] != 0x4E) return false;
 if(buffer[index + 10] != 0x2D) return false;
 if(buffer[index + 11] != 0x58) return false;
 if(buffer[index + 12] != 0x46) return false;
 if(buffer[index + 13] != 0x49) return false;
 if(buffer[index + 14] != 0x4C) return false;
 if(buffer[index + 15] != 0x45) return false;
 if(buffer[index + 16] != 0x2E) return false;
 if(buffer[index + 17] != 0x00) return false;
 return true;
}

```
## Post #21
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-21T18:02:31+00:00
- Post Title: Re: AliBat

Hopefully the directory structure is available somewhere so we don't actually have to figure out how to parse the dat files!
## Post #22
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-07-21T19:12:28+00:00
- Post Title: Re: AliBat

i probably got all the textures wrong.
[sample.jpg](https://xentaxbackup.github.io/file/4525_sample.jpg)
## Post #23
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-21T19:15:42+00:00
- Post Title: Re: AliBat

Looks right to me (granted, I don't have the game with me ATM to check whether they drew her differently)



Hair and wings might be off but maybe it's just how they did it lol
## Post #24
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-22T00:01:15+00:00
- Post Title: Re: AliBat

I'm looking through the exe with hex editor and tried running a search for the XOR keys, and there is exactly one occurrence of each of them with the ones I tested, and are quite close in proximity depending on the type of resource it is (ie: sounds)

I don't know if this is significant or not, but it won't help since it assumes I already know the key -_-

Anyways the 0x78564312 key is used 4 times for each of the *P files.

You can also see the other keys used in the other data files.



The first four correspond to the M,T, ST, and A data files.
The last four correspond to the MP, TP, STP, and AP data files.

Maybe the remaining for are the SHD's?

EDIT: lol, they are. These are in the SHD files. No directory structure..

```
//  フラグメントリンカー対応版シェーダの断片集
//==============================================================================
// 定数レジスタの割り当て=======================================================
float4x4 	projectionMatrix 	: register(c0);
float4x4 	viewMatrix 			: register(c4);
float4x4 	textureMatrix 		: register(c8);
float4 		blendWeights 		: register(c12);
float4 		diffuseColor 		: register(c13);
float4 		fadeColor 			: register(c15);
float4 		ambient 			: register(c16);
float4		lightPosition[3]	: register(c17);
float4 		lightColor[3] 		: register(c20);
float4 		boneMatrix[69] 		: register(c27);
// ブレンドステージ ============================================================
// 単一位置受け入れ-------------------------------------------------------------
void PositionBlender1(
    in float3 position: POSITION,
    out float4 blendedPosition: r_BlendedPosition
)
{
    blendedPosition = float4(position, 1);
}
vertexfragment PositionBlender1Fragment = compile_fragment vs_1_1 PositionBlender1();
// 単一法線受け入れ------------------------------------------------------------
void NormalBlender1(
    in float3 normal: NORMAL,
    out float3 blendedNormal: r_BlendedNormal
    )
{
    blendedNormal = normal;
}
vertexfragment NormalBlender1Fragment = compile_fragment vs_1_1 NormalBlender1();
// デフォームステージ ==========================================================
// 位置をビュー空間へ ----------------------------------------------------------
void PositionDefaultDeformer(
  in float4 blendedPosition :r_BlendedPosition,
  out float3 deformedPosition :r_DeformedPosition
  )
...

```


Ok so this is the batch file I used

```
xor.exe bankM01.dat bankM01_out.dat 0x2175FD9A
xor.exe bankT01.dat bankT01P_out.dat 0xFE2A5378
xor.exe bankST01.dat bankST01_out.dat 0xEA15E4A7
xor.exe bankA01.dat bankA01_out.dat 0xAE3FFAE9
xor.exe bankSHD01.dat bankSHD01_out.dat 0xE5B18EA7
xor.exe bankSHD02.dat bankSHD02_out.dat 0xC1FB39A2
xor.exe bankSHD03.dat bankSHD03_out.dat 0xAEEF76AB
xor.exe bankSHD04.dat bankSHD04_out.dat 0x92273518
xor.exe bankA01P.dat bankST01P_out.dat 0x78563412
xor.exe bankT01P.dat bankST01P_out.dat 0x78563412
xor.exe bankM01P.dat bankST01P_out.dat 0x78563412
xor.exe bankST01P.dat bankST01P_out.dat 0x78563412

```


sounds files are easy to figure out.
## Post #25
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-07-22T09:03:54+00:00
- Post Title: Re: AliBat

Yep, bankS01.dat is 0x9D2E74F3 (little endian), bankS02.dat uses 0x3F74ACE5, bank03.dat uses 0xF7C3709B and so on... others are different as well what a pain he he he. Hmmm going to have to try to figure out how to assign textures... there are references to names in the model file but the texture file is just a list of textures with no names. Wonder if filenames are encoded as a Windows Resource. Find anything else hard-coded into the EXE? In meantime I guess I'll play with getting bones hooked up.
## Post #26
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-07-24T02:22:55+00:00
- Post Title: Re: AliBat

The following below extracts 7 or 8 character models (one is same but with wings) from game with full geometry and UV maps. Textures must be applied manually still. Format is output files are lscript (LightWave).

```
#include<fstream>
using namespace std;

bool error(const char* message)
{
 cout << message << endl;
 return false;
}

bool read_object(const char* ifilename, const char* name, size_t base, const char* ofilename)
{
 ifstream file(ifilename, ios::binary);
 if(!file) return error("Failed to open file.");

 // start lscript
 ofstream ofile(ofilename);
 ofile << "main" << endl;
 ofile << "{" << endl;

 // move to base
 bool debug = false;
 cout << "object base = " << base << endl;
 file.seekg(base, ios_base::beg);

 size_t count = 0;
 bool process = true;
 while(process)
      {
       // read size of object
       unsigned int object_size;
       file.read((char*)&object_size, sizeof(object_size));
       cout << "object size = " << object_size << endl;

       // read name of object
       string object_name = "";
       for(;;) {
           char temp;
           file.read((char*)&temp, 1);
           if(temp != 0x00) object_name += temp;
           else break;
          }
       cout << "object name = " << object_name.c_str() << endl;

       // read 0x30 throw away characters
       while(file.peek() == 0x30) {
             char cx;
             file.read((char*)&cx, sizeof(cx));
            }

       // make sure we are loading the right model
       if(object_name[0] != name[0]) break;
       if(object_name[1] != name[1]) break;
       if(object_name[2] != name[2]) break;
       if(object_name[3] != name[3]) break;

       // read a 4-byte variable
       float unknown01;
       file.read((char*)&unknown01, sizeof(unknown01));
       cout << "unknown01 = " << unknown01 << endl;

       // read a 4-byte variable
       float unknown02;
       file.read((char*)&unknown02, sizeof(unknown02));
       cout << "unknown02 = " << unknown02 << endl;

       // read a 4-byte variable
       float unknown03;
       file.read((char*)&unknown03, sizeof(unknown03));
       cout << "unknown03 = " << unknown03 << endl;

       // read a 4-byte variable
       float unknown04;
       file.read((char*)&unknown04, sizeof(unknown04));
       cout << "unknown04 = " << unknown04 << endl;

       // read a 4-byte variable
       unsigned int unknown05;
       file.read((char*)&unknown05, sizeof(unknown05));
       cout << "unknown05 = " << unknown05 << endl;

       // read a 4-byte variable
       unsigned int unknown06;
       file.read((char*)&unknown06, sizeof(unknown06));
       cout << "unknown06 = " << unknown06 << endl;
       if(unknown06 != 3523) break;

       // read a 4-byte variable
       unsigned int unknown07;
       file.read((char*)&unknown07, sizeof(unknown07));
       cout << "unknown07 = " << unknown07 << endl;

       // read number of vertices
       unsigned int n_vertices;
       file.read((char*)&n_vertices, sizeof(n_vertices));
       cout << "number of vertices = " << n_vertices << endl;
 
       // read vertex buffer
       size_t vertex_size = 15*4;
       size_t vertex_buffer_size = n_vertices*vertex_size;
       float* vertex_buffer_data = (float*)::operator new(vertex_buffer_size);
       file.read((char*)vertex_buffer_data, vertex_buffer_size);

       // vertex data is followed by two 0x00000001
       unsigned int fixed1;
       file.read((char*)&fixed1, sizeof(fixed1));
       if(fixed1 != 1) return error("After vertex data, expecting 0x00000001.");
       unsigned int fixed2;
       file.read((char*)&fixed2, sizeof(fixed2));
       if(fixed2 != 1) return error("After vertex data, expecting 0x00000001.");

       // read number of indeces
       unsigned int n_indices;
       file.read((char*)&n_indices, sizeof(n_indices));
       cout << "number of indices = " << n_indices << endl;

       // read index buffer
       size_t index_size = 2;
       size_t index_buffer_size = n_indices*index_size;
       unsigned short* index_buffer = (unsigned short*)::operator new(index_buffer_size);
       file.read((char*)index_buffer, index_buffer_size);

       // set surface
       ofile << " setsurface(\"" << object_name.c_str() << "\");" << endl;

       // begin mesh edit
       ofile << " editbegin();" << endl;
       ofile << " uvmap = VMap(\"texture\", \"" << object_name.c_str() << "\", 2);" << endl;

       // save vertices
       size_t vertex_float_index = 0;
       for(size_t vertex_index = 0; vertex_index < n_vertices; vertex_index++)
          {
           // extract position
           float x = vertex_buffer_data[vertex_float_index++];
           float y = vertex_buffer_data[vertex_float_index++];
           float z = vertex_buffer_data[vertex_float_index++];
           ofile << " pointlist[" << (vertex_index + 1) << "]" << " = " << "addpoint(" << x << "," << y << "," << z << ");" << endl;

           // extract other crap
           float nx = vertex_buffer_data[vertex_float_index++];
           float ny = vertex_buffer_data[vertex_float_index++];
           float nz = vertex_buffer_data[vertex_float_index++];
           float unknown_p04 = vertex_buffer_data[vertex_float_index++];
           float unknown_p05 = vertex_buffer_data[vertex_float_index++];
           float unknown_p06 = vertex_buffer_data[vertex_float_index++];
           float unknown_p07 = vertex_buffer_data[vertex_float_index++];
           float unknown_p08 = vertex_buffer_data[vertex_float_index++];
           float unknown_p09 = vertex_buffer_data[vertex_float_index++];
           float unknown_p10 = vertex_buffer_data[vertex_float_index++];
           float unknown_p11 = vertex_buffer_data[vertex_float_index++];
           float unknown_p12 = vertex_buffer_data[vertex_float_index++];
           ofile << " uvmap.setValue(pointlist[" << (vertex_index + 1) << "], @" << unknown_p11 << ", " << (1.0 - unknown_p12) << "@);" << endl;

           // display debug data
           if(debug) {
              cout << "VERTEX_INDEX[" << vertex_index << "]" << endl;
              cout << x << endl;
              cout << y << endl;
              cout << z << endl;
              cout << nx << endl;
              cout << ny << endl;
              cout << nz << endl;
              cout << unknown_p04 << endl;
              cout << unknown_p05 << endl;
              cout << unknown_p06 << endl;
              cout << unknown_p07 << endl;
              cout << unknown_p08 << endl;
              cout << unknown_p09 << endl;
              cout << unknown_p10 << endl;
              cout << unknown_p11 << endl;
              cout << unknown_p12 << endl;
              cout << endl;
             }
          }

       // save triangle strip
       size_t tristrip_index = 0;
       if(debug) cout << index_buffer[tristrip_index] << endl;
       unsigned short i0 = index_buffer[tristrip_index + 0] + 1;
       unsigned short i1 = index_buffer[tristrip_index + 1] + 1;
       unsigned short i2 = index_buffer[tristrip_index + 2] + 1;
       ofile << " addtriangle(pointlist[" << i0 << "], pointlist[" << i1 << "], pointlist[" << i2 << "]);" << endl;

       for(tristrip_index = 1; tristrip_index < n_indices - 2; tristrip_index++) {
           if(debug) cout << index_buffer[tristrip_index] << endl;
           unsigned short i0 = index_buffer[tristrip_index + 0] + 1;
           unsigned short i1 = index_buffer[tristrip_index + 1] + 1;
           unsigned short i2 = index_buffer[tristrip_index + 2] + 1;
           if(tristrip_index % 2) ofile << " addtriangle(pointlist[" << i0 << "], pointlist[" << i2 << "], pointlist[" << i1 << "]);" << endl;
           else ofile << " addtriangle(pointlist[" << i0 << "], pointlist[" << i1 << "], pointlist[" << i2 << "]);" << endl;
          }

       // end mesh edit
       ofile << " editend();" << endl;

       // read a 4-byte variable
       unsigned int unknown08;
       file.read((char*)&unknown08, sizeof(unknown08));
       cout << "unknown08 = " << unknown08 << endl;
       if(unknown08 != 0) return error("Expecting terminiating 0.");

       // read a 4-byte variable
       unsigned int unknown09;
       file.read((char*)&unknown09, sizeof(unknown09));
       cout << "unknown09 = " << unknown09 << endl;
       if(unknown09 != 3) return error("Expecting terminiating 3.");

       // read a 4-byte variable
       unsigned int unknown10;
       file.read((char*)&unknown10, sizeof(unknown10));
       cout << "unknown10 = " << unknown10 << endl;
       //if(unknown10 != 0) return error("Expecting terminiating 0.");
      }

 // delete non-planar polygons and merge vertices
 ofile << " selmode(USER);" << endl;
 ofile << " selpolygon(SET, NONPLANAR);" << endl;
 ofile << " delete();" << endl;
 ofile << " mergepoints();" << endl;

 // end lscript
 ofile << "}" << endl;

 return true;
}

int main(void)
{
 read_object("bankM01_out.dat", "cBar.", 0x003650, "cBar.ls");
 read_object("bankM01_out.dat", "cGin.", 0x1314D8, "cGin.ls");
 read_object("bankM01_out.dat", "cKan.", 0x2843B8, "cKan.ls");
 read_object("bankM01_out.dat", "cKun.", 0x2BFE08, "cKun.ls");
 read_object("bankM01_out.dat", "cShi.", 0x2EF9C0, "cShi.ls");
 read_object("bankM01_out.dat", "cSui.", 0x3D11A8, "cSui.ls");

 read_object("bankM01P_out.dat", "cKir.", 0x0755D8, "cKir.ls");
 read_object("bankM01P_out.dat", "cGin.", 0x18486E, "cGin2.ls");
 read_object("bankM01P_out.dat", "cShi.", 0x1CE528, "cShi2.ls");

 return 0;
}


```
## Post #27
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-24T03:03:59+00:00
- Post Title: Re: AliBat

Since you noted the first integer represents the size of the model, I can probably just write a quickbms script with that o.O

```
#quickbms script
#abmdl stands for AliBat model 

get unk long
do
	savepos start
	get size long
	getdstring name 70 #just some really big number since it's null-terminated anyways
	string name += ".abmdl"
	goto start
	log name start size
	math start += size
	goto start
while start != 0x68E698

```


If you look at the output, some of the files are clearly part of the same model (re: the bones).
I just took the size of the object and wrote out that many bytes. I don't know how the data is grouped though.
## Post #28
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-07-24T08:00:02+00:00
- Post Title: Re: AliBat

Yes, the data is grouped, with bones first then stuff about materials, then more bone stuff, then mesh shapes etc. All character models seem to have unknown06 of 0x0DC3 and 4-letter names like cKun. Other models have different numbers (general meshes have an unknown06 of 0x0813), different object formats, and different naming conventions, so I guess I should load the entire object into memory and check these things and then from there parse it...

Also forgot cHin in my previous post:

read_object("bankM01_out.dat", "cHin.", 0x1C1314, "cHin.ls");
## Post #29
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-07-24T10:36:18+00:00
- Post Title: Re: AliBat

Got it to load a level I think... dunno... not sure since I really don't play games. Weird how they modeled a reflection directly using duplicate geometry.
[level.jpg](https://xentaxbackup.github.io/file/4533_level.jpg)
## Post #30
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-24T16:08:23+00:00
- Post Title: Re: AliBat

Since all characters start with a 4-letter character code and all of the related objects are grouped together, we can check the first 4 letters to verify that it is the same model.

Since characters have the same unk6 value, we can check that first before deciding whether to log the file or continue checking ahead.

That should reduce the number of files to work with to about half or a third.

The filenames for the non-character objects have variable length "prefixes" so that may be hard to work with.
If there was another value that I could use to determine which object it belongs to that would be convenient.

Then rather than having to hardcode offsets you can just parse a file normally
## Post #31
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-24T17:57:57+00:00
- Post Title: Re: AliBat

I've found a pattern with the filenames for non-character objects.

Suppose we have some object name with base-name OBJECT
Any objects that are related to it, will begin with the substring OBJECT, followed by some other characters.

The object is done when the next string has a different base-name.

Character objects have a . following the 4-character name, so one could possibly check whether the dot exists and then go from there.
