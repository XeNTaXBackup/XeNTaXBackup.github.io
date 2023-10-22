## Post #1
- Username: noik
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Apr 08, 2008 5:05 am
- Post datetime: 2008-04-09T17:36:06+00:00
- Post Title: Granado Espada .IPF format

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2008-04-09T18:18:56+00:00
- Post Title: Granado Espada .IPF format

the IPF file is a simple Zip file (rename it to .zip and open it), so repacking the files should be easy.

HOWEVER..... the Zip file is password encrypted. so you cant really exctract any files by hand and repack them without
knowing the password. so the the creator of the IPF unpacker knows the password. i can figure it out soon enough.
*brb*
## Post #3
- Username: noik
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Apr 08, 2008 5:05 am
- Post datetime: 2008-04-10T11:22:34+00:00
- Post Title: Granado Espada .IPF format

yo thx for the help^^

now im trying to brute-force these zip/ipf files lol lets see if i can find out the password o.o
well i will keep looking here if you figure out the password before me^^ (and i think you will lol)
thx a lot for the help \o/
## Post #4
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2008-04-10T12:55:20+00:00
- Post Title: Granado Espada .IPF format

Im downloading the Client now too see if i can get a clue of the Zip password.

an approach i use when finding out passwords for encrypted archives used in games or demos is by simply
looking in the Exe files or DLL files of the game, the password will almost 95% of the times be found unencrypted here.

Takes much less time than bruteforcing  , but if they have hidden the password too well then bruteforcing
is more convinient.

ill let you know if i find it!

Edit:
One of their mirrors have a faulty install file :X , i went with curse.com first, the file downloaded was only 1.2gb
in size (compared to the others at 3.6gb) , so i had an Unexpected End of Archive!

well well, redownloading!!!
## Post #5
- Username: noik
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Apr 08, 2008 5:05 am
- Post datetime: 2008-04-10T14:49:16+00:00
- Post Title: Granado Espada .IPF format

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: noik
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Apr 08, 2008 5:05 am
- Post datetime: 2008-04-13T16:16:57+00:00
- Post Title: Granado Espada .IPF format

well i found the password
but there still a problem, with that ipf extractor we can see the real names of files and folders, but when you open then with winrar/winzip, all the files is with strange letters, and when we get everything extracted, the files with strange letters lol

anyone can help??=D
any way to repack the files with the real names??
btw will try to repack using the password and the files extracted with the ipf-extractor and see if the game can regonize then

cya!! thx for the help^^

edit:
well you cant just repack all with winzip/winrar and put the password there, the game dont recognize the ipf file in this way
will see what i can do to repack the files right
cya all^^
## Post #7
- Username: noik
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Apr 08, 2008 5:05 am
- Post datetime: 2008-04-29T23:37:54+00:00
- Post Title: Granado Espada .IPF format

well since im a little busy, so i got no time to work in a extractor/repack tool, here is the password for the ipf files:

%f %f %s %s ÿÿÿÿ?[ ÿÿÿÿ?%f %f %s h %s .?.   Xÿ$$

yes this whole thing is the password lol
hope it can be usefull for anyone there
so maybe some mods for granado espada appear
when i have more time i will try to do something  
these ipf files are encrypted zip files
i think it isnt so hard to figure out how to extract/repack everything
cya
## Post #8
- Username: liyafenix
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 15, 2009 2:50 am
- Post datetime: 2009-08-14T19:56:45+00:00
- Post Title: Granado Espada .IPF format

this password does not working   
how you found this password?
## Post #9
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-08-30T08:57:12+00:00
- Post Title: Granado Espada .IPF format

I would like to bump this thread and ask if someone knows about a model viewer or converter or anything
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-10-16T03:58:17+00:00
- Post Title: Granado Espada .IPF format

I might know something
## Post #11
- Username: MrMoonKr
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Oct 16, 2009 2:18 pm
- Post datetime: 2009-10-17T05:52:15+00:00
- Post Title: Granado Espada .IPF format

Help me
I want to know how to recover the real names fo files and folders in a ipf archive.

(PS)
Sorry for my bad English ^^;;
I can do c++ programming.
## Post #12
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2009-12-11T19:47:25+00:00
- Post Title: Granado Espada .IPF format

I can easily make a packer for this.

Only need to get an algorithm for encrypting the filenames.

Atm I have to manually rip them from the files to get them but heres some data on it


datatable_force.xml
Hex: 64 61 74 61 74 61 62 6c 65 5f 66 6f 72 63 65 2e 78 6d 6c
Encrypted Hex: 90 61 6b 96 b7 c2 19 43 27 4a e8 2a a0 c4 0f 26 19 26 52

datatable_force_kk.xml
Hex: 64 61 74 61 74 61 62 6c 65 5f 66 6f 72 63 65 5f 6b 6b 2e 78 6c
Encrypted Hex: 90 61 6b 96 b7 c2 19 43 27 4a e8 2a a0 c4 0f 57 ef 61 d3 3f 63 8d

As you can see the hex is the same until the characters go different and then they are completely different.
I'm not too great on encryptions like this (I'm only good at more basic stuff when it comes to encryption).
I tried all Encryption types I could get my hands on (RC2, RC4, IDEA etc) tried using the IPF password as a key and couldn't find one which would "match".

