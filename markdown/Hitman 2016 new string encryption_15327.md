## Post #1
- Username: faqy
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jun 16, 2009 5:30 pm
- Post datetime: 2016-10-04T11:26:58+00:00
- Post Title: Hitman 2016 new string encryption

The recently version has change their encryption.
file format :

```
Strs[10]{
	long		num
	Str[num]{
		DWORD		ID
		long			len
		string[len]		string
	}
}
```

Strs[1]=english

It seems encrypted every 8 bytes.
String ID 085C56D9 display as "Destinations" in game.
Looks familiar ,but I cant figure it out.


 008D33DE8C75CACB.7z
(255.46 KiB) Downloaded 58 times
## Post #2
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2016-10-09T04:48:40+00:00
- Post Title: Hitman 2016 new string encryption

They encrypted it, don't ask me why.
Didn't take long for it to be broken.

It's using XXTEA

Keys crc32
Hash XXTEA 53527737 7506499E BD39AEE3 A59E7268
## Post #3
- Username: faqy
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jun 16, 2009 5:30 pm
- Post datetime: 2016-10-12T10:39:03+00:00
- Post Title: Hitman 2016 new string encryption

> Reply from hhchunter
>
> They encrypted it, don't ask me why.
Didn't take long for it to be broken.

It's using XXTEA

Keys crc32
Hash XXTEA 53527737 7506499E BD39AEE3 A59E7268
Ok, I'm not quite understand.
So,XXTEA keys are "53527737 7506499E BD39AEE3 A59E7268"?
But I cant use them get anything.
## Post #4
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2016-10-13T08:47:38+00:00
- Post Title: Hitman 2016 new string encryption

so can we unpack the files?
## Post #5
- Username: swixel
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 29, 2015 11:04 am
- Post datetime: 2016-10-18T00:34:03+00:00
- Post Title: Hitman 2016 new string encryption

> Reply from faqy
>
> hhchunter wrote:They encrypted it, don't ask me why.
Didn't take long for it to be broken.

It's using XXTEA

Keys crc32
Hash XXTEA 53527737 7506499E BD39AEE3 A59E7268
Ok, I'm not quite understand.
So,XXTEA keys are "53527737 7506499E BD39AEE3 A59E7268"?
But I cant use them get anything.

