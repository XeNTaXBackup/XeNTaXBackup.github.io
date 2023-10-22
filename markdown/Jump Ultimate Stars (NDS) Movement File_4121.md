## Post #1
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2010-02-06T02:42:51+00:00
- Post Title: Jump Ultimate Stars (NDS) Movement File

I've been trying to finagle this file for the longest time.

I've got the Header of the file and the header of each move. But there seem to be a bunch of wacky array's within the moves.

```
{
#pragma lockAt(0x00000000)
	char            	ID[4]; //'ALMT'
	byte                    Unknown;
	byte                    Unknown;
	byte                    NodeCount;
	byte                    MoveCount; //Number of Moves Character has...
	dword                   FlagCount; //Number of Movement Flags referenced??
	Node                    Node[NodeCount]; //Nodes??
	dword                   MoveOffsets[MoveCount]; //Move Index
	word                    FlagOffsets[FlagCount]; //Flag Index
	Flag            	Flags[FlagCount];
	byte			Pad[0]; //Padding
};

```


```
	char		Node[4]; //Ascii Node name
}Node;

typedef struct Flag{
	ubyte		Unknown; //Maybe the Flag ID to be referenced??
	ubyte		Unknown; //Maybe the Flag ID to be referenced??
	zstring	String; //Flag name, Null Terminated String
}Flag;

```


```
{
	ubyte            MoveID; //Move Number
	ubyte            ID[3]; //File #??

			word			MaxFrames; //??
			ubyte            	Framerate; //??
			bool            	CollisionEnable; //Collision??
			word            	ControlByte; //Seems to influence the arrays, THink it has to do with the amount of flags??
			//Whole bunch of Array's
	
}MOVE;

```

[ALMT.zip](https://xentaxbackup.github.io/file/2769_ALMT.zip)
