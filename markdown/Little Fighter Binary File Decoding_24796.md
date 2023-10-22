## Post #1
- Username: theunderdark
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 29, 2021 4:37 pm
- Post datetime: 2021-11-29T09:25:08+00:00
- Post Title: Little Fighter Binary File Decoding

Hello everyone,

This is my first post and I would like to take this opportunity to say hello to everyone.

I used the search function to check where exactly I may post my topic (if it is still wrong, please let me know).

On topic:
I am currently working on a project to make the sequel to Little Fighter 2 (which was unfortunately only released in China and Taiwan) available in English.

[https://www.reddit.com/r/littlefighter/ ... h_version/](https://www.reddit.com/r/littlefighter/comments/qsi6ie/little_fighter_online_english_version/)

Since the server and the game were discontinued in 2016, I got the source code after a long search  .

Unfortunately I don't have much support from China and have to decode everything manually by try and force.

Currently I have big problems with the client to connect to the server.

The client is filled with data from the Binary.bin file.
Unfortunately, I am a beginner in this field.

With the help of Hex Editor Neo I was able to look at the file.

Unfortunately, I do not know exactly how it was coded.
I am currently guessing Chinese BIG5 or GB2312.

Currently I am facing 2 big problems:

1. I would like to change the IP address (Notepad++ line 6693) from 127.0.0.1 to 192.168.1.100.  That would be 4 characters more than before. As a result, the data set is not recognised as an IP and even worse, the whole HexDump shifts by 4 characters.

It should be defined somewhere in the hex that the next 13 characters form the IP address. Or is my thinking wrong?

2. from line 9249 (in Notepad++) the data area begins.
As an example, the data set of the character Woody (line 9253)

   Woody   ?   斢&惎/ (coding GB2312)

I would like to know how I define whether the character is "active" or "not yet active (must still be activated in the game)".

My guess is the "?"

Now I would like to know what characters I need to set in binary.
For example:
   Woody   ?   斢&惎/ (coding GB2312) --> active
   Woody   !   斢&惎/ (coding GB2312) --> not active

is there a way to see the correct character set in binary e.g. in a "header" or something?

I have the same problem with StoryMode.
Every stage is currently unlocked. Normally the previous stage must be successfully completed to unlock the next one.

In the Binary.bin line 14024 I see the following entry:

   stage   ‹”Ó°¹   isLock  ‹”Õ65Wy    maxAmountPlayers‹	ºÉ‹	º`‹ 

Again I dont understand what I need to change to trigger the result.

I have uploaded the file:
[https://www.file-upload.net/download-14 ... y.bin.html](https://www.file-upload.net/download-14762506/binary.bin.html)

I ask for help to fulfil my dream and that of many fans.

Greetings
Gigi
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-11-29T09:45:12+00:00
- Post Title: Little Fighter Binary File Decoding

> where exactly I may post my topic (if it is still wrong, please let me know).
I have moved your topic to the proper section.

> I got the source code after a long search
So in this case the source code should answer all your questions, because you can check in the source how "binary.bin" file is parsed by game and you can figure out whole file format just by looking at the parsing functions. But you need to know programming a little to achieve that.

If you don't know how to start your adventure with reverse engineering, you can check our tutorials section [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)

> As a result, the data set is not recognised as an IP and even worse, the whole HexDump shifts by 4 characters.
You CAN'T edit binary data in text editor. You can only use hex editor in this case.

> It should be defined somewhere in the hex that the next 13 characters form the IP address. Or is my thinking wrong?
Yeah, it's common practice to define strings length somewhere in the binary (or in executable).

> is there a way to see the correct character set in binary e.g. in a "header" or something?
Yeah, but you need to know which value is responsible for that. That's why you need to figure out file format first.
## Post #3
- Username: theunderdark
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 29, 2021 4:37 pm
- Post datetime: 2021-11-29T10:29:24+00:00
- Post Title: Little Fighter Binary File Decoding

Thank you for moving.

By source code I mean all files that are necessary to run the game.
But not a classic source code as you know it from java or python.

Through my programming experience, I know that the Binary.bin is executed and the client is built through it.

	<body>
		<div id="root"></div>
		<script>
			const binary = process.platform == "darwin" ? "binary_mac.bin" : "binary.bin"
			nw.Window.get().evalNWBin(null, binary)
		</script>
	</body>

Currently, I can only access the binary.bin, as I could not see any other file that accesses data sets of the binary.bin, I assume that all parameters are present in the binary.bin and are parameterised.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-11-29T12:39:42+00:00
- Post Title: Little Fighter Binary File Decoding

> By source code I mean all files that are necessary to run the game.
>
> But not a classic source code as you know it from java or python.

So that's not a source code. It's just game client.   

> as I could not see any other file that accesses data sets of the binary.bin

You can use Sysinternals Process Monitor to see how the data is accessed by the game.

Then you could try to debug the game with IDA or Ghidra to figure out how parsing function is handling data.
But that is advanced stuff, so you would need some more knowledge/experience to do that.
## Post #5
- Username: theunderdark
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 29, 2021 4:37 pm
- Post datetime: 2021-11-30T08:05:45+00:00
- Post Title: Little Fighter Binary File Decoding

Thank you for the tip.
I have already made one step further.
And I was able to resolve the IP address.

Currently, the IP address is resolved via a namespace as test12345.

Server established successfully! Listening at test12345:34146.

Unfortunately I could not find the port 34146 anywhere in the binary file to change it.

I have tried:
Plaintext: 34146
Hex: BigEnding 8562
Little Ending 6285

Unfortunately without success.
Please ask someone with more experience to take a look at the file and maybe find out where the port has to be edited.
