## Post #1
- Username: Snake Plissken
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jul 06, 2011 6:35 am
- Post datetime: 2015-12-21T15:45:47+00:00
- Post Title: [newtozentax][scriptnoob] Q: Name this scripting language?

hello. i would like to know what scripting language this code is. i could guess but in doing so i could make a big fool of myself. so ill make a guess anyways: is it c++ ? idk. can you name this scripting language so i can study and figure it out? i jus need that name so i know what to start studying with. thanks for any comment helps alot.thanks. 

  random snipit of code : 

```
#include "scripts/bosses/longhunter.txt"
#include "scripts/bosses/mantis.txt"
#include "scripts/bosses/trex.txt"
#include "scripts/bosses/campainger.txt"

/*
==============================================================
VarFunctor
==============================================================
*/

funcdef void VARFUNC(const kStr &in, const kStr &in);

class VarFunctor
{
    void Add(const kStr &in gameVar, const kStr &in value)
    {
        GameVariables.Add(gameVar, value);
    }
    
    void SetValue(const kStr &in gameVar, const kStr &in value)
    {
        GameVariables.SetValue(gameVar, value);
    }
};

/*
==============================================================
InitHummer1StateVars
==============================================================
*/

void InitHummer1StateVars(VARFUNC @setFunc)
{
    setFunc("hummer1State", "0");
    setFunc("hummer1Health", "0");
    setFunc("hummer1Sector", "-1");
    setFunc("hummer1Origin", "0.0 0.0 0.0");
    setFunc("hummer1Yaw", "0.0");
}

/*
==============================================================
InitHummer2StateVars
==============================================================
*/

void InitHummer2StateVars(VARFUNC @setFunc)
{
    setFunc("hummer2State", "0");
    setFunc("hummer2Health", "0");
    setFunc("hummer2Sector", "-1");
    setFunc("hummer2Origin", "0.0 0.0 0.0");
    setFunc("hummer2Yaw", "0.0");
}

/*
==============================================================
InitLongHunterStateVars
==============================================================
*/

void InitLongHunterStateVars(VARFUNC @setFunc)
{
    setFunc("longHunterState", "0");
    setFunc("longHunterHealth", "0");
    setFunc("longHunterSector", "-1");
    setFunc("longHunterOrigin", "0.0 0.0 0.0");
    setFunc("longHunterYaw", "0.0");
    setFunc("longHunterObservationPoint", "0");
}

/*


   //// and then this is some more random code from further down in the script:


void main(void)
{
    kStr szShowIntros;

    //
    // add game variables at startup
    //
    
    // variables which are once-only should be added here
    GameVariables.Add("bStartedIntro", "0");
    
    // everything else, including anything that ought to be
    // reinitialized when a new game starts, should be added
    // in here.
    VarFunctor functor;
    SetStateVars(VARFUNC(functor.Add));
    
    // config startmap and trainingmap variables
    // note: these are created by the engine during initialization
    GameVariables.SetValue("g_startmap", "levels/level05.map");
    GameVariables.SetValue("g_restartmap", "levels/level42.map");
    GameVariables.SetValue("g_trainingmap", "levels/level47.map");
    GameVariables.SetValue("g_creditsmap", "levels/level02.map");
    GameVariables.SetValue("g_hubmapid", "5");
    GameVariables.SetValue("g_hubwarptid", "10666");
    
    // show intro cinematics?
    if(Sys.GetCvarValue("g_showgameintros", szShowIntros))
    {
        if(szShowIntros.Atoi() == 0)
        {
            // skip directly to title
            Game.ChangeMap("levels/level42.map");
            return;
        }
    }
    
    Game.ChangeMap("levels/level45.map");
}

```





so  what is the scripting language?
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-12-21T15:57:38+00:00
- Post Title: [newtozentax][scriptnoob] Q: Name this scripting language?

looks like a bespoke language based on c++, including text files is unusual in this way, and arrays are called sets in your example.

what game is this from? the name of the engine it uses will usually give some hints
## Post #3
- Username: Snake Plissken
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jul 06, 2011 6:35 am
- Post datetime: 2015-12-21T16:43:46+00:00
- Post Title: [newtozentax][scriptnoob] Q: Name this scripting language?

