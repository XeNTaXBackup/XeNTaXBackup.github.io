## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-24T07:38:12+00:00
- Post Title: Return Fire II (2) Text Encryption (PC/Windows9x-XP)

In looking through my games I noted that Return Fire 2 makes no effort to use datafles but instead encrypts the script files objfxscr.dat and RFIREII.dat

I know they are encrypted because... well... gee... it kinda says it in the header XD "**ENC**" dead giveaway. This is in both files. Apparently the header tells the program that it is encrypted so it uses possibly a code to decrypt it.

Now I'm not sure how decryption works but how would I go about doing so?

Edit: I'm trying to learn somthing by doing this  because I am trying to get into some of this myself soon. Right now I'm... well... meh.  but I have never seen efforts made to do anything about this even though the game has a good rateing. It's just anybody who wants to/has the time to spare for this untouched 1998 game.
[RFireII.rar](https://xentaxbackup.github.io/file/1071_RFireII.rar)
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-02-24T08:24:44+00:00
- Post Title: Return Fire II (2) Text Encryption (PC/Windows9x-XP)

it might be encoded somehow, but it for me looks just too structured to actually be encrypted.......
[hexx.gif](https://xentaxbackup.github.io/file/1072_hexx.gif)
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-24T09:02:47+00:00
- Post Title: Return Fire II (2) Text Encryption (PC/Windows9x-XP)

As I said, the "**ENC**" could be a tag telling the program that it is encoded/encrypted.

If it was not it would have looked much like it's relative DAT files which were plain text.
## Post #4
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2007-02-24T09:04:01+00:00
- Post Title: Return Fire II (2) Text Encryption (PC/Windows9x-XP)

it would be much of help to get a a sample of those
plain text files aswell 

just too check stuff out.
## Post #5
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-24T09:06:25+00:00
- Post Title: Return Fire II (2) Text Encryption (PC/Windows9x-XP)

Here they are, these are the two datafiles that are not encrypted/encoded.
[BtnData.rar](https://xentaxbackup.github.io/file/1073_BtnData.rar)
## Post #6
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-25T01:08:34+00:00
- Post Title: Return Fire II (2) Text Encryption (PC/Windows9x-XP)

Yes, the files are encoded. I looked through the executable and discovered this (see image). Is that an alogarithm for decodeing the files (right above it)?

Am I on the right track? Any ideas?
[Solution.PNG](https://xentaxbackup.github.io/file/1074_Solution.PNG)
## Post #7
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2007-02-25T17:15:05+00:00
- Post Title: Return Fire II (2) Text Encryption (PC/Windows9x-XP)

try to breakpoint at this adress and see if any xoring.
## Post #8
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-25T18:47:11+00:00
- Post Title: Return Fire II (2) Text Encryption (PC/Windows9x-XP)

Hm? Specify what you mean, I don't speak the full language yet.
## Post #9
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2007-02-26T13:22:40+00:00
- Post Title: Return Fire II (2) Text Encryption (PC/Windows9x-XP)

some reversers use debuggers,they break the process when the memory reach the point wanted like your string and it allow to see what code does at this place..well its matter of debugging..have lost of knowledge since time.
## Post #10
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-02-26T16:25:32+00:00
- Post Title: Return Fire II (2) Text Encryption (PC/Windows9x-XP)

Obviously he isn't familiar with debugging.
Debugging or at least disassembling the exe often is the most promising approach for (rather complex) encryption. If there is a demo that uses the same format and you give me the download link I might have a look at the algorithm. 
But as you want to learn something by doing go learn assembler, get some reversing tuts and start debugging the target.

> Reply from Darkfox
>
> Is that an alogarithm for decodeing the files (right above it)?
Am I on the right track? Any ideas?
What you found here is just a stored string that is referenced somewhere in the exe, not more. The one right above is another one that can be something totally different (and in this case it is something different -> a string with the format  "{aaaaaaaa-bbbb-cccc-ddee-")
## Post #11
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-26T20:17:54+00:00
- Post Title: Return Fire II (2) Text Encryption (PC/Windows9x-XP)

Obviously I'm not. Just got a disassembler a few days ago.

[Near the Bottom is Two Demos]](http://www.download.com/sort/3150-7563_4-0-56-1.html?)

There are a couple of demos there.
## Post #12
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-02-26T23:42:13+00:00
- Post Title: Return Fire II (2) Text Encryption (PC/Windows9x-XP)

The decryption algorithm is pretty simple. **ENC** is the header.
The byte values of the string "RFDBEncode" are just substracted from the data bytes, so
real byte = encoded byte - string byte

There is some strange stuff at the end the file, those 7 CDs. Don't know why they are there, at least they are decrypted as well and the last byte is always set to 0.
So I attached a program that decrypts the files like they reside in memory after decryption. Encryption is theoretically possible as well, but I think it won't work cause of those unknown bytes at the end.

Just drop a file on the exe to convert it.
[RF2Dekoder.rar](https://xentaxbackup.github.io/file/1075_RF2Dekoder.rar)
## Post #13
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-27T02:29:35+00:00
- Post Title: Return Fire II (2) Text Encryption (PC/Windows9x-XP)

Awsome. I figured it wouldn't be difficult, but hm... now comes the tricky part, if it works ingame. I guess there is only one way to figure that.

Edit: It looks very structured like I'd expect. Everything is understandable to me in these files. The last bytes though do seem confusing. Like...

"}	

_j^ih{ "

I'm not sure about it. But it might be a thing that signifies the end of file. Like EOF or END. Hm...

In BTNDATA.dat it does end with "END"

Edit 2: Yep, I changed the last stuff to END and put the "{" below it and it seems the game's main data can be modded now, whoot! I used the jeep as a test and changed a few things for it such as the model. Worked flawlessly, thanks!

XD I made the jeep look like the jet, made it super fast and had a ramming strength of astronomical proportions and rammed a building unintentionally causing it and the jeep to explode lol, I didn't see THAT coming. Again, kudos Rheini, it works great!

"_j^ih" I'm very certain is "END" because it marks the end of both DATs. In any case this opens doors for the game.
## Post #14
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-02-27T10:25:37+00:00
- Post Title: Return Fire II (2) Text Encryption (PC/Windows9x-XP)

> Reply from Darkfox
>
> Edit 2: Yep, I changed the last stuff to END and put the "{" below it and it seems the game's main data can be modded now, whoot! I used the jeep as a test and changed a few things for it such as the model. Worked flawlessly, thanks!
Where did you change that? In the crypted files?
Did you encode it? Or does the game accept it in decrypted form as well?

This "j^i" stuff marks both ends of the files cause each file has thos 7 0xCDs at its end. So this must be a suffix that is added after encryption.
## Post #15
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-27T10:33:35+00:00
- Post Title: Return Fire II (2) Text Encryption (PC/Windows9x-XP)

Well, it doesn't have to be re-encrypted/encoded to work. 

> This "j^i" stuff marks both ends of the files cause each file has thos 7 0xCDs at its end. So this must be a suffix that is added after encryption.

That seems to me that it is "END" marking the end of the datafile. But in any case the decoded files work ingame. Have not tested the other but the main one is fully moddable and works ingame without being encrypted.
## Post #16
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-02-27T10:48:05+00:00
- Post Title: 

Yeah but the strange thing is that the last byte is always filled with 00 and the other CDs are always decoded. This doesn't make any sense.
Maybe it's just something to confuse decryptors.
## Post #17
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2007-02-27T13:41:34+00:00
- Post Title: 

> Reply from Rheini
>
> Obviously he isn't familiar with debugging.

but you can code your own tool,thats what miss me at most.Anything is a learning matter but thats a big part
## Post #18
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-28T01:02:08+00:00
- Post Title: 

Well I can't write tools myself and I'm only new to disassembling and as for debugging...not sure. Doesn't seem it'd work on things ran under DosBox (I have two games that require this that have compression schemes) so I wouldn't know at my level. Hence partially why I am going to college.

Oh wait. I just now realised that DosBox has debugger built in I believe.
