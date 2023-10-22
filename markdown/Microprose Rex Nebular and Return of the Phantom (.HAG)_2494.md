## Post #1
- Username: mmoreira
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 03, 2007 2:17 am
- Post datetime: 2007-03-03T22:59:08+00:00
- Post Title: Microprose Rex Nebular and Return of the Phantom (.HAG)

Hello people

Im  researching some files formats with the objective of translate some adventure games to the brazilian-portuguese language. So, here I am with another question.   

I am looking for a way to extract subtitle texts from the games Rex Nebular, Return of the Phantom and dragonsphere, translate it to brazilian-portuguese and reinsert the translated text back.

After many research, the only information i found was this one.

The MicroProse HAG file format v1.0
-------------------------------------
(c) 1999 by John Doe
for comments or critics send e-mail to [john_doe@talknet.de](mailto:john_doe@talknet.de)
------------------------------------------------------------

At first, there's a 16 byte long null-terminated string which indicates
a HAG file. After that, there's a word value giving the number of files stored in the
archive.
The next record is repeated for each file entry:

size		description
--------------------------------------------
4 bytes		file offset
4 bytes		file size
14 bytes	filename


But i think this information is wrong or not complete because i tried to write a vb6 application to extract the files but it did not worked. 

If someone wants to look, i uploaded a .hag file to my website, the link is below.

