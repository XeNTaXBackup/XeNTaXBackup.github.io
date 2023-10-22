## Post #1
- Username: titanic
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Nov 30, 2006 4:58 am
- Post datetime: 2007-11-18T19:08:21+00:00
- Post Title: new AION .pak file format.need help!

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-11-18T23:29:04+00:00
- Post Title: new AION .pak file format.need help!

Could you upload the game's exe and dll files?
## Post #3
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-11-19T09:00:13+00:00
- Post Title: new AION .pak file format.need help!

Yes, that would be good.
I checked, and the bytes used to XOR against are different for each file. I guess it's calculated via one or more values from the file header.
## Post #4
- Username: titanic
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Nov 30, 2006 4:58 am
- Post datetime: 2007-11-19T13:14:06+00:00
- Post Title: new AION .pak file format.need help!

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-11-19T13:47:16+00:00
- Post Title: new AION .pak file format.need help!

Fuck. Koreans seem to like Themida ^^
Ragnarök also used it I think.
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-11-20T01:22:54+00:00
- Post Title: new AION .pak file format.need help!

Unfortunately UnThemida can't unpack the dll
## Post #7
- Username: Mark
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 27, 2007 12:57 pm
- Post datetime: 2007-12-05T03:25:45+00:00
- Post Title: new AION .pak file format.need help!

Oh, hey, someone made a thread for this before I did. Awesome! Any files that you guys need that you don't have?
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-05T09:45:03+00:00
- Post Title: new AION .pak file format.need help!

No we'd need someone that is able to unpack Themida.
## Post #9
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2007-12-05T17:51:57+00:00
- Post Title: new AION .pak file format.need help!

> Reply from john_doe
>
> Yes, that would be good.
I checked, and the bytes used to XOR against are different for each file. I guess it's calculated via one or more values from the file header.

EDIT: Solved
## Post #10
- Username: titanic
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Nov 30, 2006 4:58 am
- Post datetime: 2007-12-11T09:50:27+00:00
- Post Title: new AION .pak file format.need help!

> Reply from GameZelda
>
> john_doe wrote:Yes, that would be good.
I checked, and the bytes used to XOR against are different for each file. I guess it's calculated via one or more values from the file header.

EDIT: Solved

whats mean?
## Post #11
- Username: Mark
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 27, 2007 12:57 pm
- Post datetime: 2007-12-23T00:20:44+00:00
- Post Title: new AION .pak file format.need help!

It means this thread gets bumped.
## Post #12
- Username: Mark
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 27, 2007 12:57 pm
- Post datetime: 2007-12-27T04:45:54+00:00
- Post Title: new AION .pak file format.need help!

Who should I bribe around here to find a solution to us AION fans little predicament?
## Post #13
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-12-27T13:25:13+00:00
- Post Title: new AION .pak file format.need help!

As I already said the exe seems to be protected by themida. We need an unpacked exe to figure out the encryption algorithm.
## Post #14
- Username: Hiam
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Dec 08, 2007 10:56 pm
- Post datetime: 2008-01-07T14:28:55+00:00
- Post Title: new AION .pak file format.need help!

What you need is not a unpacked exe. What you need is a unpacked CrySystem.dll. Also, you won't need a fully working one, what you need is to be able to read the code section. And that is pretty easy, since Themida anti codes are pretty simple.

