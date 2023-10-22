## Post #1
- Username: IceReaper
- Rank: n00b
- Number of posts: 14
- Joined date: Sun May 22, 2011 9:03 pm
- Post datetime: 2022-07-20T16:33:22+00:00
- Post Title: WoW Matrix Card hash algorythm

Im searching some help. Ive stumbled across Matric Cards for a 2-factor authentication in the World of Warcraft 3.3.5a clients.
So i wrote a small server emulator which i want to fully to support the WoW authentication mechanism.



Before any thoughts go into the wrong direction: i did not find ANY server emulator which implemented the three supported 2fa systems, it seems all emulators are just ignoring these posibilities.

I already got 2 of them implemented by myself (pin and physical authenticator). But the last one, the matrix card, is a bit tricky. It seems those cards have been used in china only, and google does not find any useful information. How they work however is pretty easy to find out.


I've written a fake auth server with a faked login protocol to always send the same data from the server to the client, just to ensure there no additional variable in use. In the client i then always enter the exact same matrix values, however i keep getting a totaly different response SHA1 every time.

As the server needs to validate this information by creating the same hash itself, im pretty sure that its not using the time, as its not relyable on world-wide clients. So i guess all information required besides the actual user input is the SRP6 handshake data, which is hardcoded on server-side, or the client generated data.

Here are two examples:

```
Matrix.Columns: 10
Matrix.Rows: 8
Matrix.CellSize: 1 (how many digits are in a cell)
Matrix.CellAmount: 1 (how many cells must be entered)

The requested cells and their values are: E7 = 1

// The server data.

var serverPublic = new byte[] { 0x3C, 0xB0, 0x04, 0x6E, 0x2D, 0x07, 0x13, 0x47, 0xFD, 0xB9, 0xF8, 0x3F, 0xFF, 0x7A, 0xE2, 0x4F, 0x69, 0x72, 0x93, 0xAD, 0xC4, 0xFE, 0x80, 0x48, 0x94, 0xB6, 0x26, 0x23, 0x55, 0x51, 0xFD, 0x50 };
var serverGenerator = new byte[] { 0x07 };
var serverPrime = new byte[] { 0xB7, 0x9B, 0x3E, 0x2A, 0x87, 0x82, 0x3C, 0xAB, 0x8F, 0x5E, 0xBF, 0xBF, 0x8E, 0xB1, 0x01, 0x08, 0x53, 0x50, 0x06, 0x29, 0x8B, 0x5B, 0xAD, 0xBD, 0x5B, 0x53, 0xE1, 0x89, 0x5E, 0x64, 0x4B, 0x89 };
var serverSalt = new byte[] { 0x2F, 0x8C, 0xE8, 0xBC, 0x6A, 0xC3, 0xDE, 0x40, 0xB1, 0x4B, 0x86, 0xC7, 0x61, 0x10, 0x18, 0xCE, 0xE8, 0x05, 0x3A, 0x25, 0x61, 0x1C, 0x88, 0x6B, 0xCB, 0xDD, 0x19, 0x3F, 0xFA, 0x39, 0xDA, 0x15 };
var serverMatrixSeed = new byte[] { 0x30, 0x30, 0x30, 0x30, 0x30, 0x30, 0x30, 0x30 };

// Client response 1

var client1Public = new byte[] { 0xB5, 0x36, 0x44, 0x39, 0x17, 0x42, 0xCC, 0x44, 0x0D, 0x07, 0xB8, 0xFB, 0xFA, 0xA7, 0xB8, 0x73, 0xDA, 0x6A, 0x91, 0x1C, 0x8C, 0x88, 0xDD, 0x07, 0xFC, 0x15, 0xA6, 0x2C, 0xF8, 0x14, 0xA8, 0x1B };
var client1Proof = new byte[] { 0xCF, 0x8E, 0x03, 0x81, 0xBD, 0xDE, 0x3A, 0xFB, 0x51, 0x3C, 0x42, 0x46, 0xC6, 0x18, 0xC3, 0x7B, 0x2C, 0x5B, 0xDC, 0x23 };
var client1MatrixHash = new byte[] { 0x88, 0xFA, 0xBE, 0x4F, 0x97, 0x2D, 0xFB, 0x2D, 0x4C, 0xDA, 0xB0, 0x28, 0x58, 0x4C, 0x5D, 0x36, 0xBF, 0xCF, 0xDA, 0x96 };

// Client response 2

var client2Public = new byte[] { 0x61, 0xB2, 0xC7, 0xCE, 0x4E, 0x35, 0xD6, 0xD1, 0x8E, 0x12, 0x6E, 0x4B, 0x7E, 0xAF, 0x89, 0xFE, 0xAC, 0xA2, 0x67, 0x0D, 0x2C, 0x1D, 0x7C, 0x38, 0xD4, 0xF9, 0xDB, 0x45, 0x24, 0x19, 0x4D, 0x09 };
var client2Proof = new byte[] { 0x30, 0x98, 0xEA, 0xF7, 0x10, 0x8F, 0xD5, 0x7E, 0xEE, 0x59, 0xF0, 0xCF, 0xBF, 0xEF, 0xF6, 0xC0, 0x15, 0xCB, 0x13, 0xBC };
var client2MatrixHash = new byte[] { 0xDC, 0xFD, 0xFC, 0xFB, 0x8A, 0xD0, 0x2F, 0x3D, 0xE4, 0x8D, 0xF8, 0xE6, 0x1D, 0x5B, 0xB9, 0xD9, 0x36, 0x5E, 0xD0, 0x66 };

```


Goal is to find the formula to generate the client1MatrixHash and client2MatrixHash SHA1 hashes.

Note: Its not about creating another emulator. Its just for the interest in understanding the way this stuff works, as i find that pretty interesting
## Post #2
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-07-27T17:42:32+00:00
- Post Title: WoW Matrix Card hash algorythm

This is actually something I started looking at a long time ago and completely forgot about. 

In short, the client receives the CMD_AUTH_LOGON_CHALLENGE packet and generates it's SRP6 proof and the session key. It then, calculates all required cells using some simple math on the seed and the number of unused cells. Next, it MD5s the matrix salt and session key to generate a matrix key and initialises a SARC4 and a HMAC instance with it. Each time a digit is picked, the SARC4 instance encrypts the value and the result is appended to the HMAC buffer. Finally, when all digits have been entered, the HMAC instance is finalised with the resulting hash being the proof.

In terms of how Blizzard's server-side implementation works is anyone's guess, but since each card has a GUID I assume they have a formula for it - opposed to storing hundreds of bytes of digits as that'd be very costly. Whilst looking I didn't find any clues on this in the client (as to be expected) implementing your own custom process would be trivial.

I've re-implemented and documented the client-side implementation in C# [here](https://gist.github.com/barncastle/979c12a9c5e64d810a28ad1728e7e0f9) and have a (bad) working server proof of concept [here](https://github.com/barncastle/AIO-Sandbox/tree/matrix_card_demo). This code is intentionally written to mimic the client process. If I were to write a proper server implementation I'd trim this all down to 3 functions, one that calculates coords, one that returns a matrix value from a coord and one that hashes everything together in one go - all of which could be stateless and far cleaner.

I've also updated the [wiki's](https://wowdev.wiki/Login_Packet) packet structures. It'd be great if you could add implementation details for the pin and authenticator schemes too as it'd help others out in the future!