[http://www.consultores.srv.br/hagsample.rar](http://www.consultores.srv.br/hagsample.rar)   (1.55 mb)

I hope anyone can help me to figure out how work with this file. Thank you all!
## Post #2
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-03-06T12:01:00+00:00
- Post Title: Microprose Rex Nebular and Return of the Phantom (.HAG)

You should probably take another look at your program and see what exactly goes wrong during extraction. After taking a quick look at the files, I am pretty sure that the description you found is correct and applies to this format.
## Post #3
- Username: mmoreira
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 03, 2007 2:17 am
- Post datetime: 2007-03-07T00:35:51+00:00
- Post Title: Microprose Rex Nebular and Return of the Phantom (.HAG)

Hi Deniz, thank you for take a look!

Well, if you are sure the format is right, then i don't know what im doing wrong.

My problem is, the first 16 bytes looks right. The two next bytes should be the number of files, right? 

In the global.hag, the bytes 17 and 18 (filecount), the values are D2 00 (53760 files?) and i know that the file has not 53760 files.

the same thing happens with the section1.hag. The bytes 17 and 18 have the values 16 01 (5633 files?) and i also know that this number is incorrect.

Im not very good with hex, so if the file format is right, then i guess i don't know how to proper convert between Hex and Decimal.  
I will be glad if you can help me. 

Thank you!
## Post #4
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-03-07T01:25:33+00:00
- Post Title: Microprose Rex Nebular and Return of the Phantom (.HAG)

> Reply from mmoreira
>
> In the global.hag, the bytes 17 and 18 (filecount), the values are D2 00 (53760 files?) and i know that the file has not 53760 files.
Ah, I see the problem. 

On the PC platform, the bytes of a given number are usually stored in reverse order (this is called "little endian format" or sometimes "Intel format", you can read up the details [here](http://en.wikipedia.org/wiki/Endianness#Examples) if you like.)

So, when you see the two bytes of a word as D2 00 in that order, you have to interpret them as 00 D2, making the value a more feasible 210 instead of 53760.

This also holds for larger values (i. e. the longwords which store the offset and size) -- if you see the bytes 12 34 AB CD in a file, the actual human-readable value would be based on CD AB 34 12.

I do not know VB very good, but if you have a function there for reading larger blocks of file content at once instead of byte-wise (as I assume you are doing right now), you should go this way and read 2 bytes at once into a word-sized variable. This way, the conversion is done automatically. (If you only have larger data types at hand, such as usual integers, set the variable to zero before reading. Otherwise, you will get strange results.)
## Post #5
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-03-07T07:17:10+00:00
- Post Title: Microprose Rex Nebular and Return of the Phantom (.HAG)

You can try my really old extractor from [http://gamefileformats.netfirms.com/fil ... se/hag.zip](http://gamefileformats.netfirms.com/files/microprose/hag.zip)
It has a bug, though, you need to create a subdirectory called "x" in the path from where the program is called. All files will be extracted into this "x" directory and not the directory specified as parameter.

Almost all files are compressed, though.
Luckily I already made a decompression routine some time ago and figured out several of the formats.

Also there's no way to pack the files back to a HAG but since the format is simple it shouldn't be a problem. Compression is more difficult. Now iirc you're lucky and compression is only optional.
## Post #6
- Username: mmoreira
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 03, 2007 2:17 am
- Post datetime: 2007-03-07T18:25:27+00:00
- Post Title: Microprose Rex Nebular and Return of the Phantom (.HAG)

Thanks Deniz Oezmen! With your explanation it worked as it should! I appreciated.

John_doe, thank you so much for the info and for the extractor! It worked all right.

Well, im interested in translating the game to portuguese, so im looking for the table strings and the font image. After some investigation i think the file that contain the strings in the game is the MESSAGES.DAT inside the global.hag, but this file is compressed. I also guess that the file that contains the text font is the FONTCONV.FF/FONTINTR.FF/etc, and i think it will need to be altered to support latin chars like é, ç, ó, ã. But i have no idea how to alter this file.

John_doe, on your previous message you told that you have made a decompression routine some time ago and figured out several of the formats. Can you share this routine or application so i can try to translate the game?

to finish, you said that "Now iirc you're lucky and compression is only optional." what this means? that i can recreate the .hag file without compress and it will work?

Thanks you guys for all the help. As soon as i can finish this translation tool for microprose games i will post the executable and sources here, so anyone interested will can use it (maybe i will try to make a multiex plugin, but i still not sure about the best way to do this). I will also not forget all the help im getting here. Thanks again, i really appreciated!
## Post #7
- Username: Matsy
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Aug 21, 2006 3:12 pm
- Post datetime: 2007-03-11T06:41:47+00:00
- Post Title: Microprose Rex Nebular and Return of the Phantom (.HAG)

```
        Dim FileName(14) As Char
        Dim Reader As New IO.BinaryReader(New IO.FileStream("FilePathHere", IO.FileMode.Open))
        Dim StartChars(16) As Char
        Reader.Read(StartChars, 0, 16)
        Dim FC As Int16 = Reader.ReadInt16
        For I = 0 To FC - 1
            Dim Offset As Int32 = Reader.ReadInt32
            Dim Size As Int32 = Reader.ReadInt32
            Reader.Read(FileName, 0, 14)
            Dim NextOffset As Integer = Reader.BaseStream.Position
            Dim Writer As New IO.BinaryWriter(New IO.FileStream("ExtractedFileFolderHere" & I & ".extracted", IO.FileMode.Create))
            Reader.BaseStream.Seek(Offset, IO.SeekOrigin.Begin)
            Dim FileData(Size) As Byte
            Reader.Read(FileData, 0, Size)
            Writer.Write(FileData)
            Reader.BaseStream.Seek(NextOffset, IO.SeekOrigin.Begin)
            Writer.Flush()
            Reader.BaseStream.Flush()
        Next

```


Works for me?. (This is only the extraction part, I don't know anything about the compression)
## Post #8
- Username: mmoreira
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 03, 2007 2:17 am
- Post datetime: 2007-03-14T15:34:01+00:00
- Post Title: Microprose Rex Nebular and Return of the Phantom (.HAG)

Thanks Matsy! Your code works all right.  The john_doe extractor also works very fine. 
Now i have to figure out how to decompress the files, translate it and regenerate the .HAG files back.

I hope john_doe or anyone else can help me out!
## Post #9
- Username: mmoreira
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 03, 2007 2:17 am
- Post datetime: 2011-05-17T14:54:35+00:00
- Post Title: Microprose Rex Nebular and Return of the Phantom (.HAG)

Hi folks.

Hi john_doe, are you still around? 4 years ago you told me that you have figured out how to decompress the microprose adventures files, and also figured most of the file formats too. 

Did you have any tool or documentation you can share with me? I would like to make a tool that allows the games to be translated to other languages. If you can share the technical information and/or any code you have, it will be great!

The last years I studied more. I still not good at deciphering formats by myself, but at least now I can build my own tools based only on algorithms and file specifications. And most of the time, I can build my own encoders / packers based only on decoders/unpackers. I know it´s not much, but I'm happy with myself for be able to do this. 

I hope you still around and can share some information. Thank you!
## Post #10
- Username: mmoreira
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 03, 2007 2:17 am
- Post datetime: 2011-05-19T17:17:32+00:00
- Post Title: Microprose Rex Nebular and Return of the Phantom (.HAG)

Hi kinah00, the description I found and that Deniz Oezmen mention is only about how to extract the files contained in the .HAG file.

The files john_doe mention when he says: "Almost all files are compressed, though.
Luckily I already made a decompression routine some time ago and figured out several of the formats. "  are relative to the files contained inside the .HAG. 
And it is information about these files that I'm asking about. How can I unpack and convert images and text from the game? 
What is the structure of the contained files, so can write a tool to proper alter it, inserting my translations?

See ya.
