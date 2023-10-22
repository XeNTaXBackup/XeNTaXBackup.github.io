## Post #1
- Username: evilpie
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Nov 30, 2009 5:13 am
- Post datetime: 2009-11-30T15:04:45+00:00
- Post Title: Lithtech Engine, Combat Arms

Hello forum,

my first post .
I want to open .rez files of Combat Arms, but i could not found any documentation about Lithtech on your page, so i tried it myself.

I created this struct for 010 Editor, but for some reason it messes up after the 3 file.

```
{
    char Header[136];
    char Unknown[75];
    int  AdressFileNames;
    FSeek (AdressFileNames);
    int Unknown;
    while (1)
    {
        struct FileInfo
        {
            int Adress;
            int Unknown1;
            int Unknown2;
            int Unknown3;
            char FileExt[8];
            char FileName[8];
        } info;
        if (Strlen (info.FileName) == 0)
            break;
    }
} file;
```


Cheers Evilpie
## Post #2
- Username: evilpie
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Nov 30, 2009 5:13 am
- Post datetime: 2009-11-30T16:35:34+00:00
- Post Title: Lithtech Engine, Combat Arms

I found my mistake, for some reason they always add 5 x 0x00-bytes behinde the null-terimnated filname.
I also made my first quickbms script 

Note: This seems not to be the common rez file type, its only usable with combat arms, furthermore i only tested it with the eu version.

```

GoTo 211
GET offset LONG
GoTo offset
Get unknown LONG

For
	Get FileOffset LONG
	Get FileSize LONG
	Get unkown1 LONG
	Get unkown2 LONG
	Get FileExt STRING
	Get unkown3 LONG
	Get FileName STRING
	Get unkown4 LONG
	Get unkown5 BYTE
	
	If FileName == ""
		Break
	Endif
	
	
	String FileName += .
	String FileName += FileExt
	
	Log FileName FileOffset FileSize
Next
```
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-30T20:18:50+00:00
- Post Title: Lithtech Engine, Combat Arms

[http://wiki.xentax.com/index.php/Monolith_REZ](http://wiki.xentax.com/index.php/Monolith_REZ)
## Post #4
- Username: evilpie
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Nov 30, 2009 5:13 am
- Post datetime: 2009-11-30T20:36:44+00:00
- Post Title: Lithtech Engine, Combat Arms

Attention, this really differs from the link posted "char {127}   - Description/Header ", their are some extra bytes. But the rest should be the same.
## Post #5
- Username: LiamMitchell
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 25, 2014 11:47 pm
- Post datetime: 2017-05-07T01:13:15+00:00
- Post Title: Lithtech Engine, Combat Arms

Template for 010 Hex Editor.
(I can't put it on the wiki sadly)

```
//--- 010 Editor v8.0 Binary Template
//
// File: Lithtech REZ File Version 1
// Author: MegaByte
// Revision: 1
// Purpose: To understand REZ Files.
//--------------------------------------
// TODO: Detect empty areas.
// TODO: Identify more parts of the Archive.
enum <unsigned int> EntryType { EntryType_File, EntryType_Directory };

local int newVersion = 1;

char[] Strrev(char input[]) {
    local char temp;
    local int len = Strlen(input);
    char output[len];
    local int halfLen = len/2;
    local int i, k;
    for(i = 0,k=len-1 ; i < halfLen+1; i++,k--)
    {
        output[k] = input[i];
        output[i] = input[k];
    }
    return output;
}

typedef struct {
    unsigned int ID;
    char Ext[8];
    string Name;
    char Pad[2];

    if (Length > 0) {
        local int oldPosition = FTell();
        FSeek(Offset);
        byte Data[Length];
        FSeek(oldPosition);
    }

} RezFileEntry <size=SizeRezFileEntry,
                name=RezFileEntry_GetName>;

char[] RezFileEntry_GetName( RezFileEntry& r )
{
    return r.Name + "." + Strrev(r.Ext);
}
int SizeRezFileEntry( RezFileEntry &r )
{
    return 14 + // Base Size + 1 byte pad.
        ReadStringLength( startof(r) + 13 , header.Max_FileName ); // Read Name length.
}

struct RezEntry;

typedef struct {
    char Name[header.Max_DirectoryName];

    // Note: May have to use a stack here if a rez file has multiple directories inside each other, not sure on scoping of local variables.
    if (Length > 0) {
        local int oldPosition = FTell();
        FSeek(Offset);
    
        // Read this directories file entries.
        while(FTell() < Offset + Length) {
            RezEntry entries <optimize=false>;
        }

        FSeek(oldPosition);
    }
} RezDirectoryEntry <size=SizeRezDirectoryEntry,
                     name=RezDirectoryEntry_GetName>;

string RezDirectoryEntry_GetName( RezDirectoryEntry& r ) {
    return r.Name;
}

int SizeRezDirectoryEntry( RezDirectoryEntry &r )
{
    return ReadStringLength( startof(r) , header.Max_DirectoryName ); // Read Name length.
}


struct RezEntry {
    EntryType Type;
    unsigned int Offset;
    unsigned int Length;
    time_t Date;

    if (Type == EntryType_File) {
        RezFileEntry file;
    } else if (Type == EntryType_Directory) {
        RezDirectoryEntry directory;
    } else {
        Warning("Unhandled RezEntry file type.");
    }

};

struct REZ {
    byte num; // 38
    byte num2; // 35
    // TODO: Assert values.

    if (num == 13 && num2 == 10) {
        newVersion = 0;
    } else if (num == 38 && num2 == 35) {
        newVersion = 1;
    } else {
        Warning( "Unknown Version encountered. Halt!" );
        return -1;
    }

    char CreatedBy[60];

    if (Strncmp(CreatedBy, "RezMgr Version 1 ", 17) != 0) {
        Warning("Expecting RezMgr Version 1 in header.");
    }
    
    byte num3;
    byte num4;
    char Description[60];

    if (newVersion) {
        FSeek(195);
    } else {
        FSeek(127);
    }


    struct Header {
        unsigned int Start_Vars;
        unsigned int Root_Offset;
        unsigned int Offset_Length;
        unsigned int Blank1;
        unsigned int Index_Offset;
        time_t Date;
        unsigned int Blank2;
        unsigned int Max_DirectoryName;
        unsigned int Max_FileName;
        unsigned int Blank;
        unsigned int Start;
    } header;

    FSeek(file.header.Root_Offset);

    RezEntry rootEntry;

} file < bgcolor=0xFF00FF>;

```


I also figured out the decryption / encryption for Attributes.rez
