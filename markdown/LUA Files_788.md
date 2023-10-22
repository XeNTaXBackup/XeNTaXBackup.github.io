## Post #1
- Username: TheCheshire
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Jul 04, 2004 8:17 am
- Post datetime: 2004-07-04T03:45:06+00:00
- Post Title: LUA Files

I have downloaded and run the .pak program and it works great.  Now i have a problem opening/viewing the .lua files that i have found in some of the .pak files.  I am looking to get the background used on the main menu so that i may use it as a desktop background.  I could simply press print screen then paste it into paint but then i would be stuck with the menu options in front of the pic.  The background i am refering to is the main menu one, with a demon crucified on a pentagram.
Any ideas on how to go about getting this background ?
I have checked numerous websites for PK wallpapers and have found none that are what i am looking for.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-07-05T15:34:23+00:00
- Post Title: LUA Files

I am not quite sure how to help you, becasue I don't know which program you use (Painfull or MultiEx Commander) and if these programs give an error or something.
## Post #3
- Username: TheCheshire
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Jul 04, 2004 8:17 am
- Post datetime: 2004-07-05T17:29:39+00:00
- Post Title: LUA Files

ok let me explain this better....
I use PainFull to open LScripts.pak.  Inside of LScripts.pak are files such as
MainMenu.lua, CreateServerMenu.lua, etc.... I extract these files to a folder using PainFull. No problems.
Now i have these .lua files in a folder on my desktop.  I have no program that can open .lua files so that i may view them.  The .lua files i mentioned are obviously the background pictures for the menus but they are not .bmp or .jpg.  so how do i go about viewing these .lua files or converting them to a viewable pic?
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-07-05T20:46:50+00:00
- Post Title: LUA Files

Ah. okay. Well, you know, you can also use MultiEx Commander to open .pak files from Painkiller, and get immediate previews of files if you click them once (if Autopreview is on). 

Anyway, .lua files are text files. The name LScripts.pak should have given this away.   

Double-click one in Explorer and Windows will ask you to select a program to open them with. Choose Notepad. From now on, you will automatically open them in Notepad. 

If you are looking for the graphics, look in textures.pak. There you will find all sorts of graphic files, BMP, DDS, TGA etc. Also the menu graphics. 

As an example of the text in a lua file, here's the MainMenu.lua :

