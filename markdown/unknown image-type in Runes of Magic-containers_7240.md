## Post #1
- Username: Keili
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 26, 2011 2:14 pm
- Post datetime: 2011-08-26T08:49:49+00:00
- Post Title: unknown image-type in Runes of Magic-containers

Hello, 

as this is my first post, let me write a short introduction. In my spare time i'm working on the german fan-site [RoM-Welten](http://rom.onlinewelten.com), where you can find guides and informations about Runes of Magic. Important for us is, that we can use the game-data, which can easily be extracted with the FDB-Extractor from the *.fdb (containers for data- and image-files). Since some months there's a growing number of files, that can't be extracted. 

Normally the files are stored in blocks of compressed (probably zlib, but that's not important here) data. The FDB-Extractor unpacks the file and adds a header, which works fine for .dds, .png, .ros and .tga. But the program isn't supported anymore. 

I can add some information about the "blocks" inside of the fdb-containers:

Byte 0-3: block-size
Byte 12-15: uncompressed file-size
Byte 16-19: another size (size of data ?)
Byte 20-27: time and date
Byte 28-31: length of filename
Byte 32-(32+length+1): filename
following 16 bytes: unknown
After that starts the data. There's another size 12 bytes before the block ends. 

You can find some examples of working and (more important) of not working blocks in the attachment.

example1: an uncompressed block with header, if you delete the first bytes including the filename, you'll get example1.jpg
example1.jpg: IrfanView can open the file and suggests .jpg
example2: somehow similar to example1, but it doesn't work 
example3: like example2, but smaller
example4.dds: example3 should show the same image, maybe in another format than dds
example5: compressed block of example5.dds
example6: probably shows the same as example5.dds but looks different to example2 and 3

I would be very thankfull, if you can help me with example2, 3 and 6. You can [download the examples](http://rom.onlinewelten.com/uploads/9-Sonstiges/Umfragen/examples.zip) from RoM-Welten, as the archived is 8 kB to big to upload it here   .

Greetings from
Keili and the RoM-Welten Team
## Post #2
- Username: Keili
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 26, 2011 2:14 pm
- Post datetime: 2011-09-09T10:37:26+00:00
- Post Title: unknown image-type in Runes of Magic-containers

In the meantime i could solve the problems with example2 and 3. They actually contain compressed data, that 7Zip can handle. 

I want to thank everyone, who spent some time with my problems . Maybe someone can help me with example6.
## Post #3
- Username: qbasic
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Mar 17, 2012 4:49 am
- Post datetime: 2012-03-16T21:00:36+00:00
- Post Title: unknown image-type in Runes of Magic-containers

Did you checked [this](http://wiki.xentax.com/index.php?title=Runes_of_Magic)?

Seems, you have a troubles with decompressing data.
