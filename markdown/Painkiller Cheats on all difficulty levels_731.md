## Post #1
- Username: Wizzy
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 14, 2004 12:25 am
- Post datetime: 2004-05-17T18:09:25+00:00
- Post Title: Painkiller Cheats on all difficulty levels

Thanx to Painfull Extractor, I was able to effect the following change.

To enable cheats for all difficulty levels, unpak Console.lua from lscripts.pak, open it in your favorite text editing program, look for the == Cheats == section and remove this entire line from each cheat -

if Game.Difficulty > 1 then CONSOLE.AddMessage(TXT.Cheats.LowLevelOnly) end

then just import back into the pak file and you are done..

Cheats in all levels.

Note : I still haven't figured out why PKPERFECT and PKALLCARDS cheats do not work.
Yet.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-17T18:30:49+00:00
- Post Title: Painkiller Cheats on all difficulty levels

Nice !
## Post #3
- Username: Wizzy
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 14, 2004 12:25 am
- Post datetime: 2004-05-17T19:37:16+00:00
- Post Title: Painkiller Cheats on all difficulty levels

I'm running into problems with these ; 

-- pkalllevels [enables all levels]
--function Console:Cmd_PKALLLEVELS()
--	if IsFinalBuild() then return end
--	if Game.GMode ~= GModes.SingleGame then return end
--	
--	for i=1,table.getn(Levels) do
--		for j=1,table.getn(Levels) do
--			Game:MakeEmptyLevelStats(Levels[j][1])
--			Game.LevelsStats[Levels[j][1]].Finished = true
--		end
--	end
--	CONSOLE.AddMessage(TXT.Cheats.PKAllLevels)
--	PMENU.SwitchToMenu()
--	PMENU.SwitchToMap()
--end


-- pkperfect [finish level with perfect score]
--[[
function Console:Cmd_PKPERFECT()

	if Game.GMode ~= GModes.SingleGame then return end
	Player.ArmorFound = Game.TotalArmor
	Player.HolyItems = Game.TotalHolyItems
	Game.PlayerAmmoFound = Game.TotalAmmo
	Game.PlayerDestroyedItems = Game.TotalDestroyed
	Player.SecretsFound = Game.TotalSecrets
	GObjects:Add(TempObjName(),CloneTemplate("EndLevel.CProcess"))
end
]]--


Could someone else look at these and help figure out what I'm doing wrong ?

As you can see, the first one is commented out, but when I try to make it run i get an " 'end' expected to close function" error

The second one I haven't spent  much time on yet.
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-17T19:43:07+00:00
- Post Title: Painkiller Cheats on all difficulty levels

Note: just moved it to this forum, as it seems a nice place for a discussion.
## Post #5
- Username: Wizzy
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 14, 2004 12:25 am
- Post datetime: 2004-05-17T19:49:44+00:00
- Post Title: Painkiller Cheats on all difficulty levels

Edit edit edit, rofl.........
## Post #6
- Username: fleabay
- Rank: n00b
- Number of posts: 12
- Joined date: Sat May 08, 2004 12:59 pm
- Post datetime: 2004-05-17T21:11:23+00:00
- Post Title: Painkiller Cheats on all difficulty levels

> I'm running into problems with these ;
The -- is a comment, remove it to run the line.
The --[[   blah blah  ]]-- is a bulk comment

You probably going to want to remove all the -- and --[[, ]]-- near the function you want to run and delete the unwanted lines, like IsFinalBuild and simular.
## Post #7
- Username: Wizzy
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 14, 2004 12:25 am
- Post datetime: 2004-05-18T03:47:07+00:00
- Post Title: Painkiller Cheats on all difficulty levels

> Reply from Wizzy
>
> 

As you can see, the first one is commented out, but when I try to make it run i get an " 'end' expected to close function" error

Yes, I believe I already made it clear that I know what -- represents.
Maybe I wasn't clear enough, though.
that section of the script is commented out by default.
I did have the common sense to remove all the hyphens when attempting to get it to run.
And I had also removed the other lines as well.
It may be right under my nose, I dunno..
Do for loops need an end the same way an if statement does ?
I looked at it and thought I had an end to every event in place, but still recieved errors...

And it still doesn't work.

