## Post #1
- Username: Venushja
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 19, 2010 11:13 pm
- Post datetime: 2011-08-29T13:58:33+00:00
- Post Title: Mass Effect 2 TLK Unpack/Pack -> Help (Source code)

Hello. 
Anyone knows, how to edit this Source Code? I want to extract it, package 
it and have the same structure. Y'know, I extracted Original TLK to XML and then 
I packaged that XML back to TLK (without any changes in XML file). This new TLK 
have in result different structure (not the same structure as a structure in 
original TLK file) and the size of file was about 100kB bigger. I really need 
your help - my knowledge is not good enough to solve this. Sorry for my bad English. 
Thanx for any help.

```
http://www.megaupload.com/?d=6LE0W7U3
```


Source Code, TLK Files (PC and Xbox), TLK Tools 1.0.4 inside in rar file.
## Post #2
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-08-30T01:00:45+00:00
- Post Title: Mass Effect 2 TLK Unpack/Pack -> Help (Source code)

You tried to contact the developer of the tool?
## Post #3
- Username: Venushja
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 19, 2010 11:13 pm
- Post datetime: 2011-08-30T07:25:35+00:00
- Post Title: Mass Effect 2 TLK Unpack/Pack -> Help (Source code)

Not tried. The program sent me buddy and I pulled it from the source code and when I did not know what to do with it so I wrote here.
## Post #4
- Username: Venushja
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 19, 2010 11:13 pm
- Post datetime: 2011-09-03T07:28:44+00:00
- Post Title: Mass Effect 2 TLK Unpack/Pack -> Help (Source code)

Really anyone?
## Post #5
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-09-19T19:01:00+00:00
- Post Title: Mass Effect 2 TLK Unpack/Pack -> Help (Source code)

The structure should be the same. I know this tool and format of ME2 TLK files. They use [Huffman coding](http://en.wikipedia.org/wiki/Huffman_coding) compression scheme. Basically that means, unless you have original source code BioWare used to compile those TLK files, you'll never get the same resulting file even if you haven't changed texts at all.
## Post #6
- Username: Krait
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Nov 08, 2011 12:14 am
- Post datetime: 2011-11-07T16:41:41+00:00
- Post Title: Mass Effect 2 TLK Unpack/Pack -> Help (Source code)

Hi, I accidentally stumbled upon this forum. I'm the developer of the tool. Quick Google search would lead you to the homepage of the project: [http://social.bioware.com/project/3492/](http://social.bioware.com/project/3492/), where you could contact me 

I'm sorry for resurrecting the thread, just wanted to clarify for others.

Yes, the compression is Huffman coding, so the copy will never be 1-1. But there's another reason for the 100kB size difference. The original ME2 TLKs have one additional trick, which I didn't implement. When there is string A that is a suffix for another string B, then reference to string A is stored at the end of string B, instead of the actual string. So for example if there are three identical strings, they're stored only once, with references.

But at the time of writing the tool, I was too lazy to efficiently implement this. And the size difference is really affordable.

But the "structure", as you say, is ok. It's identical and appropriate for the format. It just lacks one optimalization, but it only means the file is _slighlty_ bigger nothing else.

The only issue with the tool is that it has very limited support for Xbox360 and PS3 TLKs. It only loads them fine and dumps to XML. But somehow, when converted back to TLK, it doesn't work on the console. I don't have any console for testing, so can't really trace the problem down.
## Post #7
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-11-07T16:58:15+00:00
- Post Title: Mass Effect 2 TLK Unpack/Pack -> Help (Source code)

> Reply from Krait
>
> The only issue with the tool is that it has very limited support for Xbox360 and PS3 TLKs. It only loads them fine and dumps to XML. But somehow, when converted back to TLK, it doesn't work on the console. I don't have any console for testing, so can't really trace the problem down.
Do you correctly handle endianness?
## Post #8
- Username: Krait
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Nov 08, 2011 12:14 am
- Post datetime: 2011-11-07T17:17:18+00:00
- Post Title: Mass Effect 2 TLK Unpack/Pack -> Help (Source code)

> Reply from mnn
>
> Krait wrote:The only issue with the tool is that it has very limited support for Xbox360 and PS3 TLKs. It only loads them fine and dumps to XML. But somehow, when converted back to TLK, it doesn't work on the console. I don't have any console for testing, so can't really trace the problem down.
Do you correctly handle endianness?

Yes, changing endianness is currently the only difference between console and PC mode in the app. That's why it can properly read the TLK to XML. But when TLK is created from such XML, it's buggy on both Xbox360 and PS3. Weird, eh?
## Post #9
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-11-07T17:30:15+00:00
- Post Title: Mass Effect 2 TLK Unpack/Pack -> Help (Source code)

Are you sure endianness is the only thing different in console versions of TLK? Because apparently, there must be something else.
## Post #10
- Username: Krait
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Nov 08, 2011 12:14 am
- Post datetime: 2011-11-07T17:43:29+00:00
- Post Title: Mass Effect 2 TLK Unpack/Pack -> Help (Source code)

> Reply from mnn
>
> Are you sure endianness is the only thing different in console versions of TLK? Because apparently, there must be something else.

Clearly it's not the only thing  I said that currently, it's the only implemented difference. And it's enough for one-way conversion only :/
Well, it's a dead end for me, because I don't own any console. I had reports from people who tried to run those TLKs on Xbox360 and PS3 and they had errors. But I couldn't understand what were the symptoms exactly and our contact was very limited unfortunately.
## Post #11
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-11-08T14:56:11+00:00
- Post Title: Mass Effect 2 TLK Unpack/Pack -> Help (Source code)

Yes there is something else, i have JTAG console here and if someone want to help i can test TLK's anytime you want. If you are interest please contact me on PM and i will send you msn, skype or IcQ .

Me and my firend spend many hours on this without the success, we also find that repacked TLK for PC has also many differents but it runs ok. I was able to run it for about 5 mints on X360 with text mess but thats about all, really unplayable at all.
Trust me PPL would ript off your hands to make it work on PS3 or Xbox360 

Mike
