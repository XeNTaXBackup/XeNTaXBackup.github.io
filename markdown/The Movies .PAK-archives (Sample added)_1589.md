## Post #1
- Username: hdnine
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 07, 2005 1:02 am
- Post datetime: 2005-11-12T19:47:39+00:00
- Post Title: The Movies .PAK-archives (Sample added)

It would be great to have a script / plugin that would let me peek inside the PAK-files in the game The Movies since they have very nice models and textures i wish to view and learn from.
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-11-13T02:10:22+00:00
- Post Title: The Movies .PAK-archives (Sample added)

Hi mate,

We can take a look at them if you can send us some archives.

Download one of our ArchiveCutter programs (mine is at [http://www.watto.org/extract/download/cutter.zip](http://www.watto.org/extract/download/cutter.zip) ) and run it. Select one of the *.pak archives and click the OK button. You can then send us the zip file that the program creates.

Thanks

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: hdnine
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 07, 2005 1:02 am
- Post datetime: 2005-11-13T13:27:25+00:00
- Post Title: The Movies .PAK-archives (Sample added)

Ok so here is a sample:

[http://www.wonderworks.se/online/themovies.zip](http://www.wonderworks.se/online/themovies.zip)

Hopefully this will help since i have no clue as how to make scripts / plugins? 
Thanks!
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-11-17T11:13:53+00:00
- Post Title: The Movies .PAK-archives (Sample added)

Thanks, I will look at it soon.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #5
- Username: hdnine
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 07, 2005 1:02 am
- Post datetime: 2005-11-18T21:55:15+00:00
- Post Title: The Movies .PAK-archives (Sample added)

No, thank you
## Post #6
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2005-11-21T06:23:42+00:00
- Post Title: The Movies .PAK-archives (Sample added)

If its anything like what Lionhead did with Fable. Good luck.
## Post #7
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-11-25T06:37:24+00:00
- Post Title: The Movies .PAK-archives (Sample added)

Hi again,

I have analysed the file you attached, and it should be easy enough to make a plugin for it. However, the archive has so many files in it that the Archive Cutter didn't grab the full directory for the archive. So, if you could, would you be able to run the Archive Cutter program again, and select the 2MB size please. The zip that will be created will probably be about 3MB in size so sorry about that, but its still much better than sending the entire archive 

Thanks mate.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #8
- Username: hdnine
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 07, 2005 1:02 am
- Post datetime: 2005-11-25T11:31:39+00:00
- Post Title: The Movies .PAK-archives (Sample added)

Ok thanks, the same link as above applies. There will now be a 3 MB file there instead. =)
## Post #9
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-11-26T10:17:54+00:00
- Post Title: The Movies .PAK-archives (Sample added)

Thanks mate, that should hopefully be OK now - I will test my plugin and get something released soon.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #10
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-11T01:18:46+00:00
- Post Title: The Movies .PAK-archives (Sample added)

Hi again,

I was able to add support for this game in the latest Game Extractor. There is a new update (1.5504) available on the website for users of the Full Version. If you are using the Basic Version, you can download the plugin here (or just wait a few weeks for me to upload a new Basic Version).

1. Download the attachment
2. Unzip the file into your GameExtractor/plugins directory
3. Restart Game Extractor.

If it doesn't work, unzip it into your GameExtractor/ directory and try again.

If that still doesn't work, let me know. Good luck.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)



Mr Mouse: If you want to add support for this game - here are the specs - I will post them on the wiki when I have some more time.

```
| The Movies *.pak |
+------------------+

// Uses ZLib Compression

4 - Version (5)
4 - First File Offset
4 - null
4 - Number Of Files
4 - Number Of Offset Pairs (256)
4 - Number Of Folder Names (43)
4 - Unknown (752)
12 - null
4 - File Directory Offset (52)
4 - Folder Directory Offset
4 - Folder Names Directory Offset

// FILE DIRECTORY
  // for each file
    4 - Unknown
    4 - Hash?
    4 - File Offset
    4 - Compressed File Length (including file data header fields and null padding)
    4 - Decompressed File Length
    4 - Hash?
    32 - Filename (null terminated)
    
// OFFSET PAIR DIRECTORY
  // for each offset pair
    4 - Relative Offset to Start of XXX (relative to what?)
    4 - Relative Offset to End of XXX (relative to what?)
    
// FOLDER NAMES DIRECTORY
  1 - null
  
  // for each folder name
    X - Folder Name
    1 - null Folder name Terminator
  
// FILE DATA
  // for each file
    4 - Compressed File Length (including file data header fields and null padding)
    4 - Decompressed File Length
    4 - Compressed File Length
    4 - null
    if (next 4 bytes == "zcmp"){
      // a second compression header
      4 - Compressed File Length (including file data header fields and null padding)
      4 - Decompressed File Length
      4 - Compressed File Length
      4 - null
      }
    X - File Data
    0-3 - null Padding to a multiple of 4 bytes
```

[Plugin_PAK_20.zip](https://xentaxbackup.github.io/file/486_Plugin_PAK_20.zip)
## Post #11
- Username: hdnine
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 07, 2005 1:02 am
- Post datetime: 2005-12-24T22:49:08+00:00
- Post Title: The Movies .PAK-archives (Sample added)

Ok, very nice. I'll give it a try! Thanks!
## Post #12
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-12-24T23:02:05+00:00
- Post Title: The Movies .PAK-archives (Sample added)

Hi mate,

This plugin is actually now in the Basic Version download - so you won't need to use the attachment here - just download the latest Basic Version from the website and it will be all set up ready to go.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