Next ?
## Post #8
- Username: fleabay
- Rank: n00b
- Number of posts: 12
- Joined date: Sat May 08, 2004 12:59 pm
- Post datetime: 2004-05-18T05:32:38+00:00
- Post Title: Painkiller Cheats on all difficulty levels

Here are 3 working functions that i use

-- pkalllevels [enables all levels]
function Console:Cmd_PKALLLEVELS()
	if Game.GMode ~= GModes.SingleGame then return end
	if Game.Difficulty > 1 then CONSOLE.AddMessage(TXT.Cheats.LowLevelOnly); return end
	for i=1,table.getn(Levels) do
		for j=1,table.getn(Levels) do
			Game:MakeEmptyLevelStats(Levels[j][1])
			Game.LevelsStats[Levels[j][1]].Finished = true
		end
	end
	CONSOLE.AddMessage(TXT.Cheats.PKAllLevels)
	PMENU.SwitchToMenu()
	PMENU.SwitchToMap()
end


-- pkallcards [gives all black tarot cards]
function Console:Cmd_PKALLCARDS()
	if Game.GMode ~= GModes.SingleGame then return end
	if Game.Difficulty > 1 then CONSOLE.AddMessage(TXT.Cheats.LowLevelOnly); return end
	for i=1,table.getn(Game.CardsAvailable) do
		Game.CardsAvailable = true
	end
	CONSOLE.AddMessage(TXT.Cheats.PKAllCards)
	PMENU.SwitchToMap()
	PMENU.SwitchToBoard()
end

-- pkperfect [finish level with perfect score]
function Console:Cmd_PKPERFECT()
	if Game.GMode ~= GModes.SingleGame then return end
	Player.ArmorFound = Game.TotalArmor
	Player.HolyItems = Game.TotalHolyItems
	Game.PlayerAmmoFound = Game.TotalAmmo
	Game.PlayerDestroyedItems = Game.TotalDestroyed
	Player.SecretsFound = Game.TotalSecrets
	GObjects:Add(TempObjName(),CloneTemplate("EndLevel.CProcess"))
end
## Post #9
- Username: Wizzy
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 14, 2004 12:25 am
- Post datetime: 2004-05-18T06:16:30+00:00
- Post Title: Painkiller Cheats on all difficulty levels

I got the PKALLCARDS one working ( before I read your post, actually ) , but I copied pasted your exact entry for PKPERFECT and still get the "unknown command" error when typing it into the console.
## Post #10
- Username: fleabay
- Rank: n00b
- Number of posts: 12
- Joined date: Sat May 08, 2004 12:59 pm
- Post datetime: 2004-05-18T14:49:58+00:00
- Post Title: Painkiller Cheats on all difficulty levels

Care to try this one?

function Console:Cmd_PKTRAUMA()
PMENU.EnableItem("Trauma")
PMENU.SetItemDesc("Trauma", TXT.MenuDesc.Trauma)
end
## Post #11
- Username: Wizzy
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 14, 2004 12:25 am
- Post datetime: 2004-05-19T02:52:15+00:00
- Post Title: Painkiller Cheats on all difficulty levels

Ok, Whatever.
You are just wasting my time - this was intended for people who actually have something to contribute, or are looking to gain something from the posts already made.
As you seem interested in nothing more than throwing useless, crap information that does not work into this setting, you fit in neither of the above categories, so begone.
I'm sure there are plenty of places where you can play your childish "l33t" games, amusing yourself by attempting to waste people's time with worthless crap - this doesn't happen to be one of those places though.
Go back to the DreamCatcher forums and pretend to be above people there.
( Well, people other than me that is - for if you start wasting my time there, or start flame wars, I will either ignore you or engage in a brief but effective display of how little you really matter)
## Post #12
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-19T07:40:19+00:00
- Post Title: Painkiller Cheats on all difficulty levels

> Reply from Wizzy
>
> Ok, Whatever.
You are just wasting my time - this was intended for people who actually have something to contribute, or are looking to gain something from the posts already made.
As you seem interested in nothing more than throwing useless, crap information that does not work into this setting, you fit in neither of the above categories, so begone.
I'm sure there are plenty of places where you can play your childish "l33t" games, amusing yourself by attempting to waste people's time with worthless crap - this doesn't happen to be one of those places though.
Go back to the DreamCatcher forums and pretend to be above people there.
( Well, people other than me that is - for if you start wasting my time there, or start flame wars, I will either ignore you or engage in a brief but effective display of how little you really matter)