I can make IPF's if I know how it encrypts the current files which I know the encrypted names for are 

2002.tff
attacker.scp
healer.scp
lib.scp
puppet.scp

script/
script/localize.scp

uiscp/
uiscp/game.scp

uixml/
uixml/autoinspect.xml


hotkey.xml
datatable_force_kk.xml
datatable_force.xml
tooltext.xml
datatable_watch.xml

usa/
usa/datatable_itemcharge.ies

Interesting ones are the folders which Encrypted Hex is:

usa/    =    a1 89 66 b3

Now it begins with u and is hex encrypted is a1 where as

uiscp/   =  81 58 06 39 4e 16

and

uixml/  = 81 58 0d 6a 6c 81

So the second character obviously affects what the first character will be.

Any help on how it encrypts the filename will be appreciated, once its worked out I will gladly make a tool for it.
## Post #13
- Username: piratesephiroth
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Nov 08, 2009 6:05 pm
- Post datetime: 2009-12-14T18:58:08+00:00
- Post Title: Granado Espada .IPF format

I thought of another approach... maybe someone could rip the decryption routine from the extractor and then encrypt the filenames via brute force.
## Post #14
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2009-12-14T21:59:39+00:00
- Post Title: Granado Espada .IPF format

> Reply from piratesephiroth
>
> I thought of another approach... maybe someone could rip the decryption routine from the extractor and then encrypt the filenames via brute force.

Ripping the decryption routine aint that easy need someone who can reverse programs pretty well.

As for encrypting filenames via brute force I got no idea why you would do that, decrypting is harder then encrypting normally.

I'm guessing there encryption algorithm for the filenames will be something like:

Letter XOR b

and every time a letter gets Xor'd it does
b = (b + x)

It will be something simple like that most likely.
So it changes with every byte encrypted.
## Post #15
- Username: piratesephiroth
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Nov 08, 2009 6:05 pm
- Post datetime: 2009-12-15T05:57:25+00:00
- Post Title: Granado Espada .IPF format

Yeah I agree that the encryption is something simple like that. Looking at the first bytes of the unencrypted/encryped files in ai.ipf, it seems that they all start with XOR F4... but this is not true for font.ttf, inside font.ipf.

hmm maybe I'm starting to understand something now... it seems that for the next letters it does some other operation. the characters no longer follow their original order... it's like they're split into groups of 8 and then the groups are scrambled. Plus, sometimes they come in order and other times they come in reverse order... I wonder if it's some bit shifting...
## Post #16
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2009-12-15T21:47:28+00:00
- Post Title: Re: Granado Espada .IPF format

> Reply from piratesephiroth
>
> Yeah I agree that the encryption is something simple like that. Looking at the first bytes of the unencrypted/encryped files in ai.ipf, it seems that they all start with XOR F4... but this is not true for font.ttf, inside font.ipf.

hmm maybe I'm starting to understand something now... it seems that for the next letters it does some other operation. the characters no longer follow their original order... it's like they're split into groups of 8 and then the groups are scrambled. Plus, sometimes they come in order and other times they come in reverse order... I wonder if it's some bit shifting...

Another possibly is they are using an encryption like blowfish or DES with a different "key" to what they use to password there files.

Edit:

