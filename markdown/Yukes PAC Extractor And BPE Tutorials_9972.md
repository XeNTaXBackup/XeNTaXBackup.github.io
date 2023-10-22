## Post #1
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2012-12-23T22:35:35+00:00
- Post Title: Yukes PAC Extractor And BPE Tutorials

WWEGamesPACExtractor.jpg (45.64 KiB) Viewed 1105 times


This file is only allowed to be hosted at XeNTaX.com or 360Haven.com unless you give a link back.  Posting this readme unedited with the download is sufficient enough. 

Download it from XeNTaX here: 

 Yukes PAC Extractor And BPE Tutorials.rar
(1.28 MiB) Downloaded 940 times

[/size]

Here is the README file -

> WWE GAMES / YUKES PAC Extractor v1.0 by Brien L. Johnson AKA brienj, President and Owner of XHP Creations
>
> 
>
> This file is only allowed to be hosted at XeNTaX.com or 360Haven.com unless you give a link back.  Posting this readme unedited with the download is sufficient enough.  Requests to host elsewhere can be made to brienj@insightbb.com
>
> 
>
> 
>
> First of all, I want to give full credit and thanks to Luigi Auriemma for his source code to decompress Yukes BPE files.
>
> 
>
> 
>
> This program opens PAC files from the Yukes wrestling games (Xbox versions), including the WWE13 PAC files which are compressed.
>
> 
>
> 
>
> Prerequisites:
>
> 
>
> You MUST have plenty of space on your HD to extract all the files.  Expect anywhere from 4 to 5 times the size of the initial PAC file size.
>
> 
>
> 
>
> Changelog:
>
> 
>
> v1.0 - Initial Release
>
> 
>
> 
>
> To Do List:
>
> 
>
> Use some of the code from this project to make a PAC file extractor/rebuilder.
>
> 
>
> 
>
> Instructions:
>
> 
>
> Just start the program and open a PAC file, then choose the directory where you want the files extracted to.  If the program says it completed, but only extracted 0 files, check the box to force the newer EPK8 format.  The difference between the older and newer formats, is the length of the names in the header.  In the older ones, the name is 4 bytes long, in the newer ones, the name is 8 bytes long.  The only ones it can not auto-detect, are the newer PAC files with only one entry.  There have been checks put in the auto-detector to prevent trying to extract a very large file if it is read incorrectly, and then it will re-run it as the newer style.  On PAC files with only one entry though, it can't auto-detect it correctly.  It shouldn't lock-up if it reads an older PAC file as a newer one, but there is the slight possibility that it could hang, and why it always tries the old format first.  I've figured out some more info on how to detect the different formats, but haven't recoded the program with the detection, because this program will be replaced with a PAC file extractor/rebuilder in the near future, so this program is just to hold you over until that gets released, so you can start exploring what is contained in the PAC files.
>
> 
>
> 
>
> Extra Instructions:
>
> 
>
> The program will overwrite all files with the same name, so if you extract the PAC file a second time, it will overwrite the files it exracted the first time.  Since the program can extract THOUSANDS of files, it's ridiculous for it to ask if it can overwrite anything, so it does it by default.  After the files are extracted, wait until the program tells you it is completely done processing the files before you start opening files in a hex editor or whatever.  It goes through and renames files appropriately and cleans-up some left over files from the extracton process.
>
> 
>
> This comes with additional source code with comments for a "decompressBPE" program and a "YukesBPE.dll" file to use in your own programs.  For people that do not know C++ and program in .NET, I've also included a "SampleYukesBPEProgram" with source code that shows you how to use the "YukesBPE.dll" file with your .NET program.  People that program in C/C++ should not need any help, although they can use the pre-compiled "YukesBPE.dll" file if they wanted, the exports are listed in the "SampleYukesBPEProgram".
>
> 
>
> 
>
> If you need any help with this program, just go to http://www.xhpcreations.com and there are links to the XHP Creations Twitter and Facebook page where I can help if needed or post your questions in the topic for the program at XeNTaX.com or 360Haven.com.  If you like this work and feel like donating anything, my PayPal email is brienj@insightbb.com
>
> 
>
> Hope you enjoy!

The Source Code from the "decompressBPE" program -

