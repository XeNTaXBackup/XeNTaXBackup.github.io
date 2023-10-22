## Post #1
- Username: kundalicious
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 18, 2017 11:48 pm
- Post datetime: 2017-06-18T19:39:06+00:00
- Post Title: OrbX FTX Central - Extracting DLC content

Hi everyone, 

I initially posted in the wrong thread, so I have copied it over here. Maybe the mods can delete my previous post from the Game Archive.
I'm new here and was directed to this forum by a member of the CS.RIN.RU forums.
Essentially what I am trying to do is find a way of extracting game files from a special zip file. 

======================Explanation of how the .zip file was acquired ====================================
The client: [OrbX FTX Central](https://orbxdirect.com/ftxcentral#)
This is like the steam client - however, no transactions are carried out. It lists your purchases and the files which are available for download. If you want to repo what I'm doing, get a free account, and add some freeware to your account using the link above. It should then appear on the client. 

For demonstration purposes, I will be using the [E049 Laufenselden Airfield](https://orbxdirect.com/product/eo49) Addon. 

I have tried to investigate the internal workings of the client, but issued with some compressed files has led me to this forum. 
What the client does:

When you click "Install Product," the client communicates with the official server and downloads the required files to your temporary folder => %AppData%\Local\Temp\Orbx\..\
The data is downloaded to a file with extension zip.XCDL
This .zip.XCDL file is then converted to a .zip file
Then the game data is extracted to the appropriate location
=================================================================================================

The issue I'm having is with the extraction part. I saved the .zip file from the Temp folder, but the contents of it are still encrypted. I am assuming that the client decrypts the files on the fly, when extracting the data. 

With regards to the saved .zip file, inside it, there is a file with no extension, and will not open like a traditional compressed file. [Download from here.](http://www115.zippyshare.com/v/oj9vbmEs/file.html)


I'd be grateful if anyone could take a look at it for me!