Microsoft Enhanced Cryptographic Provider v1.0:
Encrypt(const unsigned char * pDataIn, int dataInSize, unsigned char* pDataOut)
## Post #17
- Username: piratesephiroth
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Nov 08, 2009 6:05 pm
- Post datetime: 2009-12-17T10:50:27+00:00
- Post Title: Re: Granado Espada .IPF format

Well... look at [this](http://0x33.org/forum/showthread.php?p=204326#post204326), Uli.

Anyway I can find the find any file (it seems) using that extractor plus a zip viewer that allows me to view/insert any character in the file names (actually a friend of mine modified it and added the rename function)...

offtopic: I remember you saying something about the ies files on that ai forum... do you actually understand them? it seems that the characters are swapped...
## Post #18
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2009-12-17T14:00:46+00:00
- Post Title: Re: Granado Espada .IPF format

> Reply from piratesephiroth
>
> Well... look at this, Uli.

Anyway I can find the find any file (it seems) using that extractor plus a zip viewer that allows me to view/insert any character in the file names (actually a friend of mine modified it and added the rename function)...

offtopic: I remember you saying something about the ies files on that ai forum... do you actually understand them? it seems that the characters are swapped...

Thanks for the link!
Will look through it now and find what I need.

Edit: Yeah I did the IES files a little while ago when I said what I said over there I mean its one of those so obvious ones you hit  yourself when you notice.

IES Data, numbers are stored as float and strings have the swap characters

a = '
A = @

the rest were just swapped normally (B with C etc) Z was swapped with something else which I cant remember off the top of my head
(Basicly Ascii Number +- 1)
## Post #19
- Username: piratesephiroth
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Nov 08, 2009 6:05 pm
- Post datetime: 2009-12-17T21:05:00+00:00
- Post Title: Re: Granado Espada .IPF format

But if if you still can't find the encryption method, you can use brute force, as I stated before...

We'd just try the decryption function in every possible value until we found the proper decrypted character... then we have our first encrypted value. Then we continue the process now keeping the first encrypted char there and bruteforcing the second one (repeating the same decrypting step) until we find our desired second char... and so on.

I don't know... it works in my silly mind.  (and using the extractor + hex editor as well)
## Post #20
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2009-12-17T22:43:56+00:00
- Post Title: Re: Granado Espada .IPF format

> Reply from piratesephiroth
>
> But if if you still can't find the encryption method, you can use brute force, as I stated before...

We'd just try the decryption function in every possible value until we found the proper decrypted character... then we have our first encrypted value. Then we continue the process now keeping the first encrypted char there and bruteforcing the second one (repeating the same decrypting step) until we find our desired second char... and so on.

I don't know... it works in my silly mind.  (and using the extractor + hex editor as well)

no brute forcing is just not practical at all, you can try it and get back to me when you get why it wouldn't work.

(Look up how big a 8 byte Hex Key is in Decimal and work out how many times it would have to loop)

Edit: (Ended up making the adjustments myself, god how I hate C++)

Edit2:
Screenshot of Skeleton program
[http://i64.photobucket.com/albums/h193/ ... nshot1.jpg](http://i64.photobucket.com/albums/h193/SWG-Uli/IPFPackerscreenshot1.jpg)
## Post #21
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2009-12-23T16:47:50+00:00
- Post Title: Re: Granado Espada .IPF format

The contents of this post was deleted because of possible forum rules violation.
## Post #22
- Username: piratesephiroth
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Nov 08, 2009 6:05 pm
- Post datetime: 2009-12-24T09:26:56+00:00
- Post Title: Re: Granado Espada .IPF format

Wow so you got the filename encryption hahah nice. (EDIT: ah databanks I see)

But what's the issue with the directories? Is that because of the encryption? The files are all in the root folder but the complete path is read from the filename inside the Central Directory Record... but well if we're replacing files we need them to be in the correct folders anyway.

Also something might be going a little weird, since the Extractor reads even WinRAR-packed IPFs...
## Post #23
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2009-12-24T12:17:29+00:00
- Post Title: Re: Granado Espada .IPF format

The contents of this post was deleted because of possible forum rules violation.
## Post #24
- Username: piratesephiroth
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Nov 08, 2009 6:05 pm
- Post datetime: 2009-12-24T21:21:56+00:00
- Post Title: Re: Granado Espada .IPF format

> Reply from Uli
>
> If the ZLib i got would add the password and merge the ipfs then i would use that but it wont, its the easiest to apply the encrypted name to tho
"Merge" the ipfs?

And about the zipping dll... couldn't you use the ones AI Builder uses? After all, all you need is to make a normal zip file without directories and then replace the original entriesin the CDR by the encrypted filenames (including paths, if that's the case) . Simple byte replacement won't work for those situations, since you have to add a longer string.

EDIT: Yeah I don't really understand why it can't create those files within subfolders. You must be doing more than it's needed.
## Post #25
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2009-12-25T19:09:48+00:00
- Post Title: Re: Granado Espada .IPF format

> Reply from piratesephiroth
>
> Uli wrote:If the ZLib i got would add the password and merge the ipfs then i would use that but it wont, its the easiest to apply the encrypted name to tho
"Merge" the ipfs?

And about the zipping dll... couldn't you use the ones AI Builder uses? After all, all you need is to make a normal zip file without directories and then replace the original entriesin the CDR by the encrypted filenames (including paths, if that's the case) . Simple byte replacement won't work for those situations, since you have to add a longer string.