Now who is trolling and flaming, Fleabay,  or you Wizzy?
## Post #13
- Username: Wizzy
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 14, 2004 12:25 am
- Post datetime: 2004-05-19T17:32:34+00:00
- Post Title: Painkiller Cheats on all difficulty levels

Nope, not me.
But the information he posts is worthless, as it is simply a case of NOTHING he posts working.
So, given this fact, it strikes me that posting stuff he knows does not work is just an effort to amuse himself.
Yawn.
I have tried to give him the benefit of the doubt by actually trying everything I can find from him to see if it works, and quite simply, it is all a bunch of crap that does nothing.
And, at the other site, he has even gone so far as to represent himself as some sort of "l33t" type, the whole clannish mentality thing.
Well, I guess that might have some credence if anything he "offers" would actually work.
But it doesn't.
And I started this to get people involved who would either have something real to offer or who were looking to learn more about it.
He has only offered posts that contain bogus information, and obviously has no interest in learning anything, given his (laughably )assumed stance of "being ahead of everyone else" in re the scripting capabilities.
Therefore, I utterly fail to understand how his presence here has any reason whatsoever, other than to attempt to achieve the same "status" he has appointed to himself at the other site.
A status based upon nothing REAL, whatsoever, as nothing he posts is ( when you get right down to it ) worth the time it takes to read it.
Were he actually making any real effort to be a part of this and contribute, all would be well - but he is doing nothing more, it strikes me, than playing silly childish games by posting crap that doesn't work - the inevitable result of which is that the more people who try it and find it doesn't work, the greater the chance of increased posts by people whom he has irritated by wasting their time.
The kind of people this individual needs to feed his ego are those who fail to realize that he is just wasting their time, and who will post their frustration over and over again at not being able to get what he posted to work - a tactic which suggests to me that this individual is either a very emotionally insecure teenager or a very maladjusted "adult".
So far, his very presence here has developed into nothing more, collectively, than an utter waste of time.
So I would contend that his being here and posting crap that is only going to irritate people by virtue of it being an utter waste of their time makes this a case of him trying to employ what he surely regards as a "clever" way of trolling -- not by direct comments, but by doing something he knows will irritate people and spur them to angry posts. 
So, indeed, who IS the one trolling ?
Spamming ?
## Post #14
- Username: fleabay
- Rank: n00b
- Number of posts: 12
- Joined date: Sat May 08, 2004 12:59 pm
- Post datetime: 2004-05-19T17:48:52+00:00
- Post Title: Painkiller Cheats on all difficulty levels

I will be posting a new version of my scripts later on today at dreamcatcher.  I think you will find many people thanking me for my WORKING efforts in the next few days, much in the same way as the last time.

Everything I have tried to help you with has worked fine for others.  I don't need to be insulted for trying to help someone, even if your having problems.
## Post #15
- Username: Wizzy
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 14, 2004 12:25 am
- Post datetime: 2004-05-19T18:05:28+00:00
- Post Title: Painkiller Cheats on all difficulty levels

Really ?
Hmmm, ok......
Will these new versions be ones that actually do anything at all ?
Let's see - I read the read me file and followed your instructions to the letter about creating folders and placing of files.
Nothing.
And never mind that your assertion that you were able to enable the cheats with the scripts you posted being in error, even when importing them back into lscripts.pak....
But I'll listen if you have something else to add that you may have failed to address in the read me file.
## Post #16
- Username: fleabay
- Rank: n00b
- Number of posts: 12
- Joined date: Sat May 08, 2004 12:59 pm
- Post datetime: 2004-05-19T19:55:24+00:00
- Post Title: 

There will be an installer to keep everyone from needing to worry about the details.
## Post #17
- Username: Wizzy
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 14, 2004 12:25 am
- Post datetime: 2004-05-19T23:19:49+00:00
- Post Title: 

