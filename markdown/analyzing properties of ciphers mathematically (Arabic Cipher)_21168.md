## Post #1
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2019-09-25T16:27:45+00:00
- Post Title: analyzing properties of ciphers mathematically (Arabic Cipher)

this example just show how behind a subject that seems trivial in first look , there are many enigma ...

I wish we can discuss about other encryption algorithms here too ?
but understanding of most of them is so hard although demonstrating of the concept maybe is easier in a Computer Algebra System like Maple :
[https://www.mapleprimes.com/posts/21118 ... ment203741](https://www.mapleprimes.com/posts/211188-Arabic-Cipher#comment203741)
-------------------------------------------------------------
Arabic Cipher
This is a simple encryption method to hide text messages /b]

Mentioned in Arabic manuscripts with more than hundreds years old ...

PRINCIPLE :

Just the place of letters in the sentence rearranged as described below :

For example "ABCDE" we pick up the First letter "A" from the left and write it as the last letter in the Right "......A"

but this time we pick up the letter "E" as the last letter from Right and place it at the Left Side of the previous one  ".....EA"

and this cycle continue until for rest letters ... "CDBEA" .

by this way the text become hard to discover !

It is Amazing that for decoding this message you should repeat the same rearrangment algorithm several times until the readable text appears as the first "ABCDE"

EXample :

"AlbertEinstein"

"iEntsrteebilnA"

"eterbsitlnnEAi"

 "tilsnbnrEeAtie"

"rnEbenAstliiet"

"sAtnleibiEentr"

 "biieElennttArs"

"nenltEteAirisb"

"etAEitrlinsebn"

"lritnisEeAbtne"

"EseiAnbttinrel"

"tbtniAnireeslE"

"inrAeienstlbEt"

"nesitelAbrEnti"

"AlbertEinstein"

the same text appeared after 14 step cycle