EDIT: Yeah I don't really understand why it can't create those files within subfolders. You must be doing more than it's needed.

My current Packer can pack new files into an existing IPF.
Packing files with Subfolders is simple stuff, there are issues such as packing folders you do not want, however there is a good ZIP DLL I want to get my hands on but I'm worried incase it has a 30 day trial limit (At least what I seen it does have it) but it would make things within folders easier to pack however I'm not sure how merging new files into a current IPF would go.

ZLib is a good Zipping DLL to use and everything, its easier because you can encrypt the filename before it actually gets packed so you can make it any length you want, problem with it is you can not add the password (That does not matter) but you can not "merge" the new files into a current IPF it would overwrite the entire ipf.
## Post #26
- Username: piratesephiroth
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Nov 08, 2009 6:05 pm
- Post datetime: 2009-12-25T22:10:29+00:00
- Post Title: Re: Granado Espada .IPF format

Ah, it can insert files into IPF's... nice. It would be cool if it could modify the contents of those bloated game archives and remove all the old useless outdated files and also our own injected files.

Ah yeah, and looking at your ui.db file I saw this:

```
EncryptedString=97AB385C
```


while the correct is

```
EncryptedString=97AB385C001B3D6280BF25749CAB4AA4CEF6FA
```


the encryption can generate nulls... that might have confused your dumping tool.

EDIT: Also

```
EncryptedString=99163C72731DC6FADE2C4735FA1DF5F5E486C632C740472D1B540D763F777226D8A8
```


```
EncryptedString=99163C72731DC6FADE2C4735FA1DF5F5E486C632C740472D1B540D763F777226D8A8000D2B32A824214256034F
```


there might be others.. I just picked these at random.

EDIT2: You guys say it's not necessary to set a password, but with me both the launcher and the extractor fail if I try to do it like that...
## Post #27
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2009-12-26T15:47:05+00:00
- Post Title: Re: Granado Espada .IPF format

yeah, when i generated the hex i did not bother making it loop on the size of the name, it loops until null so there might be a few like that >.>


Edit:

Will edit the code and fix it soon

Edit2:

Ok I have editted it and just testing it now

Edit3:

Meh with loop fix its still doing it >.>

Edit4:

Got it using memcpy() so i can get the full string with the null in, got it doing while(counter < length)  but it still is occuring

Edit5:

Wait for Edit6, still got the problem >.>
## Post #28
- Username: piratesephiroth
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Nov 08, 2009 6:05 pm
- Post datetime: 2009-12-27T22:44:29+00:00
- Post Title: Re: Granado Espada .IPF format

waiting for edit5
 
ok then are those encrypted names being read as strings or what? I guess you're using someone else's funtion for that step.


but I still believe it's possible to bruteforce them...


this is the decryption, more or less, as seen from a stupid guy's point of view:
1 build decryption keys
2 read encrypted character
3 decrypt it
4 save registers
5 replaces the encrypted value in buffer by the decrypted one
6 restore registers
repeat process with the next character and so on until the last one


so what if you did it like this:
1 build decryption keys
2 read encrypted character
3 decrypt it
4 save registers

