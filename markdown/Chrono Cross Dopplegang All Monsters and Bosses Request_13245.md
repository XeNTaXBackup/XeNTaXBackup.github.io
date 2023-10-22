## Post #1
- Username: dragicorn
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Sep 18, 2011 3:21 am
- Post datetime: 2015-08-26T15:28:26+00:00
- Post Title: Chrono Cross: Dopplegang All Monsters and Bosses Request

So, I came across Chrono Cross a few days ago, and I am left wondering: How do I fix the code to play as boss monsters with the Dopplegang ability?!

Sure, the following code allows dopplegang to be used on all doppleganged monsters:

800712B8 FFDF
800712BA FFFF
800712BC BFFF
800712BE FBFB
800712C0 FFFF
800712C2 F4E7
800712C4 FFBF
800712C6 77FF
800712C8 E73F
800712CA 537A
800712CC F0F0
800712CE 01F7
800712D0 BC4E
800712D2 07C0

The problem is when you try this code:

800712B8 0127
800712BA 0000
800712BC 0000
800712BE 0000
800712C0 0000
800712C2 0000
800712C4 0000
800712C6 0000
800712C8 0000
800712CA 0000
800712CC 0000
800712CE 0000
800712D0 0000
800712D2 0000

You'll get only the following doppleganged  monsters:

Radius
Beach Bum
Sandsquirt
Mamma Komodo
Peppor

All of the above work perfectly, with the exception of the Boss Monster, Mamma Komodo.

Try this on any other boss monsters, and you'll get the same error, as far as I heard.

After some deep research, I found that there were a few people on the EZboards Forums that used to be that knew the code... and possibly might still have the code. Unfortionately, EZboards has been discontinued, after several times being redirected to a different web hoster before shutting down.

Back on Gamehacking.com, there is a mention of that site having the code as well. One user, Amy, said something about CDX(?), perhaps that was the actual forums, because I can't find that forum. Anyway, TruWizdom(?) was the one who gave Amy the code, who then gave Mytru the code, and then Amy lost the code. The code was up for a while longer, then the site went through a change (some hacker deleted it, as far I read), and the code was lost.

If anyone knows exactly or can figure out for me the exact meathod to fix the Boss Monsters' doppleganger transformation, then that would be great.

What happens:

Install EPSXE 1.80+
Installing PEC into Epsxe (I'll provide it for you. It's a rare and hard to find file, so I saved you the trouble of searching)
1. Download Provided File
2. Extract
3. Run Exe
4. Put PEC into My Documents/PEC
5. Put PEC plugin into EPSXE plugins folder
6. Install PEC
7. Run EPSXE
8. Hardware Video Card: PEC Plugin
9. Hardware Video Card PEC Plugin: Configure for your computer's compatibility.
10. Configure the Controller to your liking. You can't do this while in-game!

Go to the PEC installation directory
Go to user.ini
Add in the code I provide below:
"Custom Doppleganger Monsters
800712B8 0127
800712BA 0000
800712BC 0000
800712BE 0000
800712C0 0000
800712C2 0000
800712C4 0000
800712C6 0000
800712C8 0000
800712CA 0000
800712CC 0000
800712CE 0000
800712D0 0000
800712D2 0000

Save as user.ini

Remember to select all files while saving!

Run EPSXE
Run PEC (found in program files/ search PEC in Window's 8 start screen)
In PEC, click file, then user database
Check the box that says "Custom Doppleganger Monsters", then hit OK at the bottom right. Then click yes.
Pop In CD
Load Memory Card (I'll provide it for you, it is a special memory card with all 6 of the dragons ready to be battled in 6 different slots, as well as the Tyranno, and the Fire Dragon somewhere at the beginning of the game. It also contains an extra save that I used to set up the Dragon Fights. The save that you want is the bottom right, which already has Sprigg ready for battle with the sky dragon {although Lynx, Draggy, and Poshul are the only ones you can see, Sprigg takes Lynx' place during battles})
Load one of the last 6 slots.
In PEC: Send Cheats to Plugin
Approach the Sky Dragon and press the x key button
In battle, use the left/right keys to select Sprigg.
Use the Up/Down and X button Keys to Select Elements
Choose Dopplegang.
Assuming the code was properly inserted, you should only have 5 monsters available to dopplegang.
Select Mama Komodo.
Watch as the game crashes.
...

Below is the PEC file I download from it's original site, Gamer's Lounge.
[http://www.mediafire.com/download/8ss9e ... +3.2.2.zip](http://www.mediafire.com/download/8ss9ebc2c2jonk0/PEC+3.2.2.zip)
[Chrono Cross 6 Dragons.zip](https://xentaxbackup.github.io/file/9630_Chrono Cross 6 Dragons.zip)
## Post #2
- Username: alvaro
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Oct 25, 2019 11:21 pm
- Post datetime: 2021-07-08T21:04:05+00:00
- Post Title: Chrono Cross: Dopplegang All Monsters and Bosses Request

hi, i'm a brazilian so don't be surprised about the errors, i'm using google translator, i don't know if you're still active in 2021 but to this day i have a doubt, is there no possibility for someone to adjust the bosses that crash the game to that are fully playable, plus add element grids for enemies that can't be used in dopellang, make like a ppf patch or matic
