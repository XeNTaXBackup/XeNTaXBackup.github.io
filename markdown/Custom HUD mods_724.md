## Post #1
- Username: BarfHappy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 04, 2004 5:51 am
- Post datetime: 2004-05-14T07:16:41+00:00
- Post Title: Custom HUD mods

Haro haro- 

here is my custom HUD for painkiller thx to MrMouse for extraction/import in pak files 

so it features:
metroid prime-like HUD
3D radar with positioning for closest objective
bunny hop speed meter on the left
souls count meter (before reaching demon morph) on the right
life and armor gauges (in the middle, upper one is life lower is armor each only decreases when below 100)
easy-to-see ammo gauges (the big colored ones) on each side

i will enhance the experience with glowing things but i m quite happy with the result for now

[http://tokyo.cool.ne.jp/barfhappy/primehud.zip](http://tokyo.cool.ne.jp/barfhappy/primehud.zip)


So... what did i change ?

i created new textures 

in lscript/hud/hud.lua
i added several materials in the Hud definition wich i initialized in Hud:LoadData() .
I modified some older ones too.

I modified the code in Hud:Render(delta) to display correctly my elements

if you want to do modifications, don t forget to allways use:
Cfg.HUDSize*w/1024 as multipliyer for width/horizontal position values
Cfg.HUDSize*h/768  as multipliyer for height/vertical position values

Cfg.HUDSize is the ratio (small, medium, large), w and h must be initialized like that:
local w,h = R3D.ScreenSize()
they give you width and height of the screen
btw 1024*768 is the internal resolution of the game and you use it to place your objects

for example if you want to draw an element of yours in the middle of the screen you ll write:

```
local trans = HUD.GetTransparency()

local mysizex, mysizey = MATERIAL.Size(self._matMyMaterial)

self:QuadTrans(self._matMyMaterial,(512-mysizex/2)*Cfg.HUDSize*w/1024,(384-mysizey/2)*Cfg.HUDSize*h/768,Cfg.HUDSize,false,trans)

```


and so on and so forth, i ll let you explore the code (dirty, i ve not cleaned up the commentaries) 

anyway, to change the weapon icons and ammo display you have to modify each weapon lua function DrawHUD(delta)

they are in templates/weapons
painkiller.lua
shotgun.lua
stakegungl.lua
minigunrl.lua
driverelectro.lua
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-14T11:29:34+00:00
- Post Title: Custom HUD mods

Lovely stuff!
## Post #3
- Username: Wizzy
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 14, 2004 12:25 am
- Post datetime: 2004-05-14T15:38:12+00:00
- Post Title: Custom HUD mods

While I think that is has a great look to it, I am only curious about one thing :
Are you going to go ahead and transform everything else in the game to being overly-sleek ?

TronKiller ?
Independence War : Killer of Pain ?
It, as good as it looks, just looks as if you borrowed it from some sci-fi shooter game.
How about making one that fits the look of the rest of the game ?
## Post #4
- Username: BarfHappy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 04, 2004 5:51 am
- Post datetime: 2004-05-14T16:15:50+00:00
- Post Title: Custom HUD mods

Well i just did that a day off, i wanted to make something waiting for the map editor  

Yes as i said it is a metroid-prime like HUD i completely borrowed the design on it

I ve already been asked to make a demonic one ... i may do it soon 

anyway i updated it with a real radar showing all the ennemies in sight
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-18T11:18:51+00:00
- Post Title: Custom HUD mods

Not bad, is that available from the same link you posted above?

I want to give it a try  And if you do have a "demonic" one, let me know as well
## Post #6
- Username: BarfHappy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 04, 2004 5:51 am
- Post datetime: 2004-05-22T06:32:21+00:00
- Post Title: Custom HUD mods

ehehe yup  
i have a less invasive radar-only version : [http://tokyo.cool.ne.jp/barfhappy/miniradar.zip](http://tokyo.cool.ne.jp/barfhappy/miniradar.zip) 

for the demonic version i am in the process to make one for a big mod, but i don t now when i ll be done woth it... i am out a lot with my bf lately so i don t have much time ^^

i ll keep you informed

and great job for the new painfull, beeing able to insert new files and directories is great