```
#include <stdafx.h>
#include <windows.h>

// include all of the following in all target environments
// using <cstring> instead of <string> to be compatible with newer g++
#include <cstring>
#include <fstream>
#include <iostream>
#include <stdio.h>

// if this isn't included, you would have to type 'std::ifstream' instead of just 'ifstream' for example
// lazy way to do it, but it's a small program
using namespace std;

// declare constant variables
const char *MAGIC_HEADER = "BPE ";

// function prototypes
static int xgetc(unsigned char **in, unsigned char *inl);
int yukes_bpe(unsigned char *in, int insz, unsigned char *out, int outsz, int fill_outsz);

// only include for windows versions to use the function that most computer geeks that use the console HATE :)
void ClearScreen();

// program start function
int main(int argc, char* argv[])
{
	// declare and initialize the variables used in this function
	// will be used to make sure it has the 'magic' of a BPE file
	char *magic = new char[4];
	// our input buffer
	char *inbuffer;
	// our output buffer
	char *outbuffer;
	// used to calculate the compressed size
	char *readzsize = new char[4];
	// used to calculate the uncompressed size
	char *readsize = new char[4];
	// compressed size
	int zsize;
	// uncompressed size
	int size;
	// difference between size and zsize or (size - zsize)
	int fillsize;

	// make sure that there are three arguments passed to the program, which are:
	// the program name, the input file name, and the output filename
	if (argc != 3)
	{
		// comes here if there are not three arguments

		// only include this function call on Windows, to make geeks mad that you cleared out the console contents :)
		ClearScreen();

		// obligatory fancy ASCII art to show what a geek you are
		cout << "\n================================================================";
		cout << "\n+++++++++++++====   ==   ==  ====  ==       ==++++++++++++++====";
		cout << "\n==================  ==  ===  ====  ==  ====  ===================";
		cout << "\n=+++++++++++++====  ==  ===  ====  ==  ====  ==++++++++++++++===";
		cout << "\n===================    ====  ====  ==  ====  ===================";
		cout << "\n==+++++++++++++=====  =====        ==       ====++++++++++++++==";
		cout << "\n===================    ====  ====  ==  =========================";
		cout << "\n===+++++++++++++==  ==  ===  ====  ==  ==========++++++++++++++=";
		cout << "\n==================  ==  ===  ====  ==  =========================";
		cout << "\n===     =========  ====  ==  ====  ==  ===========++++++++++++++";
		cout << "\n==  ===  =======================================================";
		cout << "\n=  ================================  ===========================";
		cout << "\n=  ========  =   ====   ====   ===    ==  ===   ===  = ====   ==";
		cout << "\n=  ========    =  ==  =  ==  =  ===  =======     ==     ==  =  =";
		cout << "\n=  ========  =======     =====  ===  ===  ==  =  ==  =  ===  ===";
		cout << "\n=  ========  =======  ======    ===  ===  ==  =  ==  =  ====  ==";
		cout << "\n==  ===  ==  =======  =  ==  =  ===  ===  ==  =  ==  =  ==  =  =";
		cout << "\n===     ===  ========   ====    ===   ==  ===   ===  =  ===   ==";
		cout << "\n================================================================";

		// gives program info and usage instructions
		cout << "\n\nYukes BPE Decompress example program";
		cout << "\nby Brien L. Johnson of XHP Creations";

		// 'argv[0]' is the first argument, which is the name of the program
		cout << "\n\nUsage: " << argv[0] << " <inputfile> <outputfile>";
		cout << "\n\nWebsite: ";
		cout << "\nhttp://www.xhpcreations.com";
		cout << "\n\nSpecial thanks to Luigi Auriemmma for yuke_bpe.c source code!\n\n";

		// return any code that says it didn't complete the task, in this case we use -1 to show an error
		return -1;
	}
	else
	{
		// comes here if there are three arguments

		// open an input filestream named 'file' in binary mode with the second argument value 'argv[1]'
		ifstream file(argv[1], ios::in|ios::binary);

		// checks if the file is open
		if (file.is_open())
		{
			// make sure the starting file position is at the beginning of file
			file.seekg(0, ios::beg);

			// read the contents of the first four bytes into 'magic'
			file.read(magic, 4);

			// use a compare to make sure the first four bytes (char*) of 'magic' match our constant 'MAGIC_HEADER'			
			if (memcmp(magic, MAGIC_HEADER, 4) != 0)
			{
				// if they don't match, insult the user for opening a file that isn't a BPE file
				cout << "Open a BPE file, you numbskull!";

				// return error code
				return -1;
			}
			// continue code since they opened a BPE file

			// set the file position to the 8th byte
			file.seekg(8, ios::beg);

			// read the contents of the next four bytes into 'readzsize'
			file.read(readzsize, 4);

			// set the file position to the 12th byte
			file.seekg(12, ios::beg);

			// read the contents of the next four bytes into 'readsize'
			file.read(readsize, 4);

			// set the value of 'zsize' using the four bytes in 'readzsize'
			memcpy(&zsize, readzsize, sizeof(long));

			// set the value of 'size' using the four bytes in 'readsize'
			memcpy(&size, readsize, sizeof(long));

			// they are only four bytes in size, but we can delete 'readzsize' and 'readsize'
			// and free the HUGE amount of memory they are using :)
			delete[] readzsize;
			delete[] readsize;

			// initialize input buffer 'inbuffer' to the size of 'zsize', our compressed size
			inbuffer = new char[zsize];

			// set the file position to the 16th byte
			file.seekg(16, ios::beg);

			// read the contents of the file of 'zsize' number of bytes into the input buffer 'inbuffer'
			file.read(inbuffer, zsize);

			// calculate the fillsize
			fillsize = size - zsize;

			// the all important closing of the file
			file.close();		
		}	
		else
		{
			// if the file can't open, we of course assume they are an idiot and insult them again
			cout << "\nUnable to open " << argv[1] << " you numbskull.  Does the file exist?\n";

			// return error code
			return -1;
		}

		// initialize output buffer 'outbuffer' to the size of 'size', our uncompressed size
		outbuffer = new char[size];

		// call the function which uncompresses the input buffer to the output buffer
		// 'inbuffer' and 'outbuffer' are not unsigned, which the function requires, so we cast them correctly
		// with 'reinterpret_cast<unsigned char*>'
		int x = yukes_bpe((reinterpret_cast<unsigned char*>(inbuffer)), zsize, (reinterpret_cast<unsigned char*>(outbuffer)), size, fillsize);

		// open an output filestream named 'file2' in binary mode with the third argument value 'argv[2]'
		ofstream file2(argv[2], ios_base::out|ios_base::binary);

		// checks if the file is open
		if (file2.is_open())
		{
			// if the file opened, write the changed contents of the output buffer 'outbuffer' to disk
			file2.write(outbuffer, size);

			// let the person know the file saved correctly
			cout << "\nSuccessfully saved " << argv[2] << " to disk.\n";

			// return successful code
			return 0;
		}
		else
		{
			// let the person know that the file couldn't be saved and they were probably an idiot again
			cout << "\nCannot write " << argv[2] << " to disk, you knucklehead.  Do you have the file opened in your hex editor?\n";

			// return an error code
			return -1;
		}
	}
}

// the following two functions for Yukes BPE decompression were written by Luigi Auriemma

static int xgetc(unsigned char **in, unsigned char *inl) {
	int     ret;
	if(*in >= inl) return(-1);
	ret = **in;
	(*in)++;
	return(ret);
}

int yukes_bpe(unsigned char *in, int insz, unsigned char *out, int outsz, int fill_outsz) {
	unsigned char   stack[512 + 4096];
	int             c,
		count,
		i,
		size,
		n;

	unsigned char   *inl,
		*o,
		*outl;

	inl  = in + insz;
	o    = out;
	outl = out + outsz;

	count = 0;
	for(;;) {
		i = 0;
		do {
			if((c = xgetc(&in, inl)) < 0) break;
			if(c > 127) {
				c -= 127;
				while((c > 0) && (i < 256)) {
					stack[i * 2] = i;
					c--;
					i++;
				}
			}
			c++;
			while((c > 0) && (i < 256)) {
				if((n = xgetc(&in, inl)) < 0) break;
				stack[i * 2] = n;
				if(i != n) {
					if((n = xgetc(&in, inl)) < 0) break;
					stack[(i * 2) + 1] = n;
				}
				c--;
				i++;
			}
		} while(i < 256);

		if((n = xgetc(&in, inl)) < 0) break;
		size = n;
		if((n = xgetc(&in, inl)) < 0) break;
		size |= (n << 8);

		while(size || count) {
			if(count) {
				count--;
				n = stack[count + 512];
			} else {
				if((n = xgetc(&in, inl)) < 0) break;
				size--;
			}
			c = stack[n * 2];
			if(n == c) {
				if(o >= outl) return(-1);
				*o++ = n;
			} else {
				if((count + 512 + 2) > sizeof(stack)) return(-1);
				stack[count + 512] = stack[(n * 2) + 1];
				stack[count + 512 + 1] = c;
				count += 2;
			}
		}
	}
	if(fill_outsz) {    // this is what is wanted by the format
		memset(o, 0, outl - o);
		o = outl;
	}
	return(o - out);
}

// the dreaded ClearScreen function which clears all the contents out of the console window, and
// of course it must be included in my program :)
void ClearScreen()
{
	HANDLE                     hStdOut;
	CONSOLE_SCREEN_BUFFER_INFO csbi;
	DWORD                      count;
	DWORD                      cellCount;
	COORD                      homeCoords = { 0, 0 };

	hStdOut = GetStdHandle( STD_OUTPUT_HANDLE );
	if (hStdOut == INVALID_HANDLE_VALUE) return;

	// get the number of cells in the current buffer
	if (!GetConsoleScreenBufferInfo( hStdOut, &csbi )) return;
	cellCount = csbi.dwSize.X *csbi.dwSize.Y;

	// fill the entire buffer with spaces
	if (!FillConsoleOutputCharacter(
		hStdOut,
		(TCHAR) ' ',
		cellCount,
		homeCoords,
		&count
		)) return;

	// fill the entire buffer with the current colors and attributes
	if (!FillConsoleOutputAttribute(
		hStdOut,
		csbi.wAttributes,
		cellCount,
		homeCoords,
		&count
		)) return;

	// move the cursor home
	SetConsoleCursorPosition( hStdOut, homeCoords );
}

```