here comes the choice:

-it's not the desired character
 add 1 to the value of the encrypted charater
 decrypts it again (with the same keys)
 repeat until you get it right
-it is the desired character
 replaces the encrypted value in buffer by the decrypted one
 restore registers
 move on

as far as I can see, you'd have to bruteforce 256 values for each character at a maximum, what is not really that much and wouldn't take that long... if we work with one filename at once

please don't call me a moron if all this bullshit is really just bullshit hahahah
## Post #29
- Username: juggernault
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 28, 2009 1:14 pm
- Post datetime: 2009-12-28T08:46:30+00:00
- Post Title: Re: Granado Espada .IPF format

hi guys, i am new here.. i tried to run the IPF packer in windows 7, it seems like it is not working. When i try to click pack to ipf file , it crashes. Any idea what should i do?

Thank you.
## Post #30
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2009-12-28T17:20:24+00:00
- Post Title: Re: Granado Espada .IPF format

With the crashing try running it in XP Compatibility mode if that does not work then I will get the link to another packer i made which is only built for the AI.ipf for GE which should have all the DLLs etc which is needed.


> Reply from piratesephiroth
>
> waiting for edit5
but I still believe it's possible to bruteforce them...


this is the decryption, more or less, as seen from a stupid guy's point of view:
1 build decryption keys
2 read encrypted character
3 decrypt it
4 save registers
5 replaces the encrypted value in buffer by the decrypted one
6 restore registers
repeat process with the next character and so on until the last one


so what if you did it like this:
1 build decryption keys
2 read encrypted character
3 decrypt it
4 save registers

here comes the choice:

-it's not the desired character
 add 1 to the value of the encrypted charater
 decrypts it again (with the same keys)
 repeat until you get it right
-it is the desired character
 replaces the encrypted value in buffer by the decrypted one
 restore registers
 move on

as far as I can see, you'd have to bruteforce 256 values for each character at a maximum, what is not really that much and wouldn't take that long... if we work with one filename at once

I kinda fail to see the reason to use bruteforce, if you could explain why it is needed then I might listen a bit better.
Using databanks is a lot more efficient and quicker (My program can go through a databank in less then 1 second and some databanks are 1mb+)

I do not see what bruteforcing achieves at all.
## Post #31
- Username: piratesephiroth
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Nov 08, 2009 6:05 pm
- Post datetime: 2009-12-28T23:23:48+00:00
- Post Title: Re: Granado Espada .IPF format

Well brute forcing is an alternative to encryption...
I don't really think of it as an essential part of the program, but I believe it could be a neat extra tool.
## Post #32
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2009-12-29T00:16:05+00:00
- Post Title: Re: Granado Espada .IPF format

> Reply from piratesephiroth
>
> Well brute forcing is an alternative to encryption...
I don't really think of it as an essential part of the program, but I believe it could be a neat extra tool.

Again, I fail to see how brute forcing is an alternative to encryption 

I really dislike saying things like this but: Research things before mentioning it.  From the looks you got no idea how brute forcing works other than its a way of "cracking" its just not as simple as that and there is a lot to it.

255 * Length Of String * Possible Combinations = one heck of a big number which means a lot of loops.

Example:
Something of three letters
255 * 3 * 16777215 = 12834569475
(16777215 = FFFFFF)


From the outlooks the name encryption probably uses Windows encrypting due to things mentioned in the client however its got lookup tables and everything instead of getting the encryption its just easier to compile all the current filenames from existing IPFs into a databank.  You will not need to add any files that do not exist in the IPF files.

If you want to use bruteforce something look on the internet there are plenty of tools.
## Post #33
- Username: emriv
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 20, 2010 7:37 pm
- Post datetime: 2010-05-23T13:18:46+00:00
- Post Title: Re: Granado Espada .IPF format

hey, is there anyone who cracked password to ies.ipf?

if not so I got a question.

Password to ai.ipf  has got 38 letters, it contains everything, normal letters, special letters
So Im wondering what is the best way to crack password like that, 
Rainbow tables? brute force?  any other way?
or someone who cracked it could share it 

also im interested how to write X-trap bypass, it doesnt let me read the packets with WPE Pro. Anyone got any clues how to do that? I appreciate everything.
## Post #34
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2010-05-31T14:55:06+00:00
- Post Title: Re: Granado Espada .IPF format