its from the new version of turok dino hunter ( the turok 1 (first turok)  that was on n64, that was released on steam a few days ago. the game actually uses a custom made new engine. or so the developer claims. he even gives the engine that is claimed to be his own custom work a custom name of his choosing. i think i can take his word for it. but it seems to be heavily based on those engines that run some of the early call of duty games? i could be very in correct there. i just notice the SETA commands used with the console. like seta developer "1" i know ive seen that before. and then the maps are in .map and he uses other methods that were commonly used in some of the quake ( quake2 ? ) engines. im new to all of this but this is the info i gathered. outside of that there is no evidence that his engine is based off of one of those stated. i say this becuse the games install / build/ root folder and folder structures are very very different then that of those engines i thought it may be based on .

EDIT: the guy who made this script and the engine it works with most def is a fan of old school game engines
## Post #4
- Username: Snake Plissken
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jul 06, 2011 6:35 am
- Post datetime: 2015-12-21T16:50:33+00:00
- Post Title: [newtozentax][scriptnoob] Q: Name this scripting language?

> Reply from WRS
>
> looks like a bespoke language based on c++, including text files is unusual in this way, and arrays are called sets in your example.

what game is this from? the name of the engine it uses will usually give some hints

thanks for this info it really helps. now that i know to come at it from a persudo  c++ perspective i should be alot better off as i go about getting into understanding this game. and modding it.
## Post #5
- Username: Snake Plissken
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jul 06, 2011 6:35 am
- Post datetime: 2015-12-21T16:52:12+00:00
- Post Title: [newtozentax][scriptnoob] Q: Name this scripting language?

i also came across this just now and the top of it leads me to further belive its based on some quake engine. 

 sorry for posting the whole thing:

```
// DESCRIPTION:
//      Quake Source Object Class
//

#include "scripts/common.txt"

/*
==============================================================
TurokQuakeSource
==============================================================
*/

shared class TurokQuakeSource : ScriptObject
{
    kActor @self;
    float duration;
    float currentTime;
    float velocity;
    float angle;
    
    TurokQuakeSource(kActor @actor)
    {
        @self = actor;
        duration = 0;
        currentTime = 0;
        velocity = 0;
        angle = 0;
    }
    
    /*
    ==============================================================
    SetupShake
    ==============================================================
    */
    
    void SetupShake(const kVec3 &in location, const float v, const float a, const float d)
    {
        self.Origin() = location;
        velocity = v;
        angle = a * 0.3333333432674408f;
        duration = Math::Fabs(d);
        currentTime = duration;
    }
    
    /*
    ==============================================================
    SetupThump
    ==============================================================
    */
    
    void SetupThump(const kVec3 &in location, const float d)
    {
        float ang, vel;
        
        ang = -(Math::pi / (60.0f / d));
        vel = d * 1.706666666666667f;
        
        SetupShake(location, vel, ang, d);
    }
    
    /*
    ==============================================================
    OnTick
    ==============================================================
    */
    
    void OnTick(void)
    {
        kPuppet @target = Player.Actor();
        
        if(currentTime <= 0.0f)
        {
            self.Remove();
            return;
        }
        
        if((PlayLoop.Ticks() & 3) == 0)
        {
            float power;
            float dist;
            float av, rv;
            float dx, dy;
        
            power = currentTime / duration;
            av = (Math::RandCFloat() * (angle * 0.5f)) * power;
            rv = (Math::RandCFloat() * (angle * 0.5f)) * power;
            
            dx = self.Origin().x - target.Origin().x;
            dy = self.Origin().y - target.Origin().y;
            
            dist = 1024.0f - Math::Sqrt(dx * dx + dy * dy);
            
            if(dist < 0.0f)
            {
                dist = 0.0f;
            }
            
            /*if(target.OnGround())
            {
                float vel = ((Math::RandFloat() * (velocity * 0.5f)) + (velocity * 0.5f)) * power;
                target.Velocity().z = ((dist * vel * 0.0009765625f) * 15.0f) * GAME_DELTA_TIME;
            }*/
        
            target.RecoilPitch() = (dist * av * 0.00390625f);
            target.Roll() = (dist * rv * 0.00390625f);
        }
        
        currentTime -= 0.02f;
    }
    
    /*
    ==============================================================
    OnSpawn
    ==============================================================
    */
    
    void OnSpawn(void)
    {
    }
};

```


the scripts name is quakesource.txt
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-12-21T17:10:45+00:00
- Post Title: [newtozentax][scriptnoob] Q: Name this scripting language?

put all that stuff in code tags:

> [ code ][/ code ]

but yeah, if you have access to all these scripts modding should be really simple
## Post #7
- Username: atom0s
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Sep 27, 2014 4:19 pm
- Post datetime: 2016-03-30T21:01:30+00:00
- Post Title: [newtozentax][scriptnoob] Q: Name this scripting language?

Removed.
