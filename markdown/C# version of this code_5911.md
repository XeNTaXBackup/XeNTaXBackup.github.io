## Post #1
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-01-25T16:35:57+00:00
- Post Title: C# version of this code

I'm trying to make my own tool about .lng files, but I need the C# code.

```
//                                                                                            //
//                                      GAME TRANSLATOR                                       //
//                            Game Language Translation Assistant                             //
//                                 http://www.watto.org/trans                                 //
//                                                                                            //
//                           Copyright (C) 2006-2009  WATTO Studios                           //
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
import org.watto.Settings;
import org.watto.component.WSProgressDialog;
import org.watto.component.WSTableColumn;
import org.watto.manipulator.FileManipulator;

import java.io.File;

/**
**********************************************************************************************

**********************************************************************************************
**/
public class Plugin_ColinMcRaeDiRT extends ArchivePlugin {


/**
**********************************************************************************************

**********************************************************************************************
**/
  public Plugin_ColinMcRaeDiRT() {

    super("ColinMcRaeDiRT","ColinMcRaeDiRT");

    //           read write replace
    setProperties(true,false,true);
    setAllowsUnicode(false);

    setGames("Colin McRae DiRT");
    setExtensions("lng");
    setPlatforms("PC");

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


      // 4 - Header (LGNT)
      if (fm.readString(4).equals("LGNT")){
        rating += 50;
        }

      // 4 - File Length
      if (fm.readIntB() == fm.length()){
        rating += 5;
        }

      return rating;

      }
    catch (Throwable t){
      return 0;
      }
    }


/**
**********************************************************************************************

**********************************************************************************************
**/
  public Resource[] read(File path) {
    try {

      // RESETTING THE GLOBAL VARIABLES
      setDefaultProperties(true);

      FileManipulator fm = new FileManipulator(path,"r");
      long arcSize = fm.getLength();


      // 4 - Header (LGNT)
      // 4 - File Length

      // 4 - Header (HSHS)
      fm.skip(12);

      // 4 - Length of Header Section (12)
      int headerSectionLength = fm.readIntB();
      check.length(headerSectionLength,arcSize);
      fm.skip(headerSectionLength + 4);

      // 4 - Header (HSHT)
      // 4 - Length of Header Table
      int headerTableLength = fm.readIntB();
      check.length(headerTableLength,arcSize);
      fm.skip(headerTableLength + 8);

      // 4 - Header (SIDA)
      // 4 - Directory Length

      // 4 - Number Of Entries
      int numFiles = fm.readIntB();
      check.numFiles(numFiles);


      int[] codeOffsets = new int[numFiles];
      int[] valueOffsets = new int[numFiles];
      for (int i=0;i<numFiles;i++){
        // 4 - Code Offset (relative to the first entry in the code directory)
        codeOffsets[i] = fm.readIntB();

        // 4 - Value Offset (relative to the first entry in the value directory)
        valueOffsets[i] = fm.readIntB();
        }


      // 4 - Header (SIDB)
      fm.skip(4);

      // 4 - Directory Length
      long nextDirOffset = fm.getFilePointer() + 4 + fm.readIntB();

      long relOffset = fm.getFilePointer();



      Resource[] resources = new Resource[numFiles];
      WSProgressDialog.setMaximum(numFiles);


      // read the resources
      String[] codes = new String[numFiles];
      for (int i=0;i<numFiles;i++){
        fm.seek(relOffset + codeOffsets[i]);

        // X - Code
        // 1 - null Code Terminator
        codes[i] = fm.readNullString();
        }


      fm.seek(nextDirOffset);

      // 4 - Header (LNGB)
      // 4 - Directory Length
      fm.skip(8);

      relOffset = fm.getFilePointer();


      for (int i=0;i<numFiles;i++){
        fm.seek(relOffset + valueOffsets[i]);

        // X - Text
        // 1 - null Text Terminator
        String original = fm.readNullString();

        //original
        resources[i] = new Resource_ColinMcRaeDiRT(original,codes[i]);
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


/**
**********************************************************************************************

**********************************************************************************************
**/
  public void write(Resource[] resources, File path) {
    try {

      FileManipulator fm = new FileManipulator(path,"rw");
      FileManipulator src = new FileManipulator(new File(Settings.getString("CurrentArchive")),"r");

      int numFiles = resources.length;
      WSProgressDialog.setMaximum(numFiles);

      // 4 - Header (LGNT)
      // 4 - File Length

      // 4 - Header (HSHS)
      fm.write(src.read(12));

      // 4 - Length of Header Section (12)
      int headerSectionLength = fm.readIntB();
      fm.writeIntB(headerSectionLength);
      fm.write(src.read(headerSectionLength));

      // 4 - Header (HSHT)
      fm.write(src.read(4));

      // 4 - Length of Header Table
      int headerTableLength = fm.readIntB();
      fm.writeIntB(headerTableLength);
      fm.write(src.read(headerTableLength));


      src.close();


      // 4 - Header (SIDA)
      fm.writeString("SIDA");

      // 4 - Directory Length
      fm.writeIntB(numFiles*8);

      // 4 - Number Of Entries
      fm.writeIntB(numFiles);


      // write the offsets directory
      int codeOffset = 0;
      int valueOffset = 0;

      for (int i=0;i<numFiles;i++){
        // 4 - Code Offset (relative to the first entry in the code directory)
        fm.writeIntB(codeOffset);

        // 4 - Value Offset (relative to the first entry in the value directory)
        fm.writeIntB(valueOffset);

        Resource text = resources[i];
        if (text instanceof Resource_ColinMcRaeDiRT){
          Resource_ColinMcRaeDiRT resource = (Resource_ColinMcRaeDiRT)text;
          codeOffset += ((Resource_ColinMcRaeDiRT)text).getCode().length() + 1;
          }
        valueOffset += text.getTranslated().length() + 1;
        }




      WSProgressDialog.setMessage(Language.get("Progress_WritingFiles"));


      // 4 - Header (SIDB)
      fm.writeString("SIDB");

      // 4 - Directory Length
      fm.writeIntB(codeOffset);


      // write the code directory
      for (int i=0;i<numFiles;i++){
        Resource text = resources[i];
        if (text instanceof Resource_ColinMcRaeDiRT){
          Resource_ColinMcRaeDiRT resource = (Resource_ColinMcRaeDiRT)text;
          fm.writeNullString(resource.getCode());
          }
        else {
          fm.writeByte(0);
          }
        }



      // 4 - Header (LNGB)
      fm.writeString("LNGB");

      // 4 - Directory Length
      fm.writeIntB(valueOffset);


      // write the value directory
      for (int i=0;i<numFiles;i++){
        fm.writeNullString(resources[i].getTranslated());
        WSProgressDialog.setValue(i);
        }


      fm.close();

      }
    catch (Throwable t){
      logError(t);
      }
    }


/**
**********************************************************************************************
Gets a blank resource of this type, for use when adding resources
**********************************************************************************************
**/
public Resource getBlankResource(){
  return new Resource_ColinMcRaeDiRT();
  }


/**
**********************************************************************************************
Gets all the columns
**********************************************************************************************
**/
  public WSTableColumn[] getColumns() {
    WSTableColumn[] baseColumns = super.getColumns();
    int numColumns = baseColumns.length;

    // copy the base columns into a new array
    WSTableColumn[] columns = new WSTableColumn[numColumns+1];
    System.arraycopy(baseColumns,0,columns,0,numColumns);

    // add the additional columns...

    //code,languageCode,class,editable,sortable
    columns[numColumns] = new WSTableColumn("Code",'C',String.class,true,true);

    return columns;
    }


/**
**********************************************************************************************

**********************************************************************************************
**/
  public Object getColumnValue(Resource text, char code) {
    if (text instanceof Resource_ColinMcRaeDiRT){
      Resource_ColinMcRaeDiRT resource = (Resource_ColinMcRaeDiRT)text;

      if (code == 'C'){
        return resource.getCode();
        }
      }

    return super.getColumnValue(text,code);
    }


/**
**********************************************************************************************

**********************************************************************************************
**/
  public void setColumnValue(Resource text, char code, Object value) {
    try {
      if (text instanceof Resource_ColinMcRaeDiRT){
        Resource_ColinMcRaeDiRT resource = (Resource_ColinMcRaeDiRT)text;

        if (code == 'C'){
          resource.setCode((String)value);
          return;
          }
        }
      }
    catch (Throwable t){
      }

    super.setColumnValue(text,code,value);
    }



  }

```
## Post #2
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2011-01-26T19:34:14+00:00
- Post Title: C# version of this code

It plugs into other classes and thus can't be converted by looking at that single file. It would take a lot of conversions to change that into C#. You'd basically be converting the entire base application (At least the plugin system) and then that plugin itself. Java to C# isn't hard if you just take the time to convert a file by hand. Any automated process is going to cause unforeseen problems down the road.
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2011-01-26T22:04:05+00:00
- Post Title: C# version of this code

And don't create threads like this, along the lines of "here's a lot of work, do it for me"
Asking for a tool to convert code automatically or asking how to port specific constructs is appropriate.