> Reply from emriv
>
> hey, is there anyone who cracked password to ies.ipf?

if not so I got a question.

Password to ai.ipf  has got 38 letters, it contains everything, normal letters, special letters
So Im wondering what is the best way to crack password like that, 
Rainbow tables? brute force?  any other way?
or someone who cracked it could share it 

also im interested how to write X-trap bypass, it doesnt let me read the packets with WPE Pro. Anyone got any clues how to do that? I appreciate everything.

```
%f %f %s %s ÿÿÿÿ?[ ÿÿÿÿ?%f %f %s h %s .?.   Xÿ$$
```


Thats the password, you get it from either the Launcher EXE or the Game EXE.

The Encryption on the names of the files inside the IPF uses some byte tables to do it which may be connected to ZIP2 Encryption.


Anyway, on X-Trap bypass I refuse to tell you or even help you to do that since you said "WPE Pro" also the Packets are encrypted with Blowfish, I don't think that it uses the same password as the IPF either.

This site is about reversing file formats and that not about "hacking" so if you might want to start looking else where for your stuff or work out how to do it people will only spoon feed some stuff.
## Post #35
- Username: Slozhny
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Aug 31, 2009 6:03 am
- Post datetime: 2011-04-26T09:31:48+00:00
- Post Title: Re: Granado Espada .IPF format

