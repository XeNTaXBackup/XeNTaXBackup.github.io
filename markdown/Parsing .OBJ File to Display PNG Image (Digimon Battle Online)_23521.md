## Post #1
- Username: Karlitaki
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Oct 25, 2014 11:32 pm
- Post datetime: 2021-02-27T06:39:34+00:00
- Post Title: Parsing .OBJ File to Display PNG Image (Digimon Battle Online)

Hey there! i want to help a fellow friend with his request so i decided to make a topic for him instead 

Topic Title: Parsing .obj file to display the pngs

Hello guys i need help to read a .obj file to display the png view or at last help to understand the archive structure so i can code a reading function.

Game: Digimon Battle Online

The file is here:
[https://mega.nz/file/EjJEiJ6a#tMnEd1dow ... wCWbeP8THY](https://mega.nz/file/EjJEiJ6a#tMnEd1dowk_DYBlqSORl06yWQxcWAFlwtwCWbeP8THY)

Appreciate any support!
## Post #2
- Username: aspadm
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Nov 26, 2015 3:43 am
- Post datetime: 2021-03-01T20:45:05+00:00
- Post Title: Parsing .OBJ File to Display PNG Image (Digimon Battle Online)

Oh, well, your friend just posted this on several forums.

In any case, looks like game has two formats: for tiles and objects, which are the parts of game level.
Provided example file is object file.

Object file structure (in the Kaitai Struct .ksy format):

```
  id: obj
  file-extension: obj
  endian: le
  encoding: ascii
seq:
  - id: magic
    contents: "DCOBJECT0.01"
  - id: unk
    size: 20
  - id: unk_a
    type: u2
  - id: unk_b
    type: u2
  - id: unk_c
    type: u2
  - id: unk_d
    type: u2
  - id: inds
    size: 400
  - id: len_a
    type: u4
  - id: buf_a
    size: len_a * 2
  - id: len_b
    type: u4
  - id: buf_b
    size: len_b * 2

```

Tile format:

```
  id: obj
  file-extension: obj
  endian: le
  encoding: ascii
seq:
  - id: magic
    contents: "DCTILE0.03"
  - id: unk_a
    type: u4
  - id: unk_b
    type: u4
  - id: len_a
    type: u4
  - id: buf_a_a
    size: len_a * 4
  - id: buf_a_b
    size: len_a * 4
  - id: buf_a_c
    size: len_a * 4
  - id: len_b
    type: u4
  - id: buf_b
    size: len_b * 2
  - id: inds
    size: 200
# there is must be another data, DIY (I don't have sample for tests)

```