> MainMenu =
>
> {
>
> 	firstTimeShowItems = 80,
>
> 
>
> 	bgStartFrame = { 120, 243, 267 },
>
> 	bgEndFrame   = { 180, 266, 291 },
>
> 
>
> 	textColor	= R3D.RGBA( 100, 100, 100, 255 ),
>
> 	disabledColor = R3D.RGBA( 155, 155, 155, 255 ),
>
> 
>
> 	fontBigTex  = "HUD/font_texturka_alpha",
>
> 	fontSmallTex  = "HUD/font_texturka_alpha",
>
> 	descColor	= R3D.RGB( 255, 255, 255 ),
>
> 
>
> 	useItemBG = true,
>
> 
>
> 	items		=
>
> 	{
>
> 		SignAPact =
>
> 		{
>
> 			text = TXT.Menu.SignAPact,
>
> 			desc = TXT.MenuDesc.SignAPact,
>
> 			x	 = -1,
>
> 			y	 = 210,
>
> 			action = "PainMenu:SignAPact()",
>
> --			action = "PMENU:SwitchToMap()",
>
> 			sndLightOn = "menu/menu/option-light-on_main",
>
> --			disabled = 1,
>
> 		},
>
> 
>
> 		LoadGame =
>
> 		{
>
> 			text = TXT.Menu.LoadGame,
>
> 			desc = TXT.MenuDesc.LoadGame,
>
> 			x	 = -1,
>
> 			y	 = 290,
>
> 			action = "PainMenu:ActivateScreen(LoadSaveMenu)",
>
> --			disabled = 1,
>
> 			sndLightOn = "menu/menu/option-light-on_main2",
>
> 		},
>
> 
>
> 		Multiplayer =
>
> 		{
>
> 			text = TXT.Menu.Multiplayer,
>
> 			desc = TXT.MenuDesc.Multiplayer,
>
> 			x	 = -1,
>
> 			y	 = 370,
>
> 			action = "PainMenu:ActivateScreen(MultiplayerMenu)",
>
> 			sndLightOn = "menu/menu/option-light-on_main3",
>
> 			disabled = 1,
>
> 		},
>
> 
>
> 		Options =
>
> 		{
>
> 			text = TXT.Menu.Options,
>
> 			desc = TXT.MenuDesc.Options,
>
> 			x	 = -1,
>
> 			y	 = 450,
>
> 			action = "PainMenu:ActivateScreen(OptionsMenu)",
>
> 			sndLightOn = "menu/menu/option-light-on_main4",
>
> 		},
>
> 
>
> 		Quit =
>
> 		{
>
> 			text = TXT.Menu.Quit,
>
> 			desc = TXT.MenuDesc.Quit,
>
> 			x	 = -1,
>
> 			y	 = 530,
>
> --			action = "PainMenu:AskYesNo( Languages.Texts[469], 'Exit()', 'PainMenu:ActivateScreen(MainMenu)' )",
>
> 			action = "PainMenu:AskYesNo( Languages.Texts[469], 'PainMenu:ActivateScreen(DemoEnd)', 'PainMenu:ActivateScreen(MainMenu)' )",
>
> 			sndLightOn = "menu/menu/option-light-on_main5",
>
> 		},
>
> 
>
> 		BackButton =
>
> 		{
>
> 			text = TXT.Menu.Return,
>
> 			desc = TXT.MenuDesc.Return,
>
> 			textColor	= R3D.RGBA( 255, 255, 255, 255 ),
>
> 			x	 = 72,
>
> 			y	 = 660,
>
> 			fontBigSize = 36,
>
> 			align = MenuAlign.Left,
>
> 			inGameOnly = 1,
>
> 			action = "PMENU.ResumeSounds(); PMENU.ReturnToGame()",
>
> 			useItemBG = false,
>
> 		},
>
> 
>
> 		BackToMap =
>
> 		{
>
> 			text = TXT.Menu.ReturnToMap,
>
> 			desc = TXT.MenuDesc.ReturnToMap,
>
> 			textColor	= R3D.RGBA( 255, 255, 255, 255 ),
>
> 			x	 = 952,
>
> 			y	 = 660,
>
> 			fontBigSize = 36,
>
> 			align = MenuAlign.Right,
>
> 			inGameOnly = 1,
>
> 			action = "PainMenu:AskReturnToMap()",
>
> 			useItemBG = false,
>
> 		},
>
> 
>
> 		Credits =
>
> 		{
>
> 			text = TXT.Menu.Credits,
>
> 			desc = TXT.MenuDesc.Credits,
>
> 			textColor	= R3D.RGBA( 255, 255, 255, 255 ),
>
> 			x	 = -1,
>
> 			y	 = 660,
>
> 			fontBigSize = 36,
>
> 			action = "PMENU.ShowCredits()",
>
> 			useItemBG = false,
>
> 		},
>
> --[[
>
> 		Quit =
>
> 		{
>
> 			text = TXT.Menu.Quit,
>
> 			desc = TXT.MenuDesc.Quit,
>
> 			textColor	= R3D.RGBA( 255, 255, 255, 255 ),
>
> 			x	 = 952,
>
> 			y	 = 660,
>
> 			fontBigSize = 36,
>
> --			exitStart = 170,
>
> --			exitEnd = 240,
>
> 			align = MenuAlign.Right,
>
> --			action = "Exit()",
>
> 			action = "PainMenu:AskYesNo( Languages.Texts[469], 'Exit()', 'PainMenu:ActivateScreen(MainMenu)' )",
>
> --			action = "PainMenu:AskYesNo( 'Are you sure you want to quit Painkiller?\\nPeople Can Fly', 'Exit()', 'PainMenu:ActivateScreen(MainMenu)' )",
>
> 			useItemBG = false,
>
> 			sndAccept   = "menu/menu/quit-accept",
>
> 			sndLightOn  = "menu/menu/quit-light-on",
>
> 		},
>
> 
>
> 		Image =
>
> 		{
>
> 			type = MenuItemTypes.ImageButton,
>
> 			text = "",
>
> 			desc = "ImageButton test",
>
> 			image = "HUD/Map/karta_swiec",
>
> 			imageUnder = "HUD/Map/karta_wcisnieta",
>
> 			x	 = 10,
>
> 			y	 = 520,
>
> 			action = "",
>
> 		},
>
> 
>
> 		Weapons =
>
> 		{
>
> 			text		= "Weapons",
>
> 			desc		= "Go to weapon configuration screen",
>
> 			action		= "PainMenu:ActivateScreen(WeaponsConfig)",
>
> 			x			= 492,
>
> 			y			= 660,
>
> 			fontBigSize = 36,
>
> 			align		= MenuAlign.Right,
>
> 			useItemBG	= false,
>
> 			textColor	= R3D.RGBA( 255, 255, 255, 255 ),
>
> 			descColor	= R3D.RGB( 255, 255, 255 ),
>
> 			sndAccept   = "menu/menu/apply-accept",
>
> 			sndLightOn  = "menu/menu/back-light-on",
>
> 			fontBigTex  = "HUD/font_texturka_alpha",
>
> 			fontSmallTex= "HUD/font_texturka_alpha",
>
> 		}
>
> ]]--
>
> 	}
>
> }
## Post #5
- Username: TheCheshire
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Jul 04, 2004 8:17 am
- Post datetime: 2004-07-05T20:57:32+00:00
- Post Title: LUA Files

okay, so that's figured out.  Now, where in the world did they hid the main menu background picture !?  lol
i also get an error message when i try to upload my avatar to the site
## Post #6
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2004-07-06T03:32:50+00:00
- Post Title: LUA Files

