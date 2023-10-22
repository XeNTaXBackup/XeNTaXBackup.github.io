## Post #1
- Username: brienj
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2013-04-12T21:52:58+00:00
- Post Title: My source code for that C64 music player

I composed some tunes in 2011, 2012 on the C64 and coded a new presenter for those. 
This is the source code, Relaunch64 style. 

The code in action:
[http://www.youtube.com/watch?v=GmhB-is33NU](http://www.youtube.com/watch?v=GmhB-is33NU)

Or used on an old tune from 1992:
[http://www.youtube.com/watch?v=LqbKf4BEYSo](http://www.youtube.com/watch?v=LqbKf4BEYSo)


```
.import binary "e:\c64\work\sprgrey.bin"

.pc = $5000 "sprites2"
.import binary "e:\c64\work\sprtest.bin"

.pc = $6000 "logo"
.import binary "e:\c64\work\logo_xntx_koala.bin"

.pc = $4500 "text"
.import binary "e:\c64\work\text.bin"

.pc = $4800 "chars"
.import binary "e:\c64\work\chars.bin" 


.pc = $1000 "music"
.import binary "e:\c64\work\stroyka_1992.bin" 

//.pc =$0801 "Basic Upstart Program"
:BasicUpstart($8800)
.var kernel_clearscreen = $e544
.var cia_interrupt_control = $dc0d
.var cia_nmi_control = $dd0d
.var music_init = $1000
.var music_play = $1003
.var border_color = $d020
.var back_color = $d021
.var screen_control_reg1 = $d011
.var raster_interrupt = $d012
.var interrupt_register = $d01a



//;----- DC0D: Paragraph @CIA Interrupt Control Register (Read IRQs/Write Mask)@ -----
// DDOD: CIA Interrupt Control Register (Read NMls/Write Mask)
// FFFE-FFFF: Execution address of interrupt service routine.
// D012: Read: Current raster line (bits #0-#7).
// D012: Write: Raster line to generate interrupt at (bits #0-#7).
//---------------------------------------------------------

.pc = $8800 "main program"

 		   jsr kernel_clearscreen
              //ssei
              
              
//------init irq stuf--------------------                               
                   
                       
        
  // this makes sure bit 7 is clear (8th bit of raster-line pointer)                       
                    
	  lda cur_beat_col
              sta border_color                         
//---------------			init music---------------
              lda #$00                          
              tax                               
              tax                               
              jsr music_init
               
              lda #$00   	// reset timer
 	  sta $dc0e   // set 60 hz
             sta $dc0f     // enable tod
              sta $dc08
              sta $dc09
              sta $dc0a
//	  sta $dc0b
              lda #$01
              sta tbreak                         
 //             lda #$00                          
 //             sta $3fff                         

  
// ---------------------- 	general sprite stuff-----



 	//-----------------------------DATA pointers voor channel sprites             
              lda #$20                          
              sta $07f8      // sprite 0 data pointer in blocks of 64 , $3c = 0f00                   
              sta $07f9      // sprite 1 data pointer in blocks of 64 , $3c = 0f00                    
              sta $07fa      // sprite 2 data pointer in blocks of 64 , $3c = 0f00	
              ldx #$23  
              stx $07fb      // sprite 3 data pointer in blocks of 64 , $3c = 0f00
		  inx 
              stx $07fc      // sprite 4 data pointer in blocks of 64 , $3c = 0f00                                   
		  inx 
              stx $07fd      // sprite 5 data pointer in blocks of 64 , $3c = 0f00                                   
		  inx 
              stx $07fe      // sprite 6 data pointer in blocks of 64 , $3c = 0f00                                   
		  ldx #$22 
              stx $07ff      // sprite 7 data pointer in blocks of 64 , $3c = 0f00 
 	//-----------------------------DATA pointers voor scroll sprites             
                                  
// ------------------		general screen and vic setup colours for bitmap graphics
              	
                  lda $dd00  // get VIC bank Port A, serial bus access, status
			sta std2   // store default status
			and #$fc  // keep only those upper bits, but not the lower two
			ora #$02  // set bit 1 (not 0) --> 4000
			sta stdbm  // store it in a temp value
			sta $dd00  // and set it
			lda $d018 // Memory setup register. 
			and #$f3  // clear bit 2 and 3 
			ora #$02  // set bit 1 (whatever bit 0) to get 001 in bits of 3-1, to point to 0800 for character memory
			sta std   // store it
			sta $d018 // set it
			ldx #$00
fillc:
			lda $8328,x // store the colours at the right pos, this assumes that d018 is set to default ($19) later on, to have the SCREEN memory (the bytes!) at pos $0400 relative to vic bank   
			sta $d800,x
			lda $8428,x
			sta $d900,x
			lda $8528,x
			sta $da00,x
			lda $8628,x
			sta $db00,x
			lda $7f40,x
			sta $4400,x
//			lda $8040,x
//			sta $4500,x
			lda $8140,x
			sta $4600,x
			lda $8240,x
			sta $4700,x


			inx
			bne fillc
 	//-----------------------------DATA pointers voor scroll sprites      
              lda #$42                          
              sta $47f8      // sprite 0 data pointer in blocks of 64 , $3c = 5000 
              lda #$41                  
              sta $47f9      // sprite 1 data pointer in blocks of 64 , $3c = 5000
              lda #$40                    
              sta $47fa      // sprite 2 data pointer in blocks of 64 , $3c = 5000	
              ldx #$43  
              stx $47fb      // sprite 3 data pointer in blocks of 64 , $3c = 5000
		  inx 
              stx $47fc      // sprite 4 data pointer in blocks of 64 , $3c = 5000                                   
		  inx 
              stx $47fd      // sprite 5 data pointer in blocks of 64 , $3c = 5000                                   
		  inx 
              stx $47fe      // sprite 6 data pointer in blocks of 64 , $3c = 5000                                   
		  ldx #$42 
              stx $47ff      // sprite 7 data pointer in blocks of 64 , $3c = 5000                          
	//----------------------------
			lda #<scrolltext   // reset the charpointer for the scroller
			sta $bd
			lda #>scrolltext
			sta $be
		   lda #$00
		   sta counter1
		   lda spr_col_sp
		   sta counter2
   		   lda spr_sc_cols
   		   sta spr_col_cur
	// get the text on screen
		   ldx #$00
g_1:
		   lda title_op_txt, x
		   cmp #$00
		   beq n_1
		   sta $4577, x
		   inx
		   bne g_1
n_1:		   			 
		   ldx #$00
g_2:
		   lda composer_op_txt, x
		   cmp #$00
		   beq n_2
		   sta $463f, x
		   inx
		   bne g_2
n_2:		   			 
		   ldx #$00
g_3:
		   lda time_txt, x
		   cmp #$00
		   beq n_3
		   sta $473d, x
		   inx
		   bne g_3
n_3:		   		
		   ldx #$00
g_4:
		   lda title_txt, x
		   cmp #$00
		   beq n_4
		   sta $45c5, x
		   inx
		   bne g_4
n_4:		   	
		   ldx #$00
g_5:
		   lda composer_txt, x
		   cmp #$00
		   beq n_5
		   sta $468d, x
		   inx
		   bne g_5
n_5:
		   ldx #$00
g_6:
		   lda ras_txt, x
		   cmp #$00
		   beq n_6
		   sta $4720, x
		   inx
		   bne g_6
n_6:
		   ldx #$00
g_7:
		   lda sid_op_txt, x
		   cmp #$00
		   beq n_7
		   sta $4730, x
		   inx
		   bne g_7
n_7:	
		   ldx #$00
g_8:
		   lda sid_v_text, x
		   cmp #$00
		   beq n_8
		   sta $4735, x
		   inx
		   bne g_8
n_8:						
              jsr tprint 	// print the start time value				   				
              sei
              lda #<irqsc1                          
              sta $0314                         
              lda #>irqsc1                          
              sta $0315            
              lda #$7f                          
              sta cia_interrupt_control                         
            //  sta cia_nmi_control
              lda #$1b
              sta screen_control_reg1
              lda #$01                          
              sta interrupt_register  // enables raster interrupts, disables sprite and lightpen
       //       lda #$35                          
        //      sta $01      	// ram visible at two areas                   
              cli            // start interrupts again                   
              jmp *                         

//--------------------------IRQ START--------------------------------------------------------------------------------------------------------
 irqsc1:                       
 
              asl $d019 
//--------------------------RASTER WAIT 1-------------------------------------------------------------------------------------------------------
	  lda #$10                          
 ra_loop0:
              cmp $d012
              bne ra_loop0  
                     
//              lda #$72                          
//              sta $d012                         
              jsr outputtime
              lda $d012
              sta raster_pos         
	         jsr music_play 	// play next music frame
              lda $d012		// get the raster_time needed
              sec
              sbc raster_pos         
		   sta raster_pos
		   and #$0f			// select the lower nibble
	         jsr hexchar		
		   sta $472a		// okay put the character there
		   lda raster_pos
		   lsr			// get the high nibble
		   lsr
		   lsr
		   lsr
		   jsr hexchar
		   sta $4729		// okay put the character there
								
			lda stdbm  // flip to $4000 again for bank start
			sta $dd00
			lda #$19   // start character/bitmap mem $2000 from bank start = 6000: this is the bitmap memory! And set screen memory to $0400 relative
			sta $d018
			lda $d011  // Screen control register #1. Bitmap mode
			ora #32
			sta $d011
			lda $d016  //Screen control register #2. MultiColour
			ora #16
			sta $d016
// scroll sprites setup==============================
              ldy #$08                          
              sty $d01c      // Sprite multicolor mode register, set none to multicolor
              ldy #$00                            
              sty $d01d	// no expansion in x
              sty $d017      // no expansion in y             
	//-------------------- x y pos
              ldy #$00                          
              sty $d010      // sprites x position 8th bit. set to 0 for sprite 0-2                   
              ldx #$00
a3:
              lda spr_sc_xpos, x                                       
              sta $d000,x   // sprite 0-7 x
              inx
              lda spr_sc_xpos, x                                       
              sta $d000,x   // sprite 0-7 y
              inx
              cpx #$10
              bne a3
	//-----------------------------scroll sprites colours 
              lda spr_c0                         
              sta $d025      // sprites colour 0                   
              ldx spr_c1                                       
              stx $d026      // sprites colour 1                   
		   lda spr_col_cur
		   dec counter2
		   bne set_spr_col
		   lda spr_col_sp
		   sta counter2	
		   ldx counter1
		   lda spr_sc_cols,x
		   sta spr_col_cur
		   inc counter1
		   cpx #$05
		   bne set_spr_col
		   ldx #$00
		   stx counter1	
set_spr_col:			
              ldx #$07       // counter to 8 sprites   
an2:
              sta $d027,x      // sprite 0 extra colour                   
              dex
              bne an2
		   sta $d027,x
              lda #$07                          
              sta $d015  	// sprite enable register, enable first 3  
		
           
// end of scroll sprites setup===================	
	//-------------------scroll: define character

//			lda #$01
//			sta border_color
		      
			ldx #$00
in_loop:
			ldy spr_dat_pos,x
			clc 
			rol dumspr,x  // rotate dummy sprites
			txa
			pha
			tya
			tax
			rol $5002, x
			rol $5001, x
			rol $5000, x
			rol $5042, x
			rol $5041, x
			rol $5040, x
			rol $5082, x
			rol $5081, x
			rol $5080, x
			pla
			tax
			inx
			cpx #$08
			bne in_loop
			lda bitcheck 	// at zero ? all bits moved?
			beq rotate		// Yes? go on to get new char
			lsr bitcheck
			jmp exit_loop
rotate:
			
			eor #$80
			sta bitcheck
			ldy #$00		// okay, retrieve char data for new char
			lda ($bd),y   	// get the current scroll text character
			bne go_on
			lda #<scrolltext   // reset the charpointer for the scroller
			sta $bd
			lda #>scrolltext
			sta $be
			lda ($bd),y   	// get the current scroll text character
						
go_on:			
			inc $bd 		// check whether we looped to update the 16-bit pointer
			bne go_on_l1
			inc $be
go_on_l1:
						// char * 8

			sta charpoint
			sta $b4
			and #$00
			sta $b5 			 
			clc			// multiply by 8 
			rol $b4
			rol $b5
			clc
			rol $b4
			rol $b5
			clc
			rol $b4
			rol $b5
			// okay b4/b5 holds the pointer to the character data relative
			lda #$48  		// make it an absolute pointer
			clc
			adc $b5
			sta $b5
			ldx #$00
in_loop2:
			lda ($b4), y  	// get the character data byte
			sta dumspr, x
			inc $b4 		// check whether we looped to update the 16-bit pointer
			bne loop2  
			inc $b5
loop2:
			inx
			cpx #$08
			bne in_loop2 
exit_loop:					
//			lda #$00
//			sta border_color

//--------------------------RASTER WAIT 2-------------------------------------------------------------------------------------------------------
	  lda #$72	
ra_loop1:
              cmp $d012                          
              bne ra_loop1 
irqsc2:
              lda #$01
		   ldx #$05	
             jsr nopdelay   // time the raster duration
  //            nop
   //           nop    
 		   sta back_color
		   sta border_color
		   ldx #$01
              jsr nopdelay   // time the raster duration       
		   lda #$00
		   sta border_color			
		   sta back_color
          
			lda std	// go back to standard  screen mem position 0000 relative of bank
			sta $d018
			
			lda $d011	// make sure text mode is back on by clearing bit 5		
			and #223
			sta $d011
			lda $d016  // clear bit 4 to disable multicolour mode
			and #239
			sta $d016	
					   jsr txt_scroll                             
//--------------------------RASTER WAIT 3-------------------------------------------------------------------------------------------------------
	  lda #$9c                          
ra_loop2:
              cmp $d012
              bne ra_loop2
irqsc3:
           //   jsr music_play

 // channel sprites setup==============================
              ldy #$ff                          
              sty $d01c      // Sprite multicolor mode register, set all to multicolor                          
              ldy #$78
              sty $d01d	// x-expand sprites 3-6
              ldy #$f8
              sty $d017      // y-expand sprites 3-7             
	//-------------------- x y pos
              ldy #$07                          
              sty $d010      // sprites x position 8th bit. set to 1 for sprite 0-2                   
              ldx #$00
a2:
              lda spr_ch_xpos, x                                       
              sta $d000,x   // sprite 0-7 x
              inx
              lda spr_ch_xpos, x                                       
              sta $d000,x   // sprite 0-7 y
              inx
              cpx #$10
              bne a2
                 
	//-----------------------------channel sprites colours 
              lda spr_c0                         
              sta $d025      // sprites colour 0                   
              ldx spr_c1                                       
              stx $d026      // sprites colour 1
              lda spr_sc
              ldx #$07       // counter to 8 sprites   
an1:
              sta $d027,x      // sprite 0 extra colour                   
              dex
              sta $d027,x      // sprite 0 extra colour    
              bne an1
                                 
               lda #$ff                          
              sta $d015  	// sprite enable register, enable all 8             
// end of channel sprites setup===================	
//-----------------------------------------------------------------sprite channel roll start---------------------------------------------
		   ldx #$02
roll_mus_spr:
		   clc
	         rol $08f2            // roll sprite a	   
	         rol $08f1
		   rol $08f0
	         rol $0932            // roll sprite b	   
	         rol $0931
		   rol $0930
	         rol $0972            // roll sprite c	   
	         rol $0971
		   rol $0970
	         rol $09b2            // roll sprite d	   
	         rol $09b1
		   rol $09b0
		   rol $09f2            // roll sprite e	   
               rol $09f1
		   rol $09f0
		   clc
	         rol $08da            // roll sprite 	   
	         rol $08d9
		   rol $08d8
	         rol $091a            // roll sprite 	   
	         rol $0919
		   rol $0918
	         rol $095a            // roll sprite c	   
	         rol $0959
		   rol $0958
	         rol $099a            // roll sprite d	   
	         rol $0999
		   rol $0998
	         rol $09da            // roll sprite e	   
	         rol $09d9
		   rol $09d8
		   clc
	         rol $08c2            // roll sprite 	   
	         rol $08c1
		   rol $08c0
	         rol $0902            // roll sprite 	   
	         rol $0901
		   rol $0900
	         rol $0942            // roll sprite c	   
	         rol $0941
		   rol $0940
	         rol $0982            // roll sprite d	   
	         rol $0981
		   rol $0980
	         rol $09c2            // roll sprite e	   
	         rol $09c1
  		   rol $09c0
  		   clc
		   dex
		   beq roll_end
		   jmp roll_mus_spr
roll_end:
              ldx $1084
              cpx #$09                          
              bne ir1sc1_s1                        
              lda #$20
              ldx #$02
              stx spr_rotco1
              jmp ir1sc1_s1b
ir1sc1_s1:                          
		   ldx spr_rotco1
		   cpx #$00
		   beq ir1sc1_s1a
		   dec spr_rotco1	
ir1sc1_s1a:			
              lda $08f2
              ora spr_ctrot, x  // sprite colour in
              sta $08f2
    		   lda #$21                          
 
ir1sc1_s1b:
              sta $07f8
              ldx $1085                         
              cpx #$09                          
              bne ir1sc1_s2
              lda #$20
              ldx #$02
              stx spr_rotco2              
              jmp ir1sc1_s2b
ir1sc1_s2:                          
		   ldx spr_rotco2
		   cpx #$00
		   beq ir1sc1_s2a
		   dec spr_rotco2	
ir1sc1_s2a:
              lda $08da
              ora spr_ctrot, x     // sprite colour in
              sta $08da
              lda #$21   
ir1sc1_s2b:          
              sta $07f9
              ldx $1086                         
              cpx #$09                          
              bne ir1sc1_s3                        
              lda #$20
              ldx #$02
              stx spr_rotco3                 
              jmp ir1sc1_s3b
ir1sc1_s3:                          
		   ldx spr_rotco3
		   cpx #$00
		   beq ir1sc1_s3a
		   dec spr_rotco3	
ir1sc1_s3a:		
              lda $08c2
              ora spr_ctrot, x   // sprite colour in
              sta $08c2
              lda #$21                          

ir1sc1_s3b:                          
              sta $07fa

//-----------------------------------------------------------------sprite channel roll end---------------------------------------------
 
              lda #$21                          
              ldx $1084 		// goattracker on/off voice 1                       
              cpx #$09                          
              bne ir1sc3_s1                        
              lda #$20
ir1sc3_s1:                          
              sta $07f8
              lda #$21                         
              ldx $1085                        
              cpx #$09                          
              bne ir1sc3_s2                        
              lda #$20
ir1sc3_s2:                          
              sta $07f9
              lda #$21                          
              ldx $1086                         
              cpx #$09                          
              bne ir1sc3_s3                        
              lda #$20
ir1sc3_s3:                          
              sta $07fa

		   
		
		   lda $141f
		   cmp beat_trig
		   bne beat_c2
              lda $1420  		// goattracker on/off voice 1  
              cmp #$fe
              bne beat_up		   
beat_c2:
		   lda $1426
		   cmp beat_trig
		   bne beat_c3
              lda $1427  		// goattracker on/off voice 2  
              cmp #$fe
              bne beat_up		   
beat_c3:
		   lda $142d
		   cmp beat_trig
		   bne beat_down
              lda $142e  		// goattracker on/off voice 3  
              cmp #$fe
              beq beat_down		   
beat_up:      
		   lda #$00
 		   sta cur_beat_col_p			   
beat_down:
		   ldx cur_beat_col_p
		   lda beat_col, x
		   sta cur_beat_col
		   beq b_exit
		   inx
		   stx cur_beat_col_p
b_exit:		
              jsr highlight_bar

//--------------------------RASTER WAIT 4-------------------------------------------------------------------------------------------------------
	  lda #$cf                          
ra_loop3:
              cmp $d012
              bne ra_loop3
 irqsc3b: 
              lda #$01
		   ldx #$05	
             jsr nopdelay   // time the raster duration
  //            nop
   //           nop    
 		   sta back_color
		   sta border_color
		   ldx #$06
              jsr nopdelay   // time the raster duration
              nop
              nop       
		   lda #$00
		   sta border_color			
		   sta back_color

//--------------------------RASTER WAIT 5------------------------------------------------------------------------------------------------------- 
	  lda #$dd                          
ra_loop4:
              cmp $d012
              bne ra_loop4             
irqsc4:
		   lda #$01
 		   ldx #$05	
              jsr nopdelay   // time the raster start
   		   sta back_color
		   sta border_color
		   ldx #$06	
              jsr nopdelay   // time the raster duration
              nop
              nop       
		//   lda cur_beat_col
		   lda #$00
		   sta border_color
		   sta back_color

              lda std2    // go back to standard bank of 0000 to re-enable sprites
		   sta $dd00 
		   lda $d018 // switch to char rom 
              ora #$05
              sta $d018   
//--------------------------RASTER WAIT 6------------------------------------------------------------------------------------------------------- 
	  lda #$f9                          
ra_loop5:
              cmp $d012
              bne ra_loop5                                 
irqsc6:  // open the top/bottom borders

              lda $d011                         
              and #$f7                          
              sta $d011 
//--------------------------RASTER WAIT 7-------------------------------------------------------------------------------------------------------
	  lda #$ff                          
ra_loop6:
              cmp $d012
              bne ra_loop6 
              
irqsc8:  // open the top/bottom borders -reset 
              lda $d011                         
              ora #$08                          
              sta $d011                         
              jmp $ea81                               
nopdelay:
		   nop  // 2 cycles
		   dex  // 2 cycles
		   bne nopdelay  // 2 cycles when no branching, 3 cycles at branch
		   rts // 6 cycles!
//-----------------------------------------------------
outputtime:   
//-----------------------------------------------------
		   lda $dc08
  		   cmp tbreak  	// previous
                           beq texit		   	
		   sta tbreak
	 	   cmp #$00		// only calculate stuff when ten complete
	               bne texit
                           inc seconds_l
  		   lda seconds_l
  		   cmp #$0a
		   bne tprint
		   lda #$00
		   sta seconds_l	
  		   inc seconds_h
		   lda seconds_h
  		   cmp #$06
 		   bne tprint
 		   lda #$00
 		   sta seconds_h
 		   inc minutes_l
 		   lda minutes_l
 		   cmp #$0a
 		   bne tprint
 		   lda #$00
  		   sta minutes_l
 		   inc minutes_h
 		   lda minutes_h
 		   cmp #$06
 		   bne tprint
 		   lda #$00
 		   sta minutes_h
 		   sta minutes_l
 		   sta minutes_l

	

tprint:

  		   lda seconds_l
  		   adc #$30
		   sta $4747
  		   lda seconds_h
  		   adc #$30
		   sta $4746
  		   lda minutes_l
  		   adc #$30
		   sta $4744
  		   lda minutes_h
  		   adc #$30
		   sta $4743
 texit:
		   rts
		
//------------text colour scroll----------------------------------------
txt_scroll:
		   ldx #$24
		   lda txt_col_st
		   inc txt_col_st
		   cmp #$19
		   bne tcolst1
		   ldy #$00
		   sty txt_col_st			   			
tcolst1:	   tay
tcolloop:		

		   lda txt_cols, y
		   sta $d967, x
		   sta $d9b7, x		
		   sta $da30, x
		   sta $da81, x
		   iny
		   dex
//		   cpx #$28
		   beq tdone
		   cpy #$1a
		   bne tcolloop
		   ldy #$00
		   jmp tcolloop
tdone:		   	
		    rts
hexchar:  // expects a low-nibble in a to return a hex character
		   tax
		   sec
		   sbc #$0a			// subtract 10
		   bmi g_numb		// go to number
		   clc
		   adc #$01
		   jmp g_next
g_numb:		   
		   txa
		   clc
		   adc #$30
g_next:					
		   rts
		
highlight_bar: // highlights 4720-4748 with beat col
		
			ldx #$28
			lda cur_beat_col
			beq hexit
hloop1:	      sta $db1f,x
 			dex
 			bne hloop1
hexit:
 			rts
 									
		
seconds_l: .byte 0
seconds_h: .byte 0
minutes_l: .byte 0
minutes_h: .byte 0
tbreak: .byte 0
spr_c0: .byte 6 // dark grey   01
spr_c1: .byte 14 // light grey 03 
spr_sc: .byte 1  // white      02 
spr_bg: .byte 0 
spr_ctrot: .byte 01, 03, 02
spr_rotco1: .byte 02
spr_rotco2: .byte 02
spr_rotco3: .byte 02
spr_ch_xpos: .byte 08, $fe, 08, $ee, 08, $de, $e8, $ed, $b8, $ed, $88, $ed, $58, $ed, $46, $e9
spr_sc_xpos: .byte $94, $5a, $ac, $5a, $c4, $5a, $a8, $3e, $b8, $2e, $88, $2e, $58, $2e, $46, $2e
spr_dat_pos: .byte 00, 03, 06, 09,$0c, $0f, $12, $15
spr_sc_cols: .byte $06, 14, $07, $01, $07, 14
beat_col: .byte 1,1, 7, 7,14, 14,6,6, 0
cur_beat_col_p: .byte 8		// is the pointer to the last one
cur_beat_col: .byte 6
txt_col_st: .byte 0
txt_cols: .byte 6,6, 14, 14, 1, 1, 14, 14, 6,6,6,6,6,6,6,6,6,6,6,6,6,6,6,6,6,6
spr_col_sp: .byte 04
spr_col_cur: .byte 00
mbar_c3: .byte 6
charpoint: .word $0000 
dumspr: .byte $00, 0, 0, 0, 0, 0, 0, 0
xscroll: .byte 0
beat_trig: .byte 1
val: .byte 1
std: .byte 0
std2: .byte 0
keyb: .byte 0
stdbm: .byte 0 // bitmap memory shift
textmes: .text "xentax"
scrolltext: .text "one of the lost tunes, stroyka, not to be confused with the other tune with a similar name of mine, this one was never released for reasons unknown. i created the tune in voicetracker 4.2 back in 1992 on my 6581! twenty years later i upload it at csdb. who would have thought! cheers to all sceners. mr.mouse/xentax signing off...              @"
time_txt: .text "time:   :@"
ras_txt: .text "raster: $@" 
title_txt: .text "stroyka (1992)@"
title_op_txt: .text "song title:@"
sid_op_txt: .text "sid: @"
sid_v_text: .text "6581@"
composer_txt: .text "mr.mouse/xentax@"
composer_op_txt: .text "created by:@"
raster_pos: .byte 0
date_txt: .text "2012"  
bito: .byte 0
raslow: .byte $8a
counter1: .byte 0
counter2: .byte 0
destroypic: .byte 0
bitcheck: .byte $80

```
## Post #2
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2013-04-13T18:55:24+00:00
- Post Title: My source code for that C64 music player

It's been a long time since I did "real" programming like this.  We are so spoiled programming on PCs in high-level programming languages now.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-04-27T16:02:18+00:00
- Post Title: My source code for that C64 music player

I don't think I can do that even with a high-level programming language