The Source Code from the "SampleYukesBPEProgram" program -

```
using System.IO;
using System.Text;
using System.Windows.Forms;
// this is needed to use DLLImport
using System.Runtime.InteropServices;

namespace SampleYukesBPEProgram
{
    public partial class Form1 : Form
    {
        // this is where we load the functions from our unmanaged dll
        [DllImport("YukesBPE.dll")]
        public static extern int yukes_bpe(byte[] input, int insz, byte[] ouput, int outsz, int fill_outsz);
        [DllImport("YukesBPE.dll")]
        public static extern int bpefile_open_save(string filename1, string filename2);

        // setup a constant string equal to the 'magic' of a BPE file
        public const string magicString = "BPE ";

        public Form1()
        {
            InitializeComponent();
        }

        // event handler for button1 being clicked
        private void button1_Click(object sender, EventArgs e)
        {
            // check that the open and save dialogs were not cancelled and the user selected some filenames
            if (openFileDialog1.ShowDialog() == DialogResult.OK && saveFileDialog1.ShowDialog() == DialogResult.OK)
            {
                // read the file into byte array 'conts'
                byte[] conts = ReadFile(openFileDialog1.FileName);

                // setup a buffer that will be used to find some values from the file
                byte[] buff = new byte[4];

                // copy first four bytes of the file to the buffer
                Array.Copy(conts, 0, buff, 0, 4);

                // checks that the four bytes are equal to the magic string "BPE "
                if (Encoding.ASCII.GetString(buff) == magicString)
                {
                    // copy four bytes from the 8th offset to our buffer
                    Array.Copy(conts, 8, buff, 0, 4);

                    // makes sure the system BitConverter is Little Endian and reverses the bytes if it isn't
                    if (!BitConverter.IsLittleEndian)
                        Array.Reverse(buff);

                    // get the value of the compressed size from the buffer
                    int zsize = BitConverter.ToInt32(buff, 0);

                    // copy four bytes from the 12th offset to our buffer
                    Array.Copy(conts, 12, buff, 0, 4);

                    // makes sure the system BitConverter is Little Endian and reverses the bytes if it isn't
                    if (!BitConverter.IsLittleEndian)
                        Array.Reverse(buff);

                    // get the value of the uncompressed size from the buffer
                    int size = BitConverter.ToInt32(buff, 0);

                    // reset the buffer to the uncompressed size, this buffer will be changed by the function in the dll
                    buff = new byte[size];

                    // compute the fillsize
                    int fillsize = size - zsize;

                    // create a new byte array to hold the remainder of the file, which is what we want to actually decompress
                    byte[] contents = new byte[zsize];

                    // copy the file contents starting at the 16th byte, where the actual BPE data is contained
                    Array.Copy(conts, 16, contents, 0, zsize);

                    // call the 'yukes_bpe' function in the dll which will change the contents of our buffer to the decompressed bytes
                    // and make sure the function returns the decompressed size, which means it finished successfully
                    if (yukes_bpe(contents, zsize, buff, size, fillsize) == size)
                    {
                        // you should always use a try block when dealing with file I/O
                        try
                        {
                            // write the buffer contents to the name the person chose in the saveFileDialog
                            WriteFile(buff, saveFileDialog1.FileName);

                            // tell them it worked
                            MessageBox.Show("Successfully saved uncompressed file " + saveFileDialog1.FileName);
                        }
                        catch
                        {
                            // it will come here if the try block failed, meaning there was a problem with the file I/O
                            MessageBox.Show("There was an error saving " + saveFileDialog1.FileName);
                        }
                    }
                    else
                    {
                        // comes here if the yukes_bpe function did not return the decompressed size
                        MessageBox.Show("There was an error decompressing " + saveFileDialog1.FileName);
                    }
                }
                else
                {
                    // displays that the file does not have the correct BPE magic if it failed the check earlier
                    MessageBox.Show("Not a BPE file!");
                }
            }
        }

        // event handler for button2 being clicked
        private void button2_Click(object sender, EventArgs e)
        {
            // check that the open and save dialogs were not cancelled and the user selected some filenames
            if (openFileDialog1.ShowDialog() == DialogResult.OK && saveFileDialog1.ShowDialog() == DialogResult.OK)
            {
                // call the 'bpefile_open_save' function in the dll and make sure it returns 0, which means it worked
                if (bpefile_open_save(openFileDialog1.FileName, saveFileDialog1.FileName) == 0)
                {
                    // if the function returns that it worked, tell the user it was successful
                    MessageBox.Show("Successfully saved uncompressed file " + saveFileDialog1.FileName);
                }
                else
                {
                    // if the function returns anything but 0, tell the user it didn't work
                    MessageBox.Show("There was an error saving " + saveFileDialog1.FileName);
                }
            }
        }

        // function to read the file contents into a byte array
        private byte[] ReadFile(string fileName)
        {
            // create a buffer
            byte[] buff = null;

            // create a FileStream 'fs' with the correct parameters
            FileStream fs = new FileStream(fileName, FileMode.Open, FileAccess.ReadWrite);

            // create a BinaryReader 'br' with 'fs'
            BinaryReader br = new BinaryReader(fs);

            // determine the length of the file, so we can set the buffer to accept it
            long numBytes = new FileInfo(fileName).Length;

            // set the buffer length to the file length
            buff = br.ReadBytes((int)numBytes);

            // close the BinaryReader and FileStream
            br.Close();
            fs.Close();

            // return the buffer contents
            return buff;
        }

        // function to write a byte array to a file
        private void WriteFile(byte[] buff, string fileName)
        {
            // this is a check to make sure the file is not a read-only file, and if it is, remove the read-only property
            System.IO.FileInfo fi = new System.IO.FileInfo(fileName);
            if (fi.IsReadOnly && File.Exists(fileName))
            {
                fi.IsReadOnly = false;
            }

            // create a FileStream 'fs' with the correct parameters
            FileStream fs = new FileStream(fileName, FileMode.Create, FileAccess.ReadWrite);

            // create a BinaryWriter 'bw' with 'fs'
            BinaryWriter bw = new BinaryWriter(fs);

            // write the buffer contents
            bw.Write(buff);

            // close the BinaryWriter and FileStream
            bw.Close();
            fs.Close();
        }
    }
}

```


