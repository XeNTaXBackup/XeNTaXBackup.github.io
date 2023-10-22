## Post #1
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2020-09-04T13:45:51+00:00
- Post Title: Project Sekai .unity3d

Hi, 
Recently the OBT for Project Sekai came out and I tried to look at the files but seems like they're compressed or something? (Not surprised)

I was hoping maybe somebody could take a look at these and make figure it out! 

Some samples:

```
https://mega.nz/file/bo83SKiB#ET5PEa11X77oJx82TmDlRSyi-JhRdFnxnSX415CjSbM
```


Thanks!
## Post #2
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2020-09-04T13:59:49+00:00
- Post Title: Project Sekai .unity3d

files are xor, put this py script in the "files" folder of your data and it'll fix the xor stuff on every file that needs it automatically, it'll take only a few seconds
run
 python decrypt.py

```

for root, _, files in os.walk('.'):
    for file_name in files:
        with open(os.path.join(root, file_name), 'br+') as f:
            data = f.read()
            if (data[:4] == b'\x20\x00\x00\x00'):
                data = data[4:]
            elif (data[:4] == b'\x10\x00\x00\x00'):
                data = data[4:]
                header = bytes(a ^ b for a, b in zip(data[:128], (b'\xff'*5 + b'\x00'*3)*16))
                data = header + data[128:]
            f.seek(0)
            f.write(data)
            f.truncate()

```

This script was made by qwewqa on discord, not me, credit them!
## Post #3
- Username: luiz7429
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jun 16, 2017 12:26 pm
- Post datetime: 2020-09-17T22:02:01+00:00
- Post Title: Project Sekai .unity3d

how we use this script?
i only know how use noesis and some other simple extractors..
## Post #4
- Username: oreki48
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon May 14, 2018 2:10 am
- Post datetime: 2020-10-01T06:15:32+00:00
- Post Title: Project Sekai .unity3d

you must instal phyton for using that script
## Post #5
- Username: luiz7429
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jun 16, 2017 12:26 pm
- Post datetime: 2020-10-04T23:37:44+00:00
- Post Title: Project Sekai .unity3d

so..how i do that?
> Reply from oreki48 ↑Thu Oct 01, 2020 2:15 pm at Thu Oct 01, 2020 2:15 pm
>
> 
you must instal phyton for using that script
## Post #6
- Username: A EON
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Aug 08, 2020 7:12 pm
- Post datetime: 2020-10-12T08:36:32+00:00
- Post Title: Project Sekai .unity3d

Could you please explain in more detail what tools should we use? And how do you do it?

Via google translate. Sorry because my English is bad

Thanks!
## Post #7
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2020-10-14T03:40:09+00:00
- Post Title: Project Sekai .unity3d

File "E:\data\0aa3\1.py", line 3
    for root, _, files in os.walk('.')
                                     ^
SyntaxError: invalid syntax
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-10-15T07:57:26+00:00
- Post Title: Project Sekai .unity3d

here is bms script translation of that python script so you don't
have to worry about installing python or anything to unxor the files.   
*updated Oct 15, 2020 for completeness*


 ProjectSekai_unity3d_unxor.zip
(572 Bytes) Downloaded 372 times
## Post #9
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2020-10-15T08:35:24+00:00
- Post Title: Project Sekai .unity3d

Hey,

i have a question about unity3D.
Have many Game Apps which use unity.
How can import this unity3D Files maybe into 3ds max or other 3D Programs?
## Post #10
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2020-10-15T08:40:51+00:00
- Post Title: Project Sekai .unity3d

> Reply from Acewell ↑Thu Oct 15, 2020 3:57 pm at Thu Oct 15, 2020 3:57 pm
>
> 
here is bms script translation of that python script so you don't
have to worry about installing python or anything to unxor the files.   
ProjectSekai_unity3d_unxor.zip

