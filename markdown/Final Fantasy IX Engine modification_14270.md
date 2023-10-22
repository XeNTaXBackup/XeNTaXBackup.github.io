## Post #1
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2016-04-25T19:16:51+00:00
- Post Title: Final Fantasy IX: Engine modification

A new version is available: (09.06.2016) 
Git: [https://github.com/Albeoris/Memoria](https://github.com/Albeoris/Memoria)
Build: [https://yadi.sk/d/FVB-1Qs3rJwnz](https://yadi.sk/d/FVB-1Qs3rJwnz)

Features:

 Disable/Enable cheats
 Fast battles (Skip waiting or turn-based)
 Save/Load anywhere (Alt+F5 / Alt+F9)
 Edit game data
 All of characters available
 Easy rope jumping
 Change the game font
 Export text resources
 Import text resources
Important:
Update the game to the last version first!
Delete Memoria.ini from a previously installation.

Future:

 Import text resources
 Export/import graphics resources
 Exit to main menu
 Redesign the battle menu
 Rewrite the game engine
First run:

 Run game.
 If there is no error you will see "Memoria.ini" file in the game directory.
 If something went wrong you will see error in the "Memoria.log"
 If you not see "Memoria.log" try to run game with administrator rights
 If you see "Sharing violation on path" then close applications that hold this file
 If you see "at Memoria.CsvReader.Read" then fix files in the StreamingAssets\Data directory or delete them and patch again.
 If the error persists see "\FINAL FANTASY IX\x64(or x86)\FF9_Data\output_log.txt"

Configuration:

 Close the game
 Open Memoria.ini via any text editor (notepad for example)
 Change "Enable" value from 0 to 1.
 Specify other params
 Save Memoria.ini
 Run the game

Feedback, pull requests and issues are welcome.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-04-25T20:26:55+00:00
- Post Title: Final Fantasy IX: Engine modification

woah cool! i missed the steam sale so haven't bought it yet..... but wanted to tear down their engine too. they're using unity?!?

i loved that tetra master minigame so much
## Post #3
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2016-04-25T21:05:20+00:00
- Post Title: Final Fantasy IX: Engine modification

Yeah.
## Post #4
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2016-04-26T19:03:33+00:00
- Post Title: Final Fantasy IX: Engine modification

Update.
## Post #5
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2016-04-28T22:35:10+00:00
- Post Title: Final Fantasy IX: Engine modification

Update:
+ All of characters available
## Post #6
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2016-04-29T05:07:45+00:00
- Post Title: Final Fantasy IX: Engine modification

This is great.

When you mention there are plans to export graphics.
Will that include the walkmesh, as right now I'd like to extract the walkmesh for various scenes, but no tools seem to be able to do this because the walkmesh isn't being rendered, so nothing picks it up.

I would try NinjaRipper on the game, however there seems to be no way to get Ninja Ripper to work with this game at all due to it having the annoying launcher.
## Post #7
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2016-04-29T12:27:34+00:00
- Post Title: Final Fantasy IX: Engine modification

> Reply from lionheartuk
>
> This is great.

When you mention there are plans to export graphics.
Will that include the walkmesh, as right now I'd like to extract the walkmesh for various scenes, but no tools seem to be able to do this because the walkmesh isn't being rendered, so nothing picks it up.

I would try NinjaRipper on the game, however there seems to be no way to get Ninja Ripper to work with this game at all due to it having the annoying launcher.
Unfortunately, I do not know anything about 3D-formats, so I cannot export a walkmesh in a convenient format.

It's just magic words for me:

```
{
  public int floorIdx;
  public int triIdx;
  public Vector3[] originalVertices;
  public Vector3 originalCenter;
  public Vector3[] transformedVertices;
  public Vector3 transformedCenter;
  public Rect transformedRect;
  public float transformedZ;
  public int[] neighborIdx;
  public int cost;
  public int pathCost;
  public WalkMeshTriangle next;
  public WalkMeshTriangle nextListElem;
  public ushort triFlags;
}
```


If you can write a serializer for WalkMesh I can add it to the Memoria.
## Post #8
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2016-05-02T15:57:27+00:00
- Post Title: Final Fantasy IX: Engine modification

+ Import text resources
## Post #9
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2016-05-03T13:13:07+00:00
- Post Title: Final Fantasy IX: Engine modification

> Reply from Albeoris
>
> lionheartuk wrote:This is great.

When you mention there are plans to export graphics.
Will that include the walkmesh, as right now I'd like to extract the walkmesh for various scenes, but no tools seem to be able to do this because the walkmesh isn't being rendered, so nothing picks it up.

I would try NinjaRipper on the game, however there seems to be no way to get Ninja Ripper to work with this game at all due to it having the annoying launcher.
Unfortunately, I do not know anything about 3D-formats, so I cannot export a walkmesh in a convenient format.

It's just magic words for me:
Code: Select allpublic class WalkMeshTriangle
{
  public int floorIdx;
  public int triIdx;
  public Vector3[] originalVertices;
  public Vector3 originalCenter;
  public Vector3[] transformedVertices;
  public Vector3 transformedCenter;
  public Rect transformedRect;
  public float transformedZ;
  public int[] neighborIdx;
  public int cost;
  public int pathCost;
  public WalkMeshTriangle next;
  public WalkMeshTriangle nextListElem;
  public ushort triFlags;
}

If you can write a serializer for WalkMesh I can add it to the Memoria.

Unfortunately, much to my chagrin, that isn't my specialty at all. I'd love to help but I've no idea about that side of things myself.
## Post #10
- Username: Albeoris
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Oct 16, 2014 7:40 am
- Post datetime: 2016-09-27T01:02:47+00:00
- Post Title: Final Fantasy IX: Engine modification

Now I can attach debugger to the Final Fantasy IX! ^^
You can do that for the most of Unity games.
