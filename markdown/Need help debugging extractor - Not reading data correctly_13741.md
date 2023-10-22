## Post #1
- Username: UnknownToaster
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 21, 2013 9:34 am
- Post datetime: 2015-12-30T08:18:17+00:00
- Post Title: Need help debugging extractor - Not reading data correctly

Hey everyone,

I'm writing an extractor for a currently undocumented archive, it's fairly basic, but is causing some problems currently.

Here is my code:

```
{
    fileCount = binReader1.ReadInt32();

    for (int i = 0; i < fileCount; i++)
    {
        int size = binReader1.ReadInt32();
        String midValues = "" + binReader1.ReadInt64();
        int nameLength = binReader1.ReadInt32();

        String name = 
           System.Text.Encoding.Default.GetString(binReader1.ReadBytes(nameLength));

        byte[] blueprint = binReader1.ReadBytes((size) - 12 - nameLength);

        //Export blueprint for testing
        MemoryStream blueprintStream = new MemoryStream(blueprint);
        FileStream fileStream1 = new FileStream(
          "C:\\Users\\Dan\\Desktop\\blueprints\\" + i + ".blueprint", 
          FileMode.Create, FileAccess.Write);
        blueprintStream.WriteTo(fileStream1);
    }
```


The code currently can extract the DLC archive in it's entirety, but the main archive it extracts 6 files before causing issues.
The header for the archive is a 4 byte file size, two 4 byte booleans, a 4 byte integer which is the size of the following, string, then the string name.

It reads the size, which consists of the rest of the header + the file data. My program reads the size of the bytes it lists minus the bytes of header that it has already read in. This works for every file except for one that lists it's header size 12 bytes less than where it should end (but the file is read by the game, so it can't really be a bugged file, I don't think.)

Here's the problem, instead of reading to the next header, it has 12 bytes of file data that and the first 4 bytes are instead read as the next file size. I have tried a simple workaround where I read those 12 bytes, then try to use the next 4 bytes as the next file size, as would make sense. Unfortunately the value it's reading to me seems to be gibberish. It doesn't make sense for the file, from what I can tell, and I can't get it to read the values it should.

So to see what it was reading, I made it read 5 sets of 4 byte values, they match up with the header of the file after what it's supposed to be reading.
I can't make any sense of it, there's probably an obvious mistake somewhere but I'm not catching it.

Here is the set of 5 integers as well as a picture of this section of the archive (I can not distribute it, as it's copyrighted material):

```
0
1
16
1819568468

```


Bright Green: 4 Byte File Size Light Green: 2 4 Byte Booleans Bright Blue: 4 Byte String Size Light Pink: String Name Red: The Byte being read instead of the file count.

Thanks everyone, I really appreciate the help.
If you need more information, or would like me to do a set of tests, let me know.
I would gladly provide what possible to potentially help find whats wrong.

Thanks again!


Edit: I have edited the code so that it adjusts the file count to add 12 bytes if it's the 6th file, which is an unfortunately silly workaround until I understand why the size is 12 bytes short, but despite what the program was reading to me in the tests, it is reading the correct bytes with this change. 

I don't know what caused the garbage results, as well as it skipping an entire file and reading the header after the one I wanted, but the code actually is extracting and reading the headers correctly as of currently. So thanks anyways to everyone who read this. I really appreciate the people this community has to offer, luckily I was able to find a solution before bothering anyone with my programming issues.