THANKS MAN
i still cant believe they put actual model and dance motions in the game in stead of using rendered clip , imma gonna DL everything from it now xd
## Post #11
- Username: A EON
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Aug 08, 2020 7:12 pm
- Post datetime: 2020-10-15T08:47:51+00:00
- Post Title: Project Sekai .unity3d

> Reply from Acewell ↑Thu Oct 15, 2020 3:57 pm at Thu Oct 15, 2020 3:57 pm
>
> 
here is bms script translation of that python script so you don't
have to worry about installing python or anything to unxor the files.   
ProjectSekai_unity3d_unxor.zip

39 Senpai~
## Post #12
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2020-10-16T08:20:52+00:00
- Post Title: Project Sekai .unity3d

> Reply from KingJuls ↑Thu Oct 15, 2020 4:35 pm at Thu Oct 15, 2020 4:35 pm
>
> 
Hey,

i have a question about unity3D.
Have many Game Apps which use unity.
How can import this unity3D Files maybe into 3ds max or other 3D Programs?

dump
## Post #13
- Username: XxxfallingstarxxX
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 22, 2020 6:34 am
- Post datetime: 2020-10-22T08:59:05+00:00
- Post Title: Project Sekai .unity3d

> Reply from anime663 ↑Fri Sep 04, 2020 9:45 pm at Fri Sep 04, 2020 9:45 pm
>
> 
Hi, 
Recently the OBT for Project Sekai came out and I tried to look at the files but seems like they're compressed or something? (Not surprised)

I was hoping maybe somebody could take a look at these and make figure it out! 

Some samples:
Code: Select allhttps://mega.nz/file/bo83SKiB#ET5PEa11X77oJx82TmDlRSyi-JhRdFnxnSX415CjSbM

Thanks!
can u explain how u got these files i have been trying to get these files from assets data folder but im failing miserably
i would really appreaciate all the help u can provide ;-;
## Post #14
- Username: A EON
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Aug 08, 2020 7:12 pm
- Post datetime: 2020-11-04T11:33:38+00:00
- Post Title: Project Sekai .unity3d

is there no way to extract [AudioClip] from this game?
I want the BGM, and other music of course


then between [body] and [face] cannot be properly merged even though it has been [merge]
how do i fix it?

sorry for my bad english
via google translate
## Post #15
- Username: A EON
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Aug 08, 2020 7:12 pm
- Post datetime: 2020-12-04T16:04:58+00:00
- Post Title: Project Sekai .unity3d

> Reply from Acewell ↑Thu Oct 15, 2020 3:57 pm at Thu Oct 15, 2020 3:57 pm
>
> 
here is bms script translation of that python script so you don't
have to worry about installing python or anything to unxor the files.   
*updated Oct 15, 2020 for completeness*
ProjectSekai_unity3d_unxor.zip

I got a way to extract AudioClip from this game, a Python script by @DNARoma -san from the discord forum. Acewell-san could you please translate this into BMS Script?

or anyone who can, I would really appreciate and thank you.

