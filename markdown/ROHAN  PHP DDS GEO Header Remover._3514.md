## Post #1
- Username: ChaosPower
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 22, 2009 2:51 am
- Post datetime: 2009-05-27T20:20:21+00:00
- Post Title: ROHAN : PHP DDS GEO Header Remover.

```

/*
 * Concept DDS GEO Header Remover Source Release
 * Coming Soon PHP GEL GEM FILE EXTRACTOR
 * No License, Make this as your own
 */
 
 
$filename = "./item/07_bro_1.dds"; //file to read
$contents = file_get_contents($filename); //read as string

//echo strlen($contents); //Count no. of strings

echo substr($contents,3,strlen($contents)); //Removed GEO / DDS Header
$modS = substr($contents,3,strlen($contents)); // Same but is placed inside a variable

$file = fopen("./converted/test.tga","wb"); //Write to new name inside an exisiting folder

fwrite($file,$modS,filesize($filename)); //Write File

?>
```


Thanks to spintz for showing the source of the extractor. If your having a hard time to compile spintz's source then use this source instead.

GNU C++ compiler compatible, (Windows only, because of CreateDirectory and windows.h)

```
#include <windows.h>
#include <tchar.h>
#include <stdlib.h>
#include <stdio.h>
#include <string>

struct GELHeader
{
   int i1;
   int i2;
   int numberOfElements;
   int i4;
   int i5;
   int i6;

   void print()
   {
      //printf( "i1 = %d\n", i1 );
      //printf( "i2 = %d\n", i2 );
      printf( "numberOfElements = %d\n", numberOfElements );
      //printf( "i4 = %d\n", i4 );
      //printf( "i5 = %d\n", i5 );
      //printf( "i6 = %d\n", i6 );
      printf( "\n" );
   }
};

struct GELEntry
{
   int i1;
   int i2;
   char filename[128];
   int i3;
   int startOffset;
   int dataSize;
   int i6;

   void print()
   {
      //printf( "i1 = %d\n", i1 );
      //printf( "i2 = %d\n", i2 );
      printf( "filename = %s\n", filename );
      //printf( "i3 = %d\n", i3 );
      printf( "startOffset = %d\n", startOffset );
      printf( "dataSize = %d\n", dataSize );
      //printf( "i6 = %d\n", i6 );
      printf( "\n" );
   }
};

// Set this to the .GEL file that you want to extract
std::string srcGel = "C:\\Program Files\\Level Up Games\\Rohan Online CBT\\Client\\res\\bitmaps.gel";
// Set this to the .GEM file that matches the .GEL file you want to extract
std::string srcGem = "C:\\Program Files\\Level Up Games\\Rohan Online CBT\\Client\\res\\bitmaps.gem";
// This is the path where all the files will be extracted to
std::string destPath = "C:\\Users\\Loki\\Downloads\\Modder\\bitmaps\\";

int iiii = 0;
/*
char hextoascii(char a, char b)
{
char hex[5], *stopper;
hex[0] = '0';
hex[1] = 'x';
hex[2] = a;
hex[3] = b;
//hex[4] = '0';
return strtol(hex, &stopper, 16);

}
*/
int main()
{
   FILE* gelFP;
   gelFP = fopen(srcGel.c_str(), "rb" );

   if( gelFP )
   {
      FILE* gemFP;
      gemFP = fopen(srcGem.c_str(), "rb" );

      if( gemFP )
      {
         GELHeader gelHeader;
         fread( &gelHeader, sizeof( GELHeader ), 1, gelFP );
         //gelHeader.print();
        printf("Extracting Files: \n");
         for( int i=0; i<gelHeader.numberOfElements; i++ )
         {
            GELEntry gelEntry;
            fread( &gelEntry, sizeof( GELEntry ), 1, gelFP );
            //gelEntry.print();
            printf( "\b\b\b\b\b\b\b%d", i + 1 );

            if( gelEntry.dataSize > 0 )
            {
               // Create the file
               std::string sFilename = gelEntry.filename;
               size_t pos = sFilename.find_last_of( "\\" );

               std::string path = sFilename.substr( 0, pos + 1 );
               std::string filename = sFilename.substr( pos + 1, sFilename.length() - pos );
               //printf( "Path = %s\nFile = %s\n", path.c_str(), filename.c_str() );

               std::string newPath = destPath;
               newPath.append( path );
               CreateDirectory( newPath.c_str(), NULL );

               // Detect GTX files (DDS files with the header changed and the extension changed
               pos = filename.find_last_of( "." );
               //printf( "pos = %d\n", pos );
               std::string ext = filename.substr( pos + 1, filename.length() - pos - 1 );
               //printf( "ext = %s\n", ext.c_str() );

               if( ext.find( "gtx" ) != std::string::npos )
               {
                  //printf( "Found GTX file!\n" );
                  char* data = (char*)malloc( gelEntry.dataSize );
                  fseek( gemFP, gelEntry.startOffset, 0 );
                  fread( data, gelEntry.dataSize, 1, gemFP );
                  printf("%d",gelEntry.startOffset);
                  if( data[0] == 'G' && data[1] == 'E' && data[2] == 'O' )
                  {
                     // Most gtx files are DDS files with the "Magic Word" changed to GEO.  We change that here, before
                     // writing the file
                     filename.replace( pos + 1, 3, "tga" );
                     std::string fullPath = newPath;
                     fullPath.append( "\\" );
                     fullPath.append( filename );
                     //data[0] = hextoascii('0','0');
                     //data[1] = hextoascii('0','0');
                     //data[2] = hextoascii('0','a');
                     //data[0] = NULL;
                     //data[1] = NULL;
                     //data[2] = NULL;


                     FILE* outFP;
                     outFP = fopen(fullPath.c_str(), "wb" );
                     if( outFP )
                     {
                        fwrite( data, gelEntry.dataSize, 1, outFP );
                        fclose( outFP );
                     }
                  }
                  else if( data[0] == 'D' && data[1] == 'D' && data[2] == 'S' )
                  {
                     // Sometimes, DDS files have the proper header in them
                     filename.replace( pos + 1, 3, "dds" );
                     std::string fullPath = newPath;
                     fullPath.append( "\\" );
                     fullPath.append( filename );

                     FILE* outFP;
                     outFP = fopen(fullPath.c_str(), "wb" );
                     if( outFP )
                     {
                        fwrite( data, gelEntry.dataSize, 1, outFP );
                        fclose( outFP );
                     }
                  }
                  else
                  {

                     // Haven't come across this yet, but just in case, we'll know.
                     printf( "\n" );
                     printf( "Encountered UNKNOWN GTX file!\n" );
                     printf( "%c %c %c\n", data[0], data[1], data[2] );
                     printf( "\n" );
                  }

                  free( data );
               }
               else
               {
                  std::string fullPath = newPath;
                  fullPath.append( "\\" );
                  fullPath.append( filename );

                  FILE* outFP;
                  outFP = fopen(fullPath.c_str(), "wb" );
                  if( outFP )
                  {
                     void* data = malloc( gelEntry.dataSize );
                     fseek( gemFP, gelEntry.startOffset, 0 );
                     fread( data, gelEntry.dataSize, 1, gemFP );
                     fwrite( data, gelEntry.dataSize, 1, outFP );
                     free( data );
                     fclose( outFP );
                  }
               }
            }
         }

         printf( "\n\nProcess Completed\n\n" );
         fclose( gemFP );
      }

      fclose( gelFP );
   }

   return 0;
}
```


