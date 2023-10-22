## Post #1
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-01-24T17:34:02+00:00
- Post Title: Need help with map format

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-12-05T14:24:23+00:00
- Post Title: Need help with map format

Just in case somebody is interested:

```
	uint null; // 0
	uint uk2; // fest?!
	uint uk3;
//if (uk2 == 0)
//	char name[uk3];
	uint uk4;
	uint uk5;
};

struct ukstrukt2 {
	uint index;
	uint ffff;
	uint uk1;
	uint uk2;
};

struct String
{
    uint length;
    char name[length];
};

struct Header {
	uint kopf1;
	uint kopf2<format=hex>;
	uint seven; // =7
	uint AnzKopfStrukt;
	Eintrag KopfStrukt[AnzKopfStrukt]<optimize=false>;
    String mapname;
	uint width; // logical width
	uint height; // logical height
	uint uk[9];
	ukstrukt2 field[8];
} head;

/*
// uint watertype; // 0 normal, 1 Sumpf, 2 Trocken


uint sieben;
uint uk3[22];
uint AnzTrigger; //doch nicht
struct Trigger {
Eintrag eintrag;
uint uk4;
uint uk5;
uint laengetrigger;
char name[laengetrigger];
uint uk6[12];
};
Trigger triggers[AnzTrigger]<optimize=false>;
*/

//	uint uk4[23];
//	uint AnzTrigger;
//	Eintrag Trigger[AnzTrigger]<optimize=false>;


FSeek(336+head.mapname.length);
uint fineWidth; // fine grid width
uint fineHeight;
int heights[fineWidth*fineHeight];

int uk;
int uk;
int uk;
int uk;

uint numPatterns; // width*length; (x,y) coordinate addressing
uint patternIDs[numPatterns]<format=hex>; // the IDs defined in patterns.lua
// are saved row by row, i.e. 1st element is (0,0), 2nd is (1,0), and so on

int uk2;
int uk2;
int uk2;
int uk2;
uint numUKs;
uint uks[numUKs];

int uk3;
int uk3;
int uk3;
int uk3;
uint logWidth;
uint logHeight;
struct Good
{
    uint uk;
    uint ID<format=hex>; //defined in Goods.lua
} goods[logWidth*logHeight];

int uk4;
int uk4;
int uk4;
int uk4;
uint logWidth2;
uint logHeight2;
uint uks2[logWidth2*logHeight2];

int uk5;
int uk5;
int uk5;
int uk5;
uint logWidth3;
uint logHeight3;
struct UK3
{
    uint uk;
    uint uk2;
    uint uk3;
    uint uk4;
    uint uk5;
    uint uk6;
    uint uk7;
    uint uk8;
} uks3[logWidth3*logHeight3];

int uk6;
int uk6;
int uk6;
int uk6;
uint logWidth4;
uint logHeight4;
uint uks4[logWidth4*logHeight4];

FSkip(72);
uint numDeposits;
struct Deposit
{
    uint ID;
    uint uk1;
    uint uk2;
    uint uk3;
    uint uk4;
    uint uk5;
    uint uk6;
    uint uk7;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint x; // position is using fine grid
    uint y;
    float one; // 1?
    uint uk;
    uint uk;
} deposits[numDeposits];

int numAnimals;
struct Animal
{
	uint ID; // 83EF9B4A = Hirsch, 947C6E70 = Elch, 767B7941 = Hase in Dateiendian, also falsch rum
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    int uk;
    int uk;
} animals[numAnimals];

FSkip(56);

uint numDoodads;
struct Doodad
{
    uint ID;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint uk;
    uint x; // position uses fine grid
    uint y;
} doodads[numDoodads];

FSkip(80);
uint numAmbients;
struct Ambient
{
    uint ID<format=hex>;
    uint uk; // = 0?
    uint uk2; // another ID?
    uint strength; // ???
    uint x;
    uint y;
} ambients[numAmbients];
```
