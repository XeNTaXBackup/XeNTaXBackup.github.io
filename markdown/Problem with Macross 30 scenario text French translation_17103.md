## Post #1
- Username: Dyaus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 04, 2017 5:31 pm
- Post datetime: 2017-10-04T10:03:53+00:00
- Post Title: Problem with Macross 30 scenario text French translation

Hello there !

I bought the Macross 30 PS3 video game a few weeks ago, and I want to translate all its talking to practice my Japanese grammar and fully understand the game story.

I managed to get a script folder of the game, wich include, between others, a talk.lua file for all the game chapters (talk00.lua to talk09.lua).

I understand that .lua files can be opened with text editor like Notepad++, but when I do it, Notepad only displays the first sentence of a dialog scene. 

For example :

> function TALK_11_020()	--シート11シーン020
>
> 	S_F_BeforeTalk()
>
> 	CreateTalkWindow()
>
> 
>
> 	TalkFace( PO_MIN, 0, LEFT0, PO_RIO, 0, CENTER, PO_AIS, 0, RIGHT0 )
>
> 	ScenarioTalk( "R_ScenarioText211310" )		--バジュラって、この前見かけたヤツですよね？
>
> 	ScenarioTalk( "R_ScenarioText211320" )
>
> 	ScenarioTalk( "R_ScenarioText211330" )
>
> 	ScenarioTalk( "R_ScenarioText211340" )
>
> 	ScenarioTalk( "R_ScenarioText211350" )
>
> 
>
> 	AfterTalk()
>
> end
>
> 
>
> 
>
> function TALK_11_030()	--シート11シーン030
>
> 	ScenarioSpeak( "R_ScenarioText211360" )		--バジュラも気になるけど、それ以上に気になるのがバジュラの騎士様よね。
>
> 	ScenarioSpeak( "R_ScenarioText211370" )
>
> 	ScenarioSpeak( "R_ScenarioText211380" )
>
> 	ScenarioSpeak( "R_ScenarioText211390" )
>
> 	DeleteSpeak()
>
> end
>
> 
>
> 
>
> function TALK_11_040()	--シート11シーン040
>
> 	ScenarioSpeak( "R_ScenarioText211400" )		--そろそろ報告にあった目的地に着くわ。
>
> 	ScenarioSpeak( "R_ScenarioText211410" )
>
> 	DeleteSpeak()
>
> end

There should be a sentence next to every R_ScenarioText, but only the first one of each scene (in green) is displayed.

So you guessed my question : what should I do to display all the sentences ?

I'm totally novice on this, so maybe I'm completely wrong about this way to get the game talks ^^"

Thanks a lot.
## Post #2
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2017-10-04T17:10:49+00:00
- Post Title: Problem with Macross 30 scenario text French translation

If the lua file is a plain text, NP++ shows everything, if that's not happening is because the text are not in this file. Seems to me that green texts are only commentary. The game texts should be in another file type.
