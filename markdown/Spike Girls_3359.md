## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-02-18T05:07:50+00:00
- Post Title: Spike Girls

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-02-18T20:15:39+00:00
- Post Title: Spike Girls

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-02-23T13:09:53+00:00
- Post Title: Spike Girls

I ran the program signsrch on the main exe and there are several anti debug parts to this program can anyone tell me the
best way to get around this please.

```
  1755 m_huffman.c (from doomsday) [float.be.1024]
  1756 m_huffman.c (from doomsday) [double.le.2048]
  1757 m_huffman.c (from doomsday) [double.be.2048]
  1758 anti-debug: INT 41h Debugger Notification [..9]
  1759 anti-debug: INT 3's with SoftICE's I3HERE [..20]
  1760 anti-debug: BCHK BoundsChecker interface [..13]
  1761 anti-debug: ICECream detection (Windows 95). [..26]
  1762 anti-debug: Detect SoftICE VxD or SoftICE GFX VxD [..25]
  1763 anti-debug: Detect WinICE handler using INT 68h (V86) since SoftICE hooks
 [..8]
  1764 anti-debug: another INT 68h handler [..28]
  1765 anti-debug: Detect and crash SoftICE with an illegal form of the instruct
ion CMPXCHG8B [..4]
  1766 anti-debug: WINICE.BR [..9]
  1767 anti-debug: SOFTICE1 [..8]
  1768 anti-debug: Dongle protection [..3]
  1769 anti-debug: IsDebuggerPresent [..17]
  1770 anti-debug: SOFTWARE\\NuMega [..16]
  1771 anti-debug: SYSTEM\\CurrentControlSet\\Services\\IceExt [..41]
  1772 anti-debug: CheckForSoftICEBP [..18]
  1773 anti-debug: W32Dasm bug [..7]
  1774 anti-debug: Detection from SafeDisc, this is the content of secdrv.sys [.
.10]
  1775 anti-debug: Detect single-stepping and turn off the monitor (1) [..13]
  1776 anti-debug: Detect single-stepping and turn off the monitor (2) [..13]
  1777 anti-debug: Exit the program if its being debugged by checking execution
timing [..19]
  1778 anti-debug: UnhandledExceptionFilter protection [..11]
  1779 anti-debug: anti-VMWare [..21]
  1780 anti-debug: PEB!IsDebugged [..12]
  1781 anti-debug: PEB!IsDebugged (2) [..11]
  1782 anti-debug: PEB!NtGlobalFlags [..14]
  1783 anti-debug: Heap flags [..14]
  1784 anti-debug: Vista anti-debug (no name) [..29]
  1785 anti-debug: NtSetInformationThread (partial) [..9]
  1786 anti-debug: kernel32!CloseHandle and NtClose [..20]
  1787 anti-debug: Timestamp counters [..44]
  1788 anti-debug: Popf and the trap flag [..9]
  1789 anti-debug: Stack Segment register [..4]
  1790 anti-debug: Debug registers manipulation (1) [..28]
  1791 anti-debug: Debug registers manipulation (2) [..55]
  1792 anti-debug: IsIceSIDT [..26]
  1793 anti-debug: Rose's TRAP #1 [..46]
  1794 anti-debug: Rose's TRAP #3 [..10]
  1795 anti-debug: Rose's TRAP #4 (1) [..14]
  1796 anti-debug: Rose's UAC [..24]
  1797 anti-debug: Softice \\.\SICE [..9]
  1798 anti-debug: Softice \\.\NTICE [..10]
  1799 anti-debug: Softice \\.\SIWVID [..11]
  1800 anti-debug: Softice C:\siw95\nmtrans.dll [..21]
  1801 anti-debug: Softice C:\ntice\nmtrans.dll [..21]
  1802 anti-debug: Softice NmSymIsSoftICELoaded [..21]
  1803 anti-debug: SEH handler trick [..23]
  1804 anti-debug: SEH handler trick (alternate way) [..24]
  1805 anti-debug: Obfuscated RDTSC [..24]
  1806 anti-debug: OllyDbg Instruction Prefix Detection [..30]
  1807 anti-debug: PeID GenOEP Spoofing [..48]
  1808 anti-debug: PeID OEP Signature Spoofing [..20]
  1809 anti-debug: ProcDump PE Header Corruption [..35]
  1810 anti-debug: RDG OEP Signature Spoofing [..6]
  1811 anti-debug: RDTSC Instruction Debugger Latency Detection [..15]

```


I attached the full results to this post if it could help anyone tell me what was used on the games main data files.
[sg.rar](https://xentaxbackup.github.io/file/1889_sg.rar)
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-02-26T02:02:54+00:00
- Post Title: Spike Girls

Sorry for that last post here is the real result.
 offset   num  description [bits.endian.size]
 --------------------------------------------
 003524c0 190  Blowfish bfp table [32.le.72]
 00352508 192  Blowfish ks0 table [32.le.1024]
 00352908 194  Blowfish ks1 table [32.le.1024]
 00352d08 196  Blowfish ks2 table [32.le.1024]
 00353108 198  Blowfish ks3 table [32.le.1024]
 0016e159 289  MD5 digest [32.le.272&]
 0024c298 307  SHA1 / SHA0 / RIPEMD-160 initializatio
 00352480 309  padding used in hashing algorithms (0x
 003524e0 325  Haval hash pass2 [32.le.128&]
 003524c0 1300 Haval init [32.le.32&]
 00352560 1302 Haval mc3 [32.le.128]
 003525e0 1304 Haval mc4 [32.le.128]
 00352660 1306 Haval mc5 [32.le.128]
 00352640 1452 HAVAL1_DS [32.le.32]
 003525c0 1454 HAVAL2_DS [32.le.32]
 00352508 1562 Blowfish_s_init [32.le.4096]
 001962e3 1768 anti-debug: Dongle protection [..3]
 00341d26 1769 anti-debug: IsDebuggerPresent [..17]
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-02-27T22:20:57+00:00
- Post Title: Spike Girls

ok, the decoding is the simple decreasing of the byte if its lower bit is set (byte AND 1) and the increasing for the rest.
this type of obfuscation is applied only to the amount of bytes specified in the second 32 bits number of the file (offset 4, I don't know the meaning of the first one because I have not debugged or analyzed the game).
the tool can also decode the name of the folders if the second argument is a dot, example: "sgpdec.exe dj_rukwedccdfq ." which shows the decoded string "ev_soundeffect".

[http://aluigi.org/papers/sgpdec.zip](http://aluigi.org/papers/sgpdec.zip)
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-02-27T22:54:06+00:00
- Post Title: Spike Girls

are you aluigi?
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-02-27T23:05:27+00:00
- Post Title: Spike Girls

yes it's me :)
I have updated also this thread in case other people were interested to this game
