## Post #1
- Username: katzsmile
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Sep 02, 2010 2:02 pm
- Post datetime: 2010-09-02T06:58:34+00:00
- Post Title: World of Tanks/Bigworld Tech packed XML

I have a problem with decoding XML form World of Tanks. Cant solve encryption package method.

This files if non standard packed XML files. They have removed hierarchy but node names and values not encrypted or compressed. 
I has decode two files using trying reconstruct original XML handy.
EN.b (HEX:454EA162) is hardcoded packed xml header for file format detection. This header contain all of packed xml files

example:
original resources.xml looks like

```
EN.b.loadingScreenGUI.system.........."...............gui/loading_screen.gui
```


```
HEX: 454EA162006C6F6164696E6753637265656E4755490073797374656D00000100000000100100220000000100000000100000160000106775692F6C6F6164696E675F73637265656E2E677569
```

decoded

```
	<system>
		<loadingScreenGUI>	gui/loading_screen.gui	</loadingScreenGUI>
	</system>
</root>
```

that looking like fist two word is child node and parent node and the last string is value for child node.

But:
original loading_screen.xml

```
EN.b.SimpleGUIComponent.script.........................."GameLoading"
```


```
HEX: 454EA1620053696D706C65475549436F6D706F6E656E7400736372697074000001000000001000001900000001000000001001000D0000102247616D654C6F6164696E6722
```

decoded

```
	<SimpleGUIComponent>
		<script>	"GameLoading"	</script>
	</SimpleGUIComponent>
</root>
```

There is first word is parent node and second is a child node.

also all packed XML files have similar HEX structures:
after node definition:

```
HEX: 0000010000000010
```

before values:

```
000010
```

HEX: 454EA162006C6F6164696E6753637265656E4755490073797374656D00000100000000100100220000000100000000100000160000106775692F6C6F6164696E675F73637265656E2E677569

HEX: 454EA1620053696D706C65475549436F6D706F6E656E7400736372697074000001000000001000001900000001000000001001000D0000102247616D654C6F6164696E6722

But HEX: 0000010000000010 can have different this symbol (01 here) in another XML files
examle from packed engine_config.xml
0000110000000010

Please help with decoding file format.
[XML.zip](https://xentaxbackup.github.io/file/3396_XML.zip)
## Post #2
- Username: psycho
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 14, 2010 7:57 pm
- Post datetime: 2010-10-14T17:05:17+00:00
- Post Title: World of Tanks/Bigworld Tech packed XML

I  have also done some research. It is lot to describe whole file format, so I only attach packed XML parser written in Java. It isn't SAX parser - it just reads to simple tree model. 

BTW
I'm now wondering about format of *.primitives files. The format seams to be quite similar, but decoding of it will be more difficult, since it contains binary data.
[WotXmlParser.zip](https://xentaxbackup.github.io/file/3532_WotXmlParser.zip)
## Post #3
- Username: Zyw
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 17, 2010 11:45 pm
- Post datetime: 2010-11-11T18:54:42+00:00
- Post Title: World of Tanks/Bigworld Tech packed XML

I have a XML file both packed and unpacked, can it be of any help? It was modified a bit, but nothing important.
[command_mapping.zip](https://xentaxbackup.github.io/file/3590_command_mapping.zip)
## Post #4
- Username: Razor666
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 10, 2010 9:33 pm
- Post datetime: 2010-12-14T22:56:17+00:00
- Post Title: World of Tanks/Bigworld Tech packed XML

Thanks for the parser, but how can I use it on a windows system?
## Post #5
- Username: katzsmile
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Sep 02, 2010 2:02 pm
- Post datetime: 2010-12-23T14:40:47+00:00
- Post Title: World of Tanks/Bigworld Tech packed XML

> Reply from psycho
>
> I  have also done some research. It is lot to describe whole file format, so I only attach packed XML parser written in Java. It isn't SAX parser - it just reads to simple tree model. 

BTW
I'm now wondering about format of *.primitives files. The format seams to be quite similar, but decoding of it will be more difficult, since it contains binary data.

Hey how you compile this code? I'm try to compile with Eclipse and with javac and always got error  "cannot find symbol symbol  : class SimpleXmlElement"
## Post #6
- Username: katzsmile
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Sep 02, 2010 2:02 pm
- Post datetime: 2010-12-28T19:43:56+00:00
- Post Title: World of Tanks/Bigworld Tech packed XML

I did my own unpacker, which based on sources by psycho and maded in C#.
Requires Net3.5
[wotunpack_withsrc.zip](https://xentaxbackup.github.io/file/3732_wotunpack_withsrc.zip)
## Post #7
- Username: Razor666
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 10, 2010 9:33 pm
- Post datetime: 2010-12-30T06:40:12+00:00
- Post Title: World of Tanks/Bigworld Tech packed XML

Great Job!!! Many Thanks....Do you got also some "minus" values in the XML files? Shell speed in the shell.xml is sometime a negative value like -18 or so. In some other files too.
## Post #8
- Username: katzsmile
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Sep 02, 2010 2:02 pm
- Post datetime: 2011-01-03T14:26:44+00:00
- Post Title: World of Tanks/Bigworld Tech packed XML

Yes. And that is fixed in build 0.4

All new version of WoT Mod Tools will be published on my site [here](http://lead-games.com)
## Post #9
- Username: byshido
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 18, 2011 5:31 pm
- Post datetime: 2011-01-19T21:38:39+00:00
- Post Title: World of Tanks/Bigworld Tech packed XML

how to pack xml again?
