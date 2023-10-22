## Post #1
- Username: Cloud452
- Rank: veteran
- Number of posts: 91
- Joined date: Sat Oct 23, 2010 9:50 pm
- Post datetime: 2011-03-24T05:19:40+00:00
- Post Title: PSP "edat" format

So since the DLC for Dissidia 012 Duodecim are in "edat" format (found [KH Cloud](http://www.mediafire.com/?85q441y4rqmkhbp) and [Aerith data](http://www.mediafire.com/?fsk3umx77dd94mg)..though her model is in the game itself.... posted at the [GameFAQ's savedata area](http://www.gamefaqs.com/psp/605802-dissidia-012-duodecim-final-fantasy/saves))... it's currently impossible to decrypt them to get at the data? The recent PSP private keys being released doesn't change matters?

If so... that's a shame, I really wanted access to the models (to do more of these: [http://www.youtube.com/watch?v=2Rf-c-xZRY8](http://www.youtube.com/watch?v=2Rf-c-xZRY8) and to have a friend make more [cool wallpapers](http://community.livejournal.com/ffchaoticcosmos/397273.html)).
## Post #2
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-04-02T19:29:47+00:00
- Post Title: PSP "edat" format

I personally want to get access to these models as well. I could post the edat's of WoL's 4th costume with his helmet off if we figure this out.

I've been trying to find similarities to the gmo models but there doesn't seem to be any real similarities. I can't find bone names and the like. So I think it is a real archive rather than a gmo with a new extension.

But since this is mostly regarding models you may get more luck if you posted this thread in the 3D Model section.
## Post #3
- Username: codestation
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jan 18, 2011 3:52 am
- Post datetime: 2011-04-03T14:18:26+00:00
- Post Title: PSP "edat" format

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-04-04T04:33:06+00:00
- Post Title: PSP "edat" format

Well I thought I'd be clever and try GitMO on these to see if I could get anything out of them. And that doesn't work. Codestation you posted as if you were able to get the gmo out of them but the file you posted is still an Edat so it appears.
## Post #5
- Username: codestation
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jan 18, 2011 3:52 am
- Post datetime: 2011-04-04T14:34:39+00:00
- Post Title: PSP "edat" format

> Reply from Zerox
>
> Well I thought I'd be clever and try GitMO on these to see if I could get anything out of them. And that doesn't work. Codestation you posted as if you were able to get the gmo out of them but the file you posted is still an Edat so it appears.
I just left the file extension intact but is the decrypted gmo file (look at it in a hex editor), just try to change the extension and load it with the dissidia tools.
## Post #6
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-04-04T14:47:58+00:00
- Post Title: PSP "edat" format

Awesome I should have examined it more closely. So how did you go about decrypting the edat so it wws a normal gmo model? In the first post on this thread he posted a mediafire link to Cloud's edat files if you want to take a look.
## Post #7
- Username: codestation
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jan 18, 2011 3:52 am
- Post datetime: 2011-04-04T16:19:24+00:00
- Post Title: PSP "edat" format

> Reply from Zerox
>
> Awesome I should have examined it more closely. So how did you go about decrypting the edat so it wws a normal gmo model? In the first post on this thread he posted a mediafire link to Cloud's edat files if you want to take a look.
I think that the decryption of edat files is a little offtopic because the ".edat" isn't a file format per se (just the edat header followed by the DLC id, something like a hash then the encrypted content). Anyway i can't use the DLC files that the OP posted because they are tied to the PSP that downloaded it so it wont decrypt on another one (and yes, they could be loaded on another psp once decrypted).

So the only way to get the KH-Cloud GMO files is that i would have a code to download the DLC (i dont have one) or somebody with the activated DLC and CFW wants to make a dump of it.
## Post #8
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-04-04T17:01:29+00:00
- Post Title: PSP "edat" format

Well could you explain how you decrypted the WoL DLC? It wasn't dnas decryptor was it?
## Post #9
- Username: codestation
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jan 18, 2011 3:52 am
- Post datetime: 2011-04-04T17:40:20+00:00
- Post Title: PSP "edat" format

> Reply from Zerox
>
> Well could you explain how you decrypted the WoL DLC? It wasn't dnas decryptor was it?
Not at all, in fact is very simple because the game reads the DLC like they were normal files, the only difference is that the game tells the psp that the file is encrypted so when the game reads the data it gets decrypted data (i don't know why anybody has published a DLC decrypter yet, i suppose that is because the devs that can do it don't use DLC or don't care).

The simplest decrypter can be a plugin that hooks the open and read functions of the game, identify the dlc via the filename when the game tries to open it, then dump the decrypted data when the game tries to read it.

The DLC that i am interested is the Tifa one but not for the content, i want to try to modify the GMO to make my own char so i can play that without modify the game itself. Sadly i dont have a preorder code so i 'll have to wait until SE post a new Tifa DLC on the PSN.
## Post #10
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-04-04T17:44:14+00:00
- Post Title: PSP "edat" format

> Reply from codestation
>
> The simplest decrypter can be a plugin that hooks the open and read functions of the game, identify the dlc via the filename when the game tries to open it, then dump the decrypted data when the game tries to read it.
So then is this how you did it?
## Post #11
- Username: codestation
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jan 18, 2011 3:52 am
- Post datetime: 2011-04-04T18:01:32+00:00
- Post Title: PSP "edat" format

> Reply from Zerox
>
> codestation wrote:The simplest decrypter can be a plugin that hooks the open and read functions of the game, identify the dlc via the filename when the game tries to open it, then dump the decrypted data when the game tries to read it.
So then is this how you did it?

Yes (well, mine is a little different as i force the dump of all the dlc files without waiting for the game to read it), that way you dont even need to know how the DLC is decrypted, what are the keys or things like that, just grab the read buffer and dump into a file (with the drawback that you must own the DLC to do it, but after the file is dumped that doesn't matter anymore). I have my doubts about releasing a PSN DLC decrypter but i also want to work with game models and textures (whats the point to have a decrypter to myself if i am a noob to edit game models and custom textures).
## Post #12
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-04-04T19:12:18+00:00
- Post Title: PSP "edat" format

Well the people at DissidiaForums.com are trying to mod the textures for the dlc models much like you are. They are against piracy but are open to the idea of texture modding an ISO for a game you dump an ISO from yourself. So I'm sure if you shared your tool there than they would only use it as something to mod content they already own. Who knows maybe they'll teach you about texturing more than you already know. 

Besides their modding section is members only so not everyone would find it via search engine and if you say its a tool for only Dissidia I'm sure they'll treat it that way even if it was secretly capable of other things.
## Post #13
- Username: codestation
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jan 18, 2011 3:52 am
- Post datetime: 2011-04-04T19:30:37+00:00
- Post Title: PSP "edat" format

Ok then, moving the DLC discussion to DissidiaForums
## Post #14
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-04-04T19:37:48+00:00
- Post Title: PSP "edat" format

Alrighty. I'll watch for your thread then as I love using custom skins in my game and wouldn't mind modding my own pre-ordered dlc Cloud.
## Post #15
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-04-04T20:18:42+00:00
- Post Title: PSP "edat" format

> Reply from codestation
>
> Zerox wrote:Well I thought I'd be clever and try GitMO on these to see if I could get anything out of them. And that doesn't work. Codestation you posted as if you were able to get the gmo out of them but the file you posted is still an Edat so it appears.
I just left the file extension intact but is the decrypted gmo file (look at it in a hex editor), just try to change the extension and load it with the dissidia tools.

That explains why people are still using mesh2rdm. Some tool took an ancient version of it, renamed it to "gmoprw.exe", and shoved it into a "Dissidia Modding Suite" package.
## Post #16
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-04-04T20:41:59+00:00
- Post Title: Re: PSP "edat" format

I don't believe they took credit for making the viewer portion. Though I don't recall if it was ever mentioned that it was your tool that did the viewing portion. Is it something your upset about or just a "oh so that's why" kinda moment?
## Post #17
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-04-04T22:27:58+00:00
- Post Title: Re: PSP "edat" format

I have people rebrand my shit (even some of my old Half-Life mods) under their own name all the time, so I'm used to crap like that. This instance is simply annoying because:

1) It's an old version, of a program which no one should be using these days anyway. The package does not even provide information on where to get newer versions.
2) The program's readme.txt is not distributed with the program.
3) The exe is pointlessly renamed.
4) People still e-mail me with bullshit about mesh2rdm (despite what it says about the program on my web site), and this seems to be one of the main reasons why.
5) Shitting together a bunch of tools written by multiple authors into a single scummy package with no proper documentation is generally bad practice, and I find it hard to believe anyone could be so naive of the common courtesies in free software distribution.
## Post #18
- Username: Cloud452
- Rank: veteran
- Number of posts: 91
- Joined date: Sat Oct 23, 2010 9:50 pm
- Post datetime: 2011-04-08T05:03:37+00:00
- Post Title: Re: PSP "edat" format

I think the success with WOL's DLC is due to the model being in the game data, unlike KH Cloud or others they've released so far (4th Alt Zidane or Kuja). But still, hope progress can be made!
## Post #19
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-04-09T18:36:42+00:00
- Post Title: Re: PSP "edat" format

WOL isn't already in the game data...there is one for the reports cutscenes. but not playable.

The plugin has been posted on another site, but the people can't get it to work, therefore they assume it's "A bluff".
## Post #20
- Username: Cloud452
- Rank: veteran
- Number of posts: 91
- Joined date: Sat Oct 23, 2010 9:50 pm
- Post datetime: 2011-04-10T01:12:25+00:00
- Post Title: Re: PSP "edat" format

My mistake then, I should have checked what that WOL model was for then before posting. ^^;
