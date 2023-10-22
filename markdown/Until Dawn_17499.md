## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-04T16:53:13+00:00
- Post Title: Until Dawn

Until Dawn tool. Characters, static objects and levels support.

Usage: 
- unpack .core files with BMS script
- drop .UNP file onto the tool
- to convert textures, put UNP files in some folder, create "streams" subfolder there, and put .corestreams into that "streams" subfolder.



Bones are also working:


[UntilDawn_core.rar](https://xentaxbackup.github.io/file/14031_UntilDawn_core.rar)
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2018-01-05T01:31:16+00:00
- Post Title: Until Dawn

Man! You're like asset Jesus these days! Awesome work as always.
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-20T11:45:20+00:00
- Post Title: Until Dawn

Tool published. Works only with characters now.
## Post #4
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2018-01-26T18:50:44+00:00
- Post Title: Until Dawn

I'm sorry for the stupid question I have a ps4 blu-ray Until Dawn how i can extract the data from it
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-26T20:06:32+00:00
- Post Title: Until Dawn

> Reply from Crazy31139
>
> I'm sorry for the stupid question I have a ps4 blu-ray Until Dawn how i can extract the data from it
you need PS4 with FW 4.05 to do this
## Post #6
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2018-01-28T13:07:37+00:00
- Post Title: Until Dawn

Hi deamon1, could you share game files for me
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-28T20:51:44+00:00
- Post Title: Until Dawn

This game's and other game dumps are publicly available now, no need to ask me for files anymore.
## Post #8
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2018-01-29T22:33:52+00:00
- Post Title: Until Dawn

Could someone throw me a bone here? All the tools I found seem to be for creating a .pkg file for the game but I can't figure out which tool is needed to extract the .pkg in order to (I assume) use daemon1's tool.
## Post #9
- Username: Casedey
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Aug 20, 2011 1:27 pm
- Post datetime: 2018-01-29T22:59:48+00:00
- Post Title: Until Dawn

I'm stuck there too, as far as i know you need  to get a 1.76 ps4, unless there is another way to unpack the .pkg
Even the public game dumps are .pkg
How to unpack them?
## Post #10
- Username: Casedey
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-01-30T01:20:25+00:00
- Post Title: Until Dawn

all the public pkg's can be extracted with the same tools that pack them they all use a key of all 0's.
## Post #11
- Username: Casedey
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Aug 20, 2011 1:27 pm
- Post datetime: 2018-01-30T01:49:41+00:00
- Post Title: Until Dawn

Thanks @chrrox!
## Post #12
- Username: Casedey
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Aug 20, 2011 1:27 pm
- Post datetime: 2018-01-30T06:40:08+00:00
- Post Title: Until Dawn

I have a question, when i drop a file into UntilDawn_core a prompt window appears, but nothing happens, is there a step i am missing?
I got .core files from the dump, not .unp files.
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-01-30T15:29:59+00:00
- Post Title: Until Dawn

ok since now people will get .CORE files from that .PKG, I'm adding BMS script to unpack them before using the tool
## Post #14
- Username: Casedey
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Aug 20, 2011 1:27 pm
- Post datetime: 2018-01-31T12:56:39+00:00
- Post Title: Until Dawn

Thanks @daemon1
I can extract the models now.  
I noticed that maybe the tool doesn't work with some models.
With a Hex Editor i found some possible character models that didn't work, but maybe i'm wrong. XD
Regards!
## Post #15
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2018-01-31T22:29:43+00:00
- Post Title: Until Dawn

Took me much longer than it should have to figure out pkg extraction but I did eventually. 

I don't know what to look for in figuring out what files have models in them but I believe Casedey is correct. I ran through the 400+ unp files that were over 1MB in size to try and find all the character models. All the main characters had multiple models for their outfit swaps and deaths except for Sam. Found her starting outfit but not the towel* or her final outfit. 

* I know daemon1's character list says Sam's towel outfit but that's her starting outfit. It extracts some textures labeled "towel" which I'm guessing is what caused the labeling.

EDIT: It seems there might be some weight issues with the head meshes. I specifically tested Sam's starting outfit but it seems to apply to other models. The head, tongue and one of the eye meshes don't have weights for any bones (neck, jaw, etc) but the teeth, lashes, brows, other eye mesh do. I didn't see any issues with the body or hair meshes. 

* The Sam model I tested was lump_29a9543e-8913-6400-efec-7ab00021c502.unp

As an aside, the face also lack bones for the lips and cheeks. Is this an issue as well or does the game just use a weird mix of bones and morphs for facial poses?
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-02-01T15:17:04+00:00
- Post Title: Re: Until Dawn

> Reply from ssringo
>
> does the game just use a weird mix of bones and morphs for facial poses?

Yes.
## Post #17
- Username: Casedey
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Aug 20, 2011 1:27 pm
- Post datetime: 2018-02-03T10:35:26+00:00
- Post Title: Re: Until Dawn

All the character models from the first sequence of the game (The prank and when the sisters die) Are contained in the file:
levels.game.thegame.leveldescription_lump_15599944-2d32-f14f-f1a7-7aab93022496.unp (521 MB)
But the tool crashes when i drop the file.
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-02-03T13:30:34+00:00
- Post Title: Re: Until Dawn

I can't support big level packages yet, this will require too much work
## Post #19
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-02-12T23:40:24+00:00
- Post Title: Re: Until Dawn

Here's a more descriptive list of what is in the unp files, as well as adds one missing from the list (last one)

levels.game.thegame.leveldescription_lump_03ef123e-549b-16b7-d07f-f76360419438.unp	Ashley_Bloody
levels.game.thegame.leveldescription_lump_d19428b8-4531-5023-216f-617e0198c551.unp	Ashley_Indoor
levels.game.thegame.leveldescription_lump_e252f718-3acb-a153-2131-15fd9c69e69c.unp	Ashley_BloodyBruised
levels.game.thegame.leveldescription_lump_1f1ef5fb-bae6-8c6d-a15a-4610d81c0c88.unp	Wendigo Miners
levels.game.thegame.leveldescription_lump_f1552dcc-d923-d34d-35d7-414c0e13a0c5.unp	Beth-Hannah Ghosts
levels.game.thegame.leveldescription_lump_5af7cb30-a2cd-1539-dd30-abe745ceb7b7.unp	Chris_Outdoor
levels.game.thegame.leveldescription_lump_6154bb12-3229-93d5-9d65-cb561cb63f45.unp	Chris_Indoor
levels.game.thegame.leveldescription_lump_90514f95-0e6f-e814-2558-83639e792ac9.unp	Chris_Beaten
levels.game.thegame.leveldescription_lump_e630188b-2595-a745-eec0-385ac751b0ff.unp	Chris_Luggage
levels.game.thegame.leveldescription_lump_4f56a27e-bdd4-a807-46f7-c23b9fe75bda.unp	Emily_Beaten
levels.game.thegame.leveldescription_lump_5a4d4490-be68-6d3b-74d0-56ce6cfd5598.unp	Emily_Beaten_shot
levels.game.thegame.leveldescription_lump_5e6b6c00-f5de-f251-8511-405ee60f9d6f.unp	Emily_Beaten_nobite
levels.game.thegame.leveldescription_lump_4c0dd6bf-86fe-5ecd-d077-868c28549278.unp	Jack_Outdoor
levels.game.thegame.leveldescription_lump_e32b9727-039d-6b8b-a4fd-1ac76398138f.unp	Jack_Flamethrower
levels.game.thegame.leveldescription_lump_9fcde85b-cb31-c252-2bca-d1e80e519050.unp	Jessica_OutdoorBeaten
levels.game.thegame.leveldescription_lump_dec5fd90-3eeb-d248-53d1-346036d81792.unp	Jessica_IndoorBeaten
levels.game.thegame.leveldescription_lump_73fa6662-a7de-7d34-1546-9b8ef79ee938.unp	Jessica_Underwear
levels.game.thegame.leveldescription_lump_2649e626-7533-309a-8a0b-55a38fbdee6b.unp	Josh_Session5
levels.game.thegame.leveldescription_lump_3b47eb1c-e34c-c867-5c71-3c994d1d24ed.unp	Josh_PsychoMasked
levels.game.thegame.leveldescription_lump_4dfbe893-be9f-ffd8-1bfa-fea2531bbae7.unp	Josh_Outdoor
levels.game.thegame.leveldescription_lump_558afe0a-b697-a30f-81be-b0ef3ed6e252.unp	Josh_Indoor
levels.game.thegame.leveldescription_lump_90f78726-1cd8-2200-7d6a-cf74a46f1b38.unp	Josh_Session1
levels.game.thegame.leveldescription_lump_4088c1dd-6511-d5d7-3b7c-e6008d219f53.unp	Josh_Psycho
levels.game.thegame.leveldescription_lump_ac0e7918-4741-f705-9ac8-04652d4016e9.unp	Matt_Dirty-Matt_Beaten
levels.game.thegame.leveldescription_lump_5608eb40-4bd4-71ca-617e-fc538b17ed47.unp	Mike_OutdoorDirty
levels.game.thegame.leveldescription_lump_ba2361ab-950f-8de6-4e53-f1537bafeb0b.unp	Mike_Vest
levels.game.thegame.leveldescription_lump_ee951f04-9571-ff59-11c6-25261b40187e.unp	Mike_PostWendigo
levels.game.thegame.leveldescription_lump_559a431f-5c06-edc4-6c4b-ad4b96bf689a.unp	Psychiatrist_Indoor
levels.game.thegame.leveldescription_lump_29a9543e-8913-6400-efec-7ab00021c502.unp	Sam_Outdoor

levels.game.thegame.leveldescription_lump_dec5fd90-3eeb-d248-53d1-346036d81792.unp 	Jessica Indoors
## Post #20
- Username: Casedey
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Aug 20, 2011 1:27 pm
- Post datetime: 2018-02-13T04:51:37+00:00
- Post Title: Re: Until Dawn

The ones i found:
levels.game.thegame.leveldescription_lump_4e1aada8-cf3a-1d89-7958-0b18741be28b.unp
hannah_ghost1
levels.game.thegame.leveldescription_lump_57c49e0f-3164-f96e-df62-5f5e444aa621.unp
hannah_ghost2
levels.game.thegame.leveldescription_lump_7d570e92-72c5-8e8a-1721-36dcee008355.unp
wendigo_hannah
levels.game.thegame.leveldescription_lump_7411d955-c2f7-21fa-40fb-7ed5f03938ea.unp
sam_climbingbeatenwet
levels.game.thegame.leveldescription_lump_1a8f814f-5ff8-cb17-4045-37c6a288ec3f.unp
sam_climbing
levels.game.thegame.leveldescription_lump_d1533873-d151-b4c0-cd0d-d4e403a0beb5.unp
sam_towel
levels.game.thegame.leveldescription_lump_66caa9f2-31b6-32dc-67a9-14ef0364dd67.unp
sam_climbingbeaten
levels.game.thegame.leveldescription_lump_40800966-9a55-37fb-d42f-ddf46bdb0ed5.unp
emily_outdoor
levels.game.thegame.leveldescription_lump_a2244525-9b9d-d5eb-a7b7-0b4f10045cf8.unp
jessica_outdoor, mike_outdoor
levels.game.thegame.leveldescription_lump_25eede53-3222-c922-f80b-b3f81acc67a2.unp
mike_vestwet, mike_vestdirtywet, mike_vestdirty
levels.game.thegame.leveldescription_lump_15599944-2d32-f14f-f1a7-7aab93022496.unp
jessica_intro, mike_intro, emily_intro, josh_intro, matt_intro, chris_intro, sam_intro, ashley_intro, hannah_halfdressed, hannah_dead, hannah_outdoor, hannah_indoor, beth_outdoor, beth_dead, beth_indoor.
## Post #21
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2018-02-13T08:39:22+00:00
- Post Title: Re: Until Dawn

thanks for expanding the list of found models
## Post #22
- Username: Nas92
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 10, 2018 1:11 am
- Post datetime: 2018-02-25T17:56:39+00:00
- Post Title: Re: Until Dawn

Is there a way to separately convert textures?
## Post #23
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-02-26T15:12:46+00:00
- Post Title: Re: Until Dawn

Working on a new version that supports maps and level geometry, also other packages unsupported before.
## Post #24
- Username: Casedey
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Aug 20, 2011 1:27 pm
- Post datetime: 2018-02-26T15:15:58+00:00
- Post Title: Re: Until Dawn

Awesome!!!
## Post #25
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-02-26T18:28:27+00:00
- Post Title: Re: Until Dawn

New version. Level assets! Sam in towel!
## Post #26
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-02-26T21:41:28+00:00
- Post Title: Re: Until Dawn

I'm not sure why, but the tool is looking for *.corestream files that don't seem to exist.

For instance levels.game.thegame.leveldescription_lump_7411d955-c2f7-21fa-40fb-7ed5f03938ea.unp reports:

Stream not found: streams\models.characters.sam.textures.sam_face_detail01_nm.corestream
Stream not found: streams\models.characters.sam.textures.match2.skin3.top_1_0_g_sst_0.corestream

I searched the whole file collection from the disk, and they simply don't exist. Makes me wonder if it's cut content that wasn't even in the game.
## Post #27
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-02-27T01:17:21+00:00
- Post Title: Re: Until Dawn

Here's an interesting one for you:

levels.game.thegame.leveldescription_lump_af5b9be0-23ad-1dd8-0d47-58743f0e1ced.unp 
Jessica_Blanket Josh_SemiWendigo Sam_ClimbingBeatenNoTorch Emily_FrontEnd Emily_FrontEndBeaten Cop_Swat1

I kept seeing files referencing a character named "Pitch", and those led me to this swat officer:



Was he in the game? I don't remember him.
## Post #28
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-02-28T15:37:56+00:00
- Post Title: Re: Until Dawn

> Reply from volfin
>
> I'm not sure why, but the tool is looking for *.corestream files that don't seem to exist.
I see 2 possibilities for that:

1. files are not used in a model, just some leftovers

2. files were duplicates of some other files, so they have same content hash, but different names
In this case it will be hard to find them, for that we need to scan all textures in the game and compare their contents or hashes to find those that are duplicates

Case 2 is 100% present in wrinkle maps, because they only exist for one character, and all others are missing.
## Post #29
- Username: Nas92
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 10, 2018 1:11 am
- Post datetime: 2018-03-02T13:46:14+00:00
- Post Title: Re: Until Dawn

> Reply from volfin
>
> 

Was he in the game? I don't remember him.

Josh ending when he turned
## Post #30
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-03-04T16:49:30+00:00
- Post Title: Re: Until Dawn

please report if any files dont work with current tools, because soon i have to move to other games, and i will not return to these games any soon you know
## Post #31
- Username: Casedey
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Aug 20, 2011 1:27 pm
- Post datetime: 2018-03-04T18:34:14+00:00
- Post Title: Re: Until Dawn

Ok, these do not work for me:

levels.game.thegame.leveldescription_lump_384c4bc5-dd7a-d504-3cb7-3dc2c0890d2c.unp
-emily_beatennobiteshot.
levels.game.thegame.leveldescription_lump_9a0b8df3-f6d8-e08c-561f-15169cffc492.unp
-jessica_indoorbeatendead jessica_beatendead jessica_outdoorbeatendead.
levels.game.thegame.leveldescription_lump_a89e9653-2138-1fca-7ad8-e7a0409b68f8.unp
-jessica_outdoorwet jessica_underwear mike_outdoorwet jessica_indoor.
levels.game.thegame.leveldescription_lump_63a1f91b-6cd2-dc5a-618f-a880fb34482f.unp
-matt_beatensmashed.
levels.game.thegame.leveldescription_lump_e86ed9b6-c66f-905e-dbca-6e28b4713e6a.unp
-mike_vestlostfingers
levels.game.thegame.leveldescription_lump_55eadb6d-e968-2e9f-3bd6-f187125f4691.unp
-sam_climbingdirty wendigo_miner1burning.
levels.game.thegame.leveldescription_lump_719c2cf3-0d42-686a-e2ad-5a6177add2eb.unp
-sam_frontend psychiatrist_frontend.
levels.game.thegame.leveldescription_lump_1b82a7df-7aa9-05fc-f3aa-a5b19b5e721f.unp
-sam_towelluggageseated sam_climbingcleannotorch.
levels.game.thegame.leveldescription_lump_ab987d3f-5412-2e5e-3e07-4c026d1a6612.unp
-ashley_bloodydead ashley_bloodybruiseddead ashley_burnt emily_burnt mike_postwendigoeviscerated mike_postwendigoevisceratedburnt sam_climbingeviscerated wendigo_miner1.
levels.game.thegame.leveldescription_lump_773921e9-27bd-e064-dfbb-1196c044fc90.unp
-wendigo_hannahsilhouette.
levels.game.thegame.leveldescription_lump_97310fa2-16da-80e8-f328-f328ed134272.unp
psychiatrist_stage2.
levels.game.thegame.leveldescription_lump_e512a9ce-298f-a8e1-575d-3c498c8aecf3.unp
josh_psychowet josh_psychostabbedwet.

Checking for more...
## Post #32
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-03-04T20:25:36+00:00
- Post Title: Re: Until Dawn

> Reply from Casedey
>
> Checking for more...
No need to. I already see there are too many. I give up, will return to this game after a few months maybe. It has WAY too many asset types.
## Post #33
- Username: Casedey
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Aug 20, 2011 1:27 pm
- Post datetime: 2018-03-04T20:42:56+00:00
- Post Title: Re: Until Dawn

Sure, anyways i am making a list of the working ones in case someone needs it, so i am scanning every file.
## Post #34
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-03-04T20:46:34+00:00
- Post Title: Re: Until Dawn

> Reply from Casedey
>
> Sure, anyways i am making a list of the working ones in case someone needs it, so i am scanning every file.
how many percent approx. are working ?
## Post #35
- Username: Casedey
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Aug 20, 2011 1:27 pm
- Post datetime: 2018-03-04T21:02:18+00:00
- Post Title: Re: Until Dawn

I think more than 90 percent of the characters are working well, as for stages maybe the same amount.
## Post #36
- Username: Casedey
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Aug 20, 2011 1:27 pm
- Post datetime: 2018-03-09T23:34:00+00:00
- Post Title: Re: Until Dawn

List Updated:

levels.game.thegame.leveldescription_lump_15599944-2d32-f14f-f1a7-7aab93022496.unp
jessica_intro, mike_intro, emily_intro, josh_intro, matt_intro, chris_intro, sam_intro, ashley_intro, hannah_halfdressed, hannah_dead, hannah_outdoor, hannah_indoor, beth_outdoor, beth_dead, beth_indoor.
levels.game.thegame.leveldescription_lump_4e1aada8-cf3a-1d89-7958-0b18741be28b.unp
hannah_ghost1.
levels.game.thegame.leveldescription_lump_57c49e0f-3164-f96e-df62-5f5e444aa621.unp
hannah_ghost2.
levels.game.thegame.leveldescription_lump_f1552dcc-d923-d34d-35d7-414c0e13a0c5.unp
beth_ghost1, hannah_ghost5, beth_ghost2, hannah_ghost3, hannah_ghost4.
levels.game.thegame.leveldescription_lump_7d570e92-72c5-8e8a-1721-36dcee008355.unp
wendigo_hannah.
levels.game.thegame.leveldescription_lump_773921e9-27bd-e064-dfbb-1196c044fc90.unp
wendigo_hannahsilhouette.
levels.game.thegame.leveldescription_lump_d19428b8-4531-5023-216f-617e0198c551.unp
ashley_indoor.
levels.game.thegame.leveldescription_lump_33cff408-4964-6d13-ec24-94e908c79fb1.unp
ashley_outdoor.
levels.game.thegame.leveldescription_lump_03ef123e-549b-16b7-d07f-f76360419438.unp
ashley_bloody.
levels.game.thegame.leveldescription_lump_e252f718-3acb-a153-2131-15fd9c69e69c.unp
ashley_bloodybruised.
levels.game.thegame.leveldescription_lump_a30e75d3-9d6f-069d-94f0-d8171fcf58e8.unp
ashley_hanging, josh_hanging.
levels.game.thegame.leveldescription_lump_ab987d3f-5412-2e5e-3e07-4c026d1a6612.unp
ashley_bloodydead, ashley_bloodybruiseddead, ashley_burnt, emily_burnt, mike_postwendigoeviscerated, mike_postwendigoevisceratedburnt, sam_climbingeviscerated, wendigo_miner1.
levels.game.thegame.leveldescription_lump_dca5fdcd-718d-ab51-48ad-2407f1ebf979.unp
decapitated_chris_head, decapitated_ashley_head.
levels.game.thegame.leveldescription_lump_e630188b-2595-a745-eec0-385ac751b0ff.unp
chris_luggage.
levels.game.thegame.leveldescription_lump_6154bb12-3229-93d5-9d65-cb561cb63f45.unp
chris_indoor.
levels.game.thegame.leveldescription_lump_5af7cb30-a2cd-1539-dd30-abe745ceb7b7.unp
chris_outdoor.
levels.game.thegame.leveldescription_lump_90514f95-0e6f-e814-2558-83639e792ac9.unp
chris_beaten.
levels.game.thegame.leveldescription_lump_29a9543e-8913-6400-efec-7ab00021c502.unp
sam_luggage.
levels.game.thegame.leveldescription_lump_3c870811-99a5-726c-1cbe-da878b641cb7.unp
sam_indoor, chris_monk.
levels.game.thegame.leveldescription_lump_5889b9a2-1cb0-3aeb-f1bc-aba0574fb0c8.unp
chris_monk_mask.
levels.game.thegame.leveldescription_lump_d1533873-d151-b4c0-cd0d-d4e403a0beb5.unp
sam_towel.
levels.game.thegame.leveldescription_lump_850fc784-2b0b-3fc0-9177-514851bf2ab9.unp
sam_towelluggage.
levels.game.thegame.leveldescription_lump_1b82a7df-7aa9-05fc-f3aa-a5b19b5e721f.unp
sam_towelluggageseated, sam_climbingcleannotorch.
levels.game.thegame.leveldescription_lump_719c2cf3-0d42-686a-e2ad-5a6177add2eb.unp
sam_frontend, psychiatrist_frontend.
levels.game.thegame.leveldescription_lump_1a8f814f-5ff8-cb17-4045-37c6a288ec3f.unp
sam_climbing.
levels.game.thegame.leveldescription_lump_66caa9f2-31b6-32dc-67a9-14ef0364dd67.unp
sam_climbingbeaten.
levels.game.thegame.leveldescription_lump_7411d955-c2f7-21fa-40fb-7ed5f03938ea.unp
sam_climbingbeatenwet.
levels.game.thegame.leveldescription_lump_55eadb6d-e968-2e9f-3bd6-f187125f4691.unp
sam_climbingdirty, wendigo_miner1burning.
levels.game.thegame.leveldescription_lump_7678852c-a36c-f503-72b8-66af051fe2a7.unp
sam_dummy, sam_scarecrow, sam_zombie.
levels.game.thegame.leveldescription_lump_558afe0a-b697-a30f-81be-b0ef3ed6e252.unp
josh_indoor.
levels.game.thegame.leveldescription_lump_4dfbe893-be9f-ffd8-1bfa-fea2531bbae7.unp
josh_outdoor.
levels.game.thegame.leveldescription_lump_90f78726-1cd8-2200-7d6a-cf74a46f1b38.unp
josh_session1.
levels.game.thegame.leveldescription_lump_2649e626-7533-309a-8a0b-55a38fbdee6b.unp
josh_session5.
levels.game.thegame.leveldescription_lump_4088c1dd-6511-d5d7-3b7c-e6008d219f53.unp
josh_psycho.
levels.game.thegame.leveldescription_lump_3d3766c5-9c32-9d79-88a3-8180c5e75a30.unp
josh_reveal_part2.
levels.game.thegame.leveldescription_lump_dec7ec19-43a4-b027-829b-38fca32f811f.unp
joshs_fake_body.
levels.game.thegame.leveldescription_lump_e512a9ce-298f-a8e1-575d-3c498c8aecf3.unp
josh_psychowet, josh_psychostabbedwet.
levels.game.thegame.leveldescription_lump_3b47eb1c-e34c-c867-5c71-3c994d1d24ed.unp
psycho_masked.
levels.game.thegame.leveldescription_lump_a2244525-9b9d-d5eb-a7b7-0b4f10045cf8.unp
jessica_outdoor, mike_outdoor.
levels.game.thegame.leveldescription_lump_a89e9653-2138-1fca-7ad8-e7a0409b68f8.unp
jessica_outdoorwet, jessica_underwear, mike_outdoorwet, jessica_indoor.
levels.game.thegame.leveldescription_lump_73fa6662-a7de-7d34-1546-9b8ef79ee938.unp
jessica_beaten.
levels.game.thegame.leveldescription_lump_dec5fd90-3eeb-d248-53d1-346036d81792.unp
jessica_indoorbeaten.
levels.game.thegame.leveldescription_lump_9fcde85b-cb31-c252-2bca-d1e80e519050.unp
jessica_outdoorbeaten.
levels.game.thegame.leveldescription_lump_9a0b8df3-f6d8-e08c-561f-15169cffc492.unp
jessica_indoorbeatendead, jessica_beatendead, jessica_outdoorbeatendead.
levels.game.thegame.leveldescription_lump_dfb36586-d72a-9d5f-4896-9d35d9203be7.unp
jessica_indoorminersclothes, jessica_minersclothes.
levels.game.thegame.leveldescription_lump_5608eb40-4bd4-71ca-617e-fc538b17ed47.unp
mike_outdoordirty.
levels.game.thegame.leveldescription_lump_ba2361ab-950f-8de6-4e53-f1537bafeb0b.unp
mike_vest.
levels.game.thegame.leveldescription_lump_25eede53-3222-c922-f80b-b3f81acc67a2.unp
mike_vestwet, mike_vestdirtywet, mike_vestdirty.
levels.game.thegame.leveldescription_lump_e86ed9b6-c66f-905e-dbca-6e28b4713e6a.unp
mike_vestlostfingers wolf_01 wolf_02.
levels.game.thegame.leveldescription_lump_ee951f04-9571-ff59-11c6-25261b40187e.unp
mike_postwendigo.
levels.game.thegame.leveldescription_lump_f35791f7-127a-9502-aa6f-140dc086f2bd.unp
mike_outdoordirtywet, wendigo_hannahwet, mike_postwendigowet, bobbing_head_ashley, bobbing_head_chris, bobbing_head_jack, bobbing_head_jessica, bobbing_head_matt, hanging_body_ashley, hanging_body_chris, hanging_body_emily, hanging_body_emily_sawn, hanging_body_jack, hanging_body_jessica, hanging_body_jessica_indoor, hanging_body_jessica_outdoor, hanging_body_matt.
levels.game.thegame.leveldescription_lump_40800966-9a55-37fb-d42f-ddf46bdb0ed5.unp
emily_outdoor, matt_outdoor.
levels.game.thegame.leveldescription_lump_4f56a27e-bdd4-a807-46f7-c23b9fe75bda.unp
emily_beaten.
levels.game.thegame.leveldescription_lump_5e6b6c00-f5de-f251-8511-405ee60f9d6f.unp
emily_beatennobite.
levels.game.thegame.leveldescription_lump_5a4d4490-be68-6d3b-74d0-56ce6cfd5598.unp
emily_beatenshot.
levels.game.thegame.leveldescription_lump_46dca0a0-36af-6f17-685e-80c1ccce92e8.unp
emily_beatennobitewet, emily_hanging. 
levels.game.thegame.leveldescription_lump_384c4bc5-dd7a-d504-3cb7-3dc2c0890d2c.unp
emily_beatennobiteshot.
levels.game.thegame.leveldescription_lump_ac0e7918-4741-f705-9ac8-04652d4016e9.unp
matt_dirty, matt_beaten.
levels.game.thegame.leveldescription_lump_63a1f91b-6cd2-dc5a-618f-a880fb34482f.unp
matt_beatensmashed.
levels.game.thegame.leveldescription_lump_4c0dd6bf-86fe-5ecd-d077-868c28549278.unp
jack_outdoor.
levels.game.thegame.leveldescription_lump_e32b9727-039d-6b8b-a4fd-1ac76398138f.unp
jack_flamethrower.
levels.game.thegame.leveldescription_lump_1f1ef5fb-bae6-8c6d-a15a-4610d81c0c88.unp
wendigo_miner2, wendigo_miner3.
levels.game.thegame.leveldescription_lump_c56f5023-b8ea-ad0c-bff4-71a46f12b915.unp
wendigo_miner2burning, wendigo_straightjacket, Wolf.
levels.game.thegame.leveldescription_lump_559a431f-5c06-edc4-6c4b-ad4b96bf689a.unp
psychiatrist_indoor.
levels.game.thegame.leveldescription_lump_97310fa2-16da-80e8-f328-f328ed134272.unp
psychiatrist_stage2.
levels.game.thegame.leveldescription_lump_e637c13b-e263-f56d-2d5b-44045f4201a3.unp
josh_session7, psychiatrist_stage3.
levels.game.thegame.leveldescription_lump_e27ec436-d02a-ebcc-e60a-d42b94a3550d.unp
psychiatrist_stage4.
levels.game.thegame.leveldescription_lump_af5b9be0-23ad-1dd8-0d47-58743f0e1ced.unp
jessica_blanket, cop_swat1, josh_semiwendigo, sam_climbingbeatennotorch, emily_frontend, emily_frontendbeaten.

Edit: List Updated.
## Post #37
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-03-14T19:22:15+00:00
- Post Title: Re: Until Dawn

Tool updated! All "not working list" packages must work now.
Also multi-uv problem fixed.
## Post #38
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2018-03-20T03:57:46+00:00
- Post Title: Re: Until Dawn

Tools work perfect, thank you so much for your hard work.
## Post #39
- Username: Nas92
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 10, 2018 1:11 am
- Post datetime: 2018-03-31T19:39:31+00:00
- Post Title: Re: Until Dawn

I wonder if this tool will work with Hidden Agenda.
## Post #40
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-03-31T19:46:19+00:00
- Post Title: Re: Until Dawn

> Reply from Nas92
>
> I wonder if this tool will work with Hidden Agenda.
Hidden Agenda is unreal engine
Until Dawn is decima
## Post #41
- Username: pikabushka
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 02, 2018 3:09 am
- Post datetime: 2018-05-01T21:42:17+00:00
- Post Title: Re: Until Dawn

> Reply from daemon1
>
> Nas92 wrote:I wonder if this tool will work with Hidden Agenda.
Hidden Agenda is unreal engine
Until Dawn is decima

Is there any chance to fix the problems with the lack of weight on the heads of the characters? Or is this not a problem? Thank you very much for all your hard work!
## Post #42
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-02T06:16:48+00:00
- Post Title: Re: Until Dawn

there are no weights on heads
facial animations are done with morphs

i can export these morphs, but this will not help getting the face rigged
## Post #43
- Username: pikabushka
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 02, 2018 3:09 am
- Post datetime: 2018-05-02T06:20:49+00:00
- Post Title: Re: Until Dawn

> Reply from daemon1
>
> there are no weights on heads
facial animations are done with morphs

i can export these morphs, but this will not help getting the face rigged

Thank you very much for the explanation! 

But I would like to ask, how did you get it with Ashley Brown 3D model? Her head was with weights?
## Post #44
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-02T06:36:11+00:00
- Post Title: Re: Until Dawn

> Reply from pikabushka
>
> But I would like to ask, how did you get it with Ashley Brown 3D model? Her head was with weights?
eyes & eyebrows have weights
they are also present on your screenshot
## Post #45
- Username: Casedey
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Aug 20, 2011 1:27 pm
- Post datetime: 2018-05-02T20:22:45+00:00
- Post Title: Re: Until Dawn

It would be awesome if you add the option to export morphs.
## Post #46
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-05T17:20:59+00:00
- Post Title: Re: Until Dawn

yes morphs are in my plan, but no idea when i can get to it...
## Post #47
- Username: answer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 06, 2018 1:00 pm
- Post datetime: 2018-08-05T08:02:35+00:00
- Post Title: Re: Until Dawn

Not sure if it's just my importer (XNALara/XPS Model importer) or because I'm using Blender, but I had to flip the UV coordinates along the Y-axis for all the textures. Didn't experience that sort of issue with other .ascii models I've imported with this importer. Besides that, the character importing worked perfectly, great work thanks!

One thing I'm trying to sort out is removing the seam where the head and the body models were separated, even once I join them up, remove doubles, smooth it all out, and apply the same material values, there's still a noticeable difference around where it would be attached. It's almost like the head texture is brighter or something. Anyone have any ideas to figure something like this out?

edit: welp 2 minutes after posting this I found by tweaking the diffuse intensity on the head to 0.95 and leaving the torso diffuse to 1.0, the seam disappears completely. Cool.
[sam-towel.jpg](https://xentaxbackup.github.io/file/14710_sam-towel.jpg)
## Post #48
- Username: AigreDoux
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 17, 2018 11:28 am
- Post datetime: 2018-08-17T03:30:32+00:00
- Post Title: Re: Until Dawn

Is there any sort of updated list or way to figure out what each .core contains? Attempting to port some environments and it's very difficult to search through 1000+ files when characters are the only file reference we have.
## Post #49
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-10-14T16:36:22+00:00
- Post Title: Re: Until Dawn

> Reply from daemon1
>
> Nas92 wrote:I wonder if this tool will work with Hidden Agenda.
Hidden Agenda is unreal engine
Until Dawn is decima

Does the tool work on Until Dawn Rush of Blood [VR]?

I unpacked the PKG and it seems it also contains the .core files

But the BMS script won't unpack the files for some reason?

Did you make the BMS script?

Or do i need to contact a whole other person?
## Post #50
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-14T16:55:17+00:00
- Post Title: Re: Until Dawn

> Reply from Faithfullfaun
>
> Did you make the BMS script?
i dont remember
probably i did
## Post #51
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-10-14T20:30:05+00:00
- Post Title: Re: Until Dawn

> Reply from daemon1
>
> Faithfullfaun wrote:Did you make the BMS script?
i dont remember
probably i did

I have the download link if you want to look at it?

Just pm me
## Post #52
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-15T17:19:40+00:00
- Post Title: Re: Until Dawn

i dont remember anyone reporting a problem of missing textures
some of them may be unsupported format, i think i never finished them
check if you have any "unsupported" messages while extracting
## Post #53
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-10-15T22:33:40+00:00
- Post Title: Re: Until Dawn

> Reply from daemon1
>
> i dont remember anyone reporting a problem of missing textures
some of them may be unsupported format, i think i never finished them
check if you have any "unsupported" messages while extracting

I get the message 

Fatal error: unknown serialized resource.
Fatal error: EOF not reached.
Unsupported texture type 18
Unsupported texture type 15
Unsupported texture type 16
Unsupported texture type 22
Unsupported texture type 34
## Post #54
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-17T17:58:46+00:00
- Post Title: Re: Until Dawn

> Reply from Faithfullfaun
>
> Unsupported texture type 18
Unsupported texture type 15
Unsupported texture type 16
Unsupported texture type 22
Unsupported texture type 34
yes it means these textures are not extracted
## Post #55
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-10-18T12:39:56+00:00
- Post Title: Re: Until Dawn

> Reply from daemon1
>
> Faithfullfaun wrote:Unsupported texture type 18
Unsupported texture type 15
Unsupported texture type 16
Unsupported texture type 22
Unsupported texture type 34
yes it means these textures are not extracted

So does it mean that i don't have the stream that contains the texture

Or is it not supported?
## Post #56
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-10-18T16:24:02+00:00
- Post Title: Re: Until Dawn

its not supported
i plan to add support, but had no time yet
## Post #57
- Username: MorgothZeONE
- Rank: advanced
- Number of posts: 51
- Joined date: Tue May 24, 2016 7:59 am
- Post datetime: 2018-11-29T19:56:44+00:00
- Post Title: Re: Until Dawn

is the Makkapitew's model in the game files, or is he just in pre-rendered footage?
## Post #58
- Username: Lexxon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 18, 2016 1:59 am
- Post datetime: 2018-12-02T06:46:23+00:00
- Post Title: Re: Until Dawn

> Reply from MorgothZeONE
>
> is the Makkapitew's model in the game files, or is he just in pre-rendered footage?
I'm pretty sure this is him:



makkapitew_screen2.jpg (162.64 KiB) Viewed 178 times



levels.game.thegame.leveldescription_lump_9c39163d-ed72-433c-4b6a-6e4242a77a98.unp
## Post #59
- Username: MorgothZeONE
- Rank: advanced
- Number of posts: 51
- Joined date: Tue May 24, 2016 7:59 am
- Post datetime: 2018-12-07T19:46:08+00:00
- Post Title: Re: Until Dawn

> Reply from Lexxon
>
> MorgothZeONE wrote:is the Makkapitew's model in the game files, or is he just in pre-rendered footage?
I'm pretty sure this is him:
makkapitew_screen2.jpg

levels.game.thegame.leveldescription_lump_9c39163d-ed72-433c-4b6a-6e4242a77a98.unp

yep thats him

anyone know where i can get the .unp files? i dont have the game myself so i can't really extract anything and i know the files are on the web, i just don't know where to look
## Post #60
- Username: Joshdraco12
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 13, 2017 10:22 pm
- Post datetime: 2019-02-24T17:43:07+00:00
- Post Title: Re: Until Dawn

I keep getting this error when trying to extract "levels.game.thegame.leveldescription_lump_a89e9653-2138-1fca-7ad8-e7a0409b68f8.unp"

```
..
Unhandled Exception: System.IO.EndOfStreamException: Unable to read beyond the end of the stream.
   at System.IO.BinaryReader.FillBuffer(Int32 numBytes)
   at System.IO.BinaryReader.ReadInt32()
   at ????????????????????????????????????????.?????????????????????????????????????????(String[] )
```
## Post #61
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2019-03-16T20:27:57+00:00
- Post Title: Re: Until Dawn

Just thought I'd ask since I don't have the game, back could someone extract Emily? I can't find her model anywhere online.

Cheers
## Post #62
- Username: rocailloux
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 06, 2019 5:09 am
- Post datetime: 2019-06-26T10:37:08+00:00
- Post Title: Re: Until Dawn

Do someone have a list which contains what .core / .unp have inside? I am trying to find nature (trees, rocks, plants etc but it is very hard to search all the files. If someone could help me or give list I will be very greatfull!
## Post #63
- Username: thecreepytoast
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 22, 2019 8:24 pm
- Post datetime: 2019-11-09T19:57:29+00:00
- Post Title: Re: Until Dawn

i don't know if this is out of topic but i somehow got my hands on the old ps3 version of until dawn and i'm curious about extracting the 3d models. Curiously it uses .core formats too but i can't extract them using the bms script from this thread.

here is a sample if anyone wants to check it out: [https://drive.google.com/file/d/1nt-32a ... sp=sharing](https://drive.google.com/file/d/1nt-32aOtKxENYR8S3mDwSzJiEYcFNRiS/view?usp=sharing)
## Post #64
- Username: thedeclic
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat May 18, 2019 4:28 am
- Post datetime: 2020-02-17T13:17:11+00:00
- Post Title: Re: Until Dawn

HIIIIII if anyone is able to rip models and textures i reallyyy want one character.so please private message me if u can do it
will send u a paypal for your help 
pls
## Post #65
- Username: Raq
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Nov 17, 2019 1:04 am
- Post datetime: 2021-12-13T21:04:59+00:00
- Post Title: Re: Until Dawn

Is it still planned to make morph targets exportable from the model files?
## Post #66
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-12-14T08:56:00+00:00
- Post Title: Re: Until Dawn

> Reply from Raq ↑Tue Dec 14, 2021 5:04 am at Tue Dec 14, 2021 5:04 am
>
> 
Is it still planned to make morph targets exportable from the model files?
yes its still in the plan
but there are so many other things to do, that i doubt i will ever get to this
## Post #67
- Username: Raq
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Nov 17, 2019 1:04 am
- Post datetime: 2021-12-14T16:48:55+00:00
- Post Title: Re: Until Dawn

> Reply from daemon1 ↑Tue Dec 14, 2021 4:56 pm at Tue Dec 14, 2021 4:56 pm
>
> 
yes its still in the plan
but there are so many other things to do, that i doubt i will ever get to this

Aww, that's a shame, but don't worry too much about it, you already worked so much for so many games! Take all the time you need.
## Post #68
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2022-06-11T14:11:47+00:00
- Post Title: Re: Until Dawn

will these tools work with The Quarry ? will these models have a low enough poly count to work in xnalara?
## Post #69
- Username: MadHotHatter
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jun 11, 2022 10:55 pm
- Post datetime: 2022-06-11T14:58:18+00:00
- Post Title: Re: Until Dawn

I think The Quarry will use same engine as Until Dawn. I dont know if anyones working to get this models but im excited for.
## Post #70
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-06-11T15:39:10+00:00
- Post Title: Re: Until Dawn

> Reply from MadHotHatter ↑Sat Jun 11, 2022 10:58 pm at Sat Jun 11, 2022 10:58 pm
>
> 
I think The Quarry will use same engine as Until Dawn. I dont know if anyones working to get this models but im excited for.
Until Dawn used old (and very awkward) version of decima engine. I hope this will not be it.
## Post #71
- Username: MadHotHatter
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jun 11, 2022 10:55 pm
- Post datetime: 2022-06-11T15:45:01+00:00
- Post Title: Re: Until Dawn

If you saying... I can imagine how boring was to make a tool for this game.
## Post #72
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-06-11T15:47:08+00:00
- Post Title: Re: Until Dawn

All PC titles from Supermassive Games are using different UE4 versions, including Quarry.
## Post #73
- Username: MadHotHatter
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jun 11, 2022 10:55 pm
- Post datetime: 2022-06-11T15:49:24+00:00
- Post Title: Re: Until Dawn

If The Quarry was made on UE, so will not be a problem. Hard when is made on a unknown engine, i think!
## Post #74
- Username: MadHotHatter
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jun 11, 2022 10:55 pm
- Post datetime: 2022-06-11T15:54:30+00:00
- Post Title: Re: Until Dawn

While the topic of Until Dawn opened again to talk about Quarry, I wanted to know if you guys played it yet? If yes, is a good game to play? Dont wanna loose money lol
## Post #75
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2022-06-11T16:07:31+00:00
- Post Title: Re: Until Dawn

i played The Quarry day 1 and i loved it everyone survived my first playthrough!!! hopefully daemon1 can develope the tools since there is pc release the pkgs should be easy to find ; if anyone wants to check me out and my ports :

[https://www.deviantart.com/xnalaraall-might](https://www.deviantart.com/xnalaraall-might)
## Post #76
- Username: MadHotHatter
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jun 11, 2022 10:55 pm
- Post datetime: 2022-06-11T16:43:41+00:00
- Post Title: Re: Until Dawn

I'll check it
## Post #77
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2022-06-12T23:16:11+00:00
- Post Title: Re: Until Dawn

i was able to port but sadly the models dont have any facebones and the hair meshes are a mess!
[https://www.deviantart.com/xnalaraall-m ... -919101029](https://www.deviantart.com/xnalaraall-might/art/The-Quarry-Laura-XPS-919101029)
## Post #78
- Username: flvck000
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Oct 14, 2019 2:25 am
- Post datetime: 2022-06-19T18:02:20+00:00
- Post Title: Re: Until Dawn

> Reply from neonvega ↑Mon Jun 13, 2022 7:16 am at Mon Jun 13, 2022 7:16 am
>
> 
i was able to port but sadly the models dont have any facebones and the hair meshes are a mess!
https://www.deviantart.com/xnalaraall-m ... -919101029

No you didn't you're stealing the models from my patreon  and i will get them removed just contacted the support
## Post #79
- Username: Nianiouchka
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Nov 16, 2016 5:16 am
- Post datetime: 2022-08-24T03:08:00+00:00
- Post Title: Re: Until Dawn

> Reply from flvck000 ↑Mon Jun 20, 2022 2:02 am at Mon Jun 20, 2022 2:02 am
>
> 
neonvega wrote: ↑Mon Jun 13, 2022 7:16 am
i was able to port but sadly the models dont have any facebones and the hair meshes are a mess!
https://www.deviantart.com/xnalaraall-m ... -919101029


No you didn't you're stealing the models from my patreon  and i will get them removed just contacted the support

Hey, can I ask you how you got past the ''Serializing behind stopper'' error with Umodel when working on The Quarry ? I could successfully export a few characters like Eliza or Bobby myself...



But the main cast always gets me the error. A little help would be great, if possible. I'm using Unreal Engine version 4.27 override, and when I use 4.26, I get a ''Bad allocation size'' error, so no good either.

As for extracting using UnrealPak, I've used that method for games like Little Hope, but I don't know how to include the encryption key in the command for the tool to use it, unlike with Umodel where a window simply asks you for it. I always get the ''Failed to find requested encryption key 00000000000000000000000000000000'' error, obviously. I tried playing around with a crypto.json using Sublime Text, but can't figure out what to write exactly.

Which tools are you using yourself ?
## Post #80
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2022-08-24T08:44:56+00:00
- Post Title: Re: Until Dawn

Hi, see first Daemon1 post, at the top there is a description of how to use the program, and under screenshots of the link to the program
## Post #81
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-08-24T10:45:39+00:00
- Post Title: Re: Until Dawn

I think at least last page and some posts from previous page should be split into separate topic, as Until Dawn is using different engine than The Quarry, also discussed here. It's already confusing people.

@mods?
## Post #82
- Username: Nianiouchka
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Nov 16, 2016 5:16 am
- Post datetime: 2022-08-24T17:06:03+00:00
- Post Title: Re: Until Dawn

Yeah, I don't know if you were answering to me Crazy31139, but I'm talking about The Quarry, it looks like Until Dawn has its own tool. But there is no The Quarry thread, and little discussion about it. I jumped at the chance that someone might have informations about it, though it's not the right thread for that.
## Post #83
- Username: gamer4pcup
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 03, 2023 9:01 am
- Post datetime: 2023-01-06T04:51:00+00:00
- Post Title: Re: Until Dawn

I hope that with the new plugins feature in Goldhen 2.3 you can create mods with this tool (unless you can get Sam to be in a towel the whole game). Well, speaking of this, I tried it and I couldn't unzip not even a .unp stuck in the cmd window
