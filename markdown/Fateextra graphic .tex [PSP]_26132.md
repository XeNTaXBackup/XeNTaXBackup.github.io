## Post #1
- Username: Shadowmael
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 28, 2022 11:00 pm
- Post datetime: 2022-12-30T21:33:15+00:00
- Post Title: Fate/extra graphic .tex [PSP]

Sorry for my English, I'm not very good
I was doing some tests on the psp Fate/extra game files to try to translate the game, but there was a problem with the game's textures

They are compressed in the .txb files when extracting the files we got some .tex files, using the 16bp tile molester it is possible to visualize the texture however!!! It is almost impossible to correctly visualize the texture because of the color palette and the mess in the graphics. 

I didn't lose hope... When looking at the psp.im files I realized that there are still .tex files so I went after the noesis scripts to read this file, guess what!!!! I was right 
Within the noesis code it is possible to see that there are mentions of the .tex file and when I went to make some comparisons, they are really the same texture...

But I don't know anything about python, much less about noesis... Normally I use Javascript is C++ (sometimes Node.js but it's practically java with a few more things)

Could anyone here help me? If possible, I would also like a more detailed explanation about the file so I can try to make a C++ program that is able to read this file, maybe even to convert 

Along with the topic I left some sample files along with the Noesis script

Noesis plugin: [https://drive.google.com/file/d/1ddN7Ed ... p=drivesdk](https://drive.google.com/file/d/1ddN7EdA9rkZBrE72UbE9FNtpz4h7yJJV/view?usp=drivesdk)

sample .txb file: [https://drive.google.com/file/d/1dzSfzX ... p=drivesdk](https://drive.google.com/file/d/1dzSfzXrCeYo6eOlAAnZ3zO8yx9mH2Q79/view?usp=drivesdk)
## Post #2
- Username: Shadowmael
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 28, 2022 11:00 pm
- Post datetime: 2023-01-01T02:56:02+00:00
- Post Title: Fate/extra graphic .tex [PSP]

discover another interesting little thing is possible to see the texture using TextureFind 
But I still can't figure out anything about the color palette it's worse how to convert the file to .bmp or .png
