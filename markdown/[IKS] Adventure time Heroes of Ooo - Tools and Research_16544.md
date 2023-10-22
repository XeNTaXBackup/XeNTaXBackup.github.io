## Post #1
- Username: Acewell
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2017-07-15T16:31:16+00:00
- Post Title: [IKS] Adventure time: Heroes of Ooo - Tools and Research

BIN text file format:

```
4 bytes - number of strings

\\DATA
number of strings * 
{
	2 bytes - length of the string
	x bytes - string
}
```


BIN graphics file format:

```
4 bytes - size of the image

\\DATA
x bytes - image data
```


CF font file format:

```
2 bytes - MAGIC
4 bytes - PNG size
2 bytes - size of the character array

//CHARACTERS
x bytes - character array
1 byte - '\x00'

//CHAR DATA
1 byte - ???
2 bytes - x position
2 bytes - y position
1 byte - width
1 byte - height

//PNG
1 byte - '\x00'
2 bytes - size of the PNG
x bytes - PNG image data
```


Tools usage:
Adventure time: Heroes of Ooo BIN tool
Usage: <my_tool.py> file.bin 
           <my_tool.py> --write file.bin
           <my_tool.py> --help          

Adventure Time Heroes Font Tool
Usage: <my_tool.py> file.cf
           <my_tool.py> --write file.cf
           <my_tool.py> --help          


Tools download:


 Adventure_Time_Heroes_Tools_1.zip
(3.39 KiB) Downloaded 31 times
