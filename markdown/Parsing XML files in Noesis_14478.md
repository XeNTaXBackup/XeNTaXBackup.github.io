## Post #1
- Username: errno
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Oct 05, 2014 7:08 am
- Post datetime: 2016-06-18T01:59:00+00:00
- Post Title: Parsing XML files in Noesis

There's certain data for the models I am currently working on that is stored in XML files. I am using one of Python's provided XML parsers to handle them like this:

```

#a few lines later:
tree = etree.parse(xmlFilePath)
root = tree.getroot()
```


However, the code above causes Noesis to stop running the script, saying:

```
  File "C:\noesis\plugins\python\core321.zip\xml\etree\ElementTree.py", line 1488, in __init__
  File "C:\noesis\plugins\python\core321.zip\xml\parsers\expat.py", line 6, in <module>
ImportError: No module named pyexpat
```


Now, to the best of my knowledge, Noesis includes the core libraries for parsing XML, so I am unsure why it's failing. I would really wish to avoid reinventing the wheel by parsing the XML files myself. Does anyone know what would be the best way to parse XML files inside Noesis scripts?

I'm using the latest version of Noesis (v4.177)
## Post #2
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-06-18T05:25:14+00:00
- Post Title: Parsing XML files in Noesis

from xml.dom.minidom import parseString


			datasource = open(matFileName)
			data = datasource.read()
			dom = parseString(data)
			soup = BeautifulSoup(datasource, 'xml')
			tree = ET.parse('D:/Games/Data/materials.xml')
			print(tree.getroot())

			datasource.close()

you can try this.
## Post #3
- Username: errno
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Oct 05, 2014 7:08 am
- Post datetime: 2016-06-19T05:07:24+00:00
- Post Title: Parsing XML files in Noesis

Thank you for your suggestions. Unfortunately I had no luck in getting them to work. Noesis keeps complaining about some missing reference in core321.zip like pyexpat. I'm thinking this might be because these missing Python libraries aren't included with the default Noesis distribution?

Reading the beginning of __NPReadMe.txt makes me think this is exactly what is happening:
> A trimmed down core 3.2.1 Python implementation is included. No modules (ctypes, sockets, etc.) are included - if you want support for them, you have to create a folder called "DLLs" under the Noesis folder and put them in it. DLLs not compiled for Python 3.2.1 may or may not work. So I guess I will have to look around the web to download the missing modules. It's a shame if it must be done this way because this means that, unless I write my own XML parser in my script and reinvent the wheel, my script will need to include these extra DLLs to work. I'm hoping I'm wrong, is there really no built-in XML parser for Noesis?
