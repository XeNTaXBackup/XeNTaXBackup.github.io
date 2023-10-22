## Post #1
- Username: Tural
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 28, 2006 3:03 pm
- Post datetime: 2006-11-28T07:20:41+00:00
- Post Title: Sneak King / Big Bumpin' / PocketBike Racer

I'm looking for someone who would be able to get models and BSPs, as well as textures from a few games. Games are all developed by the same company, and use the same format of archive for each. The company isn't a big one, and I highly doubt there's some massive encryption on the meshes and textures. It shouldn't be too hard to do. Each level of the game has two files, a .xbp and a .xen. This is because the discs each have two games on them, one for Xbox 360 and one for the original Xbox.

Having problems adding attachments, the cutter makes 512kb files, but the max size is 256kb.

[http://savefile.com/files/296812](http://savefile.com/files/296812)
## Post #2
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2006-11-29T22:14:50+00:00
- Post Title: Sneak King / Big Bumpin' / PocketBike Racer

LOL. I have Sneak King. I have some of the stuff worked out for reading the archive.

XBP - Xbox 1
XEN - Xbox360 

The formats are nearly the same. I only have XBP and lost the High Def movies running on the xbox just to keep it smaller for testing. Images are dds and there is no encryption.

Ok just quick notes for right now:

> Bytes 	- Type
>
> 4    	- file ID?
>
> 4     	- Block Size
>
> 4 	- ?
>
> 4 	- Number of files/names
>
> 4 	- Table Block Number (take block size * this number)
>
> 4 	- Block Number to Bank Name
>
> 4 	- ?
>
> 4 	- ?
>
> 4 	- Block Number to File Checker (It will issue last used block here)
>
> 4 	- ?
>
> 4 	- (Name) Block Number (take block size * this number)
>
> 4 	- name size (total bytes)
>
> 4 	- size of table (after names) (32 bytes per listing - 32 * number of files)
>
> 4 	- Always Null?
>
> 4 	- Always 126?
>
> 
>
> 
>
> Table
>
> Bytes 	- Type
>
> 4	- Offset Block Number
>
> 4 	- Hash/ID of filename?
>
> 4	- File Size
>
> 4	- Offset in Names Bank to file name
>
> 4	- File Type in Bank Name?
>
> 4	- ?
>
> 4	- Some type of ID based on certain files?
>
> 4	- Type?

All remaining blocks will need padded and that is what some of the unknowns are doing. I'll finish and just edit again later. At the end of the file there is also a block checker to verify total blocks in file.