Ha ha ha.
Do you even know where you are ?
Well, the entire point of this thread - this very website,  is " the details"
This isn't an " I have it, you can download it " setting, but rather one intended to examine the details down to the last .
Such an approach runs counter to the very idea of modding, unless you release the file in a format which can be easily unpacked and examined in-depth.
And frankly, I fail to see the point of releasing it in a self-installing manner, at least for the users you will encounter here.
Unless, of course, you release it in 2 fashions : self-installing for those who don't want to pick things apart and examine them, and as script files for those of us who do.
But I think the one most pervasive question remaining is this : 
Is the manner in which such modified files are made available by you  going to have any real influence on whether they actually do anything or not ?
If you say yes to this, then that is utter proof that there is something you have left out insofar as what is required to make the information you HAVE posted actually work.
This would be sufficient proof that your installer would carry out tasks which you have not revealed need be carried out in order to make your mod work when attempting ( as I have ) to get it to work by manually placing files.
I have, after all, employed every bit of information you have been forthcoming with in an effort to get your "mod" to work, yet to no avail.
This suggests to me, since I am utterly confident that I am not an idiot, that there are simply some details you have elected to not disclose.
This is your right, of course, as no-one can force you to be forthcoming in this matter.
But frankly, it does strike me that, at least in forums such as these, you are simply in the wrong place to be exercising such self-aggrandizing tactics.
This is a setting in which the members are here to share information.
So either elect to become a sincere part of this open-source motivated environment, or ( I am sure ) soon find yourself completely ignored.
Frankly, as I have utterly no faith whatsoever in the possibility that you will be forthcoming ( i think you have selfishness and control issues ), I am simply ignoring you from this point forward, and will attempt to go on working out the details alone, unless someone else should come along who wishes to join in the process.
## Post #18
- Username: Wizzy
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 14, 2004 12:25 am
- Post datetime: 2004-05-20T06:29:35+00:00
- Post Title: 

Follow-up :
I apologize to fleabay, and to all who have read my "outbursts"
It would seem that I jumped the gun.
Of course, had fleabay ( being the author of said mod ) bothered to ask me if I was using the version it was meant to work with, this might not have gone on so long.
The entire time, he was aware that there was another file he had altered ( loader.lua ) which was ALSO required to make it work with v 1.15.
So, in my defense, my anger / dismissal of him was such that I believed it warranted.
It has all been an unfortunate failure to communicate needed facts on his part and a failure on my part to find out on my own what I needed to know in order to see that his stuff does indeed work as he says.
All I had previously had to go on was his assertion that it would work with either ver, 1.0 or 1.15.
In the post in which he stated that, he made no reference to the fact that the only way his file local.lua would work with v 1.15 was if you additionally downloaded and placed an amended version of loader.lua.
Had I known this, there would have been no need for this apology.
Nonetheless, it is upon me to apologize for my posts.
## Post #19
- Username: fleabay
- Rank: n00b
- Number of posts: 12
- Joined date: Sat May 08, 2004 12:59 pm
- Post datetime: 2004-05-20T14:56:45+00:00
- Post Title: 

You were being insulting long before you implied having trouble with the powermad script.  I was trying to help you change the original scripts and you were insulting even then.  I had ideas on what your problem was but didn't care to help you after the insults.

I know its flustrating getting things to work sometimes.  I had had my fair share of 'It works, must be you' comments.  I am more than willing to help people that appriciate it.  Had you asked to start with, I would have spent days on helping you.
## Post #20
- Username: Wizzy
- Rank: beginner
- Number of posts: 31
- Joined date: Fri May 14, 2004 12:25 am
- Post datetime: 2004-05-20T15:31:39+00:00
- Post Title: 

Well, I've said I apologize.
Over at the dreamcatcher forums as well.
And I still don't get this one, as now that everything else works, this still falls dead :

> Reply from fleabay
>
> Care to try this one?

function Console:Cmd_PKTRAUMA()
PMENU.EnableItem("Trauma")
PMENU.SetItemDesc("Trauma", TXT.MenuDesc.Trauma)
end

Not that I particularly need it, as it would seem that is is designed simply to enable trauma mode - the only reason I bring it up is because if it can be made to work then I'm one of those who has to know how.
And, as I also stated at the dremcatcher forums, nice work.
It is appreciated and I enjoyed it alot, especially the no clip function, as I am starting to have serious doubts as to this whole PK Jumping thing ( It is starting to strike me that PK jumping isn't something that can be done in a single player game, as I have beat my hardware to death in an effort to execute one and get no more height than from a standard jump )
Looks like it's time to find out where the settings are for standard jump height and make the default a somewhat  higher value.
I had also attempted to increase default movement speed but it didn't work.
Anyway, I visited your site and dl'd everything.
