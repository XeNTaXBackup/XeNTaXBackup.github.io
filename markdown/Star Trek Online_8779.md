## Post #1
- Username: MrBombastic
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 16, 2012 8:36 am
- Post datetime: 2012-04-16T00:47:23+00:00
- Post Title: Star Trek Online

im trying to make a little modification to star trek online the thing is i use a tier 5 ship and i would rather have it look like either a tier 1 or tier 3 ship i had so i figured i could find the texture and geometry files for those ships and rename them and replace with the ones fo r the ship im using right now so that i would get the looks of the lower tier ship and the powers of the higher one. I found out that sto has an override file for those models in case anyone wanted to make a client side alteration to the game graphics but im having a little trouble locating the files i need to replace can anyone help me with that? i managed to extract the .hogg files and get some .wtex files and some .bins but im stuck there i dont know which one is the file im looking for. has anyone had experience with this kind of thing can anyone help me?
## Post #2
- Username: GlassZeppelin
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Feb 07, 2010 9:20 am
- Post datetime: 2012-04-19T21:53:53+00:00
- Post Title: Star Trek Online

I believe the relevant mesh files are located under ..\Bin\Geobin\Cl\S
There are several folders such as "B" for Borg and "F" for Federation that contain the ship geometries.
If you want to "model-swap" so to speak, you will need to locate the relevant .mset files and swap their contents with whatever you want. 

As a quick example, you could probably get away with taking the contents of the Geo_Saucer_Excalibur.Mset file -- noting that there are two chunks with corresponding header offsets you will likely need to change as described in this thread [viewtopic.php?f=10&t=4997](http://forum.xentax.com/viewtopic.php?f=10&t=4997) -- and swapping the relevant data with, say, Geo_Saucer_Enterprised.Mset to swap the Excalibur saucer with the Enterprise D one. Textures will be messed up until you fix those, too. As for other ship parts, Cryptic's naming scheme is... well, somewhat cryptic. To me, at least, the scheme seems to be:

```

Where X = "e" for escort, "s" for science vessel, or "c" for cruiser
And # = Tier Number (presumably)

Example: 
Geo_Ship_Fed_Fe3_Saucer_Type1 = Federation Escort Tier 3 Saucer Type 1
```


If you have more questions, I'll try to help as much as I can -- but I've only done the most basic of model-swaps for STO, nothing quite as large as you want to.