> Reply from TheCheshire
>
> okay, so that's figured out.  Now, where in the world did they hid the main menu background picture !?  lol
i also get an error message when i try to upload my avatar to the site
Could you try again and copy/paste the error message you see?
## Post #7
- Username: TheCheshire
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Jul 04, 2004 8:17 am
- Post datetime: 2004-07-06T04:32:46+00:00
- Post Title: LUA Files

must have been a pixel or two over the permitted size.  so how about that main menu background ? .... anyone know where to find it ?
## Post #8
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2004-07-06T06:21:19+00:00
- Post Title: LUA Files

> Reply from TheCheshire
>
> must have been a pixel or two over the permitted size.
No actually it was a permissions issue in the forums configuration. I fixed it before you tried again.
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-07-06T07:20:23+00:00
- Post Title: LUA Files

Dude, 

> Reply from Mr.Mouse
>
> Ah. okay. Well, you know, you can also use MultiEx Commander to open .pak files from Painkiller, and get immediate previews of files if you click them once (if Autopreview is on).

> Reply from Mr.Mouse
>
> If you are looking for the graphics, look in textures.pak. There you will find all sorts of graphic files, BMP, DDS, TGA etc. Also the menu graphics.
## Post #10
- Username: TheCheshire
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Jul 04, 2004 8:17 am
- Post datetime: 2004-07-06T19:03:47+00:00
- Post Title: LUA Files

Mouse, you must take me for either a lazy person, or a retard....
I have gone thru each and ever file inside of the textures.pak files and i have found nothing.  Well, i found alot of really sweet pics, but not the one i've been typing about.  A demon crucified on a pentagram.  If you have played the game then you know the one i am referring to.  Unless .dds files are images, the background is not there.
I have gone thru every .pak file and have not found the image.
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-07-06T20:32:58+00:00
- Post Title: LUA Files

No, I don't think you are a retard. 

But I told you .DDS files are also images in a previous post.
## Post #12
- Username: TheCheshire
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Jul 04, 2004 8:17 am
- Post datetime: 2004-07-07T02:24:27+00:00
- Post Title: LUA Files

ggrrrrrrrrrrr
finally found a program to open .dds
Mouse, you duh mang
You duh MANG !
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-07-07T06:33:07+00:00
- Post Title: LUA Files

Care to translate that for me?

Anyway, if you don't read the messages people post in reply to your own posts, what more can one do?

1. I have told you to use MultiEx Commander instead of Painfull. Why? Because you can Autopreview the graphics while browsing, INCLUDING DDS files. 

2. I told you DDS files are graphics files TWICE, and still you come with "unless DDS files are graphic files the background is not there..."

That makes me wonder if you read anything people tell you. 

Another hint for you, download the DDS plugin for Adobe photoshop, if you have that program, to more easily edit DDS files. 

Oh, and I usually can't be bothered with details such as you ask for regarding games supported by MultiEx Commander, I don't actually play or do modding on all of these games, I just figure out the damn formats and that's it. But to be continously kind to you, the background you are looking for is, as I said, in textures.pak, and is called Menu.dds. 

Here it is, n'est-pas?
[Menu_s.jpg](https://xentaxbackup.github.io/file/40_Menu_s.jpg)
## Post #14
- Username: TheCheshire
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Jul 04, 2004 8:17 am
- Post datetime: 2004-07-07T13:58:36+00:00
- Post Title: LUA Files

i said you are the man, mr. mouse
i found the picture.  i read your posts, i just didnt know that .dds files were graphics files. sorry to cause you a hassle and for geting you huffy puffy.
## Post #15
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-07-07T14:02:38+00:00
- Post Title: LUA Files

No problem. I hope it has helped you out.
## Post #16
- Username: Tredo
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Aug 02, 2004 3:22 am
- Post datetime: 2004-08-07T09:28:22+00:00
- Post Title: Re: LUA Files

Use a diassambler to extract the hole shit.
## Post #17
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-07T10:43:35+00:00
- Post Title: Re: LUA Files

> Reply from Tredo
>
> Use a diassambler to extract the hole shit.

Umm, how does a disassembler help you extract anything?
## Post #18
- Username: Tredo
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Aug 02, 2004 3:22 am
- Post datetime: 2004-08-09T10:29:27+00:00
- Post Title: Re: LUA Files

That you can view in a diassambler, that Is what you get...
## Post #19
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-09T15:37:19+00:00
- Post Title: Re: LUA Files

You sure you don't mean a hex editor?  A disassembler takes binary code and turns it into assembly (human readable TEXT code).  You don't disassemble an archive file, you would disassemble, the game executable.  Not the same thing.
## Post #20
- Username: Tredo
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Aug 02, 2004 3:22 am
- Post datetime: 2004-08-09T16:40:42+00:00
- Post Title: Re: LUA Files

Okey, sorry, didnt saw that he was talking about a archive file first
## Post #21
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2004-08-09T16:46:37+00:00
- Post Title: Re: LUA Files

No Problem, just trying to clearify.
