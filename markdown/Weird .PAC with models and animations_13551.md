## Post #1
- Username: asdasd123
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Jun 14, 2015 11:07 pm
- Post datetime: 2015-11-20T13:57:54+00:00
- Post Title: Weird .PAC with models and animations

Hi,

I've been trying to extract models from a game:

- Inside the .CPK i've found these weird .PAC. 
- No program was able to open/extract the .PAC (Noesis, PACExtracter, xbcompression...)
- Opening the .PAC files with HxD I can see that they have Meshes

I know you guys are amazing when facing a new challenge, so can anyone help me extract the models from the files?

Sample:
[http://www.mediafire.com/download/t0duw ... d5/pok.pac](http://www.mediafire.com/download/t0duw8tyti52d5/pok.pac)
[http://www.mediafire.com/download/6ein1 ... 8w/pik.pac](http://www.mediafire.com/download/6ein1z8od8ol8w/pik.pac)
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-11-20T16:52:23+00:00
- Post Title: Weird .PAC with models and animations

Fortunately it's just a very basic container format.

QuickBMS script:

```
get DUMMY short
get PACSZ long

for i = 0 < FILES
	getdstring NAME 32
	get OFFSET long
	get SIZE long
	log NAME OFFSET SIZE
next i

```
## Post #3
- Username: asdasd123
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Jun 14, 2015 11:07 pm
- Post datetime: 2015-11-20T22:43:48+00:00
- Post Title: Weird .PAC with models and animations

You sir have my thanks!

And since I can't repay you, you have my word that I'll repay the kindness by donating to the poor or doing some charity.

Once again, thanks!
