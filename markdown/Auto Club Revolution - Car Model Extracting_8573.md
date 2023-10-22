## Post #1
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2012-03-17T04:40:13+00:00
- Post Title: Auto Club Revolution - Car Model Extracting

Well, i've recently trying to rip cars from this newly made game which just turned from Closed Beta into Open Beta. I'm a Beta tester of this game. I used 3DRipperDX (injected into firefox.exe) to rip the cars. I went on the website : " [http://www.autoclubrevolution.com/en/index](http://www.autoclubrevolution.com/en/index) " to rip the cars. First i log in, then i went to the car customizing part. It lets us display our car in 3D with Unity Player in browser. So i was able to rip and examine a model of a GT-R.
Here is a picture of the ripped model being opened in ZModeler 2 (Nissan GT-R) : 
NOTE : (Windows model or light glasses were not ripped due to 3DRipperDX not ripping models applied with transparency or could be Pixel Shader issues)

[http://i.imgur.com/uyRvb.jpg](http://i.imgur.com/uyRvb.jpg)

It would seem that the cars in this game does NOT have interior/cockpit models. Instead, they made the same interior/cockpit models like in Need For Speed Underground 2 (All black), But models are EXTREMELY highpoly. And the ripped rim model was combined with the rim blur model. In game i discovered that the rim was applied with a transparent material instead of using a blur texture when the car is moving in high speed. It is why the wheels looked weird when the car is speeding.

Now for the file format explanation...

Auto Club Revolution's cars were compressed in .ZIP(s). I extracted the ZIP and discovered some files. "GTR08_1.zip" was the ZIP of the GT-R. There's 3 files once i opened the extraction result. Cars (folder), Vehicles (folder, and info.txt .

Inside the " info.txt " was : c:\pro\acr\pc\data\pods\GTR08_01.zip

Car models are in .acr format, such as " gtr08_upg0_body_body0_0.acr " (Inside Cars>Nissan>GTR08 folder)

Texture files are in a double file format, which was .dds.tex, such as " lod0_upg0_ao-alloyfr.dds.tex " (Inside Vehicles>Cars>Nissan>GTR08>Textures>Next folder)

I might think that this game was made with Unity engine since the car 3d model loads with Unity Player in browsers.
An example of the .acr files and .dds.tex files are provided if anyone is interested in this kind of topic.
[[ACR] Nissan GT-R (EXAMPLE FILES).rar](https://xentaxbackup.github.io/file/5197_[ACR] Nissan GT-R (EXAMPLE FILES).rar)
