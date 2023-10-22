## Post #1
- Username: Thorongil
- Rank: Banned
- Number of posts: 17
- Joined date: Mon Mar 01, 2010 2:42 am
- Post datetime: 2011-04-16T20:09:42+00:00
- Post Title: Halo Wars (xbox360) sounds.pck [Found a how-to extract]

Below I've added the full message I got from someone who managed to extract all the sounds out of the sounds.pck file.
The problem is I bump into a wall every now & than its is there anyone who gets what he has written. I Shall upload the big file if you like/need it. 

SOURCE: [http://infectionist.com/forum/viewtopic ... 43cedd02e7](http://infectionist.com/forum/viewtopic.php?p=24828&sid=019f01727ea51aa7b103f243cedd02e7)

If you remember way back when, I said I'd be posting some whitepapers detailing the structures of various different file formats that I'd dissected. Well...as per my usual standard, I totally didn't do this, and also as per my usual standard, I was reminded of it months later and decided that now would be a great time to bring it back up. 

Now, keep in mind going into this that it's been quite a while since I've looked at these structures, but I'll do my best to remember the details. 

Today we're looking at a .pck file, but it's not a standard format, it's been customized for use in Halo Wars, as the sound repository. All of the sounds are indexed and stored inside this file in the Xbox-proprietary XMA format. The index is fairly easy to read, and there is a tool that can convert XMA audio files into WAV. The sounds.pck file can be found in a dump of the Halo Wars disc under this path: 

sound\wwise_material\GeneratedSoundBanks\xbox360\sounds.pck 

Starting, obviously, at the beginning of the file (I'm assuming you have it opened in a Hex Editor by now...) here's a table describing the structure of the header: 

```
----------------------------------- 
0x0    | 0x4  | Header Magic 
0x4    | 0x4  | Header Size (bytes) 
0x8    | 0x4  | Unk 
0xC    | 0x4  | Header Extra Data 
0x10   | 0x4  | Block 1 size 
0x14   | 0x4  | Block 2 size
```


The "Header Magic" is the first 4 bytes of the file, and it's the computer's first defense against a false file. If these 4 bytes aren't equal to "AKPK" then the game knows this file isn't right and bad stuff happens. Next, the header size. This is pretty self explanatory, it's the size of the header (the part from the beginning up to the content); for this file the header size should have a Big Endian int32 value of 174100. The next 4 bytes are unknown, I never figured out what they did, so I ignore them. Next is the Header Extra Data. I'm not sure why this is necessary, but it is. This number should be 52, remember it. Next is Block 1 size and Block 2 header size. Again, pretty self explanatory, the pck file is split into 2 blocks, simulating a file system. Block 1 contains a different type of structure that I call BKHD containers. These simulate folders because they group together audio files for a specific person, character, or enemy in the game. Block 2 contains the raw XMA files. Easy way to think of it is this: sounds.pck is a folder that contains audio files, that's block 2; block 1 is the subfolders that contain more audio files, but is organized by character. Block 1 should have a Big Endian int32 value of 1996, block 2 should be 172036. 

Now that we've read our structure information from the header, it's time to start reading the file information. Before getting into it, understand that each file is described in the header by what I call a file entry, so when I refer to a file entry or just an entry, you know what I mean. Each file entry in the index is 24 bytes. Your caret should be at offset 0x18 in the hex file, remember the Header Extra Data value, 52, move your cursor 52 bytes forward, to offset 0x4C. This is the start of block 1. The first 4 bytes of the block tell you how many files this block contains, for block 1 the Big Endian int32 value should be 83, meaning there are 83 files in block 1 (remember these are BKHD entries). Now we're at the start of the first file entry. Here is a table describing the entry structure: 

```
----------------------------------- 
0x0    | 0x4  | Entry ID 
0x4    | 0x4  | Entry Block Size 
0x8    | 0x4  | Unk 
0xC    | 0x4  | Entry Size 
0x10   | 0x4  | Block Start Offset 
0x14   | 0x4  | Unk
```


Entry ID is a unique number assigned to each entry, I use this as the filename since it's different for each entry. Entry Block Size will always be 2048, it's the size of a single block. A file will always take up at least 1 block, which means that even if the file itself is only 10 bytes, it will take up 2048 bytes in the pck file, everything after the 10 bytes will be padding. This is the equivalent of a sector on a hard drive. The next 4 bytes are unknown, and again I ignore them. Entry Size is the size of the actual file, regardless of the padding left over from the 2048-byte block size. Block Start Offset is where the file starts, in blocks. For the first file entry this has a Big Endian int32 value of 86, with a block size of 2048, that means that the actual file starts at 86 * 2048 = 176128. 

Now that you know the structure of the file entry, and how many files there are in that block, you can do a for loop to read each file entry and save the information. The structure of block 2 is exactly the same, and it starts at 0x4C + Block 1 size, since block 1 size is 1996, that means that block 2 starts at 0x818. Again, the first 4 bytes are the number of file entries, in this case 7168, and the structure follows the same rules as I just described. Just like last time, run a loop for the number of files (don't hard code this, it's bad practice) reading each file entry and saving the information. 

Finally, we can get to the actual file reading. This part is a bit of a pain, but it's not too difficult. Remember our offset for the first file entry in the block 1 (176128 bytes, or 0x2B000), move your caret to that position. You should see the text "BKHD" (see where I got the name from , this is the start of the first BKHD block. Simply read Entry Size bytes (which you read from the header) into a byte array and save it to a file, using Entry ID as the filename and, if you want, .bkhd as the extension. Do this for all of the BKHD files by using a loop. When you get to saving the XMA files (block 2) you'll want to do the same thing, but change the extension to .xma. These files are raw audio files that can be converted to WAV files by a tool that I will link to at the end of this post. Once again, simply perform a loop for the number of files there are in block 2 and save each one. 

Now, there's a lot of information that needs to be recorded so that you don't have to do everything in one step. My simple program reads the header and displays the information in a ListBox, then enables a button labeled "Dump" that lets me actually save the files. Instead of reading the header once to display the information, and again to save it, I created a very simple custom class to store the information about each entry: 

```
{ 
    public int entryID { get; set; } 
    public int entryBlockSize { get; set; } 
    public int entrySize { get; set; } 
    public int blockStart { get; set; } 
    public byte blockType { get; set; } 
}
```


When you're looping through the header reading the information, simply create a new pckItem object and save the information to it, example: 

```
item.entryID = ##; 
item.entryBlockSize = ##; 
item.entrySize = ##; 
etc...
```


The blockType is used to save information about which block you're reading from. You can do anything you want, but I simply put a 1 for block 1 and a 2 for block 2. This allows me to both separate the entries into groups in the listbox, and dynamically determine how and where to save the files in my dump method. 

Really this is a very simple structure, but it took me a while to figure it out. Hopefully this whitepaper helps at least one of you, I wish I'd had something like this in the (seemingly) endless hours that I spent staring at a hex editor, wondering how it worked. At any rate, it's all yours now. Here's the tool to convert XMA files into WAVs: 

ToWav  = [http://infectionist.com/misc/towav.zip](http://infectionist.com/misc/towav.zip)

It's simple to use, once you extract your XMA files, copy both the towav.exe and ConvAll.bat file into your save directory, then double click ConvAll.bat. It will convert all of the files automatically. 

And finally, a disclaimer: There are 7,168 XMA files in the pck file. Once converted to WAVs with towav, this totals 2 gigs of sound files. Make sure you have enough room on your hard drive for both the original XMAs and the converted WAVs, since they will both have to exist for a while during the conversion. 

If there's anything else you guys need, or something you don't understand, please let me know and I'll do what I can to help. 
[http://infectionist.com/forum/viewtopic ... 43cedd02e7](http://infectionist.com/forum/viewtopic.php?p=24828&sid=019f01727ea51aa7b103f243cedd02e7)
