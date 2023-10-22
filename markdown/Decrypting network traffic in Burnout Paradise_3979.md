## Post #1
- Username: jordanwb
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Dec 26, 2009 4:41 am
- Post datetime: 2009-12-25T21:07:50+00:00
- Post Title: Decrypting network traffic in Burnout Paradise

I know that what I want to decrypt is not a file, but its stored in a file, so I hope this is okay. I'm trying to reverse engineer the server used in Burnout Paradise for the PC since it's been going downhill lately. So far I haven't had any problems figuring out what does what, except the authentication part which seems to be encrypted.

192.168.1.7 is the IP of my machine. 159.153.239.36 is the IP of the server. The attached file contains four individual captures of the authentication process.
[captures.rar](https://xentaxbackup.github.io/file/2659_captures.rar)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-27T17:03:46+00:00
- Post Title: Decrypting network traffic in Burnout Paradise

it's a ssl connection, like:

```
openssl.exe s_client -connect  159.153.239.36:21841
```
knowing what data or type of data is exchanged is not impossible but depends.
for example my [stcppipe tool](http://aluigi.org/mytoolz.htm#stcppipe) supports the ssl connection and the visualization/dumping of the data (example: "stcppipe -D -S 159.153.239.36 21841 21841") but obviously is necessary that the client (game or software) doesn't verify the incoming certificate or it will reject the connection (and if I'm not in error the EA games verify it) and to force it to connect to yourself (127.0.0.1)

the other solution is debugging the game client setting a breakpoint to each call of the ssl function which sends the data.
## Post #3
- Username: jordanwb
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Dec 26, 2009 4:41 am
- Post datetime: 2009-12-27T18:49:23+00:00
- Post Title: Decrypting network traffic in Burnout Paradise

So my suspicions were correct: it is SSL. The thing is I am writing a program in C# which will replicate the server. I'm don't know anything about debugging programs (besides ones I've written in C#), a friend of mine does but he's in Sweden at the moment with family.