I attach the related file here: [https://mega.nz/folder/T1gSnYoa#V7eAlLcrqMDe8bKc-q9KQQ](https://mega.nz/folder/T1gSnYoa#V7eAlLcrqMDe8bKc-q9KQQ)

via google translate.
sorry for my bad english




[solved. case is closed]
[acb [Python script][DNARoma].rar](https://xentaxbackup.github.io/file/19134_acb [Python script][DNARoma].rar)
## Post #16
- Username: LeoNeed
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 22, 2020 12:00 am
- Post datetime: 2020-12-21T16:12:21+00:00
- Post Title: Re: Project Sekai .unity3d

The .acb file can be imported as a foobar2000.
download foobar2000 and plugin.

[https://www.foobar2000.org/download](https://www.foobar2000.org/download)

[https://www.foobar2000.org/components/v ... _vgmstream](https://www.foobar2000.org/components/view/foo_input_vgmstream)

run foobar2000 and go to File > Preferences > Compoments > Install... > foo_input_vgmstream.fb2k-component

and done!

drag and drop acb files.

How to convert

Right Click > Convert > Quick convert or something > set wav or something (also you need to install convert plugins) > Done!
## Post #17
- Username: A EON
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Aug 08, 2020 7:12 pm
- Post datetime: 2020-12-23T03:53:16+00:00
- Post Title: Re: Project Sekai .unity3d

> Reply from LeoNeed ↑Tue Dec 22, 2020 12:12 am at Tue Dec 22, 2020 12:12 am
>
> 

The .acb file can be imported as a foobar2000.
download foobar2000 and plugin.

https://www.foobar2000.org/download

https://www.foobar2000.org/components/v ... _vgmstream

run foobar2000 and go to File > Preferences > Compoments > Install... > foo_input_vgmstream.fb2k-component

and done!

drag and drop acb files.

How to convert

Right Click > Convert > Quick convert or something > set wav or something (also you need to install convert plugins) > Done!

Thank you very much! I will try it soon


edit :
yes...
finally i can ... i can get it.

thank you! Thank you very much!

the method you provide is clearly much simpler than what I have attempted so far.

Once again, thank you so much!


via google translate
sorry for my bad english
## Post #18
- Username: LeoNeed
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 22, 2020 12:00 am
- Post datetime: 2020-12-23T15:42:05+00:00
- Post Title: Re: Project Sekai .unity3d

change acb.bytes to acb.
It's Simple.
## Post #19
- Username: A EON
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Aug 08, 2020 7:12 pm
- Post datetime: 2020-12-23T17:34:43+00:00
- Post Title: Re: Project Sekai .unity3d

> Reply from LeoNeed ↑Wed Dec 23, 2020 11:42 pm at Wed Dec 23, 2020 11:42 pm
>
> 
change acb.bytes to acb.
It's Simple.

it works! Thank you very much
[foo1.png](https://xentaxbackup.github.io/file/19225_foo1.png)
## Post #20
- Username: LeoNeed
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 22, 2020 12:00 am
- Post datetime: 2020-12-24T07:18:56+00:00
- Post Title: Re: Project Sekai .unity3d

You can also import the .acb file of BanG Dream!
## Post #21
- Username: A EON
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Aug 08, 2020 7:12 pm
- Post datetime: 2020-12-24T08:31:56+00:00
- Post Title: Re: Project Sekai .unity3d

> Reply from LeoNeed ↑Thu Dec 24, 2020 3:18 pm at Thu Dec 24, 2020 3:18 pm
>
> 
You can also import the .acb file of BanG Dream!

Yes, I know that, but I didn't play the game and wasn't really interested, but since you've covered it maybe I'll take a look later.


Via google translate
## Post #22
- Username: souleaterLC
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Oct 29, 2020 11:01 pm
- Post datetime: 2022-03-18T00:07:32+00:00
- Post Title: Re: Project Sekai .unity3d

> Reply from Makoto ↑Fri Sep 04, 2020 9:59 pm at Fri Sep 04, 2020 9:59 pm
>
> 
files are xor, put this py script in the "files" folder of your data and it'll fix the xor stuff on every file that needs it automatically, it'll take only a few seconds
run
 python decrypt.py
Code: Select allimport os

for root, _, files in os.walk('.'):
    for file_name in files:
        with open(os.path.join(root, file_name), 'br+') as f:
            data = f.read()
            if (data[:4] == b'\x20\x00\x00\x00'):
                data = data[4:]
            elif (data[:4] == b'\x10\x00\x00\x00'):
                data = data[4:]
                header = bytes(a ^ b for a, b in zip(data[:128], (b'\xff'*5 + b'\x00'*3)*16))
                data = header + data[128:]
            f.seek(0)
            f.write(data)
            f.truncate()

This script was made by qwewqa on discord, not me, credit them!

hi is there a way to encrypt the files again? im trying to edit textures in game but when i replaced the file with the decrypted ones in the gamme it stucks, thats why i think it needs to be encrypted again to be able to mod it
## Post #23
- Username: Canelumino
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 14, 2022 3:23 am
- Post datetime: 2022-04-18T15:33:23+00:00
- Post Title: Re: Project Sekai .unity3d

can someone please explain how to extract animations and models using these tools? i'm a bit confused...
## Post #24
- Username: Drax Fynwick
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 26, 2022 3:16 pm
- Post datetime: 2022-08-26T06:17:42+00:00
- Post Title: Re: Project Sekai .unity3d

Does anyone have a new decryption script for Project Sekai? the old script didn't work.
## Post #25
- Username: MrYouKnowItAll
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 27, 2022 12:35 pm
- Post datetime: 2022-08-27T04:51:32+00:00
- Post Title: Re: Project Sekai .unity3d

Someone already ripped everything to the latest version but not all fbx are exported correctly...

[https://pjsek.ai/assets](https://pjsek.ai/assets)

Also he kept all the versions of the assets: [https://pjsek.ai/assets/ondemand/live_p ... acter/body](https://pjsek.ai/assets/ondemand/live_pv/model/character/body)

i had to use this form to download the assets from their backblaze server where they stored the assets with their correct asset version:

[https://asset-bundles.pjsek.ai/file/pjs ... ve_pv/PATH](https://asset-bundles.pjsek.ai/file/pjsekai-asset-bundles/VERSION/live_pv/PATH)

Just form the download link from this pjsek.ai site for eg:


> https://asset-bundles.pjsek.ai/file/pjs ... 3/ladies_l

Some of them are stripped with 0.0.0 so get the apk version which has the correct unity version number and type the version so that it will load the stripped version of the assets
## Post #26
- Username: Drax Fynwick
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 26, 2022 3:16 pm
- Post datetime: 2022-08-27T15:13:43+00:00
- Post Title: Re: Project Sekai .unity3d

the current version of Project Sekai is Unity Ver 2021.3.1f1
I don't know pjsek.ai has .anim file.
## Post #27
- Username: Drax Fynwick
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 26, 2022 3:16 pm
- Post datetime: 2022-08-28T02:47:03+00:00
- Post Title: Re: Project Sekai .unity3d

all the Project Sekai assets files won't load in uTinyRipper, that's why I can't rip the animation and also the facial data animation.
## Post #28
- Username: MrYouKnowItAll
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 27, 2022 12:35 pm
- Post datetime: 2022-08-28T06:45:44+00:00
- Post Title: Re: Project Sekai .unity3d

use assetripper, utinyripper doesn't load unity 2020 or 2021 assets. 

[https://github.com/ds5678/AssetRipper](https://github.com/ds5678/AssetRipper)

Also utinyripper is outdated
## Post #29
- Username: Drax Fynwick
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 26, 2022 3:16 pm
- Post datetime: 2022-08-28T11:57:58+00:00
- Post Title: Re: Project Sekai .unity3d

it exported as an unreadable file.

[https://imgur.com/kt1QVl5](https://imgur.com/kt1QVl5)
## Post #30
- Username: MrYouKnowItAll
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 27, 2022 12:35 pm
- Post datetime: 2022-08-29T04:19:31+00:00
- Post Title: Re: Project Sekai .unity3d

i'm guessing some of them are stripped...
## Post #31
- Username: XtraK
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jun 25, 2023 2:21 pm
- Post datetime: 2023-06-30T13:49:25+00:00
- Post Title: Re: Project Sekai .unity3d

is there no update on the script?

or is there a new method to explore sekai assets?
## Post #32
- Username: jomin398
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 30, 2022 10:27 am
- Post datetime: 2023-10-11T23:46:54+00:00
- Post Title: Re: Project Sekai .unity3d

Newest version is not working with xor script.
Folder structure is same but some byteData is changed.
(I don't know which is)
Need to change script code.
