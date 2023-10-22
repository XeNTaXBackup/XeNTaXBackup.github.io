## Post #1
- Username: Aroled
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 29, 2016 5:14 am
- Post datetime: 2016-10-02T11:57:03+00:00
- Post Title: [Help] Gibbed Cryptic Tools

Hello guys, I have some questions about this excellent tools [http://svn.gib.me/public/cryptic](http://svn.gib.me/public/cryptic). So my questions is:
1) When we extracted schemas from game, program also created the file 'expression functions.txt'. Why this file created? We can use this function for some our needs? and how?
2) Gibbed.Cryptic.FileFormats project contains BlobDataReader to read extracted file. But also contains PacketReader - as I understand we can use it for reading information from packet arrived from server or sending to it. Or no? If it's true can anyone explain how to use it
## Post #2
- Username: FriendCoder
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 02, 2018 12:21 pm
- Post datetime: 2018-11-27T02:34:36+00:00
- Post Title: [Help] Gibbed Cryptic Tools

Hi.

I have used these Tools a long Time ago.
What I understand at the end of 2018, the Unpack Tool is the only Working part.

The ExportSchemas is not working because the change of the Processor Architeture to x64 of the GameClient.
Also, the WindowName is the Searchparameter for the Exporter, but it also Changed over time in STO.
AutoIt helped to find the difference... You could look it up in the Taskmanager too.
More of not working things I couldn´t check, my C# skills are poor. I am more a VB.
Maybe the entrypoint to find the schemas is changed also... Dunno   

Now to Answer the question a)

The "expression functions.txt" seems to be a temporary file to Store the Function-Names inside the Client.
This is only one Part to update the Schema files.
Also there are alot of .json-Files that are Generated in the schemas Folders (by Default, but has also a CommandlineParameter for that).
All these files are there to generate a Command-Chain/-Format for the Parser.

With that you can later consume these in form of .dll-Files (generated with the Serializer-Tool).
The Serializer-Tool creates then .dll-Files that are kinda Plugins for the Converter-Tool.
This Tool reads in the "expression functions.txt" and also the .json-Files and spits out DLLs.

Then it should be possible to convert Things to Objects, etc...

For instance I would like to Convert .bin-Files, but I can´t anymore...
I am not shure if anyone is capeable nowadays...

@all: If possible please enlighten me if its Possible to get the shemas updated... 
        or how to parse the .bin-Files to xml or json, would be Great.

The answer to b)
Dunno exactliy.
What I understand is that the schemas are generated also form the Server at Runtime of the Client.
So not really to send things to the Server, but to get dynamicly things that are Serverside only.
Imagine the security of Zen-Transactions, it is generated only form the Server, and it should be only that way.
So it appears that some schemas are only captured that way. Maybe for the completeness of the schemas the Developer has built it in.

P.S.: Zombie thread risen form Stovokor... 

c.u. FriendCoder
