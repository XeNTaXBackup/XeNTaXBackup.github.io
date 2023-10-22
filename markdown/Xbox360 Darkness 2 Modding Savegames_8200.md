## Post #1
- Username: EnigmaUK
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 30, 2012 6:47 pm
- Post datetime: 2012-02-06T10:48:01+00:00
- Post Title: Xbox360 Darkness 2 Modding Savegames

hello peeps forgive me im new here and its my first post so lets have a slice of Darkness 2 savegame mods 
this is a siple savegame mod for the game that will help boost your Essence Levels and Talent point levels


your gonna need 360revolution (or any other resigner you wish to use)
a darkness 2 savegame
a hex editor (either hxd or hex workshop)


first off open 360revolution(or your preffered resigner)
drag your Darkness 2 save into it
right click CONTINUE.SAV and Extract to desktop

now close 360revolution for now (or your desired resigner)

drop the Continue.SAV into hxd(or hex workshop)
(im using Hxd for this tut)

hit CTRL+F in hxd and do a test search for Essence
make sure search direction All is selected


now you will end up at Essence= (your amounts here)
on picture 3 notice the single byte i have highlighted the 0A

if you overwrite this byte you will kill your save
so what were gonna do is
overwrite the essence points teh value we have now with 9000000
after the last 0 put in a decimal dot . right click that and fill selection
with 0A

now we do the same with TalentPoints

when thats done hit F3 go to next Essence= and do the same again untill it says cannot find Essence

when completed close down hxd and save changes

now reopen 360revolution(or whatever resigner your using)
drag your UserSavecontent save back into it
click the content tab
highlight CONTINUE.SAV
right click and Select Inject
select your new modded CONTINUE.SAV AND CLICK OK

click the Main tab after that resign/rehash
and your all done load the save up and your good to go

nice and simple way to boost your stats and points for it 
hopefully this tut made sense and apologys if its in the wrong place 
peace out
•Σиïgмλ•
## Post #2
- Username: godzcheater
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Feb 04, 2012 3:37 am
- Post datetime: 2012-02-15T17:35:26+00:00
- Post Title: Xbox360 Darkness 2 Modding Savegames

360revolution is poorly coded, I would recommend Horizon, its STFS class is eminence.
And it is quicker to load the Save into a text stream(like sublime or notepad++) then you don't have to replace the 0x0A.
