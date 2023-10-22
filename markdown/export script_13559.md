## Post #1
- Username: dominxw1011
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Aug 31, 2015 2:22 am
- Post datetime: 2015-11-22T06:32:17+00:00
- Post Title: export script

Hello, I wanna to export files from Legend: Hand of God and i've only got a script in java for game extactor(only to read file).
Can somebody rewrite it to bms or whatever if it's possible?

```
//                                                                                            //
//                                       GAME EXTRACTOR                                       //
//                               Extensible Game Archive Editor                               //
//                                http://www.watto.org/extract                                //
//                                                                                            //
//                           Copyright (C) 2002-2009  WATTO Studios                           //
//                                                                                            //
// This program is free software; you can redistribute it and/or modify it under the terms of //
// the GNU General Public License published by the Free Software Foundation; either version 2 //
// of the License, or (at your option) any later versions. This program is distributed in the //
// hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranties //
// of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License //
// at http://www.gnu.org for more details. For updates and information about this program, go //
// to the WATTO Studios website at http://www.watto.org or email watto@watto.org . Thanks! :) //
//                                                                                            //
////////////////////////////////////////////////////////////////////////////////////////////////

import org.watto.Language;
import org.watto.component.WSProgressDialog;
import org.watto.manipulator.FileManipulator;

import java.io.File;

/**
**********************************************************************************************

**********************************************************************************************
**/
public class Plugin_PAK_34 extends ArchivePlugin {

/**
**********************************************************************************************

**********************************************************************************************
**/
  public Plugin_PAK_34() {

    super("PAK_34","PAK_34");

    //         read write replace rename
    setProperties(true,false,false,false);

    setGames("Legend: Hand Of God");
    setExtensions("pak"); // MUST BE LOWER CASE
    setPlatforms("PC");

    //setFileTypes("","",
    //             "",""
    //             );

    }

/**
**********************************************************************************************

**********************************************************************************************
**/
  public int getMatchRating(FileManipulator fm) {
    try {

      int rating = 0;

      if (fm.getExtension().equals(extensions[0])){
        rating += 25;
        }

      getDirectoryFile(new File(fm.getPath()),"pak.dat");
      rating += 25;


      return rating;

      }
    catch (Throwable t){
      return 0;
      }
    }


/**
**********************************************************************************************
Reads an [archive] File into the Resources
**********************************************************************************************
**/
  public Resource[] read(File path) {
    try {

      // NOTE - Compressed files MUST know their DECOMPRESSED LENGTH
      //      - Uncompressed files MUST know their LENGTH

      addFileTypes();

      //ExporterPlugin exporter = Exporter_ZLib.getInstance();

      // RESETTING GLOBAL VARIABLES


      long arcSize = (int)path.length();

      File sourcePath = getDirectoryFile(path,"pak.dat");
      FileManipulator fm = new FileManipulator(sourcePath,"r");


      // 4 - Number Of Files
      int numFiles = fm.readIntL();
      check.numFiles(numFiles);


      Resource[] resources = new Resource[numFiles];
      WSProgressDialog.setMaximum(numFiles);

      // Loop through directory
      for(int i=0;i<numFiles;i++){

        // X - Filename (terminated by (byte 13,10))
        String filename = fm.readTerminatedString((byte)13);
        check.filename(filename);
        fm.skip(1);

        // 4 - File Length
        long length = fm.readIntL();
        check.length(length,arcSize);

        // 4 - File Offset
        long offset = fm.readIntL();
        check.offset(offset,arcSize);

        // 4 - Unknown
        fm.skip(4);


        //path,name,offset,length,decompLength,exporter
        resources[i] = new Resource(path,filename,offset,length);

        WSProgressDialog.setValue(i);
        }


      fm.close();

      return resources;

      }
    catch (Throwable t){
      logError(t);
      return null;
      }
    }



  }


```
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-11-22T11:20:29+00:00
- Post Title: export script

EDIT: Obsolete script, look below
## Post #3
- Username: dominxw1011
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Aug 31, 2015 2:22 am
- Post datetime: 2015-11-22T15:46:12+00:00
- Post Title: export script

after trying to extract in quickbms [http://imgur.com/It1oXvY](http://imgur.com/It1oXvY)
sample of file to unpack: [http://www.mediafire.com/download/2wjr3 ... aconda.pak](http://www.mediafire.com/download/2wjr3fok7m3vp5n/Anaconda.pak)
## Post #4
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-11-22T17:02:04+00:00
- Post Title: export script

I can't see anything extractable in that .pak file. There are no filenames or anything like that and it doesn't line up with the script's structure at all. It looks like a bunch of random bytes.
## Post #5
- Username: dominxw1011
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Aug 31, 2015 2:22 am
- Post datetime: 2015-11-22T17:48:47+00:00
- Post Title: export script

Here is pak which I'd like to extract: [http://www.mediafire.com/download/6hwnq ... /Model.pak](http://www.mediafire.com/download/6hwnqukh01mewow/Model.pak)
There are only granny2 files format in model.pak
[http://imgur.com/eZlmBRw](http://imgur.com/eZlmBRw)
## Post #6
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-11-22T19:24:15+00:00
- Post Title: export script

Is there some kind of .pak.dat file perhaps? It looks like the Model.pak contains just the model files, while another file contains all the filenames, offsets and sizes. It's a pretty common method for storing files in games.
## Post #7
- Username: dominxw1011
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Aug 31, 2015 2:22 am
- Post datetime: 2015-11-22T19:46:01+00:00
- Post Title: export script

model.pak.dat contain the all names of file but it's crypted: [http://imgur.com/9pkOEjT](http://imgur.com/9pkOEjT)
Here is model.pak.dat if that could help: [http://www.mediafire.com/download/omoap ... el.pak.dat](http://www.mediafire.com/download/omoaps9iwox0tci/Model.pak.dat)
## Post #8
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-11-22T20:15:07+00:00
- Post Title: export script

It's actually the data the script needed, and it's not encrypted - just some numbers stored in binary (I recommend using a hex editor to look through files like this).

Anyway, this script should work as long as you use the .pak file and not the .pak.dat file (keep in mind that both have to be in the same folder):

```
string NAME += ".pak.dat"

Open FDSE NAME 1

get FILES long 1

for i = 0 < FILES
	getct NAME string 0x0d 1
	get TRAIL  byte 1
	get SIZE   long 1
	get OFFSET long 1
	get DUMMY  long 1
	
	log NAME OFFSET SIZE
next i
```
## Post #9
- Username: dominxw1011
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Aug 31, 2015 2:22 am
- Post datetime: 2015-11-22T21:32:18+00:00
- Post Title: export script

most of the .gr2 file are corrupted about 200 works. 
It works well with .dds and .tga
