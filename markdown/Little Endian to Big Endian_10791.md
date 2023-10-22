## Post #1
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2013-09-21T02:32:32+00:00
- Post Title: Little Endian to Big Endian

Hi, was wondering if its possible to convert a hole file to Big Endian, I have been trying for hours, even tried C++ (made my head hurt) but to no avail.

I tried hacking up the DDS endian swapper but that dint work, it seemed to be in a loop.

Basically I have a 1.00mb file the first 4 bytes are big endian the next 1048612 bytes are little endian, these are 32 bit unsigned long.

I can do it manually but I was making a script to do it & failing.

I'm not even sure its possible to do.

any help would be very much appreciated.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-09-21T12:20:42+00:00
- Post Title: Little Endian to Big Endian

you can try the -E option of quickbms that was added just for this job.

use the following script:

```
math OFFSET = 4
math SIZE -= OFFSET
goto OFFSET
math SIZE /= 4
for i = 0 < SIZE
    get TMP long
next i
```

and then launch it with the following command:

```
quickbms -w -E script.bms your_file.dds
```

the changes will be applied directly to the input file
## Post #3
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2013-09-21T17:06:34+00:00
- Post Title: Little Endian to Big Endian

Thank you will that a try, I tried the -w -e but it would change anything, the the script I had made. .

Will let you know how it does.

Works thank you  it doesn't work if you add an output file, this is here I was going wrong.
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-09-27T06:12:19+00:00
- Post Title: Little Endian to Big Endian

if you still want to do it in C++. this is my code.

```
** BYTE ORDER FUNCTIONS
*/
#ifndef RC_INVOKED

template<class T>
inline void reverse_byte_order(T* data)
{
 unsigned char* ptr = reinterpret_cast<unsigned char*>(data);
 std::reverse(ptr, ptr + sizeof(T)); 
}

template<class T>
inline void reverse_byte_order(T* data, size_t elem)
{
 for(size_t i = 0; i < elem; i++) {
     unsigned char* ptr = reinterpret_cast<unsigned char*>(&data[i]);
     std::reverse(ptr, ptr + sizeof(T));
    }
}

#endif

```


usage

```
 boost::shared_array<char> data; // load the file data into here
 size_t filesize; // load the file size into here

 reverse_byte_order(reinterpret_cast<unsigned short*>(data.get()), filesize/sizeof(unsigned short)); // two-byte swap
 reverse_byte_order(reinterpret_cast<unsigned*>(data.get()), filesize/sizeof(unsigned)); // four-byte swap

```


pretty useful in converting DDS textures that need to be byte-swapped.
## Post #5
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2013-10-08T03:58:30+00:00
- Post Title: Little Endian to Big Endian

Or use [http://msdn.microsoft.com/en-us/library/a3140177.aspx](http://msdn.microsoft.com/en-us/library/a3140177.aspx) which results in far less instructions per swap.
## Post #6
- Username: Malvineous
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 16, 2010 12:34 pm
- Post datetime: 2013-10-11T12:31:44+00:00
- Post Title: Little Endian to Big Endian

I have a [C++ utility header](https://github.com/Malvineous/libgamecommon/blob/master/include/camoto/byteorder.hpp) that can also do this.

```
int val = be16toh(1234); // be16toh = big-endian 16-bit to host

std::fstream file("test.dat");
uint16_t value;
file >> u16be(value); // read 16-bit big-endian value from file stream

```
## Post #7
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2014-03-13T13:39:28+00:00
- Post Title: Little Endian to Big Endian

010 Editor

Tools > Hex Operations > Swap