I'm currently doing php version of GEL GEM extractor. 
I think this can be done by using string manipulation in php, because c++ reads the stream the same way as php but in different method.
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-27T23:37:47+00:00
- Post Title: ROHAN : PHP DDS GEO Header Remover.

1) What's the purpose of this thread?
2) Shouldn't it be in the graphics section if it is about dds files?
## Post #3
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-05-28T08:16:17+00:00
- Post Title: ROHAN : PHP DDS GEO Header Remover.

> * Coming Soon PHP GEL GEM FILE EXTRACTOR


But I sure hope that the model viewer/converter will be public soon so I can start taking some models from the game
## Post #4
- Username: ChaosPower
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 22, 2009 2:51 am
- Post datetime: 2009-05-28T22:44:46+00:00
- Post Title: ROHAN : PHP DDS GEO Header Remover.

> Reply from Rheini
>
> 1) What's the purpose of this thread?
2) Shouldn't it be in the graphics section if it is about dds files?

The source code was released here in the 3d/2d models section. DDS files of rohan also contains 2D models aswell (Like Trees). 

The topic is to show the possibility of PHP file modification and extraction. I hope other mod tools will get converted to the PHP language.

Here are the short advantages if you guys will develop mod tools with php.

1. Easy references.
2. Cross Platform.
3. You can share it through the web.

And here is what I think are the disadvantages.

1. The need for server setups / Lamp/ Wamp.

UPDATE: Here is another sample for converting it to tga. Automatically done by reading dir contents.