I really wish Hunter hadn't posted these... but I'll assume that you're using these keys/information for the purposes of localising the data under a law in your region that covers it, as I'm discussing it from/for the same from/in mine.  (e.g. fixing obvious errors in typographical things, or correcting display errors caused by IOI rushing a patch out, or localising to make the game easier/faster to play in a language other than English (so you don't need to pause and pick up a dictionary)).

A couple of things:
1. The ID field is a CRC32 of an uppercase string.
2. The offset list keys match the languages in order of the game's usage -- you can find the full names in-game, these are what the game uses in short form (en,fr,it,de,es,ru,mx,br,pl).  Given a list of localisation keys you do full relocalisation, though I've been warned off this topic by Travis (who is the community person for IOI), so I won't go into depth (though it's kind of needless to say that this is why my public repository for tooling and the localisation project are now gone).  You can get the full list of active/live languages for LOCR from the thumbs file, which is also XXTEA encrypted (but with different keys).  I'm not going to say what the keys are, but they have been revealed elsewhere.

The values are now 8-byte aligned, hinting at a block cipher.  Deduction and a negligible amount of work putting together a tool to dump the data later I got the keys, which only a handful of people were meant to see (Hunter included in that list).  I believe the source Hunter quoted is from a Vietnamese RE team who float around gamesurge and have been posting wonderfully awful things about me as of late -- the formatting matches their leaks for this and a few other things.

The four keys for XXTEA are: 0x53527737 0x7506499E 0xBD39AEE3 0xA59E7268.  I had confirmed this a little over a day after the new patches came out changing the format.  What Hunter didn't post was the delta (0x61C88647) or Sum (0xC6EF3720).  The delta is two's complement of 0x9E3779B9 (the delta usually used) and 0xC6EF3720 is the sum usually used; most developers use variants of these (something they can easily remember).  From there, if you have a decent XXTEA implementation in whatever you use, you have the data.  If you don't putting one together is trivial, or finding one is easy 

---

Sidenote: there was an effort by a group on freenode to get the game localisation data using memory dumps.  The change from their bit-twiddling cipher to XXTEA seems to have changed what's exposed and when it's exposed; the complaint being that the data in memory is limited to what's needed actively, so if you drift too far from the region of the map they reported it's missing.  How true this is I couldn't say -- I'm not interested in dumping the game repeatedly while playing to get the data when the RPKG protection is what it is (nor after Travis (who works for IOI) threatened me for "modding the engine" (despite the fact I haven't done any RE on the binary)).  However, if the reports are true this means they're doing live cipher work (which is far more expensive than a table-lookup), so this change adds overhead.  If it changes again I doubt they'll want to be putting additional overhead into an already fragile engine, so for look obvious/cheap ciphers if that's the case.
## Post #6
- Username: faqy
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jun 16, 2009 5:30 pm
- Post datetime: 2016-10-20T14:42:03+00:00
- Post Title: Hitman 2016 new string encryption

> Reply from swixel
>
> faqy wrote:hhchunter wrote:They encrypted it, don't ask me why.
Didn't take long for it to be broken.

It's using XXTEA

Keys crc32
Hash XXTEA 53527737 7506499E BD39AEE3 A59E7268
Ok, I'm not quite understand.
So,XXTEA keys are "53527737 7506499E BD39AEE3 A59E7268"?
But I cant use them get anything.

I really wish Hunter hadn't posted these... but I'll assume that you're using these keys/information for the purposes of localising the data under a law in your region that covers it, as I'm discussing it from/for the same from/in mine.  (e.g. fixing obvious errors in typographical things, or correcting display errors caused by IOI rushing a patch out, or localising to make the game easier/faster to play in a language other than English (so you don't need to pause and pick up a dictionary)).

A couple of things:
1. The ID field is a CRC32 of an uppercase string.
2. The offset list keys match the languages in order of the game's usage -- you can find the full names in-game, these are what the game uses in short form (en,fr,it,de,es,ru,mx,br,pl).  Given a list of localisation keys you do full relocalisation, though I've been warned off this topic by Travis (who is the community person for IOI), so I won't go into depth (though it's kind of needless to say that this is why my public repository for tooling and the localisation project are now gone).  You can get the full list of active/live languages for LOCR from the thumbs file, which is also XXTEA encrypted (but with different keys).  I'm not going to say what the keys are, but they have been revealed elsewhere.

The values are now 8-byte aligned, hinting at a block cipher.  Deduction and a negligible amount of work putting together a tool to dump the data later I got the keys, which only a handful of people were meant to see (Hunter included in that list).  I believe the source Hunter quoted is from a Vietnamese RE team who float around gamesurge and have been posting wonderfully awful things about me as of late -- the formatting matches their leaks for this and a few other things.

The four keys for XXTEA are: 0x53527737 0x7506499E 0xBD39AEE3 0xA59E7268.  I had confirmed this a little over a day after...
It's being sad to hear that IOI not even alowed player to mod their own game.
May be it's over protected. Most game maker go easy on this kind thing.
Anyway, thanks for the information , I'll looking to it.
## Post #7
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-10-20T19:35:45+00:00
- Post Title: Hitman 2016 new string encryption

[quote="swixel]
I really wish Hunter hadn't posted these... but I'll assume that you're using these keys/information for the purposes of localising the data under a law in your region that covers it, as I'm discussing it from/for the same from/in mine.  [/quote]


Considering there's absolutely no other use for decrypting strings, what exactly would you think people would use it for?

And considering the purpose of Xentax is to share information for the purpose of modding games, it's really not in the spirit of the forums to be withholding information. Shouldn't be advocating people withhold anything.
## Post #8
- Username: swixel
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 29, 2015 11:04 am
- Post datetime: 2016-10-20T21:07:50+00:00
- Post Title: Hitman 2016 new string encryption

> Reply from volfin
>
> And considering the purpose of Xentax is to share information for the purpose of modding games, it's really not in the spirit of the forums to be withholding information. Shouldn't be advocating people withhold anything.

The game packaged way too much data, way too early (briefings of later maps were leaking as far back as the beta).  IOI have taken a grim view of it.  The reason I wish he hadn't posted them is that they're likely to change them again if it becomes obvious (though it took 4 months from a public posting of the old cipher to it being changed so who knows).

I'm not withholding anything on the format, I just didn't post it until Hunter had replied because I wasn't really aware of it until then.  I also explained what the ID field is, so it's not like I'm withholding anything other than the old format, or what's actually there -- anyone who wants it can look, and the old format is retired to all of the strings are using the block cipher (i.e. load base then load patches to clobber matching hash values, going from chunk0 -> chunkn, dlc0 -> dlcN, patch incrementing by level).

I was also pretty sure someone else had posted the keys to thumbs.dat, but as people not from Xentax know I lost my hard drive with "useless" things and I'm yet to repopulate my drives with offsite repositories because there's a lot of other (more important) data that needs restoring first.  I could poke around them but they're not pressing -- I gave the language list too.  thumbs.dat is mostly useless now, and packagedefinitions is only interesting if you're trying to generate the RPKG entry names (most of which are unrecoverable).

As for why I wish Hunter hadn't ... well, it wasn't me who put them here, but there's a chance Travis is going to read it as if it was me anyway; IOI have already raised the potential for legal action over tampering with this product, hence the statement above.
## Post #9
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-10-22T00:31:47+00:00
- Post Title: Hitman 2016 new string encryption

They wouldn't have a leg to stand on legally. Reverse engineering has never been Illegal, and never will be, as the recent Google vs. Oracle lawsuit confirmed.

Sure they could decide to change the encryption, though I really don't understand why it's encrypted in the first place. It's not even a multiplayer game where guarding against cheating is required. It's a single player game where what you do doesn't really affect anyone else. I guess they just have a diametrically opposite viewpoint from Bethesda on modding.
## Post #10
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-11-09T01:47:23+00:00
- Post Title: Hitman 2016 new string encryption

> Reply from swixel
>
> I'm not withholding anything on the format, I just didn't post it until Hunter had replied because I wasn't really aware of it until then.

The point is that no one can handle it, right? And no one will do it.
## Post #11
- Username: swixel
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 29, 2015 11:04 am
- Post datetime: 2016-11-19T20:20:53+00:00
- Post Title: Hitman 2016 new string encryption

> Reply from adol365
>
> swixel wrote:I'm not withholding anything on the format, I just didn't post it until Hunter had replied because I wasn't really aware of it until then.

The point is that no one can handle it, right? And no one will do it.

The point was that once the game goes to physical release (which wasn't far away, and still isn't) it's unlikely they'll change the format again.  At this point it's unlikely they will (as it's post-Hokkaido), even if they do for season 2 onwards.  The move from the old cipher (which was probably using a table lookup -- I was) to XXTEA has performance overheads (as they also seem to have changed when it's done).

> Reply from volfin
>
> They wouldn't have a leg to stand on legally. Reverse engineering has never been Illegal, and never will be, as the recent Google vs. Oracle lawsuit confirmed.

Sure they could decide to change the encryption, though I really don't understand why it's encrypted in the first place. It's not even a multiplayer game where guarding against cheating is required. It's a single player game where what you do doesn't really affect anyone else. I guess they just have a diametrically opposite viewpoint from Bethesda on modding.

I agree with not understanding why they encrypted it in the first place, but I suspect it's because, despite what's been said, they knew there were leaks (or a chance of).

As for the legal issues ... cost + time + effort to defend against it after they warn people off.  It may not be a winnable position but they just have to make it inconvenient enough that it's not worth the effort.  Hunter is known to talk to me off boards by the IOI guys, so his posting it was a concern in that it could have looked like it came from me when the reality is I'm waiting for all of the dust to settle and asking them for proper support on localisation "modding" (i.e. community translation projects).  Of course they haven't replied to any of that, and the game itself has really lost its shine to me (I'm too busy with other things to want to waste my time finishing data file/structure work).  (My interactions with IOI's community head have been far from positive.)
## Post #12
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-11-20T04:39:48+00:00
- Post Title: Hitman 2016 new string encryption


## Post #13
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-11-21T09:52:59+00:00
- Post Title: Hitman 2016 new string encryption

> Reply from swixel
>
> As for the legal issues ... cost + time + effort to defend against it after they warn people off.
Ok. Let's give it up.   I'm not a hacker.
