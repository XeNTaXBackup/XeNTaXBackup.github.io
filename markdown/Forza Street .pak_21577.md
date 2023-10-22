## Post #1
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2020-01-05T20:02:10+00:00
- Post Title: Forza Street .pak

Hi! I found and extracted obb of Forza Street but I have problem with .pak file. Script for Quick BMS didn't work ([https://imgur.com/a/A54ZxeM](https://imgur.com/a/A54ZxeM) same error with all codes). I tried with unpacker from Unreal Engine but didn't work. Anybody know how to open this archive? 
Here is this .pak file: [https://mega.nz/#!6l1FXApR!KenHMBBYOcZn ... G3J3GaYaS4](https://mega.nz/#!6l1FXApR!KenHMBBYOcZn77hcTzyGfRcFlzq_EjkFOG3J3GaYaS4)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-01-09T10:43:26+00:00
- Post Title: Forza Street .pak

The data as well as its directories are encrypted. Nothing can be done without the encryption key.
## Post #3
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2020-01-11T12:11:55+00:00
- Post Title: Forza Street .pak

> Reply from Bigchillghost ↑Thu Jan 09, 2020 6:43 pm at Thu Jan 09, 2020 6:43 pm
>
> 
The data as well as its directories are encrypted. Nothing can be done without the encryption key.

Any chance to generate or get this key?
## Post #4
- Username: eyewee
- Rank: n00b
- Number of posts: 14
- Joined date: Sat May 12, 2018 2:46 am
- Post datetime: 2020-01-28T10:49:06+00:00
- Post Title: Forza Street .pak

What are wishing to extract actually?
## Post #5
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2020-01-28T22:15:53+00:00
- Post Title: Forza Street .pak

> Reply from eyewee ↑Tue Jan 28, 2020 6:49 pm at Tue Jan 28, 2020 6:49 pm
>
> 

3D models of cars.
## Post #6
- Username: eyewee
- Rank: n00b
- Number of posts: 14
- Joined date: Sat May 12, 2018 2:46 am
- Post datetime: 2020-02-04T13:27:56+00:00
- Post Title: Forza Street .pak

> Reply from zimex25 ↑Wed Jan 29, 2020 6:15 am at Wed Jan 29, 2020 6:15 am
>
> 

Well you can go to gamemodels to get these cars, and in better quality, as I know, there's no exclusive cars in forza street
## Post #7
- Username: Doliman100
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Oct 28, 2021 4:17 pm
- Post datetime: 2023-09-17T18:48:23+00:00
- Post Title: Forza Street .pak

If you are talking about Forza Street v40.0.5.2 from MS Store, then this file is in the common Unreal Engine 4.21.2 format.
1. download [https://github.com/allcoolthingsatonepl ... ealPakTool](https://github.com/allcoolthingsatoneplace/UnrealPakTool)
2. edit Crypto.json by replacing "Key":"Your Base64 key here" with "Key":"nE61K8NzgSn8v4oscU4myvFdsm+xQ1WIBIrk0/dMXRM="
3. run the following command:

```
.\UnrealPak.exe "C:\games\Microsoft.331194F9F13CC_8wekyb3d8bbwe\Gravity\Content\Paks\Gravity-UWP64.pak" -Extract "C:\games\ForzaStreet" -cryptokeys=Crypto.json
```
