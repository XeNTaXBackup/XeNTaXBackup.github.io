## Post #1
- Username: kamakazebob
- Rank: Banned
- Number of posts: 4
- Joined date: Sat Sep 27, 2008 5:49 am
- Post datetime: 2008-09-26T22:55:27+00:00
- Post Title: Web download error

Hello,  I have a problem loading Multiex Commander.

When I start Multiex it seems to be loading fine, untill the status bar says "Downloading WIKI file..."  Then a pop-up appears that says "WEB: Download error from WIKI! fce2"  Then when I click OK it comes up with another pop-up that says "Run-time error '9':  Subscript out of range", after that the program just closes itself.  I am assuming it is having problems getting the WIKI file it needs,  I just don't know why.  Help is much appreciated,  thank you.
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-09-27T08:17:32+00:00
- Post Title: Web download error

Can you attach the debug.log file after it closes? It should be in the 'data' folder.
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-09-27T15:39:16+00:00
- Post Title: Web download error

Also note that the WIKI update feature has been broken since we upgraded the WIKI software (this shouldn't cause MC to close, though...), and IIRC Mr.Mouse intends to remove the functionality with the next MexCom version.
## Post #4
- Username: kamakazebob
- Rank: Banned
- Number of posts: 4
- Joined date: Sat Sep 27, 2008 5:49 am
- Post datetime: 2008-09-27T15:57:57+00:00
- Post Title: Web download error

Here is the data log (it said the extension log is not allowed so I just copied it)

MultiEx Commander - Debug Mode - Log File
-----------------------------------------
mc32, K:\MultiEx Commander
4.3.0
-----------------------------------------
9/27/2008, 10:53:53 AM
10:53:53 AM- MEX Open MRF  10:53:53 AM
10:53:54 AM-  GetWebFile = 0
10:53:54 AM-  K:\MultiEx Commander\data\web.log
10:53:54 AM-  Error saving Weblog 
10:53:54 AM[!]- WEB: Download error from WIKI! fce2
10:53:54 AM[!]- WEB: Download error from WIKI! fce2
10:53:56 AM- Reinitializing MexCom  
10:53:58 AM- MEX Set language 
10:53:58 AM-  - Main : Setting Variables 
10:53:58 AM-  - Main : Preparing Datafile List Columns 
10:53:58 AM-  - Main : Setting Additional Variables
10:53:58 AM-  - Main : Loading SupportForm
10:53:58 AM[i]-  - Main : Setting FileFilter
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-09-27T21:52:47+00:00
- Post Title: Web download error

I think I've found the problem. I can email you a patch. Can I email it to the address you used to donate the $10 with?
## Post #6
- Username: kamakazebob
- Rank: Banned
- Number of posts: 4
- Joined date: Sat Sep 27, 2008 5:49 am
- Post datetime: 2008-09-28T04:27:15+00:00
- Post Title: Web download error

I don't remember what e-mail I used, I have switched between e-mails quite a few times lately.  You can send it to the one I registered with here, or upload it to a file hosting site, sorry.
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-09-28T09:57:42+00:00
- Post Title: Web download error

No problem. I've attached a smaller fix here. Put that in the main folder of MultiEx Commander (where you installed it in). 

Run it (please note down the text that appears) and hopefully a new file "fr.bin" will appear in the main folder. Please zip that and attach it here so I can check if it worked. Also let me know the text message. 

Then also try to run MultiEx Commander again. 

Thanks!
[fr.zip](https://xentaxbackup.github.io/file/1659_fr.zip)
## Post #8
- Username: kamakazebob
- Rank: Banned
- Number of posts: 4
- Joined date: Sat Sep 27, 2008 5:49 am
- Post datetime: 2008-09-29T00:37:21+00:00
- Post Title: Web download error

Ok, here is the text that the windows showed when I ran it:

FR Checking...
Check 1 complete
Check 2 Complete
Check file saved: K:\MultiEx Commander\fr.bin

And the fr.bin file it created is attatched.  I tried to run Multiex again but it still did the same thing.
## Post #9
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-09-30T08:10:06+00:00
- Post Title: Web download error

The fix obviously did not work. 

However, I have checked some other web-based logs, and have found that you use a blacklisted registration number.    Therefore, you lied when you suggested you donated $10 to the project. 

This is unacceptable. One of the reasons that the new update of MultiEx Commander is taking more time is because of the limited number of donations. People like you are an insult to people that do donate. You wish to have all the benefits, yet fail to acknowledge and respect the authors and legal users. 

You are banned.
## Post #10
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2008-09-30T18:29:01+00:00
- Post Title: Web download error

well he never actually SAID he donated...tho i am a nit picky bastard i still agree that he deserved the Ban...
I mean i didnt pay for Multi -Ex but as u know i did a huge ammount of advertising for it instead (tho atm i no longer have the email with the bloody serial u gave me inside it which is rather irritating since i decided to reinstall Multi-ex now im on a brand spanking new PC).
Tho eventhough i didnt pay...I still gave something in return to the community...if the guy had helped like some people here do often then i suppose itd count as him giving something to the community so then he would have been useful and would be entitled to a reward if we really gave them out like that...but when someone wants something for nothing...they need to die (well..Not die...well maybe sometimes...but something has to be done!).

YEAH ima  little bored but thats my 2 cents on it all.
## Post #11
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-09-30T18:43:27+00:00
- Post Title: Web download error

Heh, I still have the original registration number I got from you back in '05... To be honest, I have used it on more than one computer, but MexCom has been uninstalled from them all over time for various reasons, and now only one of the computers I originally installed it on still has it, though I'm not sure if I've unlocked the copy or not. In any case, I don't go brandishing my key about lightly, so hopefully you won't blacklist it because of this revelation...
## Post #12
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-09-30T18:55:27+00:00
- Post Title: Web download error

Indeed, lionheart, something had to be done. 
But I disagree with your statement that he did not say he donated. 

I asked him whether I could send something to the email he used to donate.
He then replied "I don't remember which email I used [to donate]" and then came with some lame excuse as changing email addresses of late. I mean, come ON, that was so transparent! 

And yes, anyone who helps out can get a code as a favour. That has not changed. 

Oh and Dinoguy, even if you wanted to install on 1000 computers, that would be fine with me, as long as I don't find the code on some warez site after you do hehe.  Cool that you still have the three year old code
## Post #13
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-09-30T19:08:10+00:00
- Post Title: Web download error

Ah, good then. Of course, I never actually give the code to anyone else - when I'm unlocking a copy, I copy the code directly from your PM (which I also still have from 3 years ago) to MexCom, then proceed to close the browser or navigate away from the page. Now that I think on it, I should start clearing the cache as well when I do that, and copy-pasting something else afterwards to prevent someone seeing what I'm doing and pasting the code after I get up from the computer. Regardless, though, I've never done it on a public computer, and I usually stay on the comp for some time after doing that, so no worries there.

Out of curiosity, do you manually list blacklisted codes, and do you have a similar list of whitelisted codes or something? (of course, as with all such queries of mine, you can refuse to answer if you want  )