Enjoy!
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-12-23T23:33:19+00:00
- Post Title: Yukes PAC Extractor And BPE Tutorials


## Post #3
- Username: OverTheEdge
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 18, 2010 4:24 am
- Post datetime: 2012-12-24T01:02:06+00:00
- Post Title: Yukes PAC Extractor And BPE Tutorials

Playing around with this now, dude. This thing is incredible. Thanks so much, brienj. Definitely looking forward to the rebuilder so I can put this thing to use.
## Post #4
- Username: nsieniski
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Sep 12, 2011 10:46 pm
- Post datetime: 2012-12-25T19:13:18+00:00
- Post Title: Yukes PAC Extractor And BPE Tutorials

whatever pac i try i get the message error : Error Parsing!

Anyone?
## Post #5
- Username: nsieniski
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Sep 12, 2011 10:46 pm
- Post datetime: 2012-12-25T19:18:57+00:00
- Post Title: Yukes PAC Extractor And BPE Tutorials

Ok, my bad, I was using a folder on my desktop
## Post #6
- Username: nsieniski
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Sep 12, 2011 10:46 pm
- Post datetime: 2012-12-25T19:32:05+00:00
- Post Title: Yukes PAC Extractor And BPE Tutorials

So we can unpack/open compressed pac files.
But it seem that we can't modify nor reinject anything.

