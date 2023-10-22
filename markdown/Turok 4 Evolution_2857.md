## Post #1
- Username: deadlydata
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 02, 2006 7:48 am
- Post datetime: 2007-11-27T18:47:14+00:00
- Post Title: Turok 4 Evolution

Alot of it is pretty simple... but there are still certain things I can't pull out of it.

Reason I'm asking is because me and a friend are working on a multiplayer online mod for the game which has already progressed far beyond we thought it would but there are tons of bugs like players turning invis once in a while and I think getting a better understanding over the game files will help solve this.

File Extensions: .mtf, .atr(Some kind of custom scripting language), .ati(Used when using atr's for maps), .hst(plain text) , .pcl , .fx , .amc , .atf , .anm and textures are standard .dds 

Any way here are some of the files at random.

Thanks in advance to any thing you guys find in it.

.fx

```
 http://rapidshare.com/files/72693669/Effects.rar.html 
```


atf anm  amc 

```
 http://rapidshare.com/files/72694571/humananims.rar.html 
```


ati atr mtf (Map File _ Single Player)

```
 http://rapidshare.com/files/72694968/pod-01-through-the-jungle.rar.html 
```
 

hst (Boot Up Text) 

```
 http://rapidshare.com/files/72695036/bootupsequence.rar.html 
```
 

PCL (Pre Chache List)

```
 http://rapidshare.com/files/72695276/weapons.rar.html 
```


Theres also this crazy thing they left in here their folders are dirty and theres alot of beta stuff they left laying in the pc version but yeah this should really help.

Attached and Pasted

> ;------------------------------------------------------------------------------
>
> ;                       The .god file for T4
>
> ;------------------------------------------------------------------------------
>
> ;
>
> ;   Refer to Main.god for an overview of the .god files.
>
> ;   
>
> ;------------------------------------------------------------------------------
>
> 
>
> #include "Gods\Path.god"
>
> #include "Gods\PathNode.god"
>
> 
>
> #include "Gods\NavigationLink.god"
>
> #include "Gods\NavigationNode.god"
>
> 
>
> #include "Gods\Materials.god"
>
> 
>
> #include    "Gods\Shared\Causes.god"            ;   The shared causes
>
> #include    "Gods\Shared\Events.god"            ;   The shared events
>
> #include    "Gods\Shared\LinkConditionals.god"  ;   The shared link conditionals.
>
> #include    "Gods\Causes.god"                   ;   The game-specific causes
>
> #include    "Gods\Events.god"                   ;   The game-specific events
>
> #include    "Gods\Conditionals.god"             ;   The game-specific conditionals
>
> 
>
> #include    "Gods\Collision.god"
>
> 
>
> #include "Gods\Mode.god"
>
> 
>
> #include "Gods\Shared\Actors.god"
>
> #include "Gods\Shared\Cameras.god"
>
> 
>
> #include "Gods\FaceFlags.god"
>
> 
>
> ;------------------------------------------------------------------------------
>
> ; Base AI
>
> ;------------------------------------------------------------------------------
>
> *OBJECT = "TurokAIObject"
>
> {
>
> 	*NAME	= "TurokAI"
>
> 	*INHERITS = "Object"
>
> 
>
> 	*VARIABLES = 
>
> 	{
>
> 		*Combo = "TurokAIType"
>
> 		{
>
> 			*Usage			= "Protected"
>
> 			*DisplayName	=	"Turok AI Type"
>
> 			*Value			=	0
>
> 			*Comment		=	"The Turok AI type."
>
> 
>
> 			*ComboList = 
>
> 			{
>
> 				"0 - None",
>
> 				"1 - Enemy",
>
> 				"2 - Player",
>
> 				"3 - Ally",
>
> 				"4 - Neutral Aggressive",
>
> 				"5 - Passive Aggressive",
>
> 				"6 - Passive Neutral"				
>
> 			}
>
> 		}
>
> 
>
> 		*FLOAT = "VisionEyeHeight"
>
> 		{
>
> 			*Usage			= "Protected"
>
> 			*VALUE	= 1
>
> 			*DISPLAYNAME = "Vision Eye Height"
>
> 			*Comment = "Eye Height for vision test"
>
> 		}
>
> 
>
> 		*FLOAT = "ShallowWaterHeight"
>
> 		{
>
> 			*Usage			= "Protected"
>
> 			*VALUE	= 1
>
> 			*DISPLAYNAME = "Shallow Water Height"
>
> 			*Comment = "The height at which ai is considered in shallow water"
>
> 		}
>
> 
>
> 		*FLOAT = "AimAtHeight"
>
> 		{
>
> 			*Usage			= "Protected"
>
> 			*VALUE	= 1.0f
>
> 			*DISPLAYNAME = "Aim At Height"
>
> 			*Comment = "The height at which to aim at this AI"
>
> 		}
>
> 
>
> 		*FLOAT = "AIRadius"
>
> 		{
>
> 			*Usage			= "Protected"
>
> 			*VALUE			= 0.5f
>
> 			*DISPLAYNAME	= "AI Radius"
>
> 			*Comment		= "The radius size of this AI"
>
> 		}
>
> 
>
> 		*FLOAT = "FDMult"
>
> 		{
>
> 			*VALUE	= 1.0f
>
> 			*DISPLAYNAME = "Fire Damage Multiplier"
>
> 			*Min		 = 0.0
>
> 			*Comment = "1.0 is normal"
>
> 			*Comment = "0.0 is impervious to fire"
>
> 		}
>
> 
>
> 		*Combo = "LTarg"
>
> 		{
>
> 			*DisplayName	=	"Lockable target?"
>
> 			*Value		=	0 
>
> 			*ComboList	=
>
> 			{
>
> 				"Nope",
>
> 				"Regular",
>
> 				"Primary"
>
> 			}
>
> 		}
>
> 
>
> 		*FLOAT = "PointValue"
>
> 		{
>
> 			*Usage			= "Public"
>
> 			*VALUE			= 0.0f
>
> 			*DISPLAYNAME	= "Point Value"
>
> 			*Comment		= "The value of this Object. Can be used for scoring etc."
>
> 		}
>
> 
>
> 		*BOOL = "IgnoreNav"
>
> 		{
>
> 			*Usage			= "Protected"
>
> 			*VALUE	= 0
>
> 			*DISPLAYNAME = "Ignore Nav Data"
>
> 			*Comment = "Ignore Nav Data"
>
> 		}
>
> 
>
> 
>
> 		*Group = "Multiplayer Scaling"
>
> 		{
>
> 			*BOOL = "MPSOnOff"
>
> 			{
>
> 				*VALUE	= "False"
>
> 				*DISPLAYNAME = "Enable"
>
> 				*Comment = "Use multiplayer scaling on this actor?"
>
> 			}
>
> 
>
> 			*FLOAT = "MPSFar"
>
> 			{
>
> 				*VALUE	= 100.0f
>
> 				*DISPLAYNAME = "Far distance"
>
> 				*Comment = "The distance away from the view"
>
> 				*Comment = "that the scale will start."
>
> 			}
>
> 
>
> 			*FLOAT = "MPSMid"
>
> 			{
>
> 				*VALUE	= 50
>
> 				*DISPLAYNAME = "Mid distance"
>
> 				*Comment = "The distance away from the view"
>
> 				*Comment = "that the scale will be biggest."
>
> 			}
>
> 
>
> 			*FLOAT = "MPSNea"
>
> 			{
>
> 				*VALUE	= 10
>
> 				*DISPLAYNAME = "Near distance"
>
> 				*Comment = "The distance away from the view"
>
> 				*Comment = "that the scale will be back to normal."
>
> 			}
>
> 
>
> 			*FLOAT = "MPSSca"
>
> 			{
>
> 				*VALUE	= 10.0f
>
> 				*DISPLAYNAME = "Scale multiplier"
>
> 				*Comment = "Mid distance scale."
>
> 			}
>
> 
>
> 		}
>
> 
>
> 		*Group = "Accessories"
>
> 		{
>
> 			*Comment = "Attached items"
>
> 
>
> 			*FilePick = "AccessoryName1"
>
> 			{
>
> 				*DISPLAYNAME = "Accessory1"
>
> 				*Value			=	""
>
> 				*Directory      =   "$\Data\Actors"
>
> 				*Extension      =   "atr"
>
> 			}
>
> 			*String = "AccessoryPoint1"
>
> 			{
>
> 				*DisplayName	=	"Hotpoint1"
>
> 				*Value			=	""
>
> 				*Comment		=	"The hotpoint to attach the accessory to"
>
> 			}
>
> 
>
> 			*FilePick = "AccessoryName2"
>
> 			{
>
> 				*DISPLAYNAME = "Accessory2"
>
> 				*Value			=	""
>
> 				*Directory      =   "$\Data\Actors"
>
> 				*Extension      =   "atr"
>
> 			}
>
> 			*String = "AccessoryPoint2"
>
> 			{
>
> 				*DisplayName	=	"Hotpoint2"
>
> 				*Value			=	""
>
> 				*Comment		=	"The hotpoint to attach the accessory to"
>
> 			}
>
> 
>
> 			*FilePick = "AccessoryName3"
>
> 			{
>
> 				*DISPLAYNAME = "Accessory3"
>
> 				*Value			=	""
>
> 				*Directory      =   "$\Data\Actors"
>
> 				*Extension      =   "atr"
>
> 			}
>
> 			*String = "AccessoryPoint3"
>
> 			{
>
> 				*DisplayName	=	"Hotpoint3"
>
> 				*Value			=	""
>
> 				*Comment		=	"The hotpoint to attach the accessory to"
>
> 			}
>
> 
>
> 		}
>
> 
>
> 		*Group = "Path Speed Match"
>
> 		{
>
> 			*Comment = "Path Speed Match"
>
> 
>
> 			*BOOL = "PSMONOFF"
>
> 			{
>
> 				*VALUE	= "False"
>
> 				*DISPLAYNAME = "Enable"
>
> 				*Comment = "Should this actor speed match with the player?"
>
> 			}
>
> 
>
> 			*FLOAT = "PSMPOS"
>
> 			{
>
> 				*VALUE	= 30.0f
>
> 				*DISPLAYNAME = "Infont/Behind position (meters)"
>
> 				*Comment = "Offset that this actor will stay compared to the player. "
>
> 				*Comment = "i.e."
>
> 				*Comment = "If this value is 10.0f then this actor will try and stay 10 meters ahead of the player."
>
> 				*Comment = "If this value is -20.0f then this actor will try and stay 20 meters behind the player."
>
> 			}
>
> 
>
> 			*FLOAT = "PSMACCEL"
>
> 			{
>
> 				*VALUE	= 0.15f
>
> 				*MIN	= 0.0f
>
> 				*DISPLAYNAME = "Accel"
>
> 				*Comment = "Rate at which this actor will accelerate to match get into position."
>
> 			}
>
> 
>
> 			*FLOAT = "PSMDECEL"
>
> 			{
>
> 				*VALUE	= 0.15f
>
> 				*MIN	= 0.0f
>
> 				*DISPLAYNAME = "Decel"
>
> 				*Comment = "Rate at which this actor will Decelerate to match get into position."
>
> 			}
>
> 		}
>
> 	}
>
> }
>
> 
>
> 
>
> *OBJECT = "Rocket1Actor"
>
> {
>
> 	*NAME = "Rocket1Actor"
>
> 	*INHERITS = "Actor"
>
> 	*TYPE = "OBJECT"
>
> 	*UseInActorEd = "True"
>
> 	*Variables	= 
>
> 	{
>
> 	        *FilePick           =   "ShellName"
>
>         	{
>
> 	            *DisplayName    =   "Shell Name"
>
>         	    *Value          =   ""
>
> 	            *Directory      =   "$\Data\Particle\"
>
>         	    *Extension      =   "par"
>
> 	            *Extension      =   "eff"
>
> 			*Comment		=	"The particle used for the basic ordinance shell."
>
> 	        }
>
> 	        *FilePick           =   "ExplosionName"
>
>         	{
>
> 	            *DisplayName    =   "Explosion Name"
>
>         	    *Value          =   ""
>
> 	            *Directory      =   "$\Data\Particle\"
>
> 	            *Extension      =   "par"
>
> 	            *Extension      =   "eff"
>
> 			*Comment		=	"The particle used for the collision explosion."
>
> 	        }
>
> 	        *FilePick           =   "BallisticName"
>
>         	{
>
> 			*DisplayName    =   "Ballistic Name"
>
> 			*Value          =   ""
>
> 			*Directory      =   "$\Data\Particle\"
>
> 			*Extension      =   "par"
>
> 			*Extension      =   "eff"
>
> 			*Comment		=	"The particle used for the travelling rocket."
>
> 	        }
>
> 		*Float		= "Speed"
>
> 		{
>
> 			*Value 		= 0.3f
>
> 			*DISPLAYNAME	= "Rocket Speed"
>
> 			*Comment	= "Velocity that the Rocket uses."
>
> 		}
>
> 		*Float		= "MaxTurn"
>
> 		{
>
> 			*Value 		= 0.2f
>
> 			*DISPLAYNAME	= "Max Turn Rate"
>
> 			*Comment	= "Maximum angle percentage a rocket can turn per update."
>
> 			*Comment	= "(1.0 == aim right at enemy . . . 0.0 == never turn his way)"
>
> 		}
>
> 	}
>
> }
>
> 
>
> *OBJECT = "Rocket2Actor"
>
> {
>
> 	*NAME = "Rocket2Actor"
>
> 	*INHERITS = "Actor"
>
> 	*TYPE = "OBJECT"
>
> 	*UseInActorEd = "True"
>
> }
>
> 
>
> *OBJECT = "Rocket3Actor"
>
> {
>
> 	*NAME = "Rocket3Actor"
>
> 	*INHERITS = "Actor"
>
> 	*TYPE = "OBJECT"
>
> 	*UseInActorEd = "True"
>
> 
>
> 	*Variables	= 
>
> 	{
>
> 	        *FilePick           =   "ExplosionName"
>
>         	{
>
> 			*DisplayName    =   "Explosion Name"
>
> 			*Value          =   ""
>
> 			*Directory      =   "$\Data\Particle\"
>
> 			*Extension      =   "par"
>
> 			*Extension      =   "eff"
>
> 			*Comment		=	"The particle used for the SwarmBore Explosion."
>
> 	        }
>
> 	        *FilePick           =   "BoreActorName"
>
>         	{
>
> 			*DisplayName    =   "Bore Actor Name"
>
> 			*Value          =   ""
>
> 			*Directory      =   "$\Data\Actors\"
>
> 			*Extension      =   "atr"
>
> 			*Comment		=	"The actor used to control the swarm bore."
>
> 	        }
>
> 		*Float		= "Speed"
>
> 		{
>
> 			*Value 		= 0.3f
>
> 			*DISPLAYNAME	= "Rocket Speed"
>
> 			*Comment	= "Velocity that the Rocket uses."
>
> 		}
>
> 		*Float		= "MaxTurn"
>
> 		{
>
> 			*Value 		= 0.2f
>
> 			*DISPLAYNAME	= "Max Turn Rate"
>
> 			*Comment	= "Maximum angle percentage a rocket can turn per update."
>
> 			*Comment	= "(1.0 == aim right at enemy . . . 0.0 == never turn his way)"
>
> 		}
>
> 	}
>
> }
>
> 
>
> *OBJECT = "SwarmBore"
>
> {
>
> 	*NAME = "SwarmBore"
>
> 	*INHERITS = "Actor"
>
> 	*TYPE = "OBJECT"
>
> 	*UseInActorEd = "True"
>
> 
>
> 	*Variables	= 
>
> 	{
>
> 	        *FilePick           =   "FlareParticle"
>
>         	{
>
> 			*DisplayName    =   "Flare Particle Name"
>
> 			*Value          =   ""
>
> 			*Directory      =   "$\Data\Particle\"
>
> 			*Extension      =   "par"
>
> 			*Extension      =   "eff"
>
> 			*Comment		=	"The particle used for the travelling SwarmBore."
>
> 	        }
>
> 		*Float		= "Speed"
>
> 		{
>
> 			*Value 		= 0.3f
>
> 			*DISPLAYNAME	= "Rocket Speed"
>
> 			*Comment	= "Velocity that the Rocket uses."
>
> 		}
>
> 		*Float		= "MaxTurn"
>
> 		{
>
> 			*Value 		= 0.2f
>
> 			*DISPLAYNAME	= "Max Turn Rate"
>
> 			*Comment	= "Maximum angle percentage a rocket can turn per update."
>
> 			*Comment	= "(1.0 == aim right at enemy . . . 0.0 == never turn his way)"
>
> 		}
>
> 	}
>
> }
>
> 
>
> *OBJECT = "SmartBullet"
>
> {
>
> 	*NAME = "SmartBullet"
>
> 	*INHERITS = "Actor"
>
> 	*TYPE = "OBJECT"
>
> 	*UseInActorEd = "True"
>
> 
>
> 	*Variables	= 
>
> 	{
>
> 		*Float		= "Speed"
>
> 		{
>
> 			*Value 		= 0.3f
>
> 			*DISPLAYNAME	= "Rocket Speed"
>
> 			*Comment	= "Velocity that the Rocket uses."
>
> 		}
>
> 		*Float		= "MaxTurn"
>
> 		{
>
> 			*Value 		= 0.2f
>
> 			*DISPLAYNAME	= "Max Turn Rate"
>
> 			*Comment	= "Maximum angle percentage a rocket can turn per update."
>
> 			*Comment	= "(1.0 == aim right at enemy . . . 0.0 == never turn his way)"
>
> 		}
>
> 	}
>
> }
>
> 
>
> 
>
> *OBJECT = "WeaponWheelMesh"
>
> {
>
> 	*NAME = "WeaponWheelMesh"
>
> 	*INHERITS = "Actor"
>
> 	*TYPE = "OBJECT"
>
> 	*UseInActorEd = "True"
>
> }
>
> 
>
> 
>
> 
>
> *OBJECT = "RocketPteranadonActor"
>
> {
>
> 	*NAME = "RocketPteranadon"
>
> 	*INHERITS = "Actor"
>
> 	*TYPE = "OBJECT"
>
> 	*UseInActorEd = "True"
>
> }
>
> 
>
> *OBJECT = "SkyObject"
>
> {
>
> 	*NAME = "Sky"
>
> 	*INHERITS = "Actor"
>
> 	*TYPE = "OBJECT"
>
> 	*UseInActorEd = "True"
>
> 
>
> 	*Group = "Location Offset"
>
> 	{
>
> 		*FLOAT = "X"
>
> 		{
>
> 			*VALUE	= 0
>
> 			*MIN	= -100000000000
>
> 			*DISPLAYNAME = "X"
>
> 			*DISPLAYASDISC = "255,0,0"
>
> 			*Comment = "Offset for sky sphere based on TalSet's eyeheight."
>
> 		}
>
> 		*FLOAT = "Y"
>
> 		{
>
> 			*VALUE	= 0
>
> 			*MIN	= -100000000000
>
> 			*DISPLAYNAME = "Y"
>
> 			*DISPLAYASDISC = "255,0,0"
>
> 			*Comment = "Offset for sky sphere based on TalSet's eyeheight."
>
> 		}
>
> 		*FLOAT = "Z"
>
> 		{
>
> 			*VALUE	= 0
>
> 			*MIN	= -100000000000
>
> 			*DISPLAYNAME = "Z"
>
> 			*DISPLAYASDISC = "255,0,0"
>
> 			*Comment = "Offset for sky sphere based on TalSet's eyeheight."
>
> 		}
>
> 	}
>
> }
>
> 
>
> *OBJECT = "Lock2DObject"
>
> {
>
> 	*NAME = "Lock2D"
>
> 	*INHERITS = "Actor"
>
> 	*TYPE = "OBJECT"
>
> 	*UseInActorEd = "True"
>
> 
>
> 	*Group = "Location"
>
> 	{
>
> 		*FLOAT = "X"
>
> 		{
>
> 			*VALUE	= 0
>
> 			*MIN	= 0
>
> 			*DISPLAYNAME = "X"
>
> 			*DISPLAYASDISC = "255,0,0"
>
> 			*Comment = "Location for TalSet to always stand in."
>
> 		}
>
> 		*FLOAT = "Y"
>
> 		{
>
> 			*VALUE	= 0
>
> 			*MIN	= 0
>
> 			*DISPLAYNAME = "Y"
>
> 			*DISPLAYASDISC = "255,0,0"
>
> 			*Comment = "Location for TalSet to always stand in."
>
> 		}
>
> 		*FLOAT = "Z"
>
> 		{
>
> 			*VALUE	= 0
>
> 			*MIN	= 0
>
> 			*DISPLAYNAME = "Z"
>
> 			*DISPLAYASDISC = "255,0,0"
>
> 			*Comment = "Location for TalSet to always stand in."
>
> 		}
>
> 	}
>
> 	*Group = "Direction"
>
> 	{
>
> 		*FLOAT = "Pitch"
>
> 		{
>
> 			*VALUE	= 0
>
> 			*MIN	= 0
>
> 			*DISPLAYNAME = "Pitch"
>
> 			*DISPLAYASDISC = "255,0,0"
>
> 			*Comment = "Direction TalSet will always face."
>
> 		}
>
> 		*FLOAT = "Yaw"
>
> 		{
>
> 			*VALUE	= 0
>
> 			*MIN	= 0
>
> 			*DISPLAYNAME = "Yaw"
>
> 			*DISPLAYASDISC = "255,0,0"
>
> 			*Comment = "Direction TalSet will always face."
>
> 		}
>
> 		*FLOAT = "Roll"
>
> 		{
>
> 			*VALUE	= 0
>
> 			*MIN	= 0
>
> 			*DISPLAYNAME = "Roll"
>
> 			*DISPLAYASDISC = "255,0,0"
>
> 			*Comment = "Direction TalSet will always face."
>
> 		}
>
> 	}
>
> }
>
> 
>
> 
>
> ;------------------------------------------------------------------------------
>
> ; Enemy AI
>
> ;------------------------------------------------------------------------------
>
> *OBJECT = "EnemyAIObject"
>
> {
>
> 	*NAME	= "EnemyAI"
>
> 	*INHERITS = "TurokAIObject"
>
> 	*TYPE	= "OBJECT"
>
> 
>
> 	*AIMODES = 
>
> 	{
>
> 		Idle,
>
> 		AlertIdle,
>
> 		CrouchIdle,
>
> 		ProneIdle,
>
> 		RotateLeft,
>
> 		RotateRight,
>
> 		AlertRotateLeft,
>
> 		AlertRotateRight,
>
> 		StandingSleep,
>
> 		Walk,
>
> 		AlertWalk,
>
> 		CrouchWalk,
>
> 		ProneCrawl,
>
> 		Run,
>
> 		AlertRun,
>
> 		FireRun,
>
> 		FireStarter,
>
> 		FireDeath,
>
> 		Fall,
>
> 		ExaggeratedFall,
>
> 		FallDeath,
>
> 		Jump,
>
> 		Climb,
>
> 		ClimbEnd,
>
> 		HangClimb,
>
> 		Damaged,
>
> 		Death,
>
> 		PoisonDamage,
>
> 		PoisonDeath,
>
> 		ExplosionDeath,
>
> 		ExplosionDamage,
>
> 		ImplodeDeath,
>
> 		GravityHeld,
>
> 		Attack,
>
> 		SecondAttack,
>
> 		ThirdAttack,
>
> 		FourthAttack,
>
> 		FifthAttack,
>
> 		CrouchAttack,
>
> 		ProneAttack,
>
> 		UnderwaterIdle,
>
> 		UnderwaterSwim,
>
> 		WatersurfaceIdle,
>
> 		WatersurfaceSwim,
>
> 		SwimmingAttack,
>
> 		SquatIdle,
>
> 		Taunt,
>
> 		Talk,
>
> 		Special1,
>
> 		Special2,
>
> 		Special3,
>
> 		Special4
>
> 	}
>
> 
>
> 	*VARIABLES = 
>
> 	{
>
> 
>
> 		*Group = "Detection"
>
> 		{
>
> 			*Comment = "Sight, sound and smell detection parameters."
>
> 
>
> 			*BOOL = "IGNOREPLAYER"
>
> 			{
>
> 				*VALUE	= "False"
>
> 				*DISPLAYNAME = "Ignore Player?"
>
> 				*Comment = "No detection.  Ignores player."
>
> 			}
>
> 
>
> 			*BOOL = "ProvokeOnly"
>
> 			{
>
> 				*VALUE	= "False"
>
> 				*DISPLAYNAME = "Respond Only To Provoked"
>
> 				*Comment = "AI only selects a target when attacked by it."
>
> 			}
>
> 
>
> 			*BOOL = "CONEVISION"
>
> 			{
>
> 				*VALUE	= "True"
>
> 				*DISPLAYNAME = "Cone Vision?"
>
> 				*Comment = "True for forward cone sight."
>
> 				*Comment = "False for 360 degree sight."
>
> 			}
>
> 
>
> 
>
> 			*FLOAT = "SIGHTRADIUS"
>
> 			{
>
> 				*VALUE	= 20
>
> 				*MIN	= 0
>
> 				*DISPLAYNAME = "Sight Radius"
>
> 				*DISPLAYASDISC = "255,0,0"
>
> 				*Comment = "Distance the AI can see."
>
> 			}
>
> 
>
> 			*FLOAT = "SXZAngle"
>
> 			{
>
> 				*VALUE	= 90
>
> 				*MIN	= 0
>
> 				*DISPLAYNAME = "Cone XZ Angle"
>
> 				*Comment = "XZ Angle for cone vision."
>
> 			}
>
> 
>
> 			*FLOAT = "SYAngle"
>
> 			{
>
> 				*VALUE	= 45
>
> 				*MIN	= 0
>
> 				*DISPLAYNAME = "Cone Y Angle"
>
> 				*Comment = "Y Angle for cone vision."
>
> 			}
>
> 
>
> 			*FLOAT = "SOUNDRADIUS"
>
> 			{
>
> 				*VALUE	= 30
>
> 				*MIN	= 0
>
> 				*DISPLAYNAME = "Sound Radius"
>
> 				*DISPLAYASDISC = "205,120,30"
>
> 				*Comment = "Distance the AI can hear."
>
> 			}
>
> 
>
> 			*FLOAT = "LostContactResetTime"
>
> 			{
>
> 				*VALUE			= -1.0
>
> 				*DISPLAYNAME	= "Lost Contact Reset Time"
>
> 			}
>
> 
>
> 			*BOOL = "IgnAlBox"
>
> 			{
>
> 				*VALUE	= "false"
>
> 				*DISPLAYNAME = "Ignore Alarm Boxes?"
>
> 				*Comment = "True - ignores alarms"
>
> 				*Comment = "False - responds to alarms."
>
> 			}
>
> 
>
> 			*BOOL = "OnlyPTarget"
>
> 			{
>
> 				*VALUE	= "false"
>
> 				*DISPLAYNAME = "Only Player Target"
>
> 				*Comment = "True - The player is the only actor that will be considered for targetting"
>
> 				*Comment = "False - Or not."
>
> 			}
>
> 
>
> 
>
> 			*BOOL = "HasPTarget"
>
> 			{
>
> 				*VALUE	= "false"
>
> 				*DISPLAYNAME = "Always Detects Player"
>
> 				*Comment = "True - Always detects player as a target, even if it can't normally detect him"
>
> 				*Comment = "False - Or not."
>
> 			}
>
> 
>
> 			*BOOL = "HasSTarget"
>
> 			{
>
> 				*VALUE	= "false"
>
> 				*DISPLAYNAME = "Shooter is Target"
>
> 				*Comment = "True - Has shooter as a target, even if it can't normally detect him"
>
> 				*Comment = "False - Or not."
>
> 			}
>
> 
>
> 		}
>
> 
>
> 		*Group = "Movement"
>
> 		{
>
> 			*Comment = "Movement parameters."
>
> 
>
> 			*FLOAT = "MovementSpeed"
>
> 			{
>
> 				*VALUE	= 2.2
>
> 				*MIN	= 0
>
> 				*DISPLAYNAME = "Movement Speed"
>
> 				*Comment = "Running Movement speed in m/s."
>
> 			}
>
> 
>
> 			*FLOAT = "SlowMovementSpeed"
>
> 			{
>
> 				*VALUE	= 1.0
>
> 				*MIN	= 0
>
> 				*DISPLAYNAME = "Slow Movement Speed"
>
> 				*Comment = "Walking Movement speed in m/s."
>
> 			}
>
> 
>
> 			*FLOAT = "TurningSpeed"
>
> 			{
>
> 				*VALUE	= 180
>
> 				*MIN	= 0
>
> 				*DISPLAYNAME = "Turning Speed"
>
> 				*Comment = "Turning speed in degrees/s."
>
> 			}
>
> 
>
> 			*FLOAT = "PitchSpeed"
>
> 			{
>
> 				*VALUE	= 180
>
> 				*MIN	= 0
>
> 				*DISPLAYNAME = "Pitch Speed"
>
> 				*Comment = "Pitch speed in degrees/s."
>
> 			}
>
> 
>
> 			*BOOL = "SlowTurn"
>
> 			{
>
> 				*VALUE	= "False"
>
> 				*DISPLAYNAME = "Slow Moving Turn?"
>
> 			}
>
> 
>
> 			*BOOL = "AlwaysRun"
>
> 			{
>
> 				*VALUE	= "False"
>
> 				*DISPLAYNAME = "Always Run?"
>
> 			}
>
> 
>
> 			*BOOL = "AlwaysWalk"
>
> 			{
>
> 				*VALUE	= "False"
>
> 				*DISPLAYNAME = "Always Walk?"
>
> 			}
>
> 
>
> 			*BOOL = "CanCrawl"
>
> 			{
>
> 				*Usage			= "Protected"
>
> 				*VALUE	= "False"
>
> 				*DISPLAYNAME = "Can Crawl?"
>
> 				*Comment = "True if AI can use crawl links."
>
> 			}
>
> 
>
> 			*BOOL = "DFTurrets"
>
> 			{
>
> 				*VALUE	= "false"
>
> 				*DISPLAYNAME = "Drop for Turrets?"
>
> 				*Comment = "True - drops to avoid turrets"
>
> 				*Comment = "False - dont drop for turrets."
>
> 			}
>
> 
>
> 			*BOOL = "AIAvoid"
>
> 			{
>
> 				*VALUE	= "True"
>
> 				*DISPLAYNAME = "AI Avoidance?"
>
> 			}
>
> 
>
> 			*BOOL = "CantBePushed"
>
> 			{
>
> 				*VALUE	= "false"
>
> 				*DISPLAYNAME = "Cant Be Pushed"
>
> 				*Comment = "True - AI cant be Force pushed"
>
> 				*Comment = "False - AI can be pushed."
>
> 			}
>
> 
>
> 			*Group = "Climbing"
>
> 			{
>
> 				*BOOL = "CanClimb"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE	= "False"
>
> 					*DISPLAYNAME = "Can Climb?"
>
> 					*Comment = "True if AI can scale climbable surfaces."
>
> 				}
>
> 
>
> 				*BOOL = "CanMonkeyClimb"
>
> 				{
>
> 					*VALUE	= "False"
>
> 					*DISPLAYNAME = "Can Monkey Climb?"
>
> 					*Comment = "True if AI can use monkeybar climbable surfaces."
>
> 				}
>
> 
>
> 				*FLOAT = "ClimbEndHeight"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= 1.0
>
> 					*DISPLAYNAME	= "ClimbEndHeight"
>
> 				}
>
> 			}
>
> 
>
> 			*Group = "Swimming"
>
> 			{
>
> 				*BOOL = "CanSwim"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE	= "False"
>
> 					*DISPLAYNAME = "Can Swim?"
>
> 					*Comment = "True if AI can swim in water."
>
> 				}
>
> 
>
> 				*FLOAT = "FastSwimmingSpeed"
>
> 				{
>
> 					*VALUE	= 3.0
>
> 					*MIN	= 0
>
> 					*DISPLAYNAME = "Fast Swimming Speed"
>
> 					*Comment = "Fast Swimming speed in m/s."
>
> 				}
>
> 
>
> 				*FLOAT = "SlowSwimmingSpeed"
>
> 				{
>
> 					*VALUE	= 1.0
>
> 					*MIN	= 0
>
> 					*DISPLAYNAME = "Slow Swimming Speed"
>
> 					*Comment = "Slow Swimming speed in m/s."
>
> 				}
>
> 			}
>
> 
>
> 		}
>
> 
>
> 		*Group = "Leash"
>
> 		{
>
> 			*BOOL = "LEASHED"
>
> 			{
>
> 				*VALUE	= "False"
>
> 				*DISPLAYNAME = "Leashed to point?"
>
> 				*Comment = "True if AI stays within the leash radius"
>
> 				*Comment = "of its creation spot."
>
> 			}
>
> 
>
> 			*FLOAT = "LEASHRADIUS"
>
> 			{
>
> 				*VALUE	= 50
>
> 				*MIN	= 0
>
> 				*DISPLAYNAME = "Leash Radius"
>
> 				*DISPLAYASDISC = "155,30,140"
>
> 			}
>
> 
>
> 			*BOOL = "LeashedToRegion"
>
> 			{
>
> 				*VALUE	= "False"
>
> 				*DISPLAYNAME = "Leashed to region?"
>
> 				*Comment = "True if AI stays within the smallest region "
>
> 				*Comment = "surrounding it at creation."
>
> 			}
>
> 
>
> 			*BOOL = "RegionTargets"
>
> 			{
>
> 				*VALUE	= "False"
>
> 				*DISPLAYNAME = "Ignore Targets?"
>
> 				*Comment = "True if AI ignores targets outside its leash"
>
> 			}
>
> 
>
> 			*FLOAT = "FleeR"
>
> 			{
>
> 				*VALUE	= 20
>
> 				*MIN	= 0
>
> 				*DISPLAYNAME = "Flee Radius"
>
> 			}
>
> 
>
> 		}
>
> 
>
> 		*Group = "Cover"
>
> 		{
>
> 
>
> 			*FLOAT = "COVERRADIUS"
>
> 			{
>
> 				*VALUE	= 40
>
> 				*MIN	= 0
>
> 				*DISPLAYNAME = "Cover Radius"
>
> ;				 *DISPLAYASDISC = "155,30,140"
>
> 				*Comment = "The max distance the AI will seek out a cover position."
>
> 			}
>
> 
>
> 			*Int = "MinCoverShots"
>
> 			{
>
> 				*VALUE	= 1
>
> 				*MIN	= 1
>
> 				*DISPLAYNAME = "Min Shots"
>
> 			}
>
> 
>
> 			*Int = "MaxCoverShots"
>
> 			{
>
> 				*VALUE	= 1
>
> 				*MIN	= 1
>
> 				*DISPLAYNAME = "Max Shots"
>
> 			}
>
> 
>
> 			*BOOL = "CUCCover"
>
> 			{
>
> 				*VALUE	= "true"
>
> 				*DISPLAYNAME = "Use Circle Cover"
>
> 			}
>
> 
>
> 			*BOOL = "CUUCover"
>
> 			{
>
> 				*VALUE	= "true"
>
> 				*DISPLAYNAME = "Use PopUp Cover"
>
> 			}
>
> 
>
> 			*BOOL = "CUOCover"
>
> 			{
>
> 				*VALUE	= "true"
>
> 				*DISPLAYNAME = "Use PopOut Cover"
>
> 			}
>
> 
>
> 		}
>
> 
>
> 
>
> 		*Group = "Logic"
>
> 		{
>
> 			*Comment = "AI Logic Parameters"
>
> 
>
> 			*INT = "LogicInitialAttackChance"
>
> 			{
>
> 				*VALUE			= 1
>
> 				*MIN			= 0
>
> 				*DISPLAYNAME	= "Intial Attack Chance"
>
> 			}
>
> 
>
> 			*INT = "LogicAttackChance"
>
> 			{
>
> 				*VALUE			= 1
>
> 				*MIN			= 0
>
> 				*DISPLAYNAME	= "Attack Chance"
>
> 			}
>
> 
>
> 			*BOOL = "WANTSCOVER"
>
> 			{
>
> 				*VALUE	= "False"
>
> 				*DISPLAYNAME = "Seeks Cover?"
>
> 				*Comment = "True if AI seeks out cover when threatened."
>
> 			}
>
> 
>
> 			*INT = "LogicInitialCoverChance"
>
> 			{
>
> 				*VALUE			= 0
>
> 				*MIN			= 0
>
> 				*DISPLAYNAME	= "Initial Cover Chance"
>
> 			}
>
> 
>
> 			*INT = "LogicCoverChance"
>
> 			{
>
> 				*VALUE			= 0
>
> 				*MIN			= 0
>
> 				*DISPLAYNAME	= "Cover Chance"
>
> 			}
>
> 
>
> 			*FLOAT = "BreachRadius"
>
> 			{
>
> 				*VALUE			= -1.0
>
> 				*DISPLAYNAME	= "Breach Radius"
>
> 				*Comment		= "Use -1 for no breach"
>
> 			}
>
> 
>
> 			*BOOL = "AttackOnBreach"
>
> 			{
>
> 				*VALUE	= "False"
>
> 				*DISPLAYNAME = "Attack On Breach"
>
> 				*Comment = "True if AI switches to attack when player within the breach radius"
>
> 			}
>
> 
>
> 			*FLOAT = "AttackResetTime"
>
> 			{
>
> 				*VALUE			= -1.0
>
> 				*DISPLAYNAME	= "Attack Reset Time"
>
> 				*Comment		= "The time in attack mode before a new attack logic is selected."
>
> 				*Comment		= "Use -1 for never resetting."
>
> 			}
>
> 
>
> 			*FLOAT = "DamageLogicChangeAmount"
>
> 			{
>
> 				*VALUE			= -1.0
>
> 				*DISPLAYNAME	= "Damage Logic Change"
>
> 			}
>
> 
>
> 			*FLOAT = "FearfulThreshhold"
>
> 			{
>
> 				*VALUE			= -1.0
>
> 				*DISPLAYNAME	= "Fearful Threshhold"
>
> 				*Comment		= "The health level below which the AI will be fearful."
>
> 			}
>
> 
>
> 			*FLOAT = "CriticalThreshhold"
>
> 			{
>
> 				*VALUE			= -1.0
>
> 				*DISPLAYNAME	= "Critical Threshhold"
>
> 				*Comment		= "The health level below which the AI will sellect critical damage logic."
>
> 			}
>
> 
>
> 			*Group = "Critical Logic"
>
> 			{
>
> 				*INT = "CritNoChange"
>
> 				{
>
> 					*VALUE			= 1
>
> 					*MIN			= 0
>
> 					*DISPLAYNAME	= "No Change Chance"
>
> 				}
>
> 
>
> 				*INT = "CritFlee"
>
> 				{
>
> 					*VALUE			= 0
>
> 					*MIN			= 0
>
> 					*DISPLAYNAME	= "Flee Chance"
>
> 				}
>
> 
>
> 				*INT = "CritRetreat"
>
> 				{
>
> 					*VALUE			= 0
>
> 					*MIN			= 0
>
> 					*DISPLAYNAME	= "Retreat Chance"
>
> 				}
>
> 
>
> 				*INT = "CritKamikaze"
>
> 				{
>
> 					*VALUE			= 0
>
> 					*MIN			= 0
>
> 					*DISPLAYNAME	= "Kamikaze Chance"
>
> 				}
>
> 
>
> 				*INT = "CritSurrender"
>
> 				{
>
> 					*VALUE			= 0
>
> 					*MIN			= 0
>
> 					*DISPLAYNAME	= "Surrender Chance"
>
> 				}
>
> 
>
> 				*INT = "CritCover"
>
> 				{
>
> 					*VALUE			= 0
>
> 					*MIN			= 0
>
> 					*DISPLAYNAME	= "Cover Chance"
>
> 				}
>
> 
>
> 				*INT = "CritProne"
>
> 				{
>
> 					*VALUE			= 0
>
> 					*MIN			= 0
>
> 					*DISPLAYNAME	= "Prone Chance"
>
> 				}
>
> 
>
> 			}
>
> 
>
> 			*Combo = "SGR"
>
> 			{
>
> 				*Usage			= "Protected"
>
> 				*DisplayName	=	"Sticky Grenade"
>
> 				*Value			=	0
>
> 				*ComboList		=
>
> 				{
>
> 					"No Change",
>
> 					"Flee",
>
> 					"Kamikaze"
>
> 				}
>
> 			}
>
> 		}
>
> 
>
> 
>
> 		*Group = "Attack"
>
> 		{
>
> 			*Comment = "Attacking parameters."
>
> 
>
> 			*Group = "Primary Attack"
>
> 			{
>
> 				*FilePick = "WeaponName1"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*DISPLAYNAME = "Weapon"
>
> 					*Value			=	""
>
> 					*Directory      =   "$\Data\Actors\EnemyWeapons"
>
> 					*Extension      =   "atr"
>
> 				}
>
> 
>
> 				*BOOL = "UsePrimary1"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE	= "True"
>
> 					*DISPLAYNAME = "Uses Primary Weapon"
>
> 				}
>
> 
>
> 				*String = "WeaponPoint1"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*DisplayName	=	"Hotpoint"
>
> 					*Value			=	""
>
> 					*Comment		=	"The hotpoint to attach the weapon to"
>
> 				}
>
> 
>
> 				*FLOAT = "WeaponRange1"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE	= 20
>
> 					*MIN	= 0
>
> 					*DISPLAYNAME = "Attack Range"
>
> 				}
>
> 			}
>
> 
>
> 			*Group = "Second Attack"
>
> 			{
>
> 				*FilePick = "WeaponName2"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*DISPLAYNAME = "Weapon"
>
> 					*Value			=	""
>
> 					*Directory      =   "$\Data\Actors\EnemyWeapons"
>
> 					*Extension      =   "atr"
>
> 				}
>
> 
>
> 				*BOOL = "UsePrimary2"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE	= "False"
>
> 					*DISPLAYNAME = "Uses Primary Weapon"
>
> 				}
>
> 
>
> 				*String = "WeaponPoint2"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*DisplayName	=	"Hotpoint"
>
> 					*Value			=	""
>
> 					*Comment		=	"The hotpoint to attach the weapon to"
>
> 				}
>
> 
>
> 				*FLOAT = "WeaponRange2"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE	= 20
>
> 					*MIN	= 0
>
> 					*DISPLAYNAME = "Attack Range"
>
> 				}
>
> 			}
>
> 
>
> 			*Group = "Third Attack"
>
> 			{
>
> 				*FilePick = "WeaponName3"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*DISPLAYNAME = "Weapon"
>
> 					*Value			=	""
>
> 					*Directory      =   "$\Data\Actors\EnemyWeapons"
>
> 					*Extension      =   "atr"
>
> 				}
>
> 
>
> 				*BOOL = "UsePrimary3"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE	= "False"
>
> 					*DISPLAYNAME = "Uses Primary Weapon"
>
> 				}
>
> 
>
> 				*String = "WeaponPoint3"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*DisplayName	=	"Hotpoint"
>
> 					*Value			=	""
>
> 					*Comment		=	"The hotpoint to attach the weapon to"
>
> 				}
>
> 
>
> 				*FLOAT = "WeaponRange3"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE	= 20
>
> 					*MIN	= 0
>
> 					*DISPLAYNAME = "Attack Range"
>
> 				}
>
> 			}
>
> 
>
> 			*Group = "Fourth Attack"
>
> 			{
>
> 				*FilePick = "WeaponName4"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*DISPLAYNAME = "Weapon"
>
> 					*Value			=	""
>
> 					*Directory      =   "$\Data\Actors\EnemyWeapons"
>
> 					*Extension      =   "atr"
>
> 				}
>
> 
>
> 				*BOOL = "UsePrimary4"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE	= "False"
>
> 					*DISPLAYNAME = "Uses Primary Weapon"
>
> 				}
>
> 
>
> 				*String = "WeaponPoint4"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*DisplayName	=	"Hotpoint"
>
> 					*Value			=	""
>
> 					*Comment		=	"The hotpoint to attach the weapon to"
>
> 				}
>
> 
>
> 				*FLOAT = "WeaponRange4"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE	= 20
>
> 					*MIN	= 0
>
> 					*DISPLAYNAME = "Attack Range"
>
> 				}
>
> 
>
> 			}
>
> 
>
> 			*Group = "Fifth Attack"
>
> 			{
>
> 				*FilePick = "WeaponName5"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*DISPLAYNAME = "Weapon"
>
> 					*Value			=	""
>
> 					*Directory      =   "$\Data\Actors\EnemyWeapons"
>
> 					*Extension      =   "atr"
>
> 				}
>
> 
>
> 				*BOOL = "UsePrimary5"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE	= "False"
>
> 					*DISPLAYNAME = "Uses Primary Weapon"
>
> 				}
>
> 
>
> 				*String = "WeaponPoint5"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*DisplayName	=	"Hotpoint"
>
> 					*Value			=	""
>
> 					*Comment		=	"The hotpoint to attach the weapon to"
>
> 				}
>
> 
>
> 				*FLOAT = "WeaponRange5"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE	= 20
>
> 					*MIN	= 0
>
> 					*DISPLAYNAME = "Attack Range"
>
> 				}
>
> 
>
> 			}
>
> 
>
> 			*Group = "Close Range"
>
> 			{
>
> 				*Comment = "Close Range Attack"
>
> 
>
> 				*INT = "CloseRangeChance"
>
> 				{
>
> 					*VALUE	= 25
>
> 					*MIN	= 0
>
> 					*DISPLAYNAME = "Chance"
>
> 					*Comment = "The chance the AI will select close range attack"
>
> 				}
>
> 
>
> 				*FLOAT = "CloseRangeDist"
>
> 				{
>
> 					*VALUE	= 5
>
> 					*MIN	= 0
>
> 					*DISPLAYNAME = "Distance"
>
> 					*Comment = "The distance from target in close range attack"
>
> 				}
>
> 			}
>
> 
>
> 			*Group = "Medium Range"
>
> 			{
>
> 				*Comment = "Medium Range Attack"
>
> 
>
> 				*INT = "MediumRangeChance"
>
> 				{
>
> 					*VALUE	= 50
>
> 					*MIN	= 0
>
> 					*DISPLAYNAME = "Chance"
>
> 					*Comment = "The chance the AI will select medium range attack"
>
> 				}
>
> 
>
> 				*FLOAT = "MediumRangeDist"
>
> 				{
>
> 					*VALUE	= 15
>
> 					*MIN	= 0
>
> 					*DISPLAYNAME = "Distance"
>
> 					*Comment = "The distance from target in medium range attack"
>
> 				}
>
> 			}
>
> 
>
> 			*Group = "Long Range"
>
> 			{
>
> 				*Comment = "Long Range Attack"
>
> 
>
> 				*INT = "LongRangeChance"
>
> 				{
>
> 					*VALUE	= 25
>
> 					*MIN	= 0
>
> 					*DISPLAYNAME = "Chance"
>
> 					*Comment = "The chance the AI will select long range attack"
>
> 				}
>
> 
>
> 				*FLOAT = "LongRangeDist"
>
> 				{
>
> 					*VALUE	= 30
>
> 					*MIN	= 0
>
> 					*DISPLAYNAME = "Distance"
>
> 					*Comment = "The distance from target in long range attack"
>
> 				}
>
> 			}
>
> 
>
> 			*BOOL = "IsSniper"
>
> 			{
>
> 				*VALUE	= "False"
>
> 				*DISPLAYNAME = "Sniper"
>
> 				*Comment = "The AI will not move from placed spot"
>
> 			}
>
> 
>
> 			*INT = "CrouchAttackChance"
>
> 			{
>
> 				*VALUE	= 0
>
> 				*MIN	= 0
>
> 				*DISPLAYNAME = "Crouch Attack Chance"
>
> 				*Comment = "The chance out of 100 the AI will crouch when attacking"
>
> 			}
>
> 
>
> 			*INT = "ProneAttackChance"
>
> 			{
>
> 				*VALUE	= 0
>
> 				*MIN	= 0
>
> 				*DISPLAYNAME = "Prone Attack Chance"
>
> 				*Comment = "The chance out of 100 the AI will go prone when attacking"
>
> 			}
>
> 
>
> 			*BOOL = "KeepADis"
>
> 			{
>
> 				*VALUE			= "True"
>
> 				*DISPLAYNAME	= "Keep Attack Distance"
>
> 				*Comment		= "Keep distance away from target when in medium or long range attack"
>
> 			}
>
> 
>
> 		}
>
> 
>
> 		*Group = "Head Tracking"
>
> 		{
>
> 			*BOOL = "UseHeadTracking"
>
> 			{
>
> 				*VALUE	= "False"
>
> 				*DISPLAYNAME = "Head Tracking"
>
> 			}
>
> 
>
> 			*Group = "Head"
>
> 			{
>
> 				*int = "HeadBoneIndex"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= -1
>
> 					*DISPLAYNAME	= "BoneIndex"
>
> 				}
>
> 
>
> 				*Combo = "HeadPitchAxis"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*DisplayName	=	"Pitch Axis"
>
> 					*Value			=	2 
>
> 					*ComboList		=
>
> 					{
>
> 						"X+",
>
> 						"X-",
>
> 						"Y+",
>
> 						"Y-",
>
> 						"Z+",
>
> 						"Z-"
>
> 					}
>
> 				}
>
> 
>
> 				*Combo = "HeadYawAxis"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*DisplayName	=	"Yaw Axis"
>
> 					*Value			=	4
>
> 					*ComboList		=
>
> 					{
>
> 						"X+",
>
> 						"X-",
>
> 						"Y+",
>
> 						"Y-",
>
> 						"Z+",
>
> 						"Z-"
>
> 					}
>
> 				}
>
> 
>
> 				*FLOAT = "HeadXFix"
>
> 				{
>
> 					*Usage		= "Protected"
>
> 					*VALUE	= 0
>
> 					*DISPLAYNAME = "X Fix"
>
> 				}
>
> 
>
> 				*FLOAT = "HeadYFix"
>
> 				{
>
> 					*Usage		= "Protected"
>
> 					*VALUE	= 0
>
> 					*DISPLAYNAME = "Y Fix"
>
> 				}
>
> 
>
> 				*FLOAT = "HeadZFix"
>
> 				{
>
> 					*Usage		= "Protected"
>
> 					*VALUE	= 0
>
> 					*DISPLAYNAME = "Z Fix"
>
> 				}
>
> 
>
> 				*FLOAT = "HeadPitchMax"
>
> 				{
>
> 					*Usage		= "Protected"
>
> 					*VALUE	= 0
>
> 					*DISPLAYNAME = "Pitch Max"
>
> 				}
>
> 
>
> 				*FLOAT = "HeadPitchMin"
>
> 				{
>
> 					*Usage		= "Protected"
>
> 					*VALUE	= 0
>
> 					*DISPLAYNAME = "Pitch Min"
>
> 				}
>
> 
>
> 				*FLOAT = "HeadYawMax"
>
> 				{
>
> 					*Usage		= "Protected"
>
> 					*VALUE	= 0
>
> 					*DISPLAYNAME = "Yaw Max"
>
> 				}
>
> 
>
> 				*FLOAT = "HeadYawMin"
>
> 				{
>
> 					*Usage		= "Protected"
>
> 					*VALUE	= 0
>
> 					*DISPLAYNAME = "Yaw Min"
>
> 				}
>
> 
>
> 				*FLOAT = "HeadPitchCorr"
>
> 				{
>
> 					*Usage		= "Protected"
>
> 					*VALUE	= 0
>
> 					*DISPLAYNAME = "Pitch Correction"
>
> 				}
>
> 
>
> 				*FLOAT = "HeadPPCorr"
>
> 				{
>
> 					*Usage		= "Protected"
>
> 					*VALUE	= 0
>
> 					*DISPLAYNAME = "Parent Pitch Correction"
>
> 				}
>
> 
>
> 				*FLOAT = "HeadPYCorr"
>
> 				{
>
> 					*Usage		= "Protected"
>
> 					*VALUE	= 90
>
> 					*DISPLAYNAME = "Parent Yaw Correction"
>
> 				}
>
> 
>
> 			}
>
> 
>
> 
>
> 			*Group = "Spine"
>
> 			{
>
> 				*int = "BackBoneIndex"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= -1
>
> 					*DISPLAYNAME	= "BoneIndex"
>
> 				}
>
> 
>
> 				*Combo = "BackPitchAxis"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*DisplayName	=	"Pitch Axis"
>
> 					*Value			=	2 
>
> 					*ComboList		=
>
> 					{
>
> 						"X+",
>
> 						"X-",
>
> 						"Y+",
>
> 						"Y-",
>
> 						"Z+",
>
> 						"Z-"
>
> 					}
>
> 				}
>
> 
>
> 				*Combo = "BackYawAxis"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*DisplayName	=	"Yaw Axis"
>
> 					*Value			=	4
>
> 					*ComboList		=
>
> 					{
>
> 						"X+",
>
> 						"X-",
>
> 						"Y+",
>
> 						"Y-",
>
> 						"Z+",
>
> 						"Z-"
>
> 					}
>
> 				}
>
> 
>
> 				*FLOAT = "BackXFix"
>
> 				{
>
> 					*Usage		= "Protected"
>
> 					*VALUE	= 0
>
> 					*DISPLAYNAME = "X Fix"
>
> 				}
>
> 
>
> 				*FLOAT = "BackYFix"
>
> 				{
>
> 					*Usage		= "Protected"
>
> 					*VALUE	= 0
>
> 					*DISPLAYNAME = "Y Fix"
>
> 				}
>
> 
>
> 				*FLOAT = "BackZFix"
>
> 				{
>
> 					*Usage		= "Protected"
>
> 					*VALUE	= 0
>
> 					*DISPLAYNAME = "Z Fix"
>
> 				}
>
> 
>
> 				*FLOAT = "BackPitchMax"
>
> 				{
>
> 					*Usage		= "Protected"
>
> 					*VALUE	= 0
>
> 					*DISPLAYNAME = "Pitch Max"
>
> 				}
>
> 
>
> 				*FLOAT = "BackPitchMin"
>
> 				{
>
> 					*Usage		= "Protected"
>
> 					*VALUE	= 0
>
> 					*DISPLAYNAME = "Pitch Min"
>
> 				}
>
> 
>
> 				*FLOAT = "BackYawMax"
>
> 				{
>
> 					*Usage		= "Protected"
>
> 					*VALUE	= 0
>
> 					*DISPLAYNAME = "Yaw Max"
>
> 				}
>
> 
>
> 				*FLOAT = "BackYawMin"
>
> 				{
>
> 					*Usage		= "Protected"
>
> 					*VALUE	= 0
>
> 					*DISPLAYNAME = "Yaw Min"
>
> 				}
>
> 
>
> 				*FLOAT = "BackPitchCorr"
>
> 				{
>
> 					*Usage		= "Protected"
>
> 					*VALUE	= 0
>
> 					*DISPLAYNAME = "Pitch Correction"
>
> 				}
>
> 
>
> 				*FLOAT = "BackPPCorr"
>
> 				{
>
> 					*Usage		= "Protected"
>
> 					*VALUE	= 0
>
> 					*DISPLAYNAME = "Parent Pitch Correction"
>
> 				}
>
> 
>
> 				*FLOAT = "BackPYCorr"
>
> 				{
>
> 					*Usage		= "Protected"
>
> 					*VALUE	= 90
>
> 					*DISPLAYNAME = "Parent Yaw Correction"
>
> 				}
>
> 
>
> 			}
>
> 
>
> 
>
> 
>
> 		}
>
> 
>
> 		*Group = "Tail Tracking"
>
> 		{
>
> 			*BOOL = "UseTailTracking"
>
> 			{
>
> 				*Usage			= "Protected"
>
> 				*VALUE			= "False"
>
> 				*DISPLAYNAME	= "Tail Tracking"
>
> 			}
>
> 
>
> 			*Group = "Base"
>
> 			{
>
> 				*int = "BaseBoneIndex"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= -1
>
> 					*DISPLAYNAME	= "BoneIndex"
>
> 				}
>
> 
>
> 				*Combo = "BasePitchAxis"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*DisplayName	= "Pitch Axis"
>
> 					*Value			= 3 
>
> 					*ComboList		=
>
> 					{
>
> 						"X+",
>
> 						"X-",
>
> 						"Y+",
>
> 						"Y-",
>
> 						"Z+",
>
> 						"Z-"
>
> 					}
>
> 				}
>
> 
>
> 				*Combo = "BaseYawAxis"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*DisplayName	= "Yaw Axis"
>
> 					*Value			= 5
>
> 					*ComboList		=
>
> 					{
>
> 						"X+",
>
> 						"X-",
>
> 						"Y+",
>
> 						"Y-",
>
> 						"Z+",
>
> 						"Z-"
>
> 					}
>
> 				}
>
> 
>
> 				*FLOAT = "BaseXFix"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= -90
>
> 					*DISPLAYNAME	= "X Fix"
>
> 				}
>
> 
>
> 				*FLOAT = "BaseYFix"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= 0
>
> 					*DISPLAYNAME	= "Y Fix"
>
> 				}
>
> 
>
> 				*FLOAT = "BaseZFix"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= -90
>
> 					*DISPLAYNAME	= "Z Fix"
>
> 				}
>
> 
>
> 				*FLOAT = "BasePitchMax"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= 90
>
> 					*DISPLAYNAME	= "Pitch Max"
>
> 				}
>
> 
>
> 				*FLOAT = "BasePitchMin"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= -90
>
> 					*DISPLAYNAME	= "Pitch Min"
>
> 				}
>
> 
>
> 				*FLOAT = "BaseYawMax"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= 180
>
> 					*DISPLAYNAME	= "Yaw Max"
>
> 				}
>
> 
>
> 				*FLOAT = "BaseYawMin"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= -180
>
> 					*DISPLAYNAME	= "Yaw Min"
>
> 				}
>
> 
>
> 				*FLOAT = "BasePitchCorr"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= -20
>
> 					*DISPLAYNAME	= "Pitch Correction"
>
> 				}
>
> 			}
>
> 
>
> 
>
> 			*Group = "NearBase"
>
> 			{
>
> 				*int = "NearBaseBoneIndex"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= -1
>
> 					*DISPLAYNAME	= "BoneIndex"
>
> 				}
>
> 
>
> 				*Combo = "NearBasePitchAxis"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*DisplayName	= "Pitch Axis"
>
> 					*Value			= 3 
>
> 					*ComboList		=
>
> 					{
>
> 						"X+",
>
> 						"X-",
>
> 						"Y+",
>
> 						"Y-",
>
> 						"Z+",
>
> 						"Z-"
>
> 					}
>
> 				}
>
> 
>
> 				*Combo = "NearBaseYawAxis"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*DisplayName	= "Yaw Axis"
>
> 					*Value			= 5
>
> 					*ComboList		=
>
> 					{
>
> 						"X+",
>
> 						"X-",
>
> 						"Y+",
>
> 						"Y-",
>
> 						"Z+",
>
> 						"Z-"
>
> 					}
>
> 				}
>
> 
>
> 				*FLOAT = "NearBaseXFix"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= -90
>
> 					*DISPLAYNAME	= "X Fix"
>
> 				}
>
> 
>
> 				*FLOAT = "NearBaseYFix"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= 0
>
> 					*DISPLAYNAME	= "Y Fix"
>
> 				}
>
> 
>
> 				*FLOAT = "NearBaseZFix"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= -90
>
> 					*DISPLAYNAME	= "Z Fix"
>
> 				}
>
> 
>
> 				*FLOAT = "NearBasePitchMax"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= 20
>
> 					*DISPLAYNAME	= "Pitch Max"
>
> 				}
>
> 
>
> 				*FLOAT = "NearBasePitchMin"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= -20
>
> 					*DISPLAYNAME	= "Pitch Min"
>
> 				}
>
> 
>
> 				*FLOAT = "NearBaseYawMax"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= 30
>
> 					*DISPLAYNAME	= "Yaw Max"
>
> 				}
>
> 
>
> 				*FLOAT = "NearBaseYawMin"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= -30
>
> 					*DISPLAYNAME	= "Yaw Min"
>
> 				}
>
> 
>
> 				*FLOAT = "NearBasePitchCorr"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= 0
>
> 					*DISPLAYNAME	= "Pitch Correction"
>
> 				}
>
> 			}
>
> 
>
> 			*Group = "NearTip"
>
> 			{
>
> 				*int = "NearTipBoneIndex"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= -1
>
> 					*DISPLAYNAME	= "BoneIndex"
>
> 				}
>
> 
>
> 				*Combo = "NearTipPitchAxis"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*DisplayName	= "Pitch Axis"
>
> 					*Value			= 3 
>
> 					*ComboList		=
>
> 					{
>
> 						"X+",
>
> 						"X-",
>
> 						"Y+",
>
> 						"Y-",
>
> 						"Z+",
>
> 						"Z-"
>
> 					}
>
> 				}
>
> 
>
> 				*Combo = "NearTipYawAxis"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*DisplayName	= "Yaw Axis"
>
> 					*Value			= 5
>
> 					*ComboList		=
>
> 					{
>
> 						"X+",
>
> 						"X-",
>
> 						"Y+",
>
> 						"Y-",
>
> 						"Z+",
>
> 						"Z-"
>
> 					}
>
> 				}
>
> 
>
> 				*FLOAT = "NearTipXFix"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= -90
>
> 					*DISPLAYNAME	= "X Fix"
>
> 				}
>
> 
>
> 				*FLOAT = "NearTipYFix"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= 0
>
> 					*DISPLAYNAME	= "Y Fix"
>
> 				}
>
> 
>
> 				*FLOAT = "NearTipZFix"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= -90
>
> 					*DISPLAYNAME	= "Z Fix"
>
> 				}
>
> 
>
> 				*FLOAT = "NearTipPitchMax"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= 30
>
> 					*DISPLAYNAME	= "Pitch Max"
>
> 				}
>
> 
>
> 				*FLOAT = "NearTipPitchMin"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= -30
>
> 					*DISPLAYNAME	= "Pitch Min"
>
> 				}
>
> 
>
> 				*FLOAT = "NearTipYawMax"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= 30
>
> 					*DISPLAYNAME	= "Yaw Max"
>
> 				}
>
> 
>
> 				*FLOAT = "NearTipYawMin"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= -30
>
> 					*DISPLAYNAME	= "Yaw Min"
>
> 				}
>
> 
>
> 				*FLOAT = "NearTipPitchCorr"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= 0
>
> 					*DISPLAYNAME	= "Pitch Correction"
>
> 				}
>
> 			}
>
> 
>
> 			*Group = "Tip"
>
> 			{
>
> 				*int = "TipBoneIndex"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= -1
>
> 					*DISPLAYNAME	= "BoneIndex"
>
> 				}
>
> 
>
> 				*Combo = "TipPitchAxis"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*DisplayName	= "Pitch Axis"
>
> 					*Value			= 3 
>
> 					*ComboList		=
>
> 					{
>
> 						"X+",
>
> 						"X-",
>
> 						"Y+",
>
> 						"Y-",
>
> 						"Z+",
>
> 						"Z-"
>
> 					}
>
> 				}
>
> 
>
> 				*Combo = "TipYawAxis"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*DisplayName	= "Yaw Axis"
>
> 					*Value			= 5
>
> 					*ComboList		=
>
> 					{
>
> 						"X+",
>
> 						"X-",
>
> 						"Y+",
>
> 						"Y-",
>
> 						"Z+",
>
> 						"Z-"
>
> 					}
>
> 				}
>
> 
>
> 				*FLOAT = "TipXFix"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= -90
>
> 					*DISPLAYNAME	= "X Fix"
>
> 				}
>
> 
>
> 				*FLOAT = "TipYFix"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= 0
>
> 					*DISPLAYNAME	= "Y Fix"
>
> 				}
>
> 
>
> 				*FLOAT = "TipZFix"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= -90
>
> 					*DISPLAYNAME	= "Z Fix"
>
> 				}
>
> 
>
> 				*FLOAT = "TipPitchMax"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= 30
>
> 					*DISPLAYNAME	= "Pitch Max"
>
> 				}
>
> 
>
> 				*FLOAT = "TipPitchMin"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= -30
>
> 					*DISPLAYNAME	= "Pitch Min"
>
> 				}
>
> 
>
> 				*FLOAT = "TipYawMax"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= 30
>
> 					*DISPLAYNAME	= "Yaw Max"
>
> 				}
>
> 
>
> 				*FLOAT = "TipYawMin"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= -30
>
> 					*DISPLAYNAME	= "Yaw Min"
>
> 				}
>
> 
>
> 				*FLOAT = "TipPitchCorr"
>
> 				{
>
> 					*Usage			= "Protected"
>
> 					*VALUE			= 0
>
> 					*DISPLAYNAME	= "Pitch Correction"
>
> 				}
>
> 			}
>
> 		}
>
> 
>
> 
>
> 		*String = "InitialState"
>
> 		{
>
> 			*DisplayName	=	"Initial State"
>
> 			*Value			=	""
>
> 			*Comment		=	"The initial state"
>
> 		}
>
> 
>
> 		*String = "InitialMode"
>
> 		{
>
> 			*DisplayName	=	"Initial Mode"
>
> 			*Value			=	""
>
> 			*Comment		=	"The initial Mode"
>
> 		}
>
> 
>
> 		*Combo = "InitialAlert"
>
> 		{
>
> 			*DisplayName	=	"Initial Alert Level"
>
> 			*Value			=	0 
>
> 			*ComboList		=
>
> 			{
>
> 				"None",
>
> 				"Low",
>
> 				"Medium",
>
> 				"High"
>
> 			}
>
> 		}
>
> 
>
> 		*FLOAT = "DefTransBlend"
>
> 		{
>
> 			*VALUE			=	0.266667
>
> 			*DISPLAYNAME	=	"Default Blend"
>
> 			*Comment		=	"Default transition blend time"
>
> 		}
>
> 
>
> 		*Group = "Wander/Search"
>
> 		{
>
> 			*FLOAT = "WTime"
>
> 			{
>
> 				*VALUE			=	-1.0
>
> 				*DISPLAYNAME	=	"Wander Time"
>
> 				*Comment		=	"The time to stay in wander before switching to patrol"
>
> 				*Comment		=	"Use -1 for never switching"
>
> 			}
>
> 
>
> 			*FLOAT = "WPTime"
>
> 			{
>
> 				*VALUE			=	-1.0
>
> 				*DISPLAYNAME	=	"Wander Pause Time"
>
> 				*Comment		=	"The time to pause at wander destination before moving to the next one"
>
> 				*Comment		=	"Use -1 for never switching"
>
> 			}
>
> 
>
> 		}
>
> 
>
> 		*Group = "Death"
>
> 		{
>
> 
>
> 			*BOOL = "ResetWhenDie"
>
> 			{
>
> 				*VALUE	= "False"
>
> 				*DISPLAYNAME = "Reset When Die"
>
> 				*Comment = "True if resets after dying."
>
> 			}
>
> 
>
> 			*FLOAT = "RDelay"
>
> 			{
>
> 				*VALUE			=	-1.0
>
> 				*DISPLAYNAME	=	"Reset Delay"
>
> 				*Comment		=	"The time to delay before resetting"
>
> 				*Comment		=	"Use -1 for no delay"
>
> 			}
>
> 
>
> 			*BOOL = "GibDeath"
>
> 			{
>
> 				*VALUE	= "False"
>
> 				*DISPLAYNAME = "Gib When Die"
>
> 				*Comment = "True if gibs on death."
>
> 			}
>
> 
>
> 			*FilePick = "GibPart"
>
> 			{
>
> 				*DisplayName	=	"Gib Particle"
>
> 				*Value			=	""
>
> 				*Directory      =   "$\Data\Particle\"
>
> 				*Extension      =   "par"
>
> 				*Extension      =   "eff"
>
> 			}
>
> 		}
>
> 
>
>         *Group = "Sound"
>
>         {
>
>             *Sound = "LDSound"
>
>             {
>
>                 *DisplayName    =   "Light Damage Sound"
>
>             }
>
>             *Sound = "MDSound"
>
>             {
>
>                 *DisplayName    =   "Medium Damage Sound"
>
>             }
>
>             *Sound = "HDSound"
>
>             {
>
>                 *DisplayName    =   "Heavy Damage Sound"
>
>             }
>
> 
>
>         }
>
> 
>
> 
>
> 
>
> 		*BOOL = "UseGroundTracking"
>
> 		{
>
> 			*Usage			= "Protected"
>
> 			*VALUE			= "False"
>
> 			*DISPLAYNAME	= "Ground Tracking"
>
> 			*COMMENT		= "AI aligns itself to the slope of the ground."
>
> 		}
>
> 
>
> 		*BOOL = "CanBeSwarmBored"
>
> 		{
>
> 			*Usage			= "Protected"
>
> 			*VALUE	= "True"
>
> 			*DISPLAYNAME = "Can Be Swarm Bored?"
>
> 		}
>
> 
>
> 		*Group = "Spawn Actors"
>
> 		{
>
> 			*Comment = "Actors to spawn when this enemy dies"
>
> 
>
> 			*FilePick = "SpawnActor1"
>
> 			{
>
> 				*DISPLAYNAME = "SpawnActor1"
>
> 				*Value		 = ""
>
> 				*Directory   = "$\Data\Actors"
>
> 				*Extension   = "atr"
>
> 			}
>
> 
>
> 			*FilePick = "SpawnActor2"
>
> 			{
>
> 				*DISPLAYNAME = "SpawnActor2"
>
> 				*Value		 = ""
>
> 				*Directory   = "$\Data\Actors"
>
> 				*Extension   = "atr"
>
> 			}
>
> 
>
> 			*FilePick = "SpawnActor3"
>
> 			{
>
> 				*DISPLAYNAME = "SpawnActor3"
>
> 				*Value		 = ""
>
> 				*Directory   = "$\Data\Actors"
>
> 				*Extension   = "atr"
>
> 			}
>
> 
>
> 			*FilePick = "SpawnActor4"
>
> 			{
>
> 				*DISPLAYNAME = "SpawnActor4"
>
> 				*Value		 = ""
>
> 				*Directory   = "$\Data\Actors"
>
> 				*Extension   = "atr"
>
> 			}
>
> 
>
> 			*FilePick = "SpawnActor5"
>
> 			{
>
> 				*DISPLAYNAME = "SpawnActor5"
>
> 				*Value		 = ""
>
> 				*Directory   = "$\Data\Actors"
>
> 				*Extension   = "atr"
>
> 			}
>
> 
>
> 			*FLOAT	  = "SpawnActor1Velocity"
>
> 			{
>
> 				*VALUE	= 3.0f
>
> 				*DISPLAYNAME = "Actor 1 Velocity"
>
> 				*Comment = "Speed that the first spawned actor moves away from the enemy"
>
> 			}
>
> 
>
> 			*FLOAT	  = "SpawnActor2Velocity"
>
> 			{
>
> 				*VALUE	= 3.0f
>
> 				*DISPLAYNAME = "Actor 2 Velocity"
>
> 				*Comment = "Speed that the second spawned actor moves away from the enemy"
>
> 			}
>
> 
>
> 			*FLOAT	  = "SpawnActor3Velocity"
>
> 			{
>
> 				*VALUE	= 3.0f
>
> 				*DISPLAYNAME = "Actor 3 Velocity"
>
> 				*Comment = "Speed that the third spawned actor moves away from the enemy"
>
> 			}
>
> 
>
> 			*FLOAT	  = "SpawnActor4Velocity"
>
> 			{
>
> 				*VALUE	= 3.0f
>
> 				*DISPLAYNAME = "Actor 4 Velocity"
>
> 				*Comment = "Speed that the fourth spawned actor moves away from the enemy"
>
> 			}
>
> 
>
> 			*FLOAT	  = "SpawnActor5Velocity"
>
> 			{
>
> 				*VALUE	= 3.0f
>
> 				*DISPLAYNAME = "Actor 5 Velocity"
>
> 				*Comment = "Speed that the fifth spawned actor moves away from the enemy"
>
> 			}
>
> 
>
> 
>
> 			*INT	  = "SpawnActor1Chance"
>
> 			{
>
> 				*VALUE	= 100
>
> 				*MAX	= 100
>
> 				*MIN	= 0
>
> 				*DISPLAYNAME = "Actor 1 Chance"
>
> 				*Comment = "The chance of the first spawned actor actually appearing"
>
> 			}
>
> 
>
> 			*INT	  = "SpawnActor2Chance"
>
> 			{
>
> 				*VALUE	= 100
>
> 				*MAX	= 100
>
> 				*MIN	= 0
>
> 				*DISPLAYNAME = "Actor 2 Chance"
>
> 				*Comment = "The chance of the second spawned actor actually appearing"
>
> 			}
>
> 
>
> 			*INT	  = "SpawnActor3Chance"
>
> 			{
>
> 				*VALUE	= 100
>
> 				*MAX	= 100
>
> 				*MIN	= 0
>
> 				*DISPLAYNAME = "Actor 3 Chance"
>
> 				*Comment = "The chance of the third spawned actor actually appearing"
>
> 			}
>
> 
>
> 			*INT	  = "SpawnActor4Chance"
>
> 			{
>
> 				*VALUE	= 100
>
> 				*MAX	= 100
>
> 				*MIN	= 0
>
> 				*DISPLAYNAME = "Actor 4 Chance"
>
> 				*Comment = "The chance of the fourth spawned actor actually appearing"
>
> 			}
>
> 
>
> 			*INT	  = "SpawnActor5Chance"
>
> 			{
>
> 				*VALUE	= 100
>
> 				*MAX	= 100
>
> 				*MIN	= 0
>
> 				*DISPLAYNAME = "Actor 5 Chance"
>
> 				*Comment = "The chance of the fifth spawned actor actually appearing"
>
> 			}
>
> 		}
>
> 	}
>
> 
>
> 	*Protected	=	"Mass"
>
> 	*Protected	=	"Gravity"
>
> 	*Protected	=	"Density"
>
> 	*Protected	=	"Drag"
>
> 	*Protected	=	"Type"
>
> 	*Protected	=	"Collides"
>
> 	*Protected	=	"Touches"
>
> 	*Protected	=	"Regions"
>
> 	*Protected	=	"Platforms"
>
> 	*Protected	=	"smStep"
>
> 	*Protected	=	"smWall"
>
> }
>
> 
>
> 
>
> *OBJECT = "TestEnemyAI"
>
> {
>
> 	*NAME	= "TestEnemyAI"
>
> 	*TYPE	= "OBJECT"
>
> 	*INHERITS = "EnemyAIObject"
>
> 	*UseInActorEd = "True"
>
> 
>
> 	*AIMODES = 
>
> 	{
>
> 		Idle,
>
> 		AlertIdle,
>
> 		CrouchIdle,
>
> 		ProneIdle,
>
> 		Walk,
>
> 		AlertWalk,
>
> 		CrouchWalk,
>
> 		ProneCrawl,
>
> 		Run,
>
> 		AlertRun,
>
> 		Jump,
>
> 		Climb,
>
> 		HangClimb,
>
> 		Damaged,
>
> 		Death,
>
> 		CornerCover,
>
> 		PopoutLeft,
>
> 		PopoutRight,
>
> 		Attack,
>
> 		CrouchAttack,
>
> 		ProneAttack,
>
> 		UnderwaterIdle,
>
> 		UnderwaterSwim,
>
> 		WatersurfaceIdle,
>
> 		WatersurfaceSwim
>
> 	}
>
> 
>
> }
>
> 
>
> 
>
> ;------------------------------------------------------------------------------
>
> ; Player
>
> ;
>
> ; PlayerAI
>
> ;------------------------------------------------------------------------------
>
> *OBJECT = "Player"
>
> {
>
> 	*NAME	= "Player"
>
> 	*INHERITS = "TurokAIObject"
>
> 	*TYPE	= "OBJECT"
>
> 	*UseInActorEd = "True"
>
> 
>
> 	*AIMODES = 
>
> 	{
>
> 		"Idle"					,
>
> 		"IdleNoControl"			,
>
> 		"Run"					,
>
> 		"Jump" 					,
>
> 		"JumpBack"				,
>
> 		"Fall" 					,
>
> 		"CheatFly" 				,
>
> 		"Shoved" 				,
>
> 
>
> 		"LedgeHang" 			,
>
> 		"LedgeShimmy"			,
>
> 
>
> 		"Ride" 					,
>
> 		"RideSteracosaurIdle"	,
>
> 		"RideSteracosaurMove"	,
>
> 		"RideSteracosaurDash"	,
>
> 
>
> 		"Climb" 				,
>
> 		"HangClimb"				,
>
> 
>
> 		"WaterSurfaceIdle"		,
>
> 		"WaterSurfaceMove"		,
>
> 		"UnderwaterIdle"		,
>
> 		"UnderwaterMove"		,
>
> 		"SwimBurst"				,
>
> 		"LeapToShore"			,
>
> 
>
> 		"UsingTurret"			,
>
> 		"UsingRC"				,
>
> 
>
> 		"PteranadonSetup"	,
>
> 		"PteranadonIdle"	,
>
> 		"PteranadonFlyUp"	,
>
> 		"PteranadonFlyUpMed" 	,
>
> 		"PteranadonFlyUpFull"	,
>
> 		"PteranadonFlyDown"  	,
>
> 		"PteranadonFlyDownMed"	,
>
> 		"PteranadonFlyDownFull"	,
>
> 		"PteranadonFlyLeft"	,
>
> 		"PteranadonFlyRight"	,
>
> 		"PteranadonEdgeLeft"	,
>
> 		"PteranadonEdgeRight"	,
>
> 		"PteranadonFireGun"	,
>
> 		"PteranadonFireMissile"	,
>
> 		"PteranadonWorldCollsion",
>
> 		"PteranadonActorCollsion",
>
> 
>
> 		"Dead",
>
> 
>
> 		"RaptorRideIdle",
>
> 		"RaptorRideIdleNoControl",
>
> 		"RaptorRideRun",
>
> 		"RaptorRideJump",
>
> 		"RaptorRideFall"
>
> 	}
>
> 
>
> 	*VARIABLES = 
>
> 	{
>
> 		*Combo = "PLAYERTYPE"
>
> 		{
>
> 			*DisplayName	=	"Player Type"
>
> 			*Value			=	0 
>
> 			*ComboList		=
>
> 			{
>
> 				"Normal player",
>
> 				"Raptor ride",
>
> 				"Steracosaur ride",
>
> 				"Pteranadon ride"
>
> 			}
>
> 		}
>
> 		*Group = "Inventory Capacity"
>
> 		{
>
> 			*Int = "MaxBowAmmo"
>
> 			{
>
> 				*DisplayName = "Max Bow Ammo"
>
> 				*Value = 20;
>
> 				*Comment = "Maximum number of arrows player can take"
>
> 			}
>
> 			*Int = "MaxTekBowAmmo"
>
> 			{
>
> 				*DisplayName = "Max TekBow Ammo"
>
> 				*Value = 20;
>
> 				*Comment = "Maximum number of tek arrows player can take"
>
> 			}
>
> 			*Int = "MaxPistolAmmo"
>
> 			{
>
> 				*DisplayName = "Max Pistol Ammo"
>
> 				*Value = 5;
>
> 				*Comment = "Maximum number of CLIPS of pistol slugs the player can take"
>
> 			}					
>
> 			*Int = "MaxShotgunAmmo"
>
> 			{
>
> 				*DisplayName = "Max Shotgun Ammo"
>
> 				*Value = 3;
>
> 				*Comment = "Maximum number of shotgun CLIPS the player can take"
>
> 			}
>
> 			*Int = "MaxMinigunAmmo"
>
> 			{
>
> 				*DisplayName = "Max Minigun Ammo"
>
> 				*Value = 5;
>
> 				*Comment = "Maximum number of minigun CLIPS the player can take"
>
> 			}					
>
> 			*Int = "MaxLauncherAmmo"
>
> 			{
>
> 				*DisplayName = "Max Rockets Ammo"
>
> 				*Value = 4;
>
> 				*Comment = "Maximum number of rocket CLIPS the player can take"
>
> 			}	
>
> 			*Int = "MaxGrenadeAmmo"
>
> 			{
>
> 				*DisplayName = "Max Grenades"
>
> 				*Value = 10;
>
> 				*Comment = "Maximum number of grenades the player can take"
>
> 			}					
>
> 			*Int = "MaxGuidedDeviceAmmo"
>
> 			{
>
> 				*DisplayName = "Max Guided Device Ammo (DON'T CHANGE)"
>
> 				*Value = 1;
>
> 				*Comment = "Leave this as 1, please"
>
> 			}					
>
> 			*Int = "MaxTechWeaponAmmo"
>
> 			{
>
> 				*DisplayName = "Max Tech Weapon Ammo"
>
> 				*Value = 4;
>
> 				*Comment = "Maximum number of Tech Weapon CLIPS the player can take"
>
> 			}		
>
> 			*Int = "MaxDarkMatterCubeAmmo"
>
> 			{
>
> 				*DisplayName = "Max Dark Matter cube Ammo (DON'T CHANGE)"
>
> 				*Value = 1;
>
> 				*Comment = "Leave this as 1, please"
>
> 			}					
>
> 		}
>
> 		*Group = "Standard Movement"
>
> 		{
>
> 			*FLOAT = "EYEHEIGHT"
>
> 			{
>
> 				*VALUE	= 1.5
>
> 				*MIN	= 0.1
>
> 				*MAX	= 50
>
> 				*DISPLAYNAME = "Eye Height"
>
> 			}
>
> 
>
> 			*FLOAT = "MAXRUNSPEED"
>
> 			{
>
> 				*VALUE	= 8
>
> 				*MIN	= 1
>
> 				*MAX	= 50
>
> 				*DISPLAYNAME = "Run Speed&a
[gameobjectdata.doc](https://xentaxbackup.github.io/file/1403_gameobjectdata.doc)
