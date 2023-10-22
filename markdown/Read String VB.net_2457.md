## Post #1
- Username: Matsy
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Aug 21, 2006 3:12 pm
- Post datetime: 2007-02-08T06:58:37+00:00
- Post Title: Read String VB.net

Hey,
When I was messing around with VB.net with a BinaryReader to read a string, I only saw an option to read a 7 character string, and no others.
Would there be an option to just read a null terminated string?, Because I can't seem to find it.

Cheers,
Matsy
## Post #2
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2007-02-09T12:16:15+00:00
- Post Title: Read String VB.net

I think the VB.net Binary String Reader reads 1 byte before the string and uses that for the string length.

I don't think I have even looked I've always just used something like this

dim test as string
dim byter as byte = 1
....
While byter <> 0
byter = bread.ReadByte
test+= Chr(byter)
End While

I'd hope there was something built in, but laziness had always resorted in me using that above.
## Post #3
- Username: Matsy
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Aug 21, 2006 3:12 pm
- Post datetime: 2007-02-09T20:59:23+00:00
- Post Title: Read String VB.net

Works perfect, Thanks
## Post #4
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2007-02-10T00:03:23+00:00
- Post Title: Read String VB.net

also very slow too

i don't use vb.net but c# equiv is


with a FileStream or BinaryReader, i use filestreams

```
fs.read(bytestring);
System.Text.ASCIIEncoding encoding = new System.Text.ASCIIEncoding();
string mystring = encoding.GetString(bytestring);
```


This works out better because its easier to change encodings. For say UTF8 or UTF16LE/BE.

VB.NET example

```
Dim str As String
Dim enc As New System.Text.ASCIIEncoding()
str = enc.GetString(dBytes)
```
