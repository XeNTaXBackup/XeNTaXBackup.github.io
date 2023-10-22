## Post #1
- Username: REfan
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Apr 05, 2012 10:42 pm
- Post datetime: 2012-11-03T01:29:05+00:00
- Post Title: Resident Evil Operation Raccoon City PC Model Extractor

Resident Evil Operation Raccoon City PC Model Extractor
By Son of Persia
October 2012


Hi again dear friends  .


Preface

This program helps you to extract Resident Evil Operation Raccoon City PC version models and export them in both OBJ/MTL and SMD formats.

Before talking more about it, I like to mention something that in my (not necessarily your's ofcourse) opinion is really impoertant and must be discussed once and for all. So, please be patient and listen to a short story about how and mainly WHY I started game file cracking. Yeah as you might already have guessed DEMAND was my main reason.

About three monthes ago, after PC version of Resident Evil Operation Raccoon City was released, I was nothing but an ultra noob in game file cracking and really loved to have all models and textures of this game. so, after dear chrrox did a great favour and released it's bms script, I finally could get my hands on the models BUT unfortunately without any textures and BONES!!!

So, I decided to apply the textures manually by myself in a 3d application and it worked thanks to chrrox. But one thing I certainly was unable to do was to apply the bones to get the rigged models - the main thing I needed to port the models to my other popular games.

Like many of you, I decided to ask the author to honor my request and if it's possible for him, do me another great favour and update his script so that it can rip the bones too. I did and repeated my requests more and more but as you might guess, the result was NULL. He simply told that is no more interested in this game and refused to add only ten lines of code(believe me, only ten lines. I know it now for sure) to his script inorder to answer my and so many others requests!!!!

After this happened I could not stop asking myself WHY?? Why shouldn't I be able to get what I want AND mainly why should I ask it from the others who simply don't (and won't) give a SHIT (to be polite, please read it RESPECT) to the other's requests???
This simple conclusion, FORCED me to move, study hard and start learning this interesting filed. So I recommend you all my dear friends to respect your dreams and FORCE them happen ONLY BY YOUR POWERFUL HANDS NOT THE OTHERS who don't even know you and do NOT care about your important requests.

At the end of this boring story, have a few words with dear game file crackers who might care : 

PLEASE before you decide to work on extracting a given game file, first decide to do it to the END and FINISH your project NOT just leave it after extracting vertices and faces. BONES my friends are the main things that give life to the characters and resources you gratefully put your pricious time and extract to make the others happy. 
So, please listen to the advice of your little ultra noob friend and extract the models with bones and full textures OR simply LEAVE IT OUT TO THE OTHERS THAT CARE AND CAN FINISH IT, without engaging yourself and wasting your pricious time pointless and useless.

Please forgive me for wasting your time but this was the story behind this tool that MUST be told and heared. Remember that my goal is not to blame, judge or bother the others(specially dear chrrox). Also forgive my awfull spelling. you know, I actually am not a native english speaker.

Let's get back to the tool I'm going to award to you my dear friends.


Program Usage

Open autorun.bet file included with the tool and replace the game installation path on your PC with "C:\Program Files\Resident Evil Operation Raccoon City" string in the file and save it. Your hardest job after doing this is to DOUBLE CLICK ON AUTORUN.BAT FILE.

Instead of using autorun.bat file, you can also create an empty batch(.bat) file yourself and add this script to it :

FOR %%a in (*.edgemodel) DO REORC_Model_Extractor.exe %%a "Game Installation Path"

You also can type the following script in commandline : 

REORC_Model_Extractor <infile.edgemodel> <"REORC installation path on your PC">

for example : REORC_Model_Extractor adawong.edgemodel "C:\Program Files\REORC"

Please remember that using double quotations " " is necessary for game installation path Unless the white spaces in the path will be ignored and you'll get a model without bones and textures. 

BUT if the game installation path on your PC does not contain any white spaces, this time you can simply add it to the above script without double quotations. 

for example : REORC_Model_Extractor adawong.edgemodel C:\REORC


Important Notice

I used visual c++ 2005 on 32-bit win 7 to compile and build this tool. As a result, older OS like win xp and other 64-bit system may not be able to run this tool. So, if that happened please do not blame me. Instead try to run this tool on a 32-bit win 7 PC.


Credits

As I already mentioned, this tool is mainly based on the awsome bms script done by dear chrrox. I just updated his script by adding bones and texture support with some help from dear Codeman. 
So, all the credits goes to these two dear guys. 


Final Words

As one of my main rules for releasing a tool to public, this tool is throughly tested to work best and as flawlessly as possible. However, like other softwares it also is not guaranteed to work perfectly and may have some bugs I've never encountered before. 
I'm asknig you to please do me this great favour and report any bugs you discovered and let me correct them in future updates(rarely possible considering my current timing constraints).

[Download Link Here](http://www.mediafire.com/?b9br6chx5ypbb1p)

Thank you so much for your attention and I hope you enjoy using my gift.

With best wishes... 

Soroosh
## Post #2
- Username: Kamillho
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-11-03T02:30:00+00:00
- Post Title: Resident Evil Operation Raccoon City PC Model Extractor

I don't understand you at all. If you don't like a script why download it?
If your request is important higher a programmer who wants to to do it for you.
Last time i checked no one here does this for money and it is a hobby so they can support whatever they want to in their free time.
Its people like you who make people not work on things because you feel it is your right to have every game model and everyone should do it for you.
You just said you used the script i made and codeman's work to make this program but you also said they should of never existed.
No one owes you or anyone else on here anything so you need to not demand anything from anyone who does thing in their free time for fun.
## Post #3
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-11-03T10:43:58+00:00
- Post Title: Resident Evil Operation Raccoon City PC Model Extractor

I tested this on W7 32-bit and 64-bit. And doesn't work.

"Open autorun.bet file included with the tool and replace the game installation path on your PC with "C:\Program Files\Resident Evil Operation Raccoon City" string in the file and save it. Your hardest job after doing this is to DOUBLE CLICK ON AUTORUN.BAT FILE." I did this and I got the same error as using your RE0 extractor tool.
## Post #4
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-11-03T13:34:45+00:00
- Post Title: Resident Evil Operation Raccoon City PC Model Extractor

I'm sorry, it's nice that you made that script for the community and everything, but as for your story, really are you serious? You even mentioned to start with Chrrox released the original script, the fact that you couldn't be grateful for even that much is really displeasing to hear, and that you feel for some reason you were owed more from him? When people reverse things they never ask for praise, and there are a lot of forums over the internet where they share models that they have ripped using the tools from this site and don't credit the people that make it, and the guys here that reverse the stuff never complain about that, they do everything they do for no money, they don't have to do this stuff for others if they don't want to. You really should be grateful that Chrrox created the first script in the first place, it's good that you learnt from it and could continue with it from there, there really was no need for you to make such bitter remarks. Well, thanks for contributing to the community I guess.
## Post #5
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2012-11-03T16:05:59+00:00
- Post Title: Resident Evil Operation Raccoon City PC Model Extractor

> Reply from Kamillho
>
> I tested this on W7 32-bit and 64-bit. And doesn't work.

"Open autorun.bet file included with the tool and replace the game installation path on your PC with "C:\Program Files\Resident Evil Operation Raccoon City" string in the file and save it. Your hardest job after doing this is to DOUBLE CLICK ON AUTORUN.BAT FILE." I did this and I got the same error as using your RE0 extractor tool.
it is because he build the app in debugmode not release ....
## Post #6
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2012-11-03T16:18:38+00:00
- Post Title: Resident Evil Operation Raccoon City PC Model Extractor

> Reply from rman2
>
> I'm sorry, it's nice that you made that script for the community and everything, but as for your story, really are you serious? You even mentioned to start with Chrrox released the original script, the fact that you couldn't be grateful for even that much is really displeasing to hear, and that you feel for some reason you were owed more from him? When people reverse things they never ask for praise, and there are a lot of forums over the internet where they share models that they have ripped using the tools from this site and don't credit the people that make it, and the guys here that reverse the stuff never complain about that, they do everything they do for no money, they don't have to do this stuff for others if they don't want to. You really should be grateful that Chrrox created the first script in the first place, it's good that you learnt from it and could continue with it from there, there really was no need for you to make such bitter remarks. Well, thanks for contributing to the community I guess.

1000x Exactly. So many of us just use these guys as a resource without ever giving anything back. and it seems when it is given back, it's with snide remarks like this topic.
## Post #7
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-11-03T17:01:41+00:00
- Post Title: Resident Evil Operation Raccoon City PC Model Extractor

> Reply from shadowmoy
>
> Kamillho wrote:I tested this on W7 32-bit and 64-bit. And doesn't work.

"Open autorun.bet file included with the tool and replace the game installation path on your PC with "C:\Program Files\Resident Evil Operation Raccoon City" string in the file and save it. Your hardest job after doing this is to DOUBLE CLICK ON AUTORUN.BAT FILE." I did this and I got the same error as using your RE0 extractor tool.
it is because he build the app in debugmode not release ....

I dont understand... So...he relased files for extract models with game bones or not?
## Post #8
- Username: REfan
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Apr 05, 2012 10:42 pm
- Post datetime: 2012-11-03T17:11:07+00:00
- Post Title: Resident Evil Operation Raccoon City PC Model Extractor

> I don't understand you at all. If you don't like a script why download it?
>
> If your request is important higher a programmer who wants to to do it for you.
>
> Last time i checked no one here does this for money and it is a hobby so they can support whatever they want to in their free time.
>
> Its people like you who make people not work on things because you feel it is your right to have every game model and everyone should do it for you.
>
> You just said you used the script i made and codeman's work to make this program but you also said they should of never existed.
>
> No one owes you or anyone else on here anything so you need to not demand anything from anyone who does thing in their free time for fun.
Here is my point dude. If you want to make the others happy, PLEASE finish it NOT just leave it after ripping polygons FOR FUNNNNNNNNNN IN YOUR FREE TIMES!!!!
You can do whatever u like to do and I pesonally do not expect a line of code from u now that I can do anything I like BY MY HANDS but to others that are still noob and love to use scripts from guys like u, plz finish a job you start OR NEVER START IT. this point is also a good one in your real life dude.

Have fun  .
## Post #9
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-11-03T17:39:43+00:00
- Post Title: Resident Evil Operation Raccoon City PC Model Extractor

Not sure If you're older than me(me '93,you '84), cuz you wrote like totally troll

"Hey I made it, you not, I'm the best, look, look".  

"PLEASE finish it NOT just leave it after ripping polygons FOR FUNNNNNNNNNN IN YOUR FREE TIMES!!!!"
You should say thanks for original tools.

"You can do whatever u like to do and I pesonally do not expect a line of code"
Who cares? RE ORC models are ugly.

"this point is also a good one in your real life dude." I think you need something diffrent than point in your life. 

"Have fun"
Thanks.
## Post #10
- Username: REfan
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Apr 05, 2012 10:42 pm
- Post datetime: 2012-11-03T17:53:25+00:00
- Post Title: Resident Evil Operation Raccoon City PC Model Extractor

Hey would you plz stop puting your nose in others stuff. 
that post was my response to what chrrox wrote.
Kamlliho, would u plz do me a favour and dissapear from the threads I start. plz do me this greate favour and forget about my tools. I'll be really gratefull if you do this for me.
## Post #11
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-11-03T18:01:55+00:00
- Post Title: Resident Evil Operation Raccoon City PC Model Extractor

I just wanted some help but I see that you're busy replying how wise you are. Nothing can beat how you started insulting me when I wrote about wrong extracted texuters from RE6.

Thread probably will be fast deleted so I wish good luck and think about that how you reply people because with attitude nobody will help you here.
## Post #12
- Username: REfan
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Apr 05, 2012 10:42 pm
- Post datetime: 2012-11-03T18:09:09+00:00
- Post Title: Resident Evil Operation Raccoon City PC Model Extractor

> Reply from Kamillho
>
> I just wanted some help but I see that you're busy replying how wise you are. Nothing can beat how you started insulting me when I wrote about wrong extracted texuters from RE6.

Thread probably will be fast deleted so I wish good luck and think about that how you reply people because with attitude nobody will help you here.
At least I do not need your help. so plz stop crying you little girl  .
## Post #13
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2012-11-03T18:53:47+00:00
- Post Title: Resident Evil Operation Raccoon City PC Model Extractor

REFan, I'd really consider how you're acting right now. Some one who does something for free in their spare time has NO requirement to satisfy anyone. Hell, I even donated to HCS when he was looking at Bad company 2 pc sound files as a measure of good will. He didn't figure out the format. But I'm not going to be an ass and ask for $50 back. No, I'm going to be happy I helped with the hosting of the site that month, and more importantly, I'm going to keep at it myself until I figure it out. When that happens I'm not going to share as a way to rub it in anyone's face, I'm going to share it to help others. And if people needed help with the tool I made, I would HELP THEM. instead of being a total ass.
## Post #14
- Username: REfan
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Apr 05, 2012 10:42 pm
- Post datetime: 2012-11-03T19:03:44+00:00
- Post Title: Resident Evil Operation Raccoon City PC Model Extractor

> REFan, I'd really consider how you're acting right now. Some one who does something for free in their spare time has NO requirement to satisfy anyone. Hell, I even donated to HCS when he was looking at Bad company 2 pc sound files as a measure of good will. He didn't figure out the format. But I'm not going to be an ass and ask for $50 back. No, I'm going to be happy I helped with the hosting of the site that month, and more importantly, I'm going to keep at it myself until I figure it out. When that happens I'm not going to share as a way to rub it in anyone's face, I'm going to share it to help others. And if people needed help with the tool I made, I would HELP THEM. instead of being a total ass.
It really dissappoints me that understanding the sentence " Finish the job you start" is that hard for some guys here. Grow up and then come to talk here babies. ASS is your whole existance you dickhead.
## Post #15
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2012-11-03T19:15:50+00:00
- Post Title: Resident Evil Operation Raccoon City PC Model Extractor

> It really dissappoints me that understanding the sentence " Finish the job you start" is that hard for some guys here. Grow up and then come to talk here babies. ASS is your whole existance you dickhead.

Other people do not need to live by your own personal mantra. They can do whatever they want. you should still act reasonably and be happy with what you got, you want to expand it into a tool that does more? go ahead! you did? great job! Just don't treat everyone else like shit in the process.
## Post #16
- Username: REfan
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Apr 05, 2012 10:42 pm
- Post datetime: 2012-11-03T19:27:34+00:00
- Post Title: Re: Resident Evil Operation Raccoon City PC Model Extractor

Thanks for your advice mate. At lease I respect the others enough by putting more time inorder to give them a complete tool not just a half tuned script that generates a milky model with much UV errors. 
Just being like " john carmack" with BILLIONS of THANKS, SCRIPTS, etc ... give not us the right to leave our job semi finished (even if we do it for anyshit like "fun in damn free times" - this damn sentence is really killing me .. for fun in free times   ) and laughing at the others and telling them hire(NOT HIGHER) a programmer to do your requets!!! what a redicules sentece. sorry but I just could not stop laughing the moment I read that   .
## Post #17
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-11-03T19:30:12+00:00
- Post Title: Re: Resident Evil Operation Raccoon City PC Model Extractor

You are calling people here babies but the only one that is speaking with an immature attitude is you, you say we don't understand 'finish what you start,' but you do not understand someone elses definition of finishing is different to anothers. You have the models from this RE game, you should finish what you started and extract all the audio from the game as well now. Please don't come back until you have extracted every single thing from the game 100%, Finish what you started
## Post #18
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2012-11-03T19:42:12+00:00
- Post Title: Re: Resident Evil Operation Raccoon City PC Model Extractor

> Reply from REfan
>
> Thanks for your advice mate. At lease I respect the others enough by putting more time inorder to give them a complete tool not just a half tuned script that generates a milky model with much UV errors. 
Just being like " john carmack" with BILLIONS of THANKS, SCRIPTS, etc ... give not us the right to leave our job semi finished (even if we do it for anyshit like "fun in damn free times" - this damn sentence is really killing me .. for fun in free times   ) and laughing at the others and telling them hire(NOT HIGHER) a programmer to do your requets!!! what a redicules sentece. sorry but I just could not stop laughing the moment I read that   .

That's your own expectation you applied to chorrox, he doesn't have to oblige it.

Meanwhile, you aren't obliging this whole community's expectations of decency. Those aren't something you can just shrug off and say grow up to, because that's not how communities work. You can't go outside and flash your junk at little girls then tell them to grow a pair, this a community site and I've seen this situation happen before. You'll get banned, and be all sour about it, have your own version of events, and you'll justify the whole situation in your mind.
## Post #19
- Username: REfan
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Apr 05, 2012 10:42 pm
- Post datetime: 2012-11-03T21:58:33+00:00
- Post Title: Re: Resident Evil Operation Raccoon City PC Model Extractor

> Reply from rman2
>
> You are calling people here babies but the only one that is speaking with an immature attitude is you, you say we don't understand 'finish what you start,' but you do not understand someone elses definition of finishing is different to anothers. You have the models from this RE game, you should finish what you started and extract all the audio from the game as well now. Please don't come back until you have extracted every single thing from the game 100%, Finish what you started
Wow!! what a solid conclusion. man you just proved the theory of relativity with this  .
your conclusion really changed my life forever. Did not you read this " I loved to have all the MODELSSSSSSSSSS and textures of this game"????? Thanks to you, now I know that a model in 3d also includes the audio!!!    .
Why do you waste your time here??? plz go to NASA or MIT for your incredible talents    .
## Post #20
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-11-03T22:11:06+00:00
- Post Title: Re: Resident Evil Operation Raccoon City PC Model Extractor

Well, thanks for proving my point, to you, that is completion, to someone else it isn't. I went back and read the REORC topic and I'm sorry to tell you this but you're a very rude and demanding person, in that topic you were constantly haranguing Chrrox and it's really selfish of you to be honest. You criticise and talk about life skills that we should gain, but if I'm honest with you you should really look at that aspect of your personality, there's nothing worse than someone that as rude as that.
## Post #21
- Username: REfan
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Apr 05, 2012 10:42 pm
- Post datetime: 2012-11-03T22:23:05+00:00
- Post Title: Re: Resident Evil Operation Raccoon City PC Model Extractor

> Reply from rman2
>
> Well, thanks for proving my point, to you, that is completion, to someone else it isn't. I went back and read the REORC topic and I'm sorry to tell you this but you're a very rude and demanding person, in that topic you were constantly haranguing Chrrox and it's really selfish of you to be honest. You criticise and talk about life skills that we should gain, but if I'm honest with you you should really look at that aspect of your personality, there's nothing worse than someone that as rude as that.
You can say whatever you like to. being rude or whatever   . If you don't like what I say, plz do not read it and simply leave it. I wish you luck   . I'm kind of person wo finishes the job he starts and if you have any problems with my point, it's your problem not mine's. anyway let's finish this conversation  .
## Post #22
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-11-03T22:52:01+00:00
- Post Title: Re: Resident Evil Operation Raccoon City PC Model Extractor

> Reply from REfan
>
> rman2 wrote:Well, thanks for proving my point, to you, that is completion, to someone else it isn't. I went back and read the REORC topic and I'm sorry to tell you this but you're a very rude and demanding person, in that topic you were constantly haranguing Chrrox and it's really selfish of you to be honest. You criticise and talk about life skills that we should gain, but if I'm honest with you you should really look at that aspect of your personality, there's nothing worse than someone that as rude as that.
You can say whatever you like to. being rude or whatever   . If you don't like what I say, plz do not read it and simply leave it. I wish you luck   . I'm kind of person wo finishes the job he starts and if you have any problems with my point, it's your problem not mine's. anyway let's finish this conversation  .

Onced you were blocked probably they will do it again but you'll never come back. You'll see why. People tried to be nice, help you, and you started insulting them. And the most funny is that you're insulting persons that 90% of them made more than you. You except culture that you don't have. You're done here. Second account and worse behavior. Third time lucky, but you won't avoid rules third time.
## Post #23
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-11-03T23:53:05+00:00
- Post Title: Re: Resident Evil Operation Raccoon City PC Model Extractor

> Reply from REfan
>
> If you don't like what I say, plz do not read it and simply leave it.

Wow, thanks again for proving my point. Do you not even see it yourself? In that topic Chrrox did exactly that, he didn't like what you said and he left it. So if that's what you'd like people to do, don't cry about people not listening to you when you tell them to add more to their script. Nothing else to say beyond this point.
## Post #24
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-11-04T04:51:54+00:00
- Post Title: Re: Resident Evil Operation Raccoon City PC Model Extractor

Lol there are ways and manners of how to express yourself and it seems refan does not know about that.

I don't know if he is the same person who released the models in z6 re forums, but the same thing is going on.

I'm not a scripter, but at least I try to contribute in something to the community as a repay on my own free way for what I have gotten here so people can get inmerse on this.

See ya and refan relax man.
## Post #25
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-11-04T07:01:49+00:00
- Post Title: Re: Resident Evil Operation Raccoon City PC Model Extractor

why so angry for guys ?
## Post #26
- Username: REfan
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Apr 05, 2012 10:42 pm
- Post datetime: 2012-11-04T18:28:17+00:00
- Post Title: Re: Resident Evil Operation Raccoon City PC Model Extractor

> Reply from Darko
>
> Lol there are ways and manners of how to express yourself and it seems refan does not know about that.

I don't know if he is the same person who released the models in z6 re forums, but the same thing is going on.

I'm not a scripter, but at least I try to contribute in something to the community as a repay on my own free way for what I have gotten here so people can get inmerse on this.

See ya and refan relax man.
you try to repay your way and so do I. so plz hold your ideas for yourself and don't tell me how to do that. guys, I'll do it the way I like and don't care about your ideas but respect them cuz they are important only for yourself not mine. 
So guys, plz stop disturbing yourself because of your internal behavioural and charactristics problems you may have experienced in your real life   .
## Post #27
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2012-11-05T04:42:51+00:00
- Post Title: Re: Resident Evil Operation Raccoon City PC Model Extractor

Hi ReFAN, thanks for the tool, I don't care about all the other stuff mentioned. Before continuing arguing or get a Ban, can you please explain better how tu use it as someone pointed out it didn't work?
I'm interested in bones for studying purposes. Thanks, regards.
## Post #28
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-11-07T08:46:08+00:00
- Post Title: Re: Resident Evil Operation Raccoon City PC Model Extractor

Yo shadowmov, so what was the format of the bones? I remember seeing at the end 4 bytes per joint but couldn't figure out what I thought was some fixed-point vector or something.
## Post #29
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2012-11-09T11:36:33+00:00
- Post Title: Re: Resident Evil Operation Raccoon City PC Model Extractor

> Reply from howfie
>
> Yo shadowmov, so what was the format of the bones? I remember seeing at the end 4 bytes per joint but couldn't figure out what I thought was some fixed-point vector or something.
howfie>calling me ?
if so just drop me a pm about it , i figurated it ages ago, even before the game was officially out lol ...
