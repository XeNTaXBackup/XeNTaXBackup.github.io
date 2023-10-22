## Post #1
- Username: flonne
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Apr 02, 2008 8:01 pm
- Post datetime: 2008-12-06T08:49:41+00:00
- Post Title: compression type? (compressed & uncompressed file available)

here're 2 files from the ps2 and psp versions of the same game, disgaea.
the files contain description of magic spells within the game, ps2 version in plain text and psp version compressed.
both files should be 90% similar with the exception of a few more special features added to the psp version.

ps2 version - magic.dat 50kb(9kb when winzipped)
text is in some intel format using 2 bytes per alphabet. since most of the file is text there're like a million 82s in there.

A: 8260    B: 8261    C: 8262    D: 8263    E: 8264
F: 8265    G: 8266    H: 8267    I: 8268    J: 8269
K: 826A    L: 826B    M: 826C    N: 826D    O: 826E
P: 826F    Q: 8270    R: 8271    S: 8272    T: 8273
U: 8274    V: 8275    W: 8276    X: 8277    Y: 8278
Z: 8279

a: 8281    b: 8282    c: 8283    d: 8284    e: 8285
f: 8286    g: 8287    h: 8288    i: 8289    j: 828A
k: 828B    l: 828C    m: 828D    n: 828E    o: 828F
p: 8290    q: 8291    r: 8292    s: 8293    t: 8294
u: 8295    v: 8296    w: 8297    x: 8298    y: 8299
z: 829A

(space): 8140   (colon): 8146
-: 817C    ': 8166    .: 8144

psp version - psp_magic.dat 9kb

spent hours reading and re-reading the file format exploration guide while trying to observe some patterns which will help me solve the mystery but to no avail.
i'll be eternally grateful to anyone who helps out  
[magic.zip](https://xentaxbackup.github.io/file/1769_magic.zip)
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-12-06T13:29:58+00:00
- Post Title: compression type? (compressed & uncompressed file available)

wtf 
never seen such a strange encoding, what is this (the "intel format" as you call it)?
## Post #3
- Username: flonne
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Apr 02, 2008 8:01 pm
- Post datetime: 2008-12-06T13:56:26+00:00
- Post Title: compression type? (compressed & uncompressed file available)

sorry if i confused you. 
the list are hex values that correspond to the alphabets and the byte order is intel. XD

the first entry would be(substituting the characters in hex workshop by mapping the values 60-9A as in the table)

0000 0000 0100 0A00 0300 8273 8292 8289 | ...........T.r.i
8290 828C 8285 8140 8272 8294 8292 8289 | .p.l.ea .S.t.r.i
828B 8285 0000 0000 0000 0000 8740 8275 | .k.e........g. V
8289 8283 8294 8289 828D 8140 8289 8293 | i.c.t.i.ma .i.s 
8140 8283 8292 8289 8290 8290 828C 8285 | a .c.r.i.p.p.l.e
8284 8140 8282 8299 8140 8252 8140 828C | .da ...ya .Ra .l
8285 8294 8288 8281 828C 8140 8282 828C | e.t.h.a.la ...l
828F 8297 8293 0000 0000 0000 0000 0000 | o.w.s...........

dont know if it's possible to map 2 bytes to an alphabet but as it is already quite clear i didnt try to do so.
basically the skill is called "Triple Strike" and description is "Victim is crippled..."
but all these are in magic.dat
psp_magic.dat should have the same content but compressed
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-12-06T14:45:02+00:00
- Post Title: compression type? (compressed & uncompressed file available)

Yeah, but where do you know that from? Did you just figure it out or is there a description of this encoding somewhere?
I mean, why would a developer use such a strange format, why not simply unicode?
## Post #5
- Username: flonne
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Apr 02, 2008 8:01 pm
- Post datetime: 2008-12-06T15:02:13+00:00
- Post Title: compression type? (compressed & uncompressed file available)

dunno. perhaps ps2 has to use that format? i'm not sure bout it.
how i knew, this guide at gamefaqs told me: [http://www.gamefaqs.com/console/ps2/file/589678/35073](http://www.gamefaqs.com/console/ps2/file/589678/35073)
it's about save game editing but i'm more interested in modding 

since character info and stuffs are in similar form of plain text as mentioned, i've managed to do things like giving characters skills that are specials belonging to someone else, change their avatars, names and so on.

problem is, the script, magic data and images are compressed/encrypted in the psp data files
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2008-12-20T15:27:46+00:00
- Post Title: compression type? (compressed & uncompressed file available)

it's a classical unicode text that can be read using notepad launched through Applocale with the japanese coding (the last that you can choose in "language of the application" of applocale when choosing the program to launch):

[http://www.microsoft.com/globaldev/tools/apploc.mspx](http://www.microsoft.com/globaldev/tools/apploc.mspx)

then load the file in the new notepad, remember that the file must contain directly the text so the bytes 82 73 82 92 82 89 82 90 82 8c and so on.

the output for that piece of text you posted is like the following:
Ｔｒｉｐｌｅ　Ｓｔｒｉｋｅ
Ｖｉｃｔｉｍ　ｉｓ　ｃｒｉｐｐｌｅｄ　ｂｙ　３　ｌｅｔｈａｌ　ｂｌｏｗｓ
(if you can't read it it's: "Triple Strike Victim is crippled by 3 lethal blows")
## Post #7
- Username: flonne
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Apr 02, 2008 8:01 pm
- Post datetime: 2008-12-25T06:40:19+00:00
- Post Title: compression type? (compressed & uncompressed file available)

yes, i realised they're from S-JIS.

[http://www.rikai.com/library/kanjitable ... sjis.shtml](http://www.rikai.com/library/kanjitables/kanji_codes.sjis.shtml)
