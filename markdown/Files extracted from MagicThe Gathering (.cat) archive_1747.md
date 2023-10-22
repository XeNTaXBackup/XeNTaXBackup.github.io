## Post #1
- Username: rkuebert
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 25, 2006 8:14 pm
- Post datetime: 2006-02-25T12:49:11+00:00
- Post Title: Files extracted from Magic:The Gathering (.cat) archive

Hi there,

I found this forum after I stumbled over "The Definitive Guide To Exploring File Formats". A great document! Just recently, I found a Master of Magic Emulator and I just couldn't figure out how that guy had come up with information about the archives. Reading the document, I played along with the Quake 2 pak0.pak file and was able to extract an image from it with HexWorkshop! Awesome! :)

I then tried (with both GameExtractor and MultiEx-Commander) to extract files from a .cat file from Magic:The Gathering. That went well, but now I do not know what to do with the extracted files. Since M:TG can be downloaded from The Underdogs,  I think it's safe to post a [link to an extracted file](http://www.bimberstube.de/cms/uploads/File%2000424) and also [another one](http://www.bimberstube.de/cms/uploads/File%2000507) .

What I learned so far (not much, but I'm still a total newbie in this business, as I read the document just yesterday):

- In the .cat file, the file sizes range from 8k to 59k. I suppose all files are card art and should have the same image size; then they needed to be compressed, right?
- All files start with 0001 0000 9C00 0000 where 9C00 seems to be the pointer to the end of the 'header'
- After this, there comes a file name, variable length, always ending with .tif (I found no sign of a TIFF header anywhere inside)
- Then, there are some bytes which are the same in all files:
0000 0000 4602 0000 D301 0000 2001 0000 E800 0000 0900 0000 0100 0000 0000 0000                                                             

- From then on, I am kind of lost. There is always the value 0080 before some kind of - for me tabular - data starts, see the following screenshot:


I could look for more bits and pieces, but I don't think I'll come to any conclusion. If anybody here has experience with these files or can give me a hint on what to do with them, I would really be grateful.

Thanks a lot!

Roland
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-02-26T16:40:40+00:00
- Post Title: Files extracted from Magic:The Gathering (.cat) archive

I'll take a look.
