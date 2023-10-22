## Post #1
- Username: tehpwnisher
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 31, 2017 4:02 pm
- Post datetime: 2017-03-01T09:51:17+00:00
- Post Title: Star Trek Online - Removing Engine Trails

Hi! I need help finding the specific files I need to change to remove the engine trails in Star Trek Online.

I have all of the tools and can manipulate the file structure to see the wtex files, but I can't find the actual files I need to change to get rid of the engine trails while you are flying around. 

Any ideas?
## Post #2
- Username: CaptainRaven74200
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 21, 2021 4:51 am
- Post datetime: 2021-05-20T20:54:16+00:00
- Post Title: Star Trek Online - Removing Engine Trails

The files are at D:\Spiele\Star Trek Online_de\Star Trek Online\Live\Localdata\texture_library\fx\Sprites\Trails\Trail_Diffuse.wtex

the Trail_Diffuse.wtex was it since last patch...now the trails are back...hope u can make it that the engine trails are off
## Post #3
- Username: royenic
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 30, 2021 4:38 pm
- Post datetime: 2021-05-30T08:41:33+00:00
- Post Title: Star Trek Online - Removing Engine Trails

/dynFxSetFXExlusionList "Cfx_Ship_Costume_Impulsetrail_Standard, Cfx_Ship_Costume_Warptrail_Standard"
## Post #4
- Username: Warbandit1981
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 01, 2021 5:13 am
- Post datetime: 2021-05-31T21:18:35+00:00
- Post Title: Star Trek Online - Removing Engine Trails

I tried out this command line and could only seem to deactivate one or the other. Impulse or warp engines. How do you string two commands at once in sto?

~always learning
## Post #5
- Username: royenic
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 30, 2021 4:38 pm
- Post datetime: 2021-06-01T02:27:26+00:00
- Post Title: Star Trek Online - Removing Engine Trails

that command is a simple one that disables both warp and impulse trails, but only the standard ones. there are a lot of trails that were previously taken care of by the texture method and i haven't gone and looked for the others since that got rid of most of them.
I have this in my keybind file:
F8 "dynFxExcludeFX Cfx_Ship_Costume_Impulsetrail_Standard $$ dynFxExcludeFX Cfx_Ship_Costume_Warptrail_Standard" ""
multiple dynFxExcludeFx commands together like this seem to have a higher character limit than dynFxSetFXExlusionList, and doing one after another doesn't undo the last.

to find the names of the trail effects you can disable i've found two options:
1. record a demo (/demorecord an then /demo_record_stop) and use stodemolauncher, which lets you see a list of effects you can hide in the recording.
2. export bins.hogg and look through Bin/Dynfx.Bin, which is basically a big list of all the effects

between these two you can basically hide any effect you don't want to see in the game. there does seem to be a character limit to key binds, though, so if you go on a crusade against buff visuals you might need more than one key. here's another example:

F9 "dynFxExcludeFX Cfx_Ship_Crewteam_Engineeringteam_Buff $$ dynFxExcludeFX Cfx_Ship_Crewteam_Tacticalteam_Buff $$ dynFxExcludeFX Cfx_Ship_Crewteam_scienceteam_Buff $$ dynFxExcludeFX Fx_Bop_Photonicofficer_Activate $$ dynFxExcludeFX Fx_Ship_Eng_Extendshields_Indicators $$ dynFxExcludeFX Fx_Ship_Eng_Emergencypowershields_Indicators $$ dynFxExcludeFX Fx_Ship_Tac_Attackpatternbeta $$ dynFxExcludeFX Fx_Ship_Tac_Attackpatternalpha $$ dynFxExcludeFX Fx_Ship_Eng_Directedenergymod $$ dynFxExcludeFX Fx_Ship_Eng_Emergencypowerweapons $$ dynFxExcludeFX fx_ship_mod_haste_buff_gen $$ dynFxExcludeFX fx_ship_mod_damage_buff $$ dynFxExcludeFX Fx_Spc_Boffpowers_Miracleworker_Narrowsensorbands $$ dynFxExcludeFX Fx_Ships_intel_predalgo_geo" ""
