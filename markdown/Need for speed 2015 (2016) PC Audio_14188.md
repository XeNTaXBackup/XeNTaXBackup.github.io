## Post #1
- Username: Svennixx
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Dec 17, 2014 5:52 am
- Post datetime: 2016-04-04T13:25:02+00:00
- Post Title: Need for speed 2015 (2016) PC Audio

Hello,

I tried to extract the sounds of nfs 2016 but im kinda stuck. I managed to extract chunkaudio.sb but it just gives me a bunch of random files that have no extensions.
I tried looking up Bf4 and Battlefront 3 audio extraction tools but can't really find any tools or methods.
Could anyone help or send me into the right direction?
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-04T16:15:19+00:00
- Post Title: Need for speed 2015 (2016) PC Audio

BF4 scripts should do that.

Why can't you use it?
## Post #3
- Username: Svennixx
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Dec 17, 2014 5:52 am
- Post datetime: 2016-04-04T16:31:36+00:00
- Post Title: Need for speed 2015 (2016) PC Audio

> Reply from daemon1
>
> BF4 scripts should do that.

Why can't you use it?
I tried to use your scripts from swbf but i keep getting errors when i run it. I tried modifying it but can't seem to fix it.
Errors: 
[http://imgur.com/ZKIXJCJ](http://imgur.com/ZKIXJCJ)
## Post #4
- Username: Svennixx
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Dec 17, 2014 5:52 am
- Post datetime: 2016-04-04T17:03:50+00:00
- Post Title: Need for speed 2015 (2016) PC Audio

Never mind. Got bf4 scripts working now and managed to get the audio files!
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-04T17:09:35+00:00
- Post Title: Need for speed 2015 (2016) PC Audio

I told you BF4 will work 

SWBF has different archive structure. That's why its only for SWBF
## Post #6
- Username: Svennixx
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Dec 17, 2014 5:52 am
- Post datetime: 2016-04-04T17:39:06+00:00
- Post Title: Need for speed 2015 (2016) PC Audio

> Reply from daemon1
>
> I told you BF4 will work 

SWBF has different archive structure. That's why its only for SWBF
The only sounds i need are not getting decoded  I see their name being printed but don't see them back in the extracted directory.
No errors reported with those files either.
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-04T17:49:30+00:00
- Post Title: Need for speed 2015 (2016) PC Audio

they must be in another codec. Can you give me exact version of script youre using?

even better, can you give me sample file thats not decoded?
## Post #8
- Username: Svennixx
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Dec 17, 2014 5:52 am
- Post datetime: 2016-04-04T17:58:29+00:00
- Post Title: Need for speed 2015 (2016) PC Audio

Uhm can't find a version but it dates back from 8 of april 2015.
These are some of the files that i can't decode:
[https://mega.nz/#!rM41mYYJ!xF3N08ftjIDW ... uxKmtLEdak](https://mega.nz/#!rM41mYYJ!xF3N08ftjIDWL6dI-OrR5J2YJbVPXhK9HuxKmtLEdak)
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-04T18:06:27+00:00
- Post Title: Need for speed 2015 (2016) PC Audio

i have a feeling these may be GIN files like the ones I decoded for other NFS games...
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-04T18:46:24+00:00
- Post Title: Need for speed 2015 (2016) PC Audio

do you have this chunk?

0116af7d1665232ea8d9aa1ba61c24cc

send it
## Post #11
- Username: Svennixx
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Dec 17, 2014 5:52 am
- Post datetime: 2016-04-04T19:48:44+00:00
- Post Title: Need for speed 2015 (2016) PC Audio

Yeah i have it.
[https://mega.nz/#!qU4l0TIb!AHLEpcBoV8M2 ... xjM9cvsae0](https://mega.nz/#!qU4l0TIb!AHLEpcBoV8M28xlPX4E1-k8JxeOxSdDMgxjM9cvsae0)
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-04T19:55:52+00:00
- Post Title: Need for speed 2015 (2016) PC Audio

just as I thought. Script can't decode them because its special format for engine sounds

you my tool [viewtopic.php?f=17&t=13430](http://forum.xentax.com/viewtopic.php?f=17&t=13430) to decode them
## Post #13
- Username: Svennixx
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Dec 17, 2014 5:52 am
- Post datetime: 2016-04-04T20:00:42+00:00
- Post Title: Need for speed 2015 (2016) PC Audio

> Reply from daemon1
>
> just as I thought. Script can't decode them because its special format for engine sounds

you my tool viewtopic.php?f=17&t=13430 to decode them
Ok so the NFS_abk_decode crashes when i try it but the gin one decodes it but the .wav that is made is damaged and cannot be played.
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-04T20:03:44+00:00
- Post Title: Need for speed 2015 (2016) PC Audio

> Reply from Svennixx
>
> daemon1 wrote:just as I thought. Script can't decode them because its special format for engine sounds

you my tool viewtopic.php?f=17&t=13430 to decode them
Ok so the NFS_abk_decode crashes when i try it but the gin one decodes it but the .wav that is made is damaged and cannot be played.

use GIN tool on chunk, not ebx file
## Post #15
- Username: Svennixx
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Dec 17, 2014 5:52 am
- Post datetime: 2016-04-04T20:10:21+00:00
- Post Title: Need for speed 2015 (2016) PC Audio

> Reply from daemon1
>
> Svennixx wrote:daemon1 wrote:just as I thought. Script can't decode them because its special format for engine sounds

you my tool viewtopic.php?f=17&t=13430 to decode them
Ok so the NFS_abk_decode crashes when i try it but the gin one decodes it but the .wav that is made is damaged and cannot be played.

use GIN tool on chunk, not ebx file
Awesome! Thanks for helping me out dude!
Last question how do i find out what chunk a .ebx file is? Will be easier finding out which sounds i want and should convert.
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-05T15:51:10+00:00
- Post Title: Re: Need for speed 2015 (2016) PC Audio

Find decode function

```
        if not self.prim.desc.name=="SoundWaveAsset": return

```

and comment the check

```
#        if not self.prim.desc.name=="SoundWaveAsset": return

```


then go a little down and after this line

```

```


add this

```

            print hexlify(chnk.ChunkId)
            return

```


Then if you delete all EBX files except those you need, you'll get a list of chunk names to decode
## Post #17
- Username: Svennixx
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Dec 17, 2014 5:52 am
- Post datetime: 2016-04-05T18:32:19+00:00
- Post Title: Re: Need for speed 2015 (2016) PC Audio

It doesn't want to print there. Not even print "test".

```
        #if not self.prim.desc.name=="SoundWaveAsset": return

        histogram=dict() #count the number of times each chunk is used by a variation to obtain the right index

        Chunks=[]
        for i in self.prim.get("$::SoundDataAsset/Chunks::array").fields:
            chnk=Stub()
            Chunks.append(chnk)
            chnk.ChunkId=i.value.get("ChunkId").value
            print hexlify(chnk.ChunkId)
            return
            
            if ChunkIdObfuscation: chnk.ChunkId="".join([chnk.ChunkId[permute] for permute in obfuscationPermutation])
                
            chnk.ChunkSize=i.value.get("ChunkSize").value
```
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-05T18:36:39+00:00
- Post Title: Re: Need for speed 2015 (2016) PC Audio

so what do you get in output? only ebx names?
## Post #19
- Username: Svennixx
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Dec 17, 2014 5:52 am
- Post datetime: 2016-04-05T18:38:47+00:00
- Post Title: Re: Need for speed 2015 (2016) PC Audio

> Reply from daemon1
>
> so what do you get in output? only ebx names?

did you comment the line as i said ?
Yeah i only get .ebx names like so:

```
toyota_supra_sz-r_overrun.ebx
toyota_supra_sz-r_playerracevehicleaudio.ebx
toyota_supra_sz-r_transmission.ebx
toyota_supra_sz-r_accel_eng_pitched_noise.ebx
toyota_supra_sz-r_accel_eng_pitched_tone.ebx
toyota_supra_sz-r_accel_exh_pitched_noise.ebx
toyota_supra_sz-r_accel_exh_pitched_tone.ebx
toyota_supra_sz-r_decel2_eng_pitched_noise.ebx
toyota_supra_sz-r_decel2_eng_pitched_tone.ebx
toyota_supra_sz-r_decel2_exh_pitched_noise.ebx
toyota_supra_sz-r_decel2_exh_pitched_tone.ebx
toyota_supra_sz-r_idle_eng.ebx
toyota_supra_sz-r_idle_exh.ebx
toyota_supra_sz-r_ignition.ebx
toyota_supra_sz-r_shutdown_eng.ebx
toyota_supra_sz-r_shutdown_exh.ebx
```


I put the snippet of the script that needed to change up at my other reply
## Post #20
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-05T18:42:47+00:00
- Post Title: Re: Need for speed 2015 (2016) PC Audio

these ebx's are not the same as the ones you sent me yesterday

try with those accel & decel
## Post #21
- Username: Svennixx
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Dec 17, 2014 5:52 am
- Post datetime: 2016-04-05T18:45:35+00:00
- Post Title: Re: Need for speed 2015 (2016) PC Audio

```
nissan_180sx_accel_eng_02_rx_tone.ebx
nissan_180sx_accel_exh_02_dyn_tone.ebx
nissan_180sx_accel_int_03_dyn_noise.ebx
nissan_180sx_accel_int_03_dyn_tone.ebx
nissan_180sx_decel_eng_rx_noise.ebx
nissan_180sx_decel_eng_rx_tone.ebx
nissan_180sx_decel_exh_rx_noise.ebx
nissan_180sx_decel_exh_rx_tone.ebx
```

Same thing... It's weird that it doesn't print in that for loop. I'm not familiair with python but I use c# everyday. So idk if its a python thing or just something wrong in my code.
## Post #22
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-05T19:26:35+00:00
- Post Title: Re: Need for speed 2015 (2016) PC Audio

looks like the script is not changed at all. Do you save it before running? Try restarting python, deleting PYC files if there are any
## Post #23
- Username: ehwasilii
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 12, 2017 9:11 pm
- Post datetime: 2017-06-29T06:15:43+00:00
- Post Title: Re: Need for speed 2015 (2016) PC Audio

> Reply from daemon1
>
> looks like the script is not changed at all. Do you save it before running? Try restarting python, deleting PYC files if there are any
A small bump, if I may.

I'm trying to do exactly the same: extract engine sounds. I've come to the point, where I successfully converted chunk you gave with your tool.
Following your instructions and editing fb3decoder script to find all the chunks I need, I'm getting an error if I comment out check (if not self.prim.desc.name=="SoundWaveAsset": return):

```
  File "C:\Python27\fb3decoder\fb3decoder.py", line 569, in <module>
    main()
  File "C:\Python27\fb3decoder\fb3decoder.py", line 566, in main
    dbx.decode()
  File "C:\Python27\fb3decoder\fb3decoder.py", line 426, in decode
    for i in self.prim.get("$::SoundDataAsset/Chunks::array").fields:
  File "C:\Python27\fb3decoder\fb3decoder.py", line 197, in get
    raise Exception("Could not find complex with name: "+str(e)+"\nFull path: "+name+"\nFilename: "+self.dbx.trueFilename)
Exception: Could not find complex with name: $::SoundDataAsset
Full path: $::SoundDataAsset/Chunks::array
Filename: Audio/Cars/CarEngine/LAMBORGHINI_AVENTADOR/Lamborghini_Aventador_Transmission
```


not sure what's next.
upd: everything else in ebx is deleted

ps: pretty much thank you for all the works and tools you've done.
## Post #24
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-06-29T12:07:30+00:00
- Post Title: Re: Need for speed 2015 (2016) PC Audio

unfortunately I don't remember much about this now.
## Post #25
- Username: soulweaver
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 10, 2017 8:41 am
- Post datetime: 2017-09-10T05:34:15+00:00
- Post Title: Re: Need for speed 2015 (2016) PC Audio

Been messing around with these, haven't gotten far because it's not my forte. For the car audio fb3decoder is only picking up sounds in the 'renders' folder, I'm assuming everything else is able to be decoded with the GIN tool, but I don't know how to get the chunk id to attempt. 

I'm not a hex genius but the files that fb3decoder can detect contain 'SoundWaveAsset' and the others do not, and their file structure looks very different. 
[https://mega.nz/#F!W4cQlYKT!jHe3Lyf3V0OWwUjJ_34KRg](https://mega.nz/#F!W4cQlYKT!jHe3Lyf3V0OWwUjJ_34KRg) here's a link to the full folder of a car if somebody smart wants to take a look at the differences.

Edit: Did some more digging, the some other car sounds come under 'OctaneAsset' and I've been able to get the chunk ids using the code already there just with a simple if statement. Going to see if I can get it to open with the Gin decoder now and rename when it's done. I'm no python genius either

Edit 2: Well it half worked. Some files that contain the 'OctanceAsset' are not decoded by GIN, but it just skips over them so no biggie, the main problem is that on some chunks the tool hangs, this is the first one it hits '144837870e001922903387d43fb710d2' which is 'Audio/Cars/CarEngine/Dodge_Viper_SRT/OctaneData/Dodge_Viper_Accel_ENG_Noise'. I'm no python genius and I can't figure out how to timeout a subprocess on 2.7 properly to just skip over it as a soft fix. Instead I'll just show you my edits on how to get the chunk id for those files.

```
if not self.prim.desc.name=="SoundWaveAsset": return
```

changes to: there is probably a better way for this but whatever

```
            if not self.prim.desc.name=="OctaneAsset": return
```


```
chnk.ChunkId=i.value.get("ChunkId").value
```

underneath this add:

```
                print self.trueFilename+ "   |   "+hexlify(chnk.ChunkId)
```


That will output the chunk id as well as the file it corresponds too.
## Post #26
- Username: soulweaver
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 10, 2017 8:41 am
- Post datetime: 2017-09-10T09:18:42+00:00
- Post Title: Re: Need for speed 2015 (2016) PC Audio

Decoded gin files seem to have some distortion or something similar behind them. Hard to explain what the sound actually is, I guess kind of like a repeating sound or like sound lag. [https://mega.nz/#F!n4ME2ZSL!AjEjT9AAFUZ8tF1_I2LCZg](https://mega.nz/#F!n4ME2ZSL!AjEjT9AAFUZ8tF1_I2LCZg) contains an example of the distortion on the car sounds, and there are also other sounds decoded by the tool normally alongside for comparison too.