Here is IPF_extractor
[http://kainits.clan.su/load/1-1-0-1](http://kainits.clan.su/load/1-1-0-1)
Just pick on the label " Скачать с сервера (123.5Kb) "
## Post #36
- Username: IHX001
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 11, 2011 5:10 am
- Post datetime: 2011-05-10T21:58:04+00:00
- Post Title: Re: Granado Espada .IPF format

Hey,

Does anyone know how to use the currently released IPF Packer? I'm trying to make my own custom se.ipf sound effects but the onscreen instructions isn't very clear to me. Can someone explain it please? Thanks!
## Post #37
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2011-08-11T17:30:54+00:00
- Post Title: Re: Granado Espada .IPF format

> Reply from IHX001
>
> Hey,

Does anyone know how to use the currently released IPF Packer? I'm trying to make my own custom se.ipf sound effects but the onscreen instructions isn't very clear to me. Can someone explain it please? Thanks!

No, IPF Packer is basicly broken.

Anyway I lost interest this quite a while back, here is how the IPF File Encryption works.

IPF Files are just a zip archive the names encrypted with Zip 2.0 algo.

Unorganized code - Note removed some things from it since it was a test program:
You will have to rebuild the function around the Encrypt and Decrypt functions for this to work.

```
#include <windows.h>


const int keyLen = 48;

unsigned char key[keyLen] = {		
0x25, 0x66, 0x20, 0x25, 0x66, 0x20, 0x25, 0x73, 
0x20, 0x25, 0x73, 0x20, 0xFF, 0xFF, 0xFF, 0xFF, 
0x3F, 0x5B, 0x20, 0xFF, 0xFF, 0xFF, 0xFF, 0x3F, 
0x25, 0x66, 0x20, 0x25, 0x66, 0x20, 0x25, 0x73,
0x20, 0x68, 0x20, 0x25, 0x73, 0x20, 0x2E, 0x3F, 
0x2E, 0x20, 0x20, 0x20, 0x58, 0xFF, 0x24, 0x24 };

//CRC Table from Zlib
const long crc_table[256] = {
  0x00000000L, 0x77073096L, 0xee0e612cL, 0x990951baL, 0x076dc419L,
  0x706af48fL, 0xe963a535L, 0x9e6495a3L, 0x0edb8832L, 0x79dcb8a4L,
  0xe0d5e91eL, 0x97d2d988L, 0x09b64c2bL, 0x7eb17cbdL, 0xe7b82d07L,
  0x90bf1d91L, 0x1db71064L, 0x6ab020f2L, 0xf3b97148L, 0x84be41deL,
  0x1adad47dL, 0x6ddde4ebL, 0xf4d4b551L, 0x83d385c7L, 0x136c9856L,
  0x646ba8c0L, 0xfd62f97aL, 0x8a65c9ecL, 0x14015c4fL, 0x63066cd9L,
  0xfa0f3d63L, 0x8d080df5L, 0x3b6e20c8L, 0x4c69105eL, 0xd56041e4L,
  0xa2677172L, 0x3c03e4d1L, 0x4b04d447L, 0xd20d85fdL, 0xa50ab56bL,
  0x35b5a8faL, 0x42b2986cL, 0xdbbbc9d6L, 0xacbcf940L, 0x32d86ce3L,
  0x45df5c75L, 0xdcd60dcfL, 0xabd13d59L, 0x26d930acL, 0x51de003aL,
  0xc8d75180L, 0xbfd06116L, 0x21b4f4b5L, 0x56b3c423L, 0xcfba9599L,
  0xb8bda50fL, 0x2802b89eL, 0x5f058808L, 0xc60cd9b2L, 0xb10be924L,
  0x2f6f7c87L, 0x58684c11L, 0xc1611dabL, 0xb6662d3dL, 0x76dc4190L,
  0x01db7106L, 0x98d220bcL, 0xefd5102aL, 0x71b18589L, 0x06b6b51fL,
  0x9fbfe4a5L, 0xe8b8d433L, 0x7807c9a2L, 0x0f00f934L, 0x9609a88eL,
  0xe10e9818L, 0x7f6a0dbbL, 0x086d3d2dL, 0x91646c97L, 0xe6635c01L,
  0x6b6b51f4L, 0x1c6c6162L, 0x856530d8L, 0xf262004eL, 0x6c0695edL,
  0x1b01a57bL, 0x8208f4c1L, 0xf50fc457L, 0x65b0d9c6L, 0x12b7e950L,
  0x8bbeb8eaL, 0xfcb9887cL, 0x62dd1ddfL, 0x15da2d49L, 0x8cd37cf3L,
  0xfbd44c65L, 0x4db26158L, 0x3ab551ceL, 0xa3bc0074L, 0xd4bb30e2L,
  0x4adfa541L, 0x3dd895d7L, 0xa4d1c46dL, 0xd3d6f4fbL, 0x4369e96aL,
  0x346ed9fcL, 0xad678846L, 0xda60b8d0L, 0x44042d73L, 0x33031de5L,
  0xaa0a4c5fL, 0xdd0d7cc9L, 0x5005713cL, 0x270241aaL, 0xbe0b1010L,
  0xc90c2086L, 0x5768b525L, 0x206f85b3L, 0xb966d409L, 0xce61e49fL,
  0x5edef90eL, 0x29d9c998L, 0xb0d09822L, 0xc7d7a8b4L, 0x59b33d17L,
  0x2eb40d81L, 0xb7bd5c3bL, 0xc0ba6cadL, 0xedb88320L, 0x9abfb3b6L,
  0x03b6e20cL, 0x74b1d29aL, 0xead54739L, 0x9dd277afL, 0x04db2615L,
  0x73dc1683L, 0xe3630b12L, 0x94643b84L, 0x0d6d6a3eL, 0x7a6a5aa8L,
  0xe40ecf0bL, 0x9309ff9dL, 0x0a00ae27L, 0x7d079eb1L, 0xf00f9344L,
  0x8708a3d2L, 0x1e01f268L, 0x6906c2feL, 0xf762575dL, 0x806567cbL,
  0x196c3671L, 0x6e6b06e7L, 0xfed41b76L, 0x89d32be0L, 0x10da7a5aL,
  0x67dd4accL, 0xf9b9df6fL, 0x8ebeeff9L, 0x17b7be43L, 0x60b08ed5L,
  0xd6d6a3e8L, 0xa1d1937eL, 0x38d8c2c4L, 0x4fdff252L, 0xd1bb67f1L,
  0xa6bc5767L, 0x3fb506ddL, 0x48b2364bL, 0xd80d2bdaL, 0xaf0a1b4cL,
  0x36034af6L, 0x41047a60L, 0xdf60efc3L, 0xa867df55L, 0x316e8eefL,
  0x4669be79L, 0xcb61b38cL, 0xbc66831aL, 0x256fd2a0L, 0x5268e236L,
  0xcc0c7795L, 0xbb0b4703L, 0x220216b9L, 0x5505262fL, 0xc5ba3bbeL,
  0xb2bd0b28L, 0x2bb45a92L, 0x5cb36a04L, 0xc2d7ffa7L, 0xb5d0cf31L,
  0x2cd99e8bL, 0x5bdeae1dL, 0x9b64c2b0L, 0xec63f226L, 0x756aa39cL,
  0x026d930aL, 0x9c0906a9L, 0xeb0e363fL, 0x72076785L, 0x05005713L,
  0x95bf4a82L, 0xe2b87a14L, 0x7bb12baeL, 0x0cb61b38L, 0x92d28e9bL,
  0xe5d5be0dL, 0x7cdcefb7L, 0x0bdbdf21L, 0x86d3d2d4L, 0xf1d4e242L,
  0x68ddb3f8L, 0x1fda836eL, 0x81be16cdL, 0xf6b9265bL, 0x6fb077e1L,
  0x18b74777L, 0x88085ae6L, 0xff0f6a70L, 0x66063bcaL, 0x11010b5cL,
  0x8f659effL, 0xf862ae69L, 0x616bffd3L, 0x166ccf45L, 0xa00ae278L,
  0xd70dd2eeL, 0x4e048354L, 0x3903b3c2L, 0xa7672661L, 0xd06016f7L,
  0x4969474dL, 0x3e6e77dbL, 0xaed16a4aL, 0xd9d65adcL, 0x40df0b66L,
  0x37d83bf0L, 0xa9bcae53L, 0xdebb9ec5L, 0x47b2cf7fL, 0x30b5ffe9L,
  0xbdbdf21cL, 0xcabac28aL, 0x53b39330L, 0x24b4a3a6L, 0xbad03605L,
  0xcdd70693L, 0x54de5729L, 0x23d967bfL, 0xb3667a2eL, 0xc4614ab8L,
  0x5d681b02L, 0x2a6f2b94L, 0xb40bbe37L, 0xc30c8ea1L, 0x5a05df1bL,
  0x2d02ef8dL
};


unsigned long seed[3];

void BuildDecryptKeys(LPBYTE key, int keyLen);
int XORKey();



Encrypt  (lElements = Length of the Char Array):	
long i;
BYTE FileName[32767] = {0};
	 seed[1] = 0x12345678;
	 seed[2] = 0x23456789;
	 seed[3] = 0x34567890;
	  BuildDecryptKeys((LPBYTE)key, keyLen);

	 memset(FileName, 0, lElements + 1);
      if(lElements > 0)
      {
         for (i=0; i < lElements; i++)
		 {
			BYTE decrypt = 0;
			BYTE curChar = plArrayOfLongs[i]; //plArrayOfLongs = Character Array
			int XKey = 0; 
			XKey = XORKey();
			decrypt = XKey ^ curChar;
			BuildDecryptKeys(&curChar, 1);
			FileName[i] = decrypt;
		 }
      }



Decrypt (lElements = Length of the Char Array):
          long i;
	  BYTE FileName[32767] = {0};
	  seed[1] = 0x12345678;
	  seed[2] = 0x23456789;
	  seed[3] = 0x34567890;
	  BuildDecryptKeys((LPBYTE)key, keyLen);

	  memset(FileName, 0, lElements + 1);
      if(lElements > 0)
      {
         for (i=0; i < lElements; i++)
		 {
			BYTE decrypt = 0;
			BYTE curChar = plArrayOfLongs[i];
			int XKey = 0; 
			XKey = XORKey();
			decrypt = XKey ^ curChar;
			BuildDecryptKeys(&decrypt, 1);
			FileName[i] = decrypt;
		 }
      }




   int XORKey()
{
	int tmp;
	tmp = (seed[3] & 0x0fffd) | 2;
	tmp = ((tmp * (tmp ^ 1)) >> 8);
	return tmp;
}


void BuildDecryptKeys(LPBYTE key, int keyLen)
{
	for(int x = 0; x < keyLen; ++x)
	{
		BYTE curChar1 = key[x];

		seed[1] = crc_table[(seed[1] & 0xff) ^ curChar1] ^ (seed[1] >> 8);
		seed[2] += seed[1] & 0xff;
		seed[2] = (seed[2] * 0x8088405L) + 1;
		seed[3] = crc_table[((seed[2] >> 24) & 0xFF) ^ (seed[3] & 0xFF)] ^ (seed[3] >> 8);
	}
}

```
