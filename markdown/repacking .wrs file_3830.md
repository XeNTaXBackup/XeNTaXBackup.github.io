## Post #1
- Username: GoldNugget
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 03, 2009 5:57 am
- Post datetime: 2009-11-03T06:25:48+00:00
- Post Title: repacking .wrs file

Hello, Ive been messing with a game andfound a tool (Gobread) that unpacks the files in a .wrs file. what i was wondering i s if there was a way to repack it with edited files to see if it worked.

Thanks,

GoldNugget
## Post #2
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2009-12-14T20:00:13+00:00
- Post Title: repacking .wrs file

This is my 16-Bit-ASM-code of my "BaggerSimulator"-WRS-file-module.
You are on your own to analyze it.

```
;21.07.2008	Begonnen
;06.12.2008	LZSS-Dekompression hinzu

wrs_mark2	textequ<"2SRW">
wrs_xor2=0a5h
wrs_mark3	textequ<"3SRW">
wrs_xor3=0b5h

;Dateiaufbau:
;wrs_mark
;for_each_file
; tbl_entry
; file_data	;LZSS-komprimiert
;endfor



wrs_struc	struct
	wrs_fname		db 20h dup(?)	;XOR 0B5h - gespeichert
	wrs_compsize	dd ?				;Big Endian
	wrs_uncompsize	dd ?				;Big Endian
wrs_struc ends


bagsim	proc
	mov cx,dword
	call read2
	.if dword ptr dat==wrs_mark2
		mov @@wrs_xor,wrs_xor2
	.else
		cmp dword ptr dat,wrs_mark3
		jnz nokng
	.endif
	call do_info
	call lzss_init
	call datcopy_dozlib
	mov ebp,dword
	.while 1
		call point
		mov cx,size wrs_struc
		call read2			;Keine Ende-Kennung!
		.break .if ax!=cx
			mov si,dx
			.repeat
				xor byte ptr[si],wrs_xor3
	@@wrs_xor equ byte ptr $-1
				inc si
			.until byte ptr[si]==0
			mov cx,length wrs_fname
			call dircreate
			mov esi,dat.wrs_compsize
			lea edi,[ebp+size wrs_struc]
			bswap esi
			lea ebp,[edi+esi]
			.continue .if carry?
				push ds di
				lds di,databufptr2
				mov ds:[di].z_stream.z_reserved,esi	;Dateigröße setzen für LZSS
				pop di ds
				call datcopy
	.endw
	ret

bagsim endp

```
