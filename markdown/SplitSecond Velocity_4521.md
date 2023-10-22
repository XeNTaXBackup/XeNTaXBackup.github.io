## Post #1
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-05-28T16:06:31+00:00
- Post Title: Split/Second Velocity

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-28T18:16:39+00:00
- Post Title: Split/Second Velocity

done just yesterday:
[http://aluigi.org/papers/bms/splitsecond.bms](http://aluigi.org/papers/bms/splitsecond.bms)

the bad thing is that the archives don't contain the filenames
## Post #3
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2010-05-29T14:59:37+00:00
- Post Title: Split/Second Velocity

have you managed to identify any of the files which get extracted? had a look at a fair few of them in a hex editor and cant work out what any of them are.
## Post #4
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-05-29T15:19:50+00:00
- Post Title: Split/Second Velocity

Found nothing so far which I know (okay only XML Files)
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-29T15:56:48+00:00
- Post Title: Split/Second Velocity

@twisted
quickbms adds an extension to the known file types, for the others you must take a look at them with a hex editor.
anyway no, I don't check the content of the extracted files because it's not my work
## Post #6
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2010-05-29T21:02:23+00:00
- Post Title: Split/Second Velocity

ok made a bit of progress, do you know if the zlss compression used is a specific variation? having a few problems reading it manually using other zlss decompression tools and recompressing it.
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-30T12:38:51+00:00
- Post Title: Split/Second Velocity

it's a classical lzss implementation, the one that you can find anywhere searching for lzss.c
## Post #8
- Username: masterX244
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 17, 2010 12:48 am
- Post datetime: 2013-07-11T15:05:06+00:00
- Post Title: Split/Second Velocity

Fo0r all researchers here that need samples: Demo of the game is available here: 
[http://www.gamefront.com/files/16509093 ... cond-Demo/](http://www.gamefront.com/files/16509093/SplitSecond-Demo/)


got a small chunk of progress in the deeper formats:
(got all in the resident.ark)
those with SXE as extension are certainly a sort of archive cause at the end this lurks around: (currently investigationg on those cause they seem promising)
FE_WC_menuBar_DXT5XUé¼   FE_WC_menuBar_obj_DXT51ù¼*   FE_WC_menuScrnBkgd_DXT5ÞjÆ   FE_WC_resultsBarArrowRed_DXT5f -G   FE_WC_resultsBarArrow_DXT5x	Â    HUD_PPicon_hexGlow_DXT5Í&›   HUD_vehicleStatsPip_DXT5¢Y¬   system_screen_texture002_RAWp}‘   system_screen_texture003_RAWºò   TEST_FloorLED_DXT5
there are FMOD sample banks inside, too;
gfx files i think link to Menu stuff >>EDIT: Verified by a random stumbling over Pure research >scaleform data
and there lurk many havok files around; but i need to dig deeeeper for more; (lost my havok viewer and some other utils due to Windows reinstall)
Edit: i think sometimes some stuff is cut off from files


when you extract residennt.ark sort by fileextension and look at the air, but and aud files; those contain filenames and other interesting referecnes
And in the unidentifiable dat files is a bunch of files with DDS magic singature but not at beginning; and they seem to be malformed somehow;

NExt Edit: snooped into the data in the dockspowerplays directory and in one XML i found sections like this:

```
      <worldmtx>
         <Row0 X="0.4856553" Y="0.0000000" Z="-0.8741504"/>
         <Row1 X="0.0000002" Y="1.0000000" Z="0.0000001"/>
         <Row2 X="0.8741504" Y="-0.0000002" Z="0.4856553"/>
         <Row3 X="-472.99265" Y="1.8311299" Z="-295.56323"/>
      </worldmtx>
      <EventParams>
         <Event idString="1224165754.3,1224165754.4,1250525011.686534244" id="0x25A08DFF">
            <Param Name="Trigger" Type="6" Value="0x2EE8C43E"/>
         </Event>
         <Event idString="1224165754.3,1224165754.4,1253008544.566076835" id="0xF156506E">
            <Param Name="Route" Type="5" Value="0x3A2807D3"/>
         </Event>
         <Event idString="1224165754.3,1224165754.4,1253008540.566076834" id="0x3688137A">
            <Param Name="Route" Type="5" Value="0xA3215669"/>
         </Event>
         <Event idString="1224165754.3,1224165754.4,1259230378.-1963406648" id="0xCC04291F">
            <Param Name="Route" Type="5" Value="0xA3215669"/>
         </Event>
         <Event idString="1224165754.3,1224165754.4,1259230344.-1963406649" id="0x5DD885A9">
            <Param Name="Route" Type="5" Value="0xD42666FF"/>
         </Event>
         <Event idString="1224165754.3,1224165754.4,1265977328.-543258727" id="0xB9AD6B2">
            <Param Name="Animation" Type="6" Value="0xED9603D1"/>
         </Event>
         <Event idString="1224165754.3,1224165754.4,1265977337.-543258726" id="0xD39FA0D0">
            <Param Name="Animation" Type="6" Value="0x916EC46C"/>
         </Event>
      </EventParams>
      <Timeline name="Powerplays\Timelines\docks\PA10_sideways_ship_launch_T.xml" id="1224165754.4" idCRC="0x6F3DFBB8">
         <transform>
            <Row0 X="1.0000000" Y="0.0000000" Z="0.0000000"/>
            <Row1 X="0.0000000" Y="1.0000000" Z="0.0000000"/>
            <Row2 X="0.0000000" Y="0.0000000" Z="1.0000000"/>
            <Row3 X="0.0000000" Y="0.0000000" Z="0.0000000"/>
         </transform>
      </Timeline>
      <Ambient>
         <NODE_FACTORY Type="0" NumberOfInstances="0" NumberOfChildren="0">
            <STATIC_POSITION>
               <node_transform>
                  <Row0 X="1.0000000" Y="0.0000000" Z="0.0000000"/>
                  <Row1 X="0.0000000" Y="1.0000000" Z="0.0000000"/>
                  <Row2 X="0.0000000" Y="0.0000000" Z="1.0000000"/>
                  <Row3 X="0.0000000" Y="0.0000000" Z="0.0000000"/>
               </node_transform>
            </STATIC_POSITION>
         </NODE_FACTORY>
      </Ambient>
   </Powerplay>
```

3rd edit: poking in the rdata section of the exe gives off some interesting stuff. strings and some filereferences; 
especially near offset 0x37a60

4th Edit: diggin in the environment ark files there are cxf-file; prolly in others, too: those are shader archives;
And i think they mess with the 00-Bytes; noticed most are 0x20


noticed a pattern of 0x and random hex and then alter a 2x with the same; sometimes there are a 1x befiore the 2x and a 3x after. i think thats the "filename" of the shaders category. I think those correlate somehow with the XMLs in xxx-powerplays.ark data in the root of data dir
before those hex strings is a byte pattern of 0x0b 20 20 20 20; that 20 could be a substitute for 0x00 but im not sure on this...
Those 0x20 are there to confuzzle us somehow;
and i have the feeling the Extraction is messed a bit in some circumstances....
look at 00000145.xml (approx 10MB) out of resident.ark; theres a very probable cutoff at the end...
0000147b.ird looks a bit different than the other uird-files, too; seems that there is some stuff missing, too
EDITS again: 
RDH-files end always with DNE; same with cxf; could be the same format but not sure again
We need more users poking inside those files to get progress to know what is what
got a trace at the tail of the sxe files; between each strings are 8 bytes; the second 4 contain the sting size at the first position
Som e SXEs have a pointer to the first file at offset 12; you need to add 20_dec to the offset to reach the coorect point;


Cars are certainly in Resident.ark; the dats with approx 3 MB size and a DDS marker at offset 0x04 are just a chain of DDses stuck together; and a integer marks the length of em
Decoder code in Java: 



```
                while(!(rf.length()==rf.getFilePointer()))
                {
                    int b1 = rf.readUnsignedByte();                       //java reads ints thoe other way round than these ar estored so i ahd to do that manually
                    int b2 = rf.readUnsignedByte()*256;
                    int b3 = rf.readUnsignedByte()*256*256;
                    int b4 = rf.readUnsignedByte()*256*256*256;
                    int i = b1+b2+b3+b4;
                    long fo = rf.getFilePointer();
                    byte[] datadump = new byte[i];
                    rf.read(datadump);
                    RandomAccessFile trg = new RandomAccessFile(filename+".id"+fo+".dds", "rw");
                    trg.write(datadump, 0, i);
                    trg.close();
                }
```


First one DDS has all 0x00s in the header repalced with 0x20's so you need to correct that manually atm; only 0x20 to keepü is at offset 0x4c 

I think SXE is cracked; current research results are
First replace all 0x20s until first DDS signature with 0x00 to deobfuscate the header; the mangling seems not to be a XOR or a AND

```
MAGIC SXET (0x53584554)
dword unknown //constant 0x0C000000
dword NULL,
dword headerSize //Size after this
dword FileEntries
dword unknown
dword padding
dword padding
dword unknown
dword offsetToTailOffset //not sure on this yet
FileMetaRecord  FMR[FileEntries]
dword OffsetToTail //starts at sizeMarker of first file
dword padding //0x00000000
dword fileEntries2 //identical with fileEntries
dword oddPointer //points to OffSetToTail
FileOffsetRecord FOR[FileEntries]
dword unknown
DataBlock //goes until TailStart
FooterEntry FET[FileEntries]



FileMetaRecord (size=16 dwords or 64 bytes)
  dword padding //0x00
  dword ID
  dword MARKER (0xFFFF0000)
  dword unknown
  dword unknown
  dword unknown
  dword dds_width
  dword dds_height
  dword unknown
  dword padding[7] //0x00000000 all the time
  

FileOffsetRecord (12byte or 3 DWORDs)
  dword unknown
  dword NULL
  dword offsetFromDataBlockStart
  
  
  
  //footer 
  
  
//  marker MN2C (0x4D4E3243)
//  Repeating until end:
FooterEntry
  dword id //links to header
  dword namesize
  String name //länge nach Size

```

Currently writing the unpacker to validate; will upload it when done

[http://nplusc.de/unSXE.jar](http://nplusc.de/unSXE.jar)
Link to my unpacker util
(usage unSXE.jar path/to.sxe after replacing all 0x20s with 0x00 in the header; youll get a OutOfMemoryError if you forget to do that)



Theory regarding the CXF-s and the RDH the Stirngs that look like hex are common between those files; i think the RDH is a sort of header or file descriptor for those CXF files
## Post #9
- Username: masterX244
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 17, 2010 12:48 am
- Post datetime: 2013-08-21T21:23:23+00:00
- Post Title: Split/Second Velocity

wish i knew how the strings wthat look like hex could be detected in the cxf, the rdh and ird files. couldd have written  a tool that could have found the patterns in those files cause they arent very obvious... sometimes the files are stored next to each other and other times they are randomly spread apart...
