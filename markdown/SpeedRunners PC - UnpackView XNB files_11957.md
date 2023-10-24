## Post #1
- Username: datahaven
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Oct 09, 2013 6:23 am
- Post datetime: 2014-09-14T14:51:36+00:00
- Post Title: SpeedRunners PC - Unpack/View XNB files

I've had a lot of fun playing [SpeedRunners](http://tinybuild.com/speedrunners) recently. It is a multi-player 2D platform race game, very similar in feel to Mario Karts. I've been playing the Steam PC version, which is currently still a beta release.

It has a very nice vector/cartoon feel graphics style, which I thought I'd take a little peek at in the game resources. 

Here's how to go about doing that if you want to have a look, too.

Game resource files are installed in the usual place for Steam games. For my computer it is:
C:\Program Files (x86)\Steam\SteamApps\common\SpeedRunners

It turns out that the .XNB file unpacking QuickBMS scripts that I wrote whilst investigating Rogue Legacy also work for the SpeedRunner character graphics files, too. Those scripts are in [this forum post.](http://forum.xentax.com/viewtopic.php?f=32&t=10855)

Use RL_uncmp_xnb.bms to turn a compressed xnb file into an uncompressed xnb file:
quickbms.exe -o RL_uncmp_xnb.bms animation_variant00.xnb

You can then use RL_extract_bmp.bms to turn the unpacked xnb into a .bmp file
quickbms.exe -o RL_extract_bmp.bms animation_variant00_unpacked.xnb

This works for all of the files in the Content\Characters folder. The unpack script seems to work on all of the xnb files in the game (that I tested) but note that the bmp extract script does not work on all of the graphics files, even when they are unpacked correctly. For example, it doesn't work on the files in the Comics directory.

The files with _atlas_ in the name are data files which describe where each animation frame is located on the corresponding spritesheet. Obviously, don't try to run RL_extract_bmp.bms on these files. However, the _unpacked.xnb versions of these files can be inspected using 010 Editor with the following template:

```
//--- 010 Editor v5.0 Binary Template
//
// File:
// Author: Adrian Dale
// Revision:
// Purpose: SpeedRunners Atlas Hack
//--------------------------------------

typedef struct AtlasDataItem
{
    byte readerType1; // s/b 2 - TextureReader
    byte NameSize; // This is actually a 7-bit encoded integer
                   // Luckily for SpeedRunners they're all small numbers
                   // so this still works.
    char Name[NameSize];
    byte readerType2; // s/b 3 - RectangleReader
    int boundsX;
    int boundsY;
    int boundsW;
    int boundsH;
    
    float originX;
    float originY;
    
    float origSizeX;
    float origSizeY;
};

char XNBTag[3]; // "XNB"
char Platform; // w, m or x
byte FlagBits; // Bit 0x01 Reach/HiDef, Bit 0x80 Uncompressed/Compressed
byte XNBFormatVersion; // 5 == XNA Game Studio 4.0
DWORD CompressedFileSize; // or FileSize for uncompressed files
// If FlagBits & 0x80 then a DWORD for uncompressed size comes next,
// Then the rest would all be compressed.
// Use my quickbms decompressor then run this script on the uncompressed file.

byte ReadersBlock[298]; 
// Need to write code for this
// It's the bit that says which readers (in the C# code) are needed
// to read the file.
// For now I've just hardcoded the size of this block for the files I
// am interested in.

// This bit is SpeedRunners-specific data
DWORD spriteFrameCount;
AtlasDataItem adi[spriteFrameCount] <optimize=false>;
DWORD maxWidth;
DWORD maxHeight;

```


A little educational tip - since SpeedRunners is written in C# that means it ships with a free copy of the source code. Well, sort of - you can easily reverse engineer it with a [suitable tool](http://ilspy.net/). That's how I worked out the atlas file format.

Using the above template, I wrote an 010 Editor script to convert the spritesheet atlas data into a .plist file so that I could view the game animations using a small program I wrote in cocos2d-x. I've not included it in this post but it is basically a longer version of this code, with a lot more print statements to make the .plist in the correct format.

```
//
// File:
// Author: Adrian Dale
// Revision:
// Purpose: Dump Atlas Frame Names for SpeedRunners Hack
//--------------------------------------
int i;
for( i = 0; i < spriteFrameCount; i++ )
{
    Printf("%s\n", adi[i].Name);
}

```


It was then relatively straightforward to use my cocos2d-x code to dump out all of the sprite frames for one of the animations and turn it into a little animated gif



SpeedRunners - Cosmonaut Taunt.gif (230.45 KiB) Viewed 185 times



On a more practical note - The unpack script works on the language localization files. The resulting unpacked file is in a semi-readable binary format, very like the atlas was. You could probably analyse/edit it using 010 Editor scripts in the same way I read the atlas files.

I haven't tried re-packing any of the graphics data and putting it back into the game, but I'm sure this would be possible. I discussed this and provided scripts (which ought to still work here) in the Rogue Legacy post.

Adrian
## Post #2
- Username: LolcatPlays
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 03, 2015 2:42 am
- Post datetime: 2015-07-02T18:55:38+00:00
- Post Title: SpeedRunners PC - Unpack/View XNB files

> Reply from datahaven
>
> I've had a lot of fun playing SpeedRunners recently. It is a multi-player 2D platform race game, very similar in feel to Mario Karts. I've been playing the Steam PC version, which is currently still a beta release.

It has a very nice vector/cartoon feel graphics style, which I thought I'd take a little peek at in the game resources. 

Here's how to go about doing that if you want to have a look, too.

Game resource files are installed in the usual place for Steam games. For my computer it is:
C:\Program Files (x86)\Steam\SteamApps\common\SpeedRunners

It turns out that the .XNB file unpacking QuickBMS scripts that I wrote whilst investigating Rogue Legacy also work for the SpeedRunner character graphics files, too. Those scripts are in this forum post.

Use RL_uncmp_xnb.bms to turn a compressed xnb file into an uncompressed xnb file:
quickbms.exe -o RL_uncmp_xnb.bms animation_variant00.xnb

You can then use RL_extract_bmp.bms to turn the unpacked xnb into a .bmp file
quickbms.exe -o RL_extract_bmp.bms animation_variant00_unpacked.xnb

This works for all of the files in the Content\Characters folder. The unpack script seems to work on all of the xnb files in the game (that I tested) but note that the bmp extract script does not work on all of the graphics files, even when they are unpacked correctly. For example, it doesn't work on the files in the Comics directory.

The files with _atlas_ in the name are data files which describe where each animation frame is located on the corresponding spritesheet. Obviously, don't try to run RL_extract_bmp.bms on these files. However, the _unpacked.xnb versions of these files can be inspected using 010 Editor with the following template:
Code: Select all//--------------------------------------
//--- 010 Editor v5.0 Binary Template
//
// File:
// Author: Adrian Dale
// Revision:
// Purpose: SpeedRunners Atlas Hack
//--------------------------------------

typedef struct AtlasDataItem
{
    byte readerType1; // s/b 2 - TextureReader
    byte NameSize; // This is actually a 7-bit encoded integer
                   // Luckily for SpeedRunners they're all small numbers
                   // so this still works.
    char Name[NameSize];
    byte readerType2; // s/b 3 - RectangleReader
    int boundsX;
    int boundsY;
    int boundsW;
    int boundsH;
    
    float originX;
    float originY;
    
    float origSizeX;
    float origSizeY;
};

char XNBTag[3]; // "XNB"
char Platform; // w, m or x
byte FlagBits; // Bit 0x01 Reach/HiDef, Bit 0x80 Uncompressed/Compressed
byte XNBFormatVersion; // 5 == XNA Game Studio 4.0
DWORD CompressedFileSize; // or FileSize for uncompressed files
// If FlagBits & 0x80 then a DWORD for uncompressed size comes next,
// Then the rest would all be compressed.
// Use my quickbms decompressor then run this script on the uncompressed file.

byte ReadersBlock[298]; 
// Need to write code for this
// It's the bit that says which readers (in the C# code) are needed
// to read the file.
// For now I've just hardcoded the size of this block for the files I
// am interested in.

// This bit is SpeedRunners-specific data
DWORD spriteFrameCount;
AtlasDataItem adi[spriteFrameCount] <optimize=false>;
DWORD maxWidth;
DWORD maxHeight;


A little educational tip - since SpeedRunners is written in C# that means it ships with a free copy of the source code. Well, sort of - you can easily reverse engineer it with a suitable tool. That's how I worked out the atlas file format.

Using the above template, I wrote an 010 Editor script to convert the spritesheet atlas data into a .plist file so that I could view the game animations using a small program I wrote in cocos2d-x. I've not included it in this post but it is basically a longer version of this code, with a lot more print statements to make the .plist in the correct format.
Code: Select all//--- 010 Editor v5.0 Script File
//
// File:
// Author: Adrian Dale
// Revision:
// Purpose: Dump Atlas Frame Names for SpeedRunners Hack
//--------------------------------------
int i;
for( i = 0; i < spriteFrameCount; i++ )
{
    Printf("%s\n", adi[i].Name);
}


It was then relatively straightforward to use my cocos2d-x code to dump out all of the sprite frames for one of the animations and turn it into a little animated gif
Taunt.gif

On a more practical note - The unpack script works on the language localization files. The resulting unpacked file is in a semi-readable binary format, very like the atlas was. You could probably analyse/edit it using 010 Editor scripts in the same way I read the atlas files.

I haven't tried re-packing any of the graphics data and putting it back into the game, but I'm sure this would be possible. I discussed this and provided scripts (which ought to still work here) in the Rogue Legacy post.

Adrian
Do you mind posting the scripts to convert the atlas into .plist?
As well as the program.
## Post #3
- Username: datahaven
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Oct 09, 2013 6:23 am
- Post datetime: 2015-07-02T21:49:50+00:00
- Post Title: SpeedRunners PC - Unpack/View XNB files

This is the 010 Editor script to convert the atlas to a plist file:

{% raw %}
```
//--- 010 Editor v5.0 Script File
//
// File:
// Author: Adrian Dale
// Revision:
// Purpose: SpeedRunners Atlas Converter
//--------------------------------------

Printf("<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n");
Printf("<!DOCTYPE plist PUBLIC \"-//Apple Computer//DTD PLIST 1.0//EN\" \"http://www.apple.com/DTDs/PropertyList-1.0.dtd\">\n");
Printf("<plist version=\"1.0\">\n");
Printf("    <dict>\n");
Printf("        <key>frames</key>\n");
Printf("        <dict>\n");

int i;
for( i = 0; i < spriteFrameCount; i++ )
{
Printf("            <key>%s</key>\n", adi[i].Name);
Printf("            <dict>\n");
Printf("                <key>frame</key>\n");
Printf("                <string>{{%d,%d},{%d,%d}}</string>\n",
                        adi[i].boundsX, adi[i].boundsY, adi[i].boundsW, adi[i].boundsH);
Printf("                <key>offset</key>\n");
Printf("                <string>{%d,%d}</string>\n", adi[i].originX * -1, adi[i].originY * -1);
Printf("                <key>rotated</key>\n");
Printf("                <false/>\n");
Printf("                <key>sourceColorRect</key>\n");
Printf("                <string>{{%d,%d},{%d,%d}}</string>\n", // TODO
                        adi[i].boundsX, adi[i].boundsY, adi[i].boundsW, adi[i].boundsH);
Printf("                <key>sourceSize</key>\n");
Printf("                <string>{%d, %d}</string>\n", maxWidth, maxHeight);
Printf("            </dict>\n");
}

Printf("        </dict>\n");
// I skipped the metadata key - do I need it?
// Yes, if texture name (.png) differs from plist name,
// Also need it so we can specify format 2
Printf("<key>metadata</key>\n");
Printf("        <dict>\n");
Printf("            <key>format</key>\n");
Printf("            <integer>2</integer>\n");
Printf("            <key>size</key>\n");
Printf("            <string>{192,50}</string>\n");
Printf("            <key>smartupdate</key>\n");
Printf("            <string>$TexturePacker:SmartUpdate:e624551a9c84414ebc63983cd5f62c16$</string>\n");
Printf("            <key>textureFileName</key>\n");
Printf("            <string>SR_Cosmonaut0001.png</string>\n");
Printf("        </dict>\n");
Printf("    </dict>\n");
Printf("</plist>\n");

```
{% endraw %}

I'm not sure where I put the code to make the animation, so I don't have that. Anyway, there are probably better ways to do what I did. Maybe something like this could be useful? [http://renderhjs.net/shoebox/](http://renderhjs.net/shoebox/)