```
            /*
             * Concept DDS GEO Header Remover Source Release
             * Coming Soon PHP GEL GEM FILE EXTRACTOR
             * No License, Make this as your own
             
             
             $filename = "./item/07_bro_1.dds"; //file to read
             $contents = file_get_contents($filename); //read as string
             //echo strlen($contents); //Count no. of strings
             echo substr($contents,3,strlen($contents)); //Removed GEO / DDS Header
             $modS = substr($contents,3,strlen($contents)); // Same but is placed inside a variable
             $file = fopen("./converted/test.tga","wb"); //Write to new name inside an exisiting folder
             fwrite($file,$modS,filesize($filename)); //Write File
             */
            
            $dir = "./items/";
            $db = scandir($dir, 0);
            echo "<table><tr><th>Directory</th><th>Basename</th><th>Filename</th></tr>";
            foreach ($db as $key=>$value)
            {
                if ($value != "." && $value != "..")
                {
                    $x = pathinfo($dir.$value);
                    echo "<tr><td>./items/</td><td>".$value."</td><td>".$x['filename']."</td></tr>";
                }
            }
            echo "</table>";
            
            ?>
        </div>
        <?php
        
        //Start file modifications
        
        foreach ($db as $key=>$value)
        {
            if ($value != "." && $value != "..")
            {
                $y = pathinfo($dir.$value);
                $contents = file_get_contents($dir.$value);
                $mod_contents = substr($contents, 3, strlen($contents));
                $newFile = fopen("./converted/TGA/".$y['filename'].".tga", "wb");
                fwrite($newFile, $mod_contents, filesize($dir.$value));
            }
        }
        
        ?>
```


PS: Required folders are converted/tga or you can change the file locations in the parameters of file_get_contents and fopen.

> Reply from pixellegolas
>
> * Coming Soon PHP GEL GEM FILE EXTRACTOR


But I sure hope that the model viewer/converter will be public soon so I can start taking some models from the game

Yes, I also hope for it too and also hoping for a source release of it.
## Post #5
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-28T23:03:48+00:00
- Post Title: ROHAN : PHP DDS GEO Header Remover.

> Reply from ChaosPower
>
> 1. Easy references.


> 2. Cross Platform.You can create cross-platform tools with D or Java as well.
Furthermore nearly every gamer runs Windows, thus normally this isn't needed anyways.

> 3. You can share it through the web.Ok for small converters and stuff but this doesn't scale for archives (uploading a 1GB archive file and then redownloading its contents? never)

> 1. The need for server setups / Lamp/ Wamp.Exactly. Noone's gonna do that, some people don't even manage to install .NET or Java for example.
## Post #6
- Username: ChaosPower
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 22, 2009 2:51 am
- Post datetime: 2009-05-28T23:22:45+00:00
- Post Title: ROHAN : PHP DDS GEO Header Remover.

Exactly, however I find php easier than c++. 

I might not continue the next release in php, but I might do this in java instead.
----------------------------------------------


Nice sig, Im thinking of switching to D language. Is it hard to study D compared to Java?

At first glance I think D is a combination of ADA Java and C#.

EDIT: D languages is very impressive. Thanks, direct machine language compilation is better. Brilliant! low compile time and low execution time. And is compatible with windows.h or windows api.
## Post #7
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-28T23:45:57+00:00
- Post Title: ROHAN : PHP DDS GEO Header Remover.

Yeah cause C++ has served its time ^^

Well D is a wonderful language, if you switch over to it you will never want to program in C++ again 
The only thing it lacks is the popularity C or Java enjoys.
Thus there are not as many tutorials, IDEs, etc. available compared to other languages.

But that's not really a problem imho. There is a highly active community of D enthusiasts. Every of my questions always has been rapidly answered in the newsgroups.

EDIT:
> Reply from ChaosPower
>
> EDIT: D languages is very impressive. Thanks, direct machine language compilation is better. Brilliant! low compile time and low execution time. And is compatible with windows.h or windows api.
Exactly. And there's even more to it
## Post #8
- Username: ChaosPower
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 22, 2009 2:51 am
- Post datetime: 2009-05-29T16:37:34+00:00
- Post Title: ROHAN : PHP DDS GEO Header Remover.

> Reply from Rheini
>
> 
The only thing it lacks is the popularity C or Java enjoys.

I wonder what will the output of an os that is develop by D. Man can't wait, I bet that this will surely catch up with java. I'm studying it now. Maybe I'll convert this PHP DDS Head Remover to D version of Gem Gel extractor. Then make a gui for it with option to extract gel gem files.
## Post #9
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-29T16:58:01+00:00
- Post Title: ROHAN : PHP DDS GEO Header Remover.

You mean an operating system written in D? I think I've already seen a project for writing a minimal kernel, but I can't remember what it was.
For making a GUI several libraries are available. There is a D port of Qt, SWT and a custom library named DFL [http://www.dprogramming.com/dfl.php](http://www.dprogramming.com/dfl.php)
## Post #10
- Username: ChaosPower
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 22, 2009 2:51 am
- Post datetime: 2009-05-30T05:11:40+00:00
- Post Title: ROHAN : PHP DDS GEO Header Remover.

I'm impress, you can really migrate fast to D language. How bout assembly capabilities? do have links where I can get reference for __asm? Thank you very much for the information.
## Post #11
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-30T15:32:29+00:00
- Post Title: ROHAN : PHP DDS GEO Header Remover.

[http://digitalmars.com/d/2.0/iasm.html](http://digitalmars.com/d/2.0/iasm.html)
