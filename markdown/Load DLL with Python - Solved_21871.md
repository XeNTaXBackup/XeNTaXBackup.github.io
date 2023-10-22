## Post #1
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-03-12T22:48:29+00:00
- Post Title: Load DLL with Python - Solved

Hi,

I am currently researching .gr2 format and want to import granny2.dll in order to decompress the files, but i am having issues with implementing it python since every example i have managed to find was written in c++.
any help would be very much appreciated

for loading the DLL i tried 2 approaches using ctypes:
first:

```
MyFunctionObject = MyDllObject._GrannyDecompressData@32
```
 
but this is an instant fail since it reads the function name up to "@" and stops so it never finds the wanted function
second:

```
func = lib['_GrannyDecompressData@32']
value = func(section.compression,0,section.data_size,ComperesedData,section.first16bit,section.first8bit,section.decompressed_size,DecompressedData)
```

it does seem to find the function, but i am un-share how to send the parameters needed for the decompression, since i keep getting errors no matter what combo i try. 


Thanks in advance
## Post #2
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-03-13T14:50:37+00:00
- Post Title: Load DLL with Python - Solved

I got it working it seems the syntax for my second try was actually correct the problem was with the parameters i was sending didn't fit what the function was expecting to receive, ill just note for anyone who might wonder here in the future  if your sending a bytes object/bytesarray  make sure its the correct size or program will crash with a debug error.
