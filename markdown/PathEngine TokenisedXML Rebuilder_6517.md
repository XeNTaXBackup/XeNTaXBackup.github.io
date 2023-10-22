## Post #1
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-04-27T19:11:58+00:00
- Post Title: PathEngine TokenisedXML Rebuilder

such tokenised xml files have the extension .tok
example tok files are in the free playable demo - [http://www.pathengine.com/downloads.php](http://www.pathengine.com/downloads.php)

i used the information provided [in the programmers guide](http://www.pathengine.com/Contents/ProgrammersGuide/WorldRepresentation/DirectXMLGeneration/TokenisedXML/page.php)

the script is a binary template for [010 Editor](http://www.sweetscape.com/010editor/)

```
    PathEngine
    Tokenised XML -> XML

    Specification:
    http://www.pathengine.com/Contents/ProgrammersGuide/WorldRepresentation/DirectXMLGeneration/TokenisedXML/page.php
*/



/*
    Element and attribute names
    Note: These are indexed from 1
*/

struct str{string s;};

str _s;
while(ReadUByte(FTell()) != 0)
  str _s;

FSkip(1);

/*
    Attributes
    Note: These are indexed from 1
*/

enum <ubyte> xmlTypes
{
    C_STR   = 1,
    SINT_32 = 2,
    SINT_16 = 3,
    SINT_8  = 4,
    UINT_32 = 5,
    UINT_16 = 6,
    UINT_8  = 7
};

struct atrb
{
  xmlTypes t;   // Attribute data type
  string s;     // Attribute name
};

atrb _a;

while(ReadUByte(FTell()) != 0)
  atrb _a;

FSkip(1);

/*
    XML structure
*/

struct xmlNode; // Prototype / forward declaration

local int lvl = -1;

struct xmlStruct
{
    lvl++;

    while(ReadUByte(FTell()) != 0)
        xmlNode node;

    FSkip(1);
    lvl--;
};

void doIndent()
{
    local int i;
    for(i=0; i<lvl; i++)
        Printf("  "); // or \t where need be
}

struct xmlNode
{
    ubyte sIdx; local ubyte idx = sIdx;

    doIndent();
    Printf("<%s", _s[sIdx-1].s);
    local ubyte as=0;
    while(ReadUByte(FTell()) != 0)
    {
        as++;
        ubyte aIdx;
        switch(_a[aIdx -1].t)
        {
            case C_STR :
                str tmp;
                Printf(" %s=\"%s\"", _a[aIdx-1].s, tmp.s);
                break;
            case SINT_32 :
                int32 tmp;
                Printf(" %s=\"%i\"", _a[aIdx-1].s, tmp);
                break;
            case SINT_16 :
                int16 tmp;
                Printf(" %s=\"%i\"", _a[aIdx-1].s, tmp);
                break;
            case SINT_8 :
                byte tmp;
                Printf(" %s=\"%i\"", _a[aIdx-1].s, tmp);
                break;
            case UINT_32 :
                uint32 tmp;
                Printf(" %s=\"%u\"", _a[aIdx-1].s, tmp);
                break;
            case UINT_16 :
                uint16 tmp;
                Printf(" %s=\"%u\"", _a[aIdx-1].s, tmp);
                break;
            case UINT_8 :
                ubyte tmp;
                Printf(" %s=\"%u\"", _a[aIdx-1].s, tmp);
                break;
        }
    }

    FSkip(1);

    if(as > 0)Printf("/>\n");
    else      Printf(">\n");

    local int on=0;
    while(ReadUByte(FTell()) != 0)
    {
        on++;
        xmlStruct x;
    }

    if(on > 0)
    {
        doIndent();
        Printf("</%s>\n", _s[idx-1].s);
    }
};


xmlStruct xml;

```
