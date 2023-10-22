## Post #1
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2004-09-20T16:54:02+00:00
- Post Title: Shell Shock Nam '67

Please look file
## Post #2
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2004-10-02T21:45:23+00:00
- Post Title: Shell Shock Nam '67

Mr Mouse,Mr Watto 
Please help me
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-10-05T14:09:42+00:00
- Post Title: Shell Shock Nam '67

hey,

Sorry for the lack of replies, I havn't visited the site much recently because I have been busy with other things, however I did just download the archive and will take a look whenever I can.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-10-05T14:29:59+00:00
- Post Title: Shell Shock Nam '67

Yes, and I just go back from my honeymoon with a truckload of work waiting there for me ...
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-10-06T12:02:05+00:00
- Post Title: Shell Shock Nam '67

Here is what I have got - but I can't seem to get the offsets to a point where extraction would be possible.

```
| Shell Shock Nam '67 *.dat |
+---------------------------+

4 - Header 1 (Core)
6 - Version (<1.76>)
6 - Header 2 (<Core>)
1-4 - Unknown (5)
0-3 - Padding (spaces)
1-4 - Directory length (Big) (UNSIGNED!) (+13 to find the start of file data)
0-3 - Padding (spaces)
1-4 - Number Of Files (Big) (UNSIGNED!)
0-3 - Padding (spaces)

// for each file
1-4 - Filename length
0-3 - padding (nulls OR spaces) (so the filename length is 4 bytes total
X - Filename (no null!)
0-3 - Padding (so the filename is a multiple of 4 bytes) (padded with nulls OR spaces)

X - File Data

// NOTES ON WORKING OUT THE SIZE OF EACH FIELD
// This archive format swaps between using byte(0) and byte(32) to represent null values.
// Therefore, you need to do the following to work out the size of the 4-byte fields...
// 1. Read the first byte (it will always have a value)
// 2. Read the second byte
// 3. if (byte2 != null AND byte2 != 32) then it is part of the value, else it should be treated as a null
// 4. Repeat steps 2 and 3 for the remaining 2 bytes
// This way you will build up the 4-byte value correctly. You could also do it the following way...
// 1. Read the 4 bytes
// 2. Working from the last of the 4 bytes, replace bytes with value byte(32) with value byte(0)
// 3. Stop when you reach a null, or when you reach a value != byte(32)
// This process should be applied to all the fields marked as size 1-4 (and its partner 0-3)

// NOTES ON THE FILE DATA
// There are no offsets stored, rather the user must walk through the file to find the file data offsets.
// To help, there is a rough pattern in that the 4 bytes before the data starts is the length of the data.
// Other than that, I don't know how to move between files, or how to determine the location of the size field.
// So, at this point in time, i do not know how to get the specific file

// for each file
X - Unknown
4 - File Data Size
X - File Data
```


Hope you can further this Mr Mouse, when you have time apart from married life  

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