I used the extractor on the MenuHD and got all the subfolders unpacked (cool, selection pictures 
But when I open the uncompressed MenuHD pac in Xpacker, is shows nothing.
So how can we modifiy and re-inject anything back in the pac?
## Post #7
- Username: nsieniski
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Sep 12, 2011 10:46 pm
- Post datetime: 2012-12-25T19:34:34+00:00
- Post Title: Yukes PAC Extractor And BPE Tutorials

sorry, I red again what Brienj said... the extractor/injector will come in a near futur 
For the moment we can explore the files.
Thanks Brienj!  You still got it bro!
## Post #8
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2012-12-25T22:16:22+00:00
- Post Title: Yukes PAC Extractor And BPE Tutorials

> Reply from nsieniski
>
> So we can unpack/open compressed pac files.
But it seem that we can't modify nor reinject anything.

I used the extractor on the MenuHD and got all the subfolders unpacked (cool, selection pictures 
But when I open the uncompressed MenuHD pac in Xpacker, is shows nothing.
So how can we modifiy and re-inject anything back in the pac?
And this is why I am making a PAC file extractor/rebuilder.
## Post #9
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2012-12-29T09:21:36+00:00
- Post Title: Yukes PAC Extractor And BPE Tutorials

The evolution to the next step -

[](http://www.facebook.com/photo.php?fbid=458715654164947&set=a.439192356117277.90677.323600111009836&type=1&relevant_count=1)
## Post #10
- Username: nsieniski
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Sep 12, 2011 10:46 pm
- Post datetime: 2012-12-29T16:56:28+00:00
- Post Title: Yukes PAC Extractor And BPE Tutorials

That is very impressive Brienj.
Thank you from all of us who really care about your work bro.
Can't wait!
## Post #11
- Username: dantheman9856
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 27, 2011 12:21 pm
- Post datetime: 2013-10-28T08:23:12+00:00
- Post Title: Yukes PAC Extractor And BPE Tutorials

I looked for an answer but couldn't find one...Error parsing?  No matter where I put the destination it always says this.
## Post #12
- Username: GameElite
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 01, 2014 12:13 am
- Post datetime: 2014-11-30T16:16:15+00:00
- Post Title: Yukes PAC Extractor And BPE Tutorials

Awesome thanks for this Brienji!
## Post #13
- Username: redman4356
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 27, 2019 4:10 am
- Post datetime: 2022-02-06T11:03:43+00:00
- Post Title: Yukes PAC Extractor And BPE Tutorials

ehh
am havin some trouble overhere, the program wouldn't start
I'd click on WWE PAC Extractor.exe and it just doesn't open
## Post #14
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-02-06T11:35:30+00:00
- Post Title: Yukes PAC Extractor And BPE Tutorials

> Reply from redman4356 ↑Sun Feb 06, 2022 7:03 pm at Sun Feb 06, 2022 7:03 pm
>
> 
ehh
am havin some trouble overhere, the program wouldn't start
I'd click on WWE PAC Extractor.exe and it just doesn't open

It works fine for me. 

Maybe try to run with compatibility mode
or move the EXE file to your desktop.
## Post #15
- Username: redman4356
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 27, 2019 4:10 am
- Post datetime: 2022-06-14T12:16:49+00:00
- Post Title: Yukes PAC Extractor And BPE Tutorials

uhh heyy sorry for responding so late
i tried using the compatability thing back then n it didnt work for me
anyways all i wanted to do was to extract the main menu of some wwe svr games and use it as a animated wallpaper
i found a way around it with other softwares and all and was able to get the job done
## Post #16
- Username: BinguBun
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Feb 26, 2023 1:27 pm
- Post datetime: 2023-02-26T14:23:05+00:00
- Post Title: Re: Yukes PAC Extractor And BPE Tutorials

hey how do i open this, i had the same problem and the person above me, i cant open it
