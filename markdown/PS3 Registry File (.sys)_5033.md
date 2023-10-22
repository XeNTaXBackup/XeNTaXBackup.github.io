## Post #1
- Username: Matsy
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Aug 21, 2006 3:12 pm
- Post datetime: 2010-09-14T09:39:44+00:00
- Post Title: PS3 Registry File (.sys)

Dear Xentax Members,

This forum looked like the most suitable forum to figure out how the PS3 Registry works. I've done some work, but I can't really figure it out.
However, there is one problem. There's a lot of 'sensitive' information in such a file, so I can't really upload it all. I can upload the header / setting values though. This might trouble the research, but I'll do my best to explain everything as good as possible.

At first, there's the header. I'm doing some templating using Hex Workshop, so I can just copy my results here.

```
 * PS3Registry.hsl - Structure definitions for the .sys PS3 Registry Format
 *  
 * Copyright (c) 2010 Mats Willemsen
 *
 *****************************************************************************
 * Revision History:
 *  09/14/10 - Mats Willemsen - Original
 */

#include "standard-types.hsl"

#pragma displayname("PS3 Registry")
#pragma fileextensions(".sys")

#pragma byteorder(big_endian)

struct HEADER
{
    char Signature[7]; // BC AD AD BC 00 00 00 
#pragma verify match_var_int("Signature[0]","0xBC")
#pragma verify match_var_int("Signature[1]","0xAD")
#pragma verify match_var_int("Signature[2]","0xAD")
#pragma verify match_var_int("Signature[3]","0xBC")
#pragma verify match_var_int("Signature[4]","0x00")
#pragma verify match_var_int("Signature[5]","0x00")
#pragma verify match_var_int("Signature[6]","0x00")
    short fileAmount1; // First File Amount.
    byte unknown1; // Unknown Value (00)
    short fileAmount2; // Second File Amount
    char unknown[4]; // BC AD AD BC (Seems to identify the end of one part)
} ;

struct SETTINGNAME
{
    ubyte unknown1; //(Ranging from 0 to 255, might also be a signed byte, I really have no idea)
    short unknown2; //(Ranging from 0 to 255, with unknown1, it's a unique combo.)
    byte size; // Size of the settingname, 0 terminated. 
    byte flag; // Flag. 0 seems to be used values, 1 seems to be debug values, and 2 non-used.
    char settingname[size + 1]; // Name of the setting.
} ;

struct FILE
{
    struct HEADER header;
    struct SETTINGNAME settings[header.fileAmount1 + header.fileAmount2 - 2]; //Seem to be two placeholder values.
} ;


```


It seems that there are two shorts for the amount of settings in the file. I really have no idea, but if you add them, you get the correct result of the amount of settings.

And then there are the unknown bytes / chars. The whole header is (in my file) like this:

```
BC AD AD BC 00 00 00 90 00 00 00 02 BC AD AD BC
```


So, the 90 00 (144) + 00 02 (512) = 656 entries, which is correct.

Then there are the setting names, plus (possibly, and likely) the position in the file.

But, unknown1 / unknown2 are a bit more weird. Throughout the file, both seem to range from 0-255, (or -128 to +128 in signed mode, no idea.

That seems to be a bit odd. But, the problem is within the following. I can't place the values in ANY way. 

Anyone here with access to their xRegistry.sys file? 

I'll add to this once I find more. 

Mats
[xRegistryHeader.zip](https://xentaxbackup.github.io/file/3443_xRegistryHeader.zip)