[http://geekserv.hornycat.org/~dick/CrySystem_dumped.rar](http://geekserv.hornycat.org/~dick/CrySystem_dumped.rar)

There you go, you will have all strings, all code. Just offsets is wrong.
Im myself investigating whats been happening to the first 32bytes of the compressedData. And i can say its not a simple xor, shr, shl method.
It's a dynamic value that's been tampered with more than that.

I'll be cross checking with the orginal CrySystem to see what they've added.

Many kisses
## Post #15
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-01-07T17:52:24+00:00
- Post Title: new AION .pak file format.need help!

Pretty simple? Doesn't this old version of Themida/Xtreme Protector use an aggressive ring0 driver?
And what about some tools identifying Xtreme Protector (though that one section is named Themida)?
Are both protections used?
## Post #16
- Username: Hiam
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Dec 08, 2007 10:56 pm
- Post datetime: 2008-01-07T18:27:40+00:00
- Post Title: 

> Reply from Rheini
>
> Pretty simple? Doesn't this old version of Themida/Xtreme Protector use an aggressive ring0 driver?
And what about some tools identifying Xtreme Protector (though that one section is named Themida)?
Are both protections used?

It's easier than that, but um both Themida, and identifing near EOF you can notice what version it is, by comparing your own protected applications, you know what version you've used. Use Peid for this, and try find a cool signature Database, I hear the next version of Peid will contain loads of signatures.

It does not use any kernel driven driver, it use hooks allthough.
Which case, you wont have to bother now, since i supplied you with a decrypted code dll.
## Post #17
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-01-07T18:36:05+00:00
- Post Title: 

Yeah but I'm into every aspect of reverse engineering, not only game file formats 
I'm really interested in how you unpacked it. There are not much tutorials out there. I only have a spanish one, but it's hard to read it using Google translation
## Post #18
- Username: Hiam
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Dec 08, 2007 10:56 pm
- Post datetime: 2008-01-07T18:49:34+00:00
- Post Title: 

Allrighty then, well drop me a pm with your msn and i'll tell you
## Post #19
- Username: Mark
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 27, 2007 12:57 pm
- Post datetime: 2008-01-14T15:15:00+00:00
- Post Title: 

Awesome, progress. Wish you guys had some kind of "donate" button, lol.
## Post #20
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-01T23:03:40+00:00
- Post Title: 

Another unpacked Crysystem.dll can be found here: [http://sharebee.com/1378465c](http://sharebee.com/1378465c)
## Post #21
- Username: Jeram
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 30, 2008 6:55 am
- Post datetime: 2008-03-30T10:59:42+00:00
- Post Title: 

Hi guys,

I'm new to this forum and very curious about Aion's textures and sounds  Is there any news about how to extract the files from the *.pak files? Since I don't much about encryption and all this stuff, the only way I can help you is uploading any needed client file to get this done.
## Post #22
- Username: Hiam
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Dec 08, 2007 10:56 pm
- Post datetime: 2008-10-14T23:22:25+00:00
- Post Title: 

```
___:33084D37                                         ; DATA XREF: ___:33085574o
___:33084D37                 cmp     edi, 20h        ; Compare Two Operands
___:33084D3A                 jnb     short loc_33084D74 ; Jump if Not Below (CF=0)
___:33084D3C                 mov     ecx, 1
___:33084D41
___:33084D41 loc_33084D41:                           ; CODE XREF: sub_33084BD0+1A2j
___:33084D41                 cmp     [ebp+var_8], 0  ; Compare Two Operands
___:33084D45                 jz      loc_330852FD    ; Jump if Zero (ZF=1)
___:33084D4B                 mov     edx, [ebp+var_4]
___:33084D4E                 sub     [ebp+var_8], ecx ; Integer Subtraction
___:33084D51                 movzx   edx, byte ptr [edx] ; Move with Zero-Extend
___:33084D54                 mov     ecx, edi
___:33084D56                 shl     edx, cl         ; Shift Logical Left
___:33084D58                 mov     ecx, 1
___:33084D5D                 add     [ebp+var_4], ecx ; Add
___:33084D60                 add     edi, 8          ; Add
___:33084D63                 or      eax, edx        ; Logical Inclusive OR
___:33084D65                 cmp     edi, 20h        ; Compare Two Operands
___:33084D68                 mov     [ebp+arg_8], 0
___:33084D6F                 mov     [ebp+arg_4], eax
___:33084D72                 jb      short loc_33084D41 ; Jump if Below (CF=1)
```
## Post #23
- Username: Katadin
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Oct 23, 2008 10:08 pm
- Post datetime: 2008-10-23T14:50:09+00:00
- Post Title: 

I hadn't seen this forum before (doh, hours wasted!) so I only managed to get as far as noticing it was a zip file with the header changed.  When I tried extracting with those 32 bytes different I got all sorts of exceptions so hopefully you wizards can work out whats changed (i.e. what the OP posted about).  I'm not a super programmer, but I do like ripping apart game files and their encryption (as long as they're fairly basic!).  ASM is a bit beyond me so the above code goes way over my head, but if I can get an idea of whats changed then I'll keep giving it a go
## Post #24
- Username: Katadin
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Oct 23, 2008 10:08 pm
- Post datetime: 2008-10-23T17:53:14+00:00
- Post Title: 

If I've made any sense of that assembly above, you'd need to know what is stored in EAX and CL, and what EBP initially points to, to make any sense of how the values are being manipulated?  Never done much debugging, but not sure how you'd inspect those without the program running?

I presume the scrambling of these 32 bytes is literally just to break the deflate routine and nothing more? If so my gut instinct is that those 32 bytes are just being encoded against a key, which I'd guess EAX points to.  Lot of guessing, but its all I've got so far
## Post #25
- Username: Hiam
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Dec 08, 2007 10:56 pm
- Post datetime: 2008-10-25T15:50:58+00:00
- Post Title: 

The above routine just give you a hint what to look for.

From my previous research i found that

The data is "simply" xor-ed by the pre-calculated table.
You can find the table and how it is xor-ed in Crysystem.dll.
## Post #26
- Username: Katadin
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Oct 23, 2008 10:08 pm
- Post datetime: 2008-10-27T12:06:58+00:00
- Post Title: 

I'm going cross-eyed looking through the .dll   What you said above was really helpful in finding the table, I just have no idea where to look to find out how it selects each entry.  Any more hints?

Edit: nevermind, think I figured it out (very sneaky!), and hopefully thats enough to find the right "key".  Getting a bit closer now!
## Post #27
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2008-10-29T22:19:24+00:00
- Post Title: 

The contents of this post was deleted because of possible forum rules violation.
## Post #28
- Username: Hiam
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Dec 08, 2007 10:56 pm
- Post datetime: 2008-10-31T16:16:09+00:00
- Post Title: 

We know, and so can we with our codes. Thats not really what the thread is about ;P
## Post #29
- Username: titanic
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Nov 30, 2006 4:58 am
- Post datetime: 2008-11-02T19:11:29+00:00
- Post Title: 

The contents of this post was deleted because of possible forum rules violation.
## Post #30
- Username: Hiam
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Dec 08, 2007 10:56 pm
- Post datetime: 2008-11-03T01:07:38+00:00
- Post Title: 

Not much of a change allthough
## Post #31
- Username: titanic
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Nov 30, 2006 4:58 am
- Post datetime: 2008-11-03T09:07:47+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from Hiam
>
> Not much of a change allthough

Yes,there aslo 32 bytes crypted.

I cant find key for Xor. have you unpack new CrySystem.dll?
## Post #32
- Username: Cori
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 06, 2008 2:27 am
- Post datetime: 2008-11-06T07:58:38+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from Hiam
>
> Not much of a change allthough
I'm a bit clueless here, but any chance someon could modify jonh_does
unpacker or pm me what to change?
## Post #33
- Username: titanic
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Nov 30, 2006 4:58 am
- Post datetime: 2008-11-08T06:50:25+00:00
- Post Title: Re: new AION .pak file format.need help!

I have try unpack dll 3 days.
no any progress.

PLS anyone can unpack this or tell me how to do.
## Post #34
- Username: roxfan
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 15, 2008 10:28 am
- Post datetime: 2008-11-15T11:59:52+00:00
- Post Title: Re: new AION .pak file format.need help!

Thanks to whoever dumped the DLL, it helped me to figure out the xor keys. I made a small converter in Python.
Edit: apparently it doesn't work with the latest client, I need a new dump of the DLL...
[pak2zip.zip](https://xentaxbackup.github.io/file/1743_pak2zip.zip)
## Post #35
- Username: roxfan
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 15, 2008 10:28 am
- Post datetime: 2008-11-22T18:27:14+00:00
- Post Title: Re: new AION .pak file format.need help!

After a weekend spent unpacking the latest DLL (Themida is a bitch), I finally succeeded in finding the new table and xor algo. Here's an updated script which should support both versions I had access to. It checks that the data unpacks cleanly and CRC matches to detect the AION version.


 pak2zip_02.zip
AION pak to zip converter, v0.2 (5.31 KiB) Downloaded 543 times


Supported CrySystem.dll versions:
1.1.7.1221 (2285568 bytes)
1.8.1027.415 (2666496 bytes)
If you have a different version which is not handled, please post the DLL.
## Post #36
- Username: caspersus
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Nov 24, 2008 5:21 pm
- Post datetime: 2008-11-24T09:30:19+00:00
- Post Title: Re: new AION .pak file format.need help!

The contents of this post was deleted because of possible forum rules violation.
## Post #37
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-11-24T16:40:40+00:00
- Post Title: Re: new AION .pak file format.need help!

rokfan, does this mean it creates a "zip" file that you can extract? But i guess the models are still some weird format that needs to be converted to?
## Post #38
- Username: roxfan
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 15, 2008 10:28 am
- Post datetime: 2008-11-24T20:22:15+00:00
- Post Title: Re: new AION .pak file format.need help!

The contents of this post was deleted because of possible forum rules violation.
## Post #39
- Username: titanic
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Nov 30, 2006 4:58 am
- Post datetime: 2008-11-25T15:45:49+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from roxfan
>
> After a weekend spent unpacking the latest DLL (Themida is a bitch), I finally succeeded in finding the new table and xor algo. Here's an updated script which should support both versions I had access to. It checks that the data unpacks cleanly and CRC matches to detect the AION version.
pak2zip_02.zip
Supported CrySystem.dll versions:
1.1.7.1221 (2285568 bytes)
1.8.1027.415 (2666496 bytes)
If you have a different version which is not handled, please post the DLL.

Thank you very much!!! You are a l33t!
## Post #40
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-11-25T16:30:36+00:00
- Post Title: Re: new AION .pak file format.need help!

oh  i hope someone can take a look at textures, I have ripped models with a 3d ripper but it doesnt take normal maps and specular maps. If we can't figure out models maybe textures?
## Post #41
- Username: caspersus
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Nov 24, 2008 5:21 pm
- Post datetime: 2008-11-26T11:28:23+00:00
- Post Title: Re: new AION .pak file format.need help!

The contents of this post was deleted because of possible forum rules violation.
## Post #42
- Username: roxfan
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 15, 2008 10:28 am
- Post datetime: 2008-11-26T19:51:33+00:00
- Post Title: Re: new AION .pak file format.need help!

The contents of this post was deleted because of possible forum rules violation.
## Post #43
- Username: blacklotus
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Nov 30, 2008 8:44 am
- Post datetime: 2008-11-30T13:00:11+00:00
- Post Title: Re: new AION .pak file format.need help!

Hi,

I am searching info on the xml files that can be found inside some pak files. Everything else unpack with success but the xml files seem to be crypted. Do you have information on this ?

Regards
## Post #44
- Username: Frigo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 01, 2008 5:55 pm
- Post datetime: 2008-12-04T09:24:25+00:00
- Post Title: Re: new AION .pak file format.need help!

Hi

The python script fails for Sounds_music.pak. Could you check why?
## Post #45
- Username: Jeram
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 30, 2008 6:55 am
- Post datetime: 2008-12-07T13:54:14+00:00
- Post Title: Re: new AION .pak file format.need help!

Thanks for your script 
I'm new to all of this so I've got one question, how do I run this script?

When I try to run it, I get this error =o

```
  File "D:\pak2zip.py", line 57, in <module>
    "\x2f\x5d\x51\xf7\x01\xe9\xb4\x93\x4e\x51\x81\x3e\xaf\x3f\xdf\x99"
TypeError: an integer is required
```
## Post #46
- Username: roxfan
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 15, 2008 10:28 am
- Post datetime: 2008-12-07T15:14:31+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from Frigo
>
> The python script fails for Sounds_music.pak. Could you check why?
Worked for me. Are you using the second version of the script? Does it fail on other .pak files too? What is your CrySystem.dll version?

> Reply from Jeram
>
> 
When I try to run it, I get this error =o.
Code: Select allTraceback (most recent call last):
  File "D:\pak2zip.py", line 57, in <module>
    "\x2f\x5d\x51\xf7\x01\xe9\xb4\x93\x4e\x51\x81\x3e\xaf\x3f\xdf\x99"
TypeError: an integer is required
What is your Python version? I tested on 2.5 and it should work on 2.6. It will not work on 3.0.
## Post #47
- Username: Jeram
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 30, 2008 6:55 am
- Post datetime: 2008-12-07T18:05:40+00:00
- Post Title: Re: new AION .pak file format.need help!

Thanks for your quick reply, I'll download ver. 2.5 then
## Post #48
- Username: caspersus
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Nov 24, 2008 5:21 pm
- Post datetime: 2008-12-10T10:12:29+00:00
- Post Title: Re: new AION .pak file format.need help!

The contents of this post was deleted because of possible forum rules violation.
## Post #49
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-12-10T11:58:04+00:00
- Post Title: Re: new AION .pak file format.need help!

Are you saying that we might get a hold of the meshes, textures and animations? This sounds really really good  Any idea what format the meshes are?
## Post #50
- Username: Katadin
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Oct 23, 2008 10:08 pm
- Post datetime: 2008-12-10T14:55:20+00:00
- Post Title: Re: new AION .pak file format.need help!

A version of the Crysis model format that doesn't seem to be recognised in any importers I've tried for 3DSMax or Blender.  If I recall they're mainly CGF files (Crytek).

Haven't really bothered looking into much of the Aion stuff for now, mainly due to Wotlk (damn you blizzard) and the fact the NA/EU version of Aion isn't out for months yet.   Would love to be able to use the models though
## Post #51
- Username: caspersus
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Nov 24, 2008 5:21 pm
- Post datetime: 2008-12-10T15:50:22+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from pixellegolas
>
> Are you saying that we might get a hold of the meshes, textures and animations? This sounds really really good  Any idea what format the meshes are?

They are in .cah format ... Which I never heard 

You can already extract textures with the python script posted in this thread. Not sure bout animations, I didnt checked those.
Textures are in .DDS format, so its no problem to open/edit em.
## Post #52
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-12-10T16:06:03+00:00
- Post Title: Re: new AION .pak file format.need help!

there is an offline hack so you can enter the character select screen and rip some models. But, i cannot access weapons or other model armors and such  So, some DDS textures i already have, even specular and normals.

Hope to see some progress of this beautiful game
## Post #53
- Username: caspersus
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Nov 24, 2008 5:21 pm
- Post datetime: 2008-12-10T16:29:50+00:00
- Post Title: Re: new AION .pak file format.need help!

I have the hack that enables me to access character creation locally, but how do you rip the models from there ???
## Post #54
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-12-10T19:20:51+00:00
- Post Title: Re: new AION .pak file format.need help!

I use 3d VIA printscreen. It captures dx8, dx9 and opengl stuff. The bad thing is it creates flat .png files instead of .dds with alpha channel. And you always have to do some welding on the objects.

Oh, 3d via printscreen only rips to .3dxml and there is a plugin for max that imports this. A guy named KOICHISENADA posted it here in the forums last week.
## Post #55
- Username: roxfan
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 15, 2008 10:28 am
- Post datetime: 2008-12-10T21:01:55+00:00
- Post Title: Re: new AION .pak file format.need help!

Thanks for the sample, caspersus. Turns out it was just uncompressed data (I was assuming it's always compressed). Made some adjustments to handle it.
[pak2zip_03.zip](https://xentaxbackup.github.io/file/1774_pak2zip_03.zip)
## Post #56
- Username: caspersus
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Nov 24, 2008 5:21 pm
- Post datetime: 2008-12-10T22:21:13+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from pixellegolas
>
> I use 3d VIA printscreen. It captures dx8, dx9 and opengl stuff. The bad thing is it creates flat .png files instead of .dds with alpha channel. And you always have to do some welding on the objects.

Oh, 3d via printscreen only rips to .3dxml and there is a plugin for max that imports this. A guy named KOICHISENADA posted it here in the forums last week.

I've downloaded and installed that program, but it doesnt work at all for me  Dunno why ~~
## Post #57
- Username: caspersus
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Nov 24, 2008 5:21 pm
- Post datetime: 2008-12-10T22:57:39+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from roxfan
>
> Thanks for the sample, caspersus. Turns out it was just uncompressed data (I was assuming it's always compressed). Made some adjustments to handle it.

Thanks for the fast update, script works flawless now 

I managed to extract the meshes pak and it contains few types of files:

.cal file - which it seems to be an index of the animation for the respective character (in this case elyos female)
.phy files - which contain some skeleton info (bones and stuff)
.cai file - somewhat similar to psy, contains the bones names
.cgf files - which is encoded somewhat, so I dont really know what it does. btw, there is a cfg file for each hair type, accessorry typ etc.
.saf file - also encoded, I dont know what is good for 

I attached a small archive with 1 of each files if anyone is interested in looking into them:
[http://rapidshare.com/files/172210683/Mesh_Files.rar](http://rapidshare.com/files/172210683/Mesh_Files.rar)
## Post #58
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-12-10T23:19:26+00:00
- Post Title: Re: new AION .pak file format.need help!

You dhould make sure you have teh right button first  Then make sure you run in a window mode.

I looked on the net about model files. .CGF files are cryengine models. Tried an importer for max but did not work. That was a hit in the face
## Post #59
- Username: caspersus
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Nov 24, 2008 5:21 pm
- Post datetime: 2008-12-11T00:17:19+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from pixellegolas
>
> You dhould make sure you have teh right button first  Then make sure you run in a window mode.

I looked on the net about model files. .CGF files are cryengine models. Tried an importer for max but did not work. That was a hit in the face

Still doesnt work. Running in window mode, using the default F10 for capturing. Nothing happends when I press it -.-

Edit: This proggie [http://web.axelero.hu/karpo/](http://web.axelero.hu/karpo/) can open the .cgf files  Unfortunatelly, it cannot export em (unless you buy a license) ~.~
## Post #60
- Username: caspersus
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Nov 24, 2008 5:21 pm
- Post datetime: 2008-12-11T01:00:23+00:00
- Post Title: Re: new AION .pak file format.need help!

A small teaser before I go to bed 

[](http://img234.imageshack.us/img234/788/aionmeshmh4.jpg)
## Post #61
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-12-11T06:21:49+00:00
- Post Title: Re: new AION .pak file format.need help!

that is cool! I did not get any textures when i tried on shugafemale.

It says on formats that it is a cryengine .cgf file. I wonder why it did not work with my importer then
## Post #62
- Username: Katadin
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Oct 23, 2008 10:08 pm
- Post datetime: 2008-12-11T09:24:38+00:00
- Post Title: Re: new AION .pak file format.need help!

Hehe awesome!  I'd even buy a license if its reasonable, though I imagine its just a matter of time before other modelling programs can open the new crytek version.

Sod it, its only 40 EUR, bit of a bargain
## Post #63
- Username: caspersus
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Nov 24, 2008 5:21 pm
- Post datetime: 2008-12-11T09:49:11+00:00
- Post Title: Re: new AION .pak file format.need help!

Actually, I think 50 bux its pretty reasonable considering you can convert over 500 3d model types with that proggie. Im thinking to buy a license =)
## Post #64
- Username: Katadin
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Oct 23, 2008 10:08 pm
- Post datetime: 2008-12-11T09:49:41+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from caspersus
>
> A small teaser before I go to bed

How did you load the texture?  When I try it gives an error it can't load it (but seems to open fine in various .dds viewers).
## Post #65
- Username: Katadin
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Oct 23, 2008 10:08 pm
- Post datetime: 2008-12-11T09:50:38+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from caspersus
>
> Actually, I think 50 bux its pretty reasonable considering you can convert over 500 3d model types with that proggie. Im thinking to buy a license =)
Yeah just downloaded it and saw it was 50.. don't mind paying that at all
## Post #66
- Username: caspersus
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Nov 24, 2008 5:21 pm
- Post datetime: 2008-12-11T10:21:40+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from Katadin
>
> caspersus wrote:A small teaser before I go to bed 



How did you load the texture?  When I try it gives an error it can't load it (but seems to open fine in various .dds viewers).

Copy the textures to same folder as the mesh and convert em to .jpg format  If you want transparency, save .dds as .tga
## Post #67
- Username: Katadin
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Oct 23, 2008 10:08 pm
- Post datetime: 2008-12-11T11:02:54+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from caspersus
>
> Copy the textures to same folder as the mesh and convert em to .jpg format  If you want transparency, save .dds as .tga

Ah weird it doesn't load the .dds, it says it should.
## Post #68
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-12-11T14:34:10+00:00
- Post Title: Re: new AION .pak file format.need help!

Now someone needs to create a better converter with bones and animations. I rather spend 50 bucks on that converter
## Post #69
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2008-12-14T18:36:14+00:00
- Post Title: Re: new AION .pak file format.need help!

What version of python do you need to run the script?
can anyone give me a quick rundown of how to run the python script.
Thanks in advance.
## Post #70
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-12-14T22:50:09+00:00
- Post Title: Re: new AION .pak file format.need help!

you place the .py in a folder with a archive.

then you need to go to command promt CMD and go to that folder.

now write pak2zip.py xxx.pak xxx.zip where xxx is the archive you want to turn into a zip
## Post #71
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2008-12-14T22:52:38+00:00
- Post Title: Re: new AION .pak file format.need help!

Thanks so much
## Post #72
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2008-12-15T13:33:38+00:00
- Post Title: Re: new AION .pak file format.need help!

"Now someone needs to create a better converter with bones and animations. I rather spend 50 bucks on that converter "



And the morph (troubleshooting  far cry and crysis plugin importer)
## Post #73
- Username: caspersus
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Nov 24, 2008 5:21 pm
- Post datetime: 2008-12-15T16:18:51+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from Katadin
>
> caspersus wrote:Copy the textures to same folder as the mesh and convert em to .jpg format  If you want transparency, save .dds as .tga

Ah weird it doesn't load the .dds, it says it should.

Only loads uncompressed .dds files. Usually, all games textures (DXT1/DXT3/DXT5) are compressed so thats why it doesnt load
## Post #74
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2008-12-15T16:23:52+00:00
- Post Title: Re: new AION .pak file format.need help!

Does anyone have a link to the client download that works?

edit: nevermind, got it. Nice stuff. Does anyone know how or if the .cgf files differ from those of Far Cry? I can see and convert them using 3d Object Converter, but I can't import them into max using the far cry Cryimporter. They must be pretty close.
## Post #75
- Username: Laos
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 01, 2009 8:39 pm
- Post datetime: 2009-01-01T17:58:02+00:00
- Post Title: Re: new AION .pak file format.need help!

Did anybody manage to decrypt these files with .xml extension, but which in fact are not xml files, when opened ?
## Post #76
- Username: blacklotus
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Nov 30, 2008 8:44 am
- Post datetime: 2009-01-04T23:11:39+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from Laos
>
> Did anybody manage to decrypt these files with .xml extension, but which in fact are not xml files, when opened ?

I can't find how to decrypt thoses files ... if someone know how to
## Post #77
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-01-05T02:51:46+00:00
- Post Title: Re: new AION .pak file format.need help!

If you look at the xml files in a hex editor all they did was pas the file with 00 on every other byte.
it is in plain text and easy to read / edit.
## Post #78
- Username: Katadin
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Oct 23, 2008 10:08 pm
- Post datetime: 2009-01-06T09:09:33+00:00
- Post Title: Re: new AION .pak file format.need help!

Its because its encoded as UTF-16/Unicode.
## Post #79
- Username: Laos
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 01, 2009 8:39 pm
- Post datetime: 2009-01-08T10:01:29+00:00
- Post Title: Re: new AION .pak file format.need help!

It's not only unicode. Second part of file is binary data.
## Post #80
- Username: Mark
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 27, 2007 12:57 pm
- Post datetime: 2009-03-24T22:21:30+00:00
- Post Title: Re: new AION .pak file format.need help!

I don't know if this will help you guys with the XML files, but here's an executable I found in one of the .pak files. It doesn't seem to do anything, but judging by its name it must do something... 
[XmlChecker.rar](https://xentaxbackup.github.io/file/1939_XmlChecker.rar)
## Post #81
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2009-04-07T14:22:03+00:00
- Post Title: Re: new AION .pak file format.need help!

any plans to make this work with the english client? can be downloaded here [ftp://ftp.aiononline.com/client/](ftp://ftp.aiononline.com/client/)
## Post #82
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2009-04-07T14:32:47+00:00
- Post Title: Re: new AION .pak file format.need help!

actually, it seems to work just fine with the english client, anyone else had any success with the encrypted part of the xml files?
## Post #83
- Username: iamhere
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 16, 2009 9:18 am
- Post datetime: 2009-04-20T14:40:27+00:00
- Post Title: Re: new AION .pak file format.need help!

Thanks to this awesome topic I've suceeded to export everything from the client. I've managed to open everything except animations. Anyone have a clue how to convert or view the animations? They are .caf extensions, I have no clue what that is.

Would be really pleased if someone could help, I'd actually pay for a converter if you make one.
## Post #84
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2009-04-20T19:57:51+00:00
- Post Title: Re: new AION .pak file format.need help!

you figured out the proprietary xml format?
## Post #85
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-04-21T03:37:58+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from iamhere
>
> Thanks to this awesome topic I've suceeded to export everything from the client. I've managed to open everything except animations. Anyone have a clue how to convert or view the animations? They are .caf extensions, I have no clue what that is.

Would be really pleased if someone could help, I'd actually pay for a converter if you make one.

What did you use to unpack the pak files? I tried RPGViewer 3.0 with the Chinese client, but all the extracted files were 0kb. Any ideas?
## Post #86
- Username: iamhere
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 16, 2009 9:18 am
- Post datetime: 2009-04-21T21:18:02+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from Theran
>
> iamhere wrote:Thanks to this awesome topic I've suceeded to export everything from the client. I've managed to open everything except animations. Anyone have a clue how to convert or view the animations? They are .caf extensions, I have no clue what that is.

Would be really pleased if someone could help, I'd actually pay for a converter if you make one.

What did you use to unpack the pak files? I tried RPGViewer 3.0 with the Chinese client, but all the extracted files were 0kb. Any ideas?

Currently RPGViewer doesn't support higher version than AION_Setup_0.9.0.0. You've probably installed AION_Setup_0.9.5.0.
## Post #87
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2009-04-22T15:55:38+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from iamhere
>
> Theran wrote:iamhere wrote:Thanks to this awesome topic I've suceeded to export everything from the client. I've managed to open everything except animations. Anyone have a clue how to convert or view the animations? They are .caf extensions, I have no clue what that is.

Would be really pleased if someone could help, I'd actually pay for a converter if you make one.

What did you use to unpack the pak files? I tried RPGViewer 3.0 with the Chinese client, but all the extracted files were 0kb. Any ideas?

Currently RPGViewer doesn't support higher version than AION_Setup_0.9.0.0. You've probably installed AION_Setup_0.9.5.0.

Probably so. Though I did manage to setup that python script to work, so I did get to convert them to zip and extract them. Been going over the cgf files to try to figure out their format.
## Post #88
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2009-04-23T16:56:17+00:00
- Post Title: Re: new AION .pak file format.need help!

[http://gib.me/aion/ConvertXml.zip](http://gib.me/aion/ConvertXml.zip)

Really makes it obvious why they went with their binary XML format (client_items.xml goes from ~12MB to ~115MB).
## Post #89
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2009-04-23T17:10:00+00:00
- Post Title: Re: new AION .pak file format.need help!

any chance you'd be willing to share the format specification for it? i'm pretty close as it is, just not sure what the 03, 02, bytes do
## Post #90
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2009-04-23T17:15:40+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from nicoli_s
>
> any chance you'd be willing to share the format specification for it? i'm pretty close as it is, just not sure what the 03, 02, bytes do[http://svn.slurm.us/public/aion/trunk/](http://svn.slurm.us/public/aion/trunk/)
## Post #91
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2009-04-23T19:06:49+00:00
- Post Title: Re: new AION .pak file format.need help!

thx a million, i knew i was close, now i know by how much
## Post #92
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2009-04-23T21:09:51+00:00
- Post Title: Re: new AION .pak file format.need help!

The contents of this post was deleted because of possible forum rules violation.
## Post #93
- Username: ๐MaCkEy๐
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu May 07, 2009 6:05 pm
- Post datetime: 2009-05-08T20:27:52+00:00
- Post Title: Re: new AION .pak file format.need help!

The contents of this post was deleted because of possible forum rules violation.
## Post #94
- Username: iamhere
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 16, 2009 9:18 am
- Post datetime: 2009-05-13T18:52:32+00:00
- Post Title: Re: new AION .pak file format.need help!

The contents of this post was deleted because of possible forum rules violation.
## Post #95
- Username: roxfan
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 15, 2008 10:28 am
- Post datetime: 2009-05-13T21:51:45+00:00
- Post Title: Re: new AION .pak file format.need help!

There was a bug in the script that made it not detect version properly if there were zero-sized files or folders in the zip.
[pak2zip_04.zip](https://xentaxbackup.github.io/file/2034_pak2zip_04.zip)
## Post #96
- Username: ๐MaCkEy๐
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu May 07, 2009 6:05 pm
- Post datetime: 2009-05-15T08:09:46+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from roxfan
>
> There was a bug in the script that made it not detect version properly if there were zero-sized files or folders in the zip.

Thank you very much!!! It's working now!...but, the next problem .xml and .html files include in this enu.pak that I think it was encryption can't view with IE or text editor or xml editor(some files can view but not correctly). Have any suggest?
## Post #97
- Username: roxfan
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 15, 2008 10:28 am
- Post datetime: 2009-05-15T23:13:43+00:00
- Post Title: Re: new AION .pak file format.need help!

See [above](http://forum.xentax.com/viewtopic.php?p=28938#p28938).
## Post #98
- Username: ๐MaCkEy๐
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu May 07, 2009 6:05 pm
- Post datetime: 2009-05-17T20:25:38+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from roxfan
>
> See above.

Yep! working on decrypt .xml file but no decrypter for .html file that I think it was encrypt too.

Could you make script for repack like "zip2pak.py" ? It's will helpful. Thanks for your kindness.

**Sorry if my English too bad**
## Post #99
- Username: gloombear
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 17, 2009 7:40 am
- Post datetime: 2009-05-20T04:47:14+00:00
- Post Title: Re: new AION .pak file format.need help!

Is there a way to convert .cgf file to .obj? or.. something 3ds max can open?
NM  Solved with 3d object converter.
## Post #100
- Username: Katadin
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Oct 23, 2008 10:08 pm
- Post datetime: 2009-06-17T13:12:57+00:00
- Post Title: Re: new AION .pak file format.need help!

Anyone have a recent CrySystem.dll unpacked or know a decent tool to do it with?

Thanks.
## Post #101
- Username: Sorix
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 17, 2009 9:48 pm
- Post datetime: 2009-06-17T14:05:00+00:00
- Post Title: Re: new AION .pak file format.need help!

The contents of this post was deleted because of possible forum rules violation.
## Post #102
- Username: Katadin
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Oct 23, 2008 10:08 pm
- Post datetime: 2009-06-17T19:06:08+00:00
- Post Title: Re: new AION .pak file format.need help!

The contents of this post was deleted because of possible forum rules violation.
## Post #103
- Username: ๐MaCkEy๐
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu May 07, 2009 6:05 pm
- Post datetime: 2009-06-18T04:09:04+00:00
- Post Title: Re: new AION .pak file format.need help!

The contents of this post was deleted because of possible forum rules violation.
## Post #104
- Username: Katadin
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Oct 23, 2008 10:08 pm
- Post datetime: 2009-06-18T08:03:54+00:00
- Post Title: Re: new AION .pak file format.need help!

The contents of this post was deleted because of possible forum rules violation.
## Post #105
- Username: ๐MaCkEy๐
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu May 07, 2009 6:05 pm
- Post datetime: 2009-06-18T11:08:42+00:00
- Post Title: Re: new AION .pak file format.need help!

The contents of this post was deleted because of possible forum rules violation.
## Post #106
- Username: Katadin
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Oct 23, 2008 10:08 pm
- Post datetime: 2009-06-18T12:54:14+00:00
- Post Title: Re: new AION .pak file format.need help!

I don't recall at what point the ENU.pak with un-encrypted HTML was introduced, it might have been the initial beta and done as an error, and later patches don't include it.
## Post #107
- Username: ๐MaCkEy๐
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu May 07, 2009 6:05 pm
- Post datetime: 2009-06-23T12:20:13+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from Katadin
>
> I don't recall at what point the ENU.pak with un-encrypted HTML was introduced, it might have been the initial beta and done as an error, and later patches don't include it.

Do you have other html file doesn't encrypted? Could you give me?

Thanks
## Post #108
- Username: Hronos
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jul 20, 2009 2:32 am
- Post datetime: 2009-07-20T03:27:41+00:00
- Post Title: Re: new AION .pak file format.need help!

If there is because the files quest_q1000.html, they are in my view encrypted AES-256. At the exit to get the file in UTF-16 and, accordingly, every second byte = 0. The sequence of these zeros is exactly repeats after 256 bytes. But almost every file in a different way.

Here is an example of decoding the file ab1_1251_dynteleporter_da.html from the Euro version of Aion

```
<!-- Rewrite Dave 31 May -->
<HtmlPages>

  <HtmlPage name="select_quest">
    <Contents cdata="true">
        <html>
        <body>
          <p>Blood for blood! You're [%username], right? I'd recognize a Daeva like you anywhere.</p>
          <p> </p>
          <p>Returning to Primum Fortress, eh?</p>
        </body>
        </html>
    </Contents>
    <npcfuncs>
      <airline_service>Teleport</airline_service>
    </npcfuncs>
  </HtmlPage>

  <HtmlPage name="select1">
    <Contents cdata="true">
        <html>
        <body>
          <p>Azphelumbra, friend.</p>
        </body>
        </html>
    </Contents>
    <Selects>
      <Act href="HACTION_FINISH_DIALOG">"Farewell."</Act>
    </Selects>
  </HtmlPage>

</HtmlPages>
```


P.s. I am sorry for my english
## Post #109
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2009-07-20T19:58:26+00:00
- Post Title: Re: new AION .pak file format.need help!

what key do you use for the decryption?
## Post #110
- Username: ๐MaCkEy๐
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu May 07, 2009 6:05 pm
- Post datetime: 2009-07-22T05:33:40+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from Hronos
>
> If there is because the files quest_q1000.html, they are in my view encrypted AES-256. At the exit to get the file in UTF-16 and, accordingly, every second byte = 0. The sequence of these zeros is exactly repeats after 256 bytes. But almost every file in a different way.

Here is an example of decoding the file ab1_1251_dynteleporter_da.html from the Euro version of Aion
Code: Select all<?xml version="1.0" encoding="UTF-16" ?>
<!-- Rewrite Dave 31 May -->
<HtmlPages>

  <HtmlPage name="select_quest">
    <Contents cdata="true">
        <html>
        <body>
          <p>Blood for blood! You're [%username], right? I'd recognize a Daeva like you anywhere.</p>
          <p> </p>
          <p>Returning to Primum Fortress, eh?</p>
        </body>
        </html>
    </Contents>
    <npcfuncs>
      <airline_service>Teleport</airline_service>
    </npcfuncs>
  </HtmlPage>

  <HtmlPage name="select1">
    <Contents cdata="true">
        <html>
        <body>
          <p>Azphelumbra, friend.</p>
        </body>
        </html>
    </Contents>
    <Selects>
      <Act href="HACTION_FINISH_DIALOG">"Farewell."</Act>
    </Selects>
  </HtmlPage>

</HtmlPages>

P.s. I am sorry for my english

What's the key ? How do you know ? or maybe about the header of the html file that already know the begin of the file.
## Post #111
- Username: Hronos
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jul 20, 2009 2:32 am
- Post datetime: 2009-07-23T21:33:27+00:00
- Post Title: Re: new AION .pak file format.need help!

Key unfortunately not. Have managed to decipher most of the files, but not all.
P.s. I am sorry for my english
## Post #112
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2009-07-23T22:12:35+00:00
- Post Title: Re: new AION .pak file format.need help!

hmmm, im not sure i understand exactly what you are saying, did you find some over way to decrypt the files, without having the decryption key? and would you be willing to share the files?
## Post #113
- Username: Pongkemon
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 11, 2009 10:21 pm
- Post datetime: 2009-07-25T14:21:37+00:00
- Post Title: Re: new AION .pak file format.need help!

Could you please provide the source (or the URL to download it) of the decryption program? It would be very helpful. Thank you.
## Post #114
- Username: Hronos
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jul 20, 2009 2:32 am
- Post datetime: 2009-07-29T08:55:22+00:00
- Post Title: Re: new AION .pak file format.need help!

I want to sell quests alone or a tool for decoding. if interested please write a personal message.
P.s. I am sorry for my english
## Post #115
- Username: kinetikopp
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 03, 2009 2:30 pm
- Post datetime: 2009-08-22T22:56:13+00:00
- Post Title: Re: new AION .pak file format.need help!

Hi I was wondering if anyone has figured anything new out about these .pak files. I have been trying to extract the font files but I am new to this and am having no luck. If anyone wants any files just let me know and I will upload them wherever you want. I have the newest US Aion client. Any information is appreciated. =]
## Post #116
- Username: Pongkemon
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 11, 2009 10:21 pm
- Post datetime: 2009-08-24T02:40:01+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from kinetikopp
>
> Hi I was wondering if anyone has figured anything new out about these .pak files. I have been trying to extract the font files but I am new to this and am having no luck. If anyone wants any files just let me know and I will upload them wherever you want. I have the newest US Aion client. Any information is appreciated. =]

็Hi. Have you tried the Python code to convert pak->zip. It should be in a previously posted thread. There are only 7 pages to search.
## Post #117
- Username: mdurrant
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Sep 07, 2009 5:21 pm
- Post datetime: 2009-09-07T09:44:58+00:00
- Post Title: Re: new AION .pak file format.need help!

Did anyone ever figure out a way to decode the .html quest dialog?

I have everything extracted and decoded perfectly (thanks to the awesome people in this thread) except for that.
## Post #118
- Username: Hronos
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jul 20, 2009 2:32 am
- Post datetime: 2009-09-15T12:42:07+00:00
- Post Title: Re: new AION .pak file format.need help!

sometime .html quest dialogs will be decoded completely. now I know only my version of decryption...
## Post #119
- Username: xenofixus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 28, 2009 2:56 am
- Post datetime: 2009-09-27T21:28:42+00:00
- Post Title: Re: new AION .pak file format.need help!

I was wondering if someone could possibly give me some information on why the pak2zip.py does not work on all the .pak files.  I was told by one person that it does not work on .pak files containing language files.  I don't really see why this would be a problem but I would appreciate an explanation about the limitations of it and perhaps a way to get the script working again, or an easy to use command line alternative.

For an example of one it does not work with, any of the .paks in \Aion\L10N\ folder (along with many others in the data folders) do not work.

I am using Aion 1.5.0.7, the latest release of the US retail.


Thanks in advance for any replies.
## Post #120
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2009-09-28T00:01:19+00:00
- Post Title: Re: new AION .pak file format.need help!

Yes it does, there was a newer version posted that fixed the bugs regarding those files.
## Post #121
- Username: xenofixus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 28, 2009 2:56 am
- Post datetime: 2009-09-28T00:33:30+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from xenofixus
>
> I was wondering if someone could possibly give me some information on why the pak2zip.py does not work on all the .pak files.  I was told by one person that it does not work on .pak files containing language files.  I don't really see why this would be a problem but I would appreciate an explanation about the limitations of it and perhaps a way to get the script working again, or an easy to use command line alternative.

> Reply from Rick
>
> Yes it does, there was a newer version posted that fixed the bugs regarding those files.

I am using the version posted on page 7 (version 0.4) and still having this problem.

I am using python26 (also tested with 25) and version 0.4 of roxfan's script.
I am running on windows 7.
My Aion is version 1.5.0.7 of the US retail.

It works for some files but not all.  An example file it does not work with is \Aion\L10N\1_enu.pak
## Post #122
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2009-09-28T01:06:13+00:00
- Post Title: Re: new AION .pak file format.need help!

0.4 works fine for me on 1_enu.pak.
## Post #123
- Username: xenofixus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 28, 2009 2:56 am
- Post datetime: 2009-09-28T01:24:38+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from Rick
>
> 0.4 works fine for me on 1_enu.pak.
Is the 0.4 on page 7 not right? (I redownloaded it)


Also, I am using the .py file using this .bat I wrote (for easy drag-n-drop)

```
set _=%_:.pak=.zip%
cd /d %0\..
"C:\Program Files\Python26\pythonw.exe" "pak2zip.py" %1 %_%
```

however I still get the same problem when using it via an administrator command prompt.

Would you mind throwing up what you have for 0.4?  Maybe I am missing something obvious here.

I also know someone else having the exact same problem as me using version 0.4 from page 7.
If it matters, the file I get is approx 44 KB and while I can browse it with winrar (7zip gives me an error) extracting anything will give me an archive corrupted error.
## Post #124
- Username: Hronos
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jul 20, 2009 2:32 am
- Post datetime: 2009-09-30T00:31:24+00:00
- Post Title: Re: new AION .pak file format.need help!

I have the same Windows 7 and pak2zip works correctly with the file 1_enu.pak from client version 1.5.0.7
Only the command line is not written the path to your python, only "pak2zip.py 1_enu.pak 1_enu.zip"
## Post #125
- Username: xenofixus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 28, 2009 2:56 am
- Post datetime: 2009-09-30T02:29:10+00:00
- Post Title: Re: new AION .pak file format.need help!

I really have no idea, its kind of annoying. >>

EDIT: I got it working, need to run it with Python.exe rather than Pythonw.exe

Rather simple mistake.
## Post #126
- Username: Hronos
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jul 20, 2009 2:32 am
- Post datetime: 2009-10-02T17:30:12+00:00
- Post Title: Re: new AION .pak file format.need help!

The contents of this post was deleted because of possible forum rules violation.
## Post #127
- Username: dabosh
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 03, 2009 7:18 am
- Post datetime: 2009-10-05T21:39:07+00:00
- Post Title: Re: new AION .pak file format.need help!

Hi!

I remeber in la2 there was file called systemmsg-e.dat and it got all data about how and where to show dmg/buf/dots in your chat window. So i was thinking about the same in aion, i rly hate those long lines and i want to make them more easy readable, but the problem is i don't know how it's called in aion?? Hope to see this thread updated a lot more.
## Post #128
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2009-10-05T22:04:40+00:00
- Post Title: Re: new AION .pak file format.need help!

It's probably in client_strings.xml.
## Post #129
- Username: dabosh
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 03, 2009 7:18 am
- Post datetime: 2009-10-06T21:30:09+00:00
- Post Title: Re: new AION .pak file format.need help!

And if i can ask one more question, what's the best soft for openening .xml files? I have tryed Gibbed.Aion.ConvertXml after that opening with notepad but no changes. And guys, you are doing a great job, but if you could add simple readfirst.txt file, it would be a lot easier for you guys answering my question, and for us (noob users) aswell
## Post #130
- Username: Spamhugger
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 29, 2009 8:52 am
- Post datetime: 2009-11-29T20:32:37+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from caspersus
>
> Katadin wrote:caspersus wrote:A small teaser before I go to bed 



How did you load the texture?  When I try it gives an error it can't load it (but seems to open fine in various .dds viewers).

Copy the textures to same folder as the mesh and convert em to .jpg format  If you want transparency, save .dds as .tga

How did you pull this off? I'm using 3D Object Converter 4.40 and I can't get the texture to load. And I've tried it as a DDS, uncompressed DDS, JPG, TGA, and BMP - all in the same directory as the mesh.

Unless there is a specific button in 3D Objector Converter I am failing to see, but I'm pretty sure I tried pushing everything.
## Post #131
- Username: robbyjenson
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Dec 10, 2009 12:11 pm
- Post datetime: 2009-12-10T23:23:50+00:00
- Post Title: Re: new AION .pak file format.need help!

I hate to bump a thread that hasn't been replied to in weeks, but I do have a question about the extracted files.

Say I want to convert them to another format that is more compatible with standard 3D modeling software (such as 3DS Max, Maya). I've done a CGF to 3DS conversion, but when I try to load a TGA texture, which looks excellent on the CGF, it looks messed up when applied to the 3DS file.

Does anyone know a solution to this problem?
## Post #132
- Username: Shira
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 21, 2017 5:58 am
- Post datetime: 2017-11-22T22:07:47+00:00
- Post Title: Re: new AION .pak file format.need help!

> Reply from Rick
>
> nicoli_s wrote:any chance you'd be willing to share the format specification for it? i'm pretty close as it is, just not sure what the 03, 02, bytes dohttp://svn.slurm.us/public/aion/trunk/

Is this still available somewhere else?
