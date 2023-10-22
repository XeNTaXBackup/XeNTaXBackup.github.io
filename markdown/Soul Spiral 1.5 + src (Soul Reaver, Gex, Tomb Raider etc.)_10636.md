## Post #1
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-07-27T13:35:21+00:00
- Post Title: Soul Spiral 1.5 + src (Soul Reaver, Gex, Tomb Raider etc.)

Soul Spiral is a utility for unpacking the contents of the bigfile.dat format used by many Crystal Dynamics games based on the engine from Gex. It can also read the pill.big data file from the PC and Playstation versions of Blood Omen.


>>[DOWNLOAD SOUL SPIRAL](https://www.thelostworlds.net/Software/Soul_Spiral.html)<<

Soul Spiral's only function is to unpack content from a monolithic data file. It is not an image/model viewer or a sound file player. Once the files are extracted, other tools (such as ModelEx, The Eye of RAW, and The Sound of Her Wings) are necessary to actually do anything with any of the files. Because the game assets are usually in a proprietary format, not all of them have been reverse-engineered well enough to do anything with yet.

If there is not a utility listed on The Lost Worlds for the file type you are interested in, there is probably nothing available to you to open it - some common examples are the textures and models from Soul Reaver 2 and Defiance.

Soul Spiral requires at least version 2.0 of the .NET Framework to be installed on your PC. It can be obtained from the Microsoft website or Windows Update.

Usage:

    Open bigfile.dat (or, for Blood Omen, pill.big).
    Soul Spiral will attempt to automatically determine the game it's from. If it is successful, you should probably just click OK. If it's NOT successful, pick the best match from the list and click OK. If it works, please email me and let me know which game it worked with and what Soul Spiral says in the "Size (Bytes)" field of the main window.
    Browse the contents and either export a single item or all of them using the Export menu.
    Make use of the contents in another utility.

Supported Formats:

Gex (Playstation and Sega Saturn) - uncompressed files only, no hashed name lookups.
Blood Omen (all Playstation and PC releases) - mostly-complete hashed name lookups.
Gex 2 (Playstation) - uncompressed files only, no hashed name lookups.
Akuji: The Heartless (Playstation) - uncompressed files only, no hashed name lookups.
Gex 3 (Playstation) - uncompressed files only, no hashed name lookups.
Soul Reaver Lighthouse Demo (Playstation) - uncompressed files only, no hashed name lookups.
Soul Reaver Fire Glyph Demo (Playstation and PC).
Soul Reaver (all Playstation and PC releases).
Soul Reaver (Dreamcast) - no hashed name lookups.
Soul Reaver 2 Air Forge Demo (Playstation 2) - no hashed name lookups.
Soul Reaver 2 (all Playstation 2 and PC retail releases) - incomplete hashed name lookups.
Legacy of Kain: Defiance (all Playstation 2 and PC releases) - incomplete hashed name lookups.
Tomb Raider: Legend Demo (Playstation 2) - no hashed name lookups.
Tomb Raider: Legend (Playstation 2 and PSP) - no hashed name lookups.

Currently Unsupported Formats:

Blood Omen 2 (all releases) - uses a completely different data file format.
Legacy of Kain: Defiance (all Xbox releases) - uses an unsupported variation of the bigfile format.
Legacy of Kain: Defiance (downloadable PC release) - uses an encrypted bigfile format.
Tomb Raider: Legend (all Xbox/Xbox 360/PC releases) - uses an unsupported variation of the bigfile format.

Known Issues:

    The save/discard buttons in the hex editor are not very good (this is my fault, not Andrew's). The green one saves changes, and the red one discards them.
