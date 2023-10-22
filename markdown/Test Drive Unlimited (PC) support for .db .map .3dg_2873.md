## Post #1
- Username: RacersHardware
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Dec 17, 2007 6:36 pm
- Post datetime: 2007-12-17T12:23:38+00:00
- Post Title: Test Drive Unlimited (PC) support for .db .map .3dg

hi all!

i have found this great site and hope you can help us in matters tdu.

test drive unlimited (tdu) use for many files the .bnk - file format what we can read with 2 tools. one tool, [http://sturm.net.nz/website.php?Section ... Test+Drive](http://sturm.net.nz/website.php?Section=Games&Page=Test+Drive) support export an import within the bnk-archive.

for modding tdu we need to read and change the global database files. this file managed all information about cars, rims, car colors, menudiscription, and so on which are stored in languagefiles. these languagesfiles can be after extract from bnk-archive natively read.
so my question is now, is there any possibility to read the db-files?

the second file support is for the .map file. i´m not 100% sure what information are all stored in this file, but after the first patch i can say here are information about all cardealers. so if we can read and editing the map-file, we can open ne cardealers, like lexus, etc. 

i attache some samplefiles. if needed more files i can up some other files.
[tdu_samples.rar](https://xentaxbackup.github.io/file/1407_tdu_samples.rar)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-12-18T19:31:52+00:00
- Post Title: Test Drive Unlimited (PC) support for .db .map .3dg

Well, the .ge file is a simple text file in unicode. Converted back it looks like this below. No luck with the other files yet. 

```
// version: 1,2
// categories: 6
// Libelle
{ERROR} 9097512
// DisplayName
{Standard} 5436562
{Light Alloy Wheels (Styling I)} 5536562
{Light Alloy Wheels (Styling III)} 5636562
{Light Alloy Wheels (Styling III)-04} 5736562
{Light Alloy Wheel (Styling IV)} 5836562
{Light Alloy Wheels (Styling V)} 5936562
{18" AMG Multi-Piece Twin-Spoke Light-Alloy Wheels} 6036562
{Light Alloy Wheels Multi-Piece (Styling III)} 6136562
{Light Alloy Wheels Dual Spoke (Styling IV)} 6236562
{Standard DB9 Wheels} 5346562
{15-Spoke Diamond Turned Alloy Wheels} 5446562
{V8 Vantage Wheels} 5546562
{BRABUS Monoblock V, Dual-Spoke Design, One-Piece, Silver Polished} 5646562
{Standard Caterham Wheels} 5746562
{Standard 2CV Wheels} 5846562
{Polished Forged Aluminum Wheels} 5946562
{Alloy Wheels with Five Holed Design } 6046562
{Standard Gallardo Wheels} 6146562
{Five-Spoke Light Alloy Wheels} 6246562
{8-Twin-Spoke Wheels} 5356562
{Standard Ferrari Enzo Wheels} 5456562
{Ferrari 250 GTO Wheels} 5556562
{Ferrari Five Spoke Light Alloy Wheels} 5656562
{ Ferrari Five Twin-Spoke Light Alloy Wheels} 5756562
{Painted Cast Aluminum Wheels} 5856562
{17" Premium Painted Cast Aluminum Wheels} 5956562
{Standard Jaguar XKR Convertible} 6056562
{Standard Mercedes-Benz SLK 55 AMG Wheels} 6156562
{Standard Mercedes-Benz SLR McLaren Wheels} 6256562
{Design 5 Branches} 5366562
{Light Alloy Wheels (Styling III)-05} 5466562
{Standard Mercedes-Benz CLK 55 AMG Wheels} 5566562
{Standard Mercedes-Benz SL300 Gullwing Wheels} 5666562
{Spoke Wheels} 5766562
{Spoke Wheels Sport Light Silver Polish} 5866562
{Design 10-Spoke} 5966562
{Design 5-Spoke} 6066562
{AMG Light-Alloy Wheels} 6166562
{Standard Nissan 350Z Wheels} 6266562
{Standard NISSAN Skyline Wheels} 5376562
{Noble 10-Spoke Alloy Polished Rims} 5476562
{18" AMG Multi-Piece Twin-Spoke Light-Alloy Wheels} 5576562
{Standard Pagani Zonda C12S Roadster Wheels} 5676562
{Standard Ducati S4R Wheels} 5776562
{Koenigsegg CC8R Magnesium Alloy Wheels with Centre Locking} 5876562
{Miura Grey Magnesium Wheels} 5976562
{Saleen Forged Alloy Wheels} 6076562
{Standard Aston Martin DB4 Zagato Wheels} 6176562
{Standard Pontiac Firebird Wheels} 6276562
{RUF-5-spoke Light-Alloy Wheels} 5386562
{Standard Audi A3 Wheels} 5486562
{Standard Audi A6 Wheels} 5586562
{Shelby Wheels} 5686562
{Ford Shelby Cobra Concept Wheels} 5786562
{Standard Alfa Romeo 17 Spoke Type} 5886562
{Standard Lotus Sport Exige Wheels} 5986562
{Rally Wheels} 6086562
{Ferrari Multi-Piece Five-Spoke Light Alloy Wheels} 6186562
{Standard Voslkwagen W12 Coupe} 6286562
{Standard Voslkwagen W12 Roadster} 5396562
{Standard Chevrolet Corvette 1957 Wheels} 5496562
{Standard Chevrolet Camaro Z28 Wheels} 5596562
{Standard Alfa Romeo 8c Competizione Wheels} 5696562
{Standard Jaguar Type E Wheels} 5796562
{Standard Dodge Viper Coupe Wheels} 5896562
{Standard Shelby GT500 Wheels} 5996562
{Standard Pontiac GTO Wheels} 6096562
{Standard Maserati Spyder Cambiocorsa Wheels} 6196562
{18" Light Alloy Wheels} 6296562
{Standard Aston Martin DB9 Volante Wheels} 5406562
{Standard Mercedes-Benz CLS 55 AMG Wheels} 5506562
{Five spoke McLaren Design Light Alloy Wheels} 5606562
{Noble designed Ten-Spoke Alloy Polished Rims} 5706562
{Noble Designed One Piece Ten-Spoke} 5806562
{Koenigsegg CC8S Magnesium Alloy Wheels with Centre Locking} 5906562
{Jaguar XJ220 One Piece Aluminum Alloy Wheels} 6006562
{Mazda RX-8 18" Alloy Wheels} 6106562
{Mazda RX-8 18" Alloy Wheels Sport} 6206562
{20" Aluminum SRT Design Wheels} 6306562
{Lightweight Aluminum Alloy Wheels} 5416562
{Standard AC 427 Wheels} 5516562
{Standard AC 289 Wheels} 5616562
{Chrysler® ME Four-Twelve Wheels} 5716562
{NISSAN Touring Wheels} 5816562
{Nissan Touring Alloy Wheels} 5916562
{NISMO Alloy Wheels} 6016562
{Standard Lotus Esprit V8 Wheels} 6116562
{Standard Audi 15-spoke design aluminium Wheels} 6216562
{Standard Spyker Wheels} 6316562
{Speedline Cast-Aluminum Painted, Ultra-Silver} 5426562
{Standard Cadillac XLV-V Wheels} 5526562
{Standard McLAREN F1 LM Wheels} 5626562
{Standard Ascari Light Alloy Wheels} 5726562
{Chrysler® Firepower Wheels} 5826562
{19" Trofeo} 5926562
{Forged Aluminum Alloy Wheels} 6026562
{Mercedes-Benz SLR McLaren Light Alloy Wheels} 6126562
{Polished Aluminum Wheels} 6226562
{8-Spokes Dark Wheels} 6326562
{Lotus 6-Spoke Wheels} 5337562
{Lotus 5-Spoke Wheels} 5437562
{Lotus 12-Spoke Wheels} 5537562
{Lotus 16-Spoke Dark Wheels} 5637562
{Lotus 16-Spoke Wheels} 5737562
{19" Seven-Spoke Alloy Wheels} 5837562
{19" Nine-Spoke Lightweght Forged Alloy Wheels} 5937562
{Ten-Spoke Alloy Wheels} 6037562
{Seven-Spoke Alloy Wheels} 6137562
{Alloy Wheels 17" with Five Holed Design} 6237562
{Alloy Wheels 18" with Spoke Design} 5347562
{Twelve-Spoke Milled Aluminum Wheels} 5447562
{Five Spoke Grey Aluminium} 5547562
{Standard Gallardo Roadster Wheels} 5647562
{Forged light Alloy Wheels with Five "Y" Spokes} 5747562
{Light Alloy Five-Spoke} 5847562
{RUF Alloy Wheels} 5947562
{RUF 3-Piece Modular Alloy Wheels} 6047562
{19" Trofeo "Grigio Mercury"} 6147562
{19" Trofeo "Ball-Polished"} 6247562
{P02 Wheels Cover} 5357562
{Design Storico 18"} 5457562
{Standard 15" Painted Wheels} 5557562
{Standard Wheels Covers} 5657562
{Five-Spoke Wheels} 5757562
{Speedline Cast-Aluminium Chrome Finish} 5857562
{17" Five Spoke Aluminum Wheels} 5957562
{19" Light Alloy Wheels} 6057562
{17" Bright Machined Cast Aluminum Wheels} 6157562
{18"Polished Aluminum Wheels} 6257562
{19"Polished Aluminum Wheels} 5367562
{Five Spoke, Polished, Aluminum} 5467562
{Five Spoke, Chrome, Aluminum} 5567562
{Five Spoke, Competition Gray,Painted Aluminum} 5667562
{Z06" polished Aluminum} 5767562
{Z06" Competition Gray-painted Aluminum} 5867562
{Forged Grey Light Alloy Wheels with Five "Y" Spoke} 5967562
{Alloy wheels 17" with Spoke Design } 6067562
{Challenge} 6167562
{AMG Alloy Wheel whith Spoke Design} 6267562
{Double Spoke Cast Alloy Wheels} 5377562
{RS4 5-Spoke Cast Alloy Wheels} 5477562
{Senta 20" Alloy Wheels} 5577562
{Design Alfa} 5677562
{Design Eleganza 17"} 5777562
{Miura Gold Magnesium Wheels} 5877562
{Lightweight Wheels "H" Cross-Section Spokes} 5977562
{Lightweight Wheels Tree Sections Spoke} 6077562
{Painted Forged Aluminum, Lightweigt Wheels} 6177562
{Saleen Seven Spoke Alloy Wheels} 6277562
{Ten-Spoke Genuine} 5387562
{ Ferrari Light Alloy Wheel Challenge Stradale Type} 5487562
{18" Polished Aluminum Wheels "Pony" Center Cap} 5587562
{Venus 18" Alloy Wheels} 5687562
{Sabre 19" Alloy Wheels} 5787562
{Carelia 19" Alloy Wheels} 5887562
{Standard Elise Cast Wheels in Matte Black Painted Finish} 5987562
{8-Spoke Wheels} 6087562
{18" 6-Spoke Avus Design Cast Alloy Wheels} 6187562
{19" One Piece Forged Aluminum Wheels} 6287562
{Forged Alloy Rims with Central Locknuts} 5397562
{Magnesium Spyker 19" Wheels} 5497562
{Hydra Alloy Wheels} 5597562
{Montreal Alloy Wheels} 5697562
{Sepang Alloy Wheels} 5797562
{Detroit Alloy Wheels} 5897562
{Maserati 3500 GT Rims} 5997562
{Seven Spoke "Spide" Aluminum Alloy Wheels} 6097562
{18" 'Zolder' Alloy Wheels} 6197562
{17" 16 Spoke Cast Alloy Wheels} 6297562
{19-inch AMG Light-Alloy Wheels Whith Twin-Spoke Design} 5407562
{7-Twin-Spoke Forged Aluminum Wheels} 5507562
{Farboud Design Alloy Wheels} 5607562
{Wiesmann Design Alloy Wheels} 5707562
{Forged Light Alloy Wheels with "Y" Spokes} 5807562
{Seven Spoke "Spide" Grey Aluminum Alloy Wheels} 5907562
{18" Aluminum Wheels} 6007562
{Forged Light Alloy Wheels} 6107562
{Standard 17" Alloy Wheels} 6207562
{Design Mugello 18"} 6307562
{19" Challenge Wheels With Titanium Stud Bolts} 5417562
{ 19-Inch Cast Aluminium Wheels  5-arm Wing Design} 5517562
{Magnesium Alloy Wheels} 5617562
{Design Sprint 17"} 5717562
{SRT6 Wheels} 5817562
{Wheels, 18" Polished Aluminum} 5917562
{Aluminum Wheels} 6017562
{Light Alloy Wheels} 6117562
{18- Five-Spoke Polished Wheels} 6217562
{18-Six Double-Spoke Chrome Wheels} 6317562
{14" Wheels} 5427562
{White} 53365512
{Alfa-Romeo} 54365512
{AMG} 55365512
{Mercedes} 56365512
{Brabus} 57365512
{Aston Martin} 58365512
{Audi} 59365512
{Caterham} 60365512
{Chevrolet} 61365512
{Chrysler} 62365512
{Citroen} 53465512
{Dodge} 54465512
{Lamborghini} 55465512
{Lotus} 56465512
{Ferrari} 57465512
{Ford} 58465512
{Jaguar} 59465512
{Mercedes} 60465512
{Maserati} 61465512
{Nissan} 62465512
{Noble} 53565512
{Pagani} 54565512
{Saleen} 55565512
{Ducati} 56565512
{Koenigsegg} 57565512
{Pontiac} 58565512
{RUF} 59565512
{Shelby} 60565512
{Volskwagen} 61565512
{Saturn} 62565512
{McLaren} 53665512
{Mazda} 54665512
{AC} 55665512
{Spyker} 56665512
{Cadillac} 57665512
{Ascari} 58665512
{MV Agusta} 59665512
{Triumph} 60665512
{Wiesmann} 61665512
{Kawasaki} 62665512
{TVR} 53765512
{Farboud} 54765512
{Default} 55765512
{Lexus} 56765512
{Edonis} 57765512
{Holden} 58765512
{Standard} 53366512
{Standard Alfa Romeo  17 Spoke Type} 54366512
{jantes 18 design à rayons} 55366512
{Light-alloy wheel (Style III)} 56366512
{Light-alloy wheel (Style V)} 57366512
{Light alloy wheel (Styling I)} 58366512
{Light alloy wheel (Styling III)} 59366512
{Light alloy wheel (Styling III)-01} 60366512
{Light alloy wheel (Styling III)-02} 61366512
{Light alloy wheel (Styling IV)} 62366512
{Light alloy wheel (Styling V)} 53466512
{Light alloy wheel multi-piece (Styling III)} 54466512
{Light alloy wheel multi-piece (Styling IV)} 55466512
{Light alloy wheel(Styling IV)} 56466512
{17 5 spoke wheel} 57466512
{18 5 spoke wheel_sport_poli_brillant} 58466512
{Design 10 rayons} 59466512
{Design 5 Branches} 60466512
{Monoblock IV, five-hole design, multi-piece, silver polished} 61466512
{Monoblock IV, five-hole design} 62466512
{Monoblock V, spoke design, multi-piece, silver polished} 53566512
{Monoblock V, dual-spoke design, multi-piece, silver polished} 54566512
{BRABUS Monoblock V, dual-spoke design, one-piece, silver polished} 55566512
{Monoblock V, spoke design, one-piece, silver polished} 56566512
{Standard DB9 Wheel} 57566512
{Standard AMV8 Wheel} 58566512
{Standard Caterham Wheel} 59566512
{Standard 2CV Wheel} 60566512
{Standard Dodge Viper Wheel} 61566512
{Standard Murciellago Wheel} 62566512
{Standard Gallardo Wheel} 53666512
{Standard Lotus Elise 111R Wheel} 54666512
{Standard Ferrari 250 GTO Wheel} 55666512
{Standard Ferrari Enzo Wheel} 56666512
{Standard Ford GT Wheel} 57666512
{Standard Ford Mustang GT Wheel} 58666512
{Standard Mercedes-Benz SLK 55 AMG Wheel} 59666512
{Standard Mercedes-Benz SLR McLaren Wheel} 60666512
{Standard Mercedes-Benz SL300 Gullwing Wheel} 61666512
{Standard Nissan 350Z Wheel} 62666512
{Standard Nissan Skyline Wheel} 53766512
{Standard Noble M12 GTO-R Wheel} 54766512
{Standard Pagani Zonda C12S Wheel} 55766512
{Standard Murciellago Roadster Wheel} 56766512
{Standard Pagani Zonda C12S Roadster Wheel} 57766512
{Standard Mercedes-Benz CLK 55 AMG Wheel} 58766512
{Standard Ducati S4R Wheel} 59766512
{Standard Koenigsegg CCR  Wheel} 60766512
{Standard Miura P400SV Wheel} 61766512
{Standard Saleen S7 TwinTurbo Wheel} 62766512
{Standard Aston Martin DB4 Zagato Wheel} 53866512
{Standard Pontiac Trans Am Wheel} 54866512
{RUF-5-spoke light-alloy wheel} 55866512
{Standard Audi A3 Wheel} 56866512
{Standard Audi A6 Wheel} 57866512
{Standard Shelby Cobra Daytona Coupe Wheel} 58866512
{Standard Ford Shelby Cobra Concept Wheel} 59866512
{Standard Lotus Sport Exige Wheel} 60866512
{Standard Corvette 1969 Wheel} 61866512
{Standard Ferrari 575M Wheel} 62866512
{Standard Voslkwagen W12 Coupe} 53966512
{Standard Voslkwagen W12 Roadster} 54966512
{Standard Jaguar XKR Convertible} 55966512
{Standard Chevrolet Camaro Z28 Wheel} 56966512
{Standard Alfa Romeo 8c Competizione Wheel} 57966512
{Standard Jaguar Type E Wheel} 58966512
{Standard Dodge Viper Coupe Wheel} 59966512
{Standard Shelby GT500 Wheel} 60966512
{Standard Pontiac GTO Wheel} 61966512
{Standard Maserati Spyder Cambiocorsa Wheel} 62966512
{Standard Saturn Sky Wheel} 54066512
{Standard Saturn Curve Wheel} 55066512
{Standard Aston Martin DB9 Volante Wheel} 56066512
{Standard Mercedes-Benz CLS 55 AMG Wheel} 57066512
{Standard McLAREN F1 Wheel} 58066512
{Noble Ten-spoke alloys polished rims} 59066512
{Noble designed Ten-spoke alloys polished rims} 60066512
{Noble designed one piece 10-spoke} 61066512
{Koenigsegg CC8R magnesium alloy wheels with centre locking} 62066512
{Koenigsegg CC8S magnesium alloy wheels with centre locking} 63066512
{Jaguar XJ220 One piece aluminium alloy wheel} 54166512
{Spoke wheel} 55166512
{Spoke wheel sport light Silver Polish} 56166512
{Design Ten Spoke} 57166512
{Design Five spoke} 58166512
{Mazda RX-8 18-inch alloy Wheel} 59166512
{Standard Chrysler 300C SRT-8, 20-inch alloy Wheel} 60166512
{Aston Martin Lightweight Alumionium Alloy Wheels} 61166512
{Standard AC 427 Wheel} 62166512
{Standard Chrysler ME Four-Twelve Wheels} 63166512
{Nismo Alloy Wheel} 54266512
{Standard Lotus Esprit V8 Wheels} 55266512
{Standard Audi 15-spoke design aluminium Wheels} 56266512
{Standard Spyker Wheels} 57266512
{20" AMG light-alloy Wheels} 58266512
{Chevrolet SSR Speedline cast-aluminium} 59266512
{Standard AC 289 Wheel} 60266512
{Standard Cadillac XLV-V wheel} 61266512
{Standard McLAREN F1 LM Wheel} 62266512
{Standard Chevrolet Corvette 1957 Wheel} 63266512
{Standard Ascari Light Alloy } 53376512
{Standard Ferrari 288 GTO Wheel} 54376512
{Standard Chrysler Firpower Wheel} 55376512
{Standard Ferrari F430 Alloy Wheel} 56376512
{Standard Maserati GranSport Wheel} 57376512
{Standard MV Agusta Brutale Wheel} 58376512
{Optional 15 spoke diamond Turned Alloy Wheels} 59376512
{Nissan Touring Wheel} 60376512
{Nissan Touring Alloy Wheel } 61376512
{Mazda RX-8 18-inch alloy Wheel Sport} 62376512
{Mercedes-Benz SLR McLaren Light Alloy Wheel} 53476512
{Dodge Viper Alloy Wheel} 54476512
{Lotus 16 spokes Dark Wheel} 55476512
{Lotus 6 Spokes Wheel} 56476512
{Lotus 5 Spokes Wheel} 57476512
{Lotus 12 Spokes Wheel} 58476512
{Lotus 16 spokes Wheel} 59476512
{Aston Martin 19" seven spoke Alloy Wheels} 60476512
{10-Spoke Alloy Wheel} 61476512
{7-Spoke Alloy Wheel} 62476512
{Aston Martin 19" nine Spoke Lightweght Forged Alloy Wheels} 53576512
{18" AMG multi-piece twin-spoke light-alloy wheels} 54576512
{light alloy wheel multi-piece (Styling III)} 55576512
{light alloy wheel Dual Spoke (Styling IV)} 56576512
{Alloy wheels 18 with spoke design } 57576512
{Alloy wheels 17 with five Holed design } 58576512
{Standard Shelby_GR1_wheel} 59576512
{Gallardo_Grey_rims} 60576512
{Gallardo_Roadster_rims} 61576512
{Ducati_999R_rims} 62576512
{Ducati_1000DS_rims} 53676512
{RUF Rturbo Rims} 54676512
{RUF RGT Rims} 55676512
{Mustang_GTR_Rims} 56676512
{Maserati Trofeo gris} 57676512
{Maserati Trofeo poly} 58676512
{corvette 71 rim Base} 59676512
{Corvette 71 rim Option} 60676512
{Tamburini_wheels} 61676512
{Speed_Triple_wheel} 62676512
{Brera_standard_rims} 53776512
{challenger_rims} 54776512
{SSR_chrome_rims} 55776512
{MC12_wheels} 56776512
{Mustang_gt_rimsA} 57776512
{Mustang_rims_18} 58776512
{C6_poly} 59776512
{C6_Chrome} 60776512
{C6_Gray} 61776512
{Z06_Rims} 62776512
{Z06_Rims_option} 53876512
{Gallardo_spyder_grey} 54876512
{Wiesmann_gt_base} 55876512
{CLK_GTR_Rims} 56876512
{McLAREN_GTR_rims} 57876512
{RS4_base_rims} 58876512
{RS4_option_rims} 59876512
{XK_20_rims} 60876512
{Brera_design_Alfa} 61876512
{Brera_design_Elegance} 62876512
{Countch_25th_rims} 53976512
{Miura_Gold_Rims} 54976512
{ZX10R_rims} 55976512
{Z1000_rims} 56976512
{Ford_GT_option_rims} 57976512
{Diablo_GT} 58976512
{S281_Rim} 59976512
{C6_options} 60976512
{F430_strad_option} 61976512
{Mustang_pony} 62976512
{X150_standard} 54076512
{X150_19sabre} 55076512
{S150_19carelia} 56076512
{Lotus_elise_sprim} 57076512
{DB7_RimsZ} 58076512
{S4_rims} 59076512
{Spider90th_rims} 60076512
{Spyk_option_rim} 61076512
{XKR_hydra} 62076512
{XKR_Montreal} 63076512
{XKR_Sepang} 54176512
{XKR_detroit} 55176512
{Tuscan_rims} 56176512
{3500GT_rims} 57176512
{Sagaris_rims} 58176512
{Golf_rims} 59176512
{SL65_ST_Rims} 60176512
{F612_rims} 61176512
{Elise_twinspoke} 62176512
{Farboud_Rims} 63176512
{Default_car_rims} 54276512
{Wiesmann_rst_base} 55276512
{Wiesmann_rst_o} 56276512
{Wiesmann_gt_o} 57276512
{Sagaris_grey} 58276512
{CTSV_rims} 59276512
{Nismo_option} 60276512
{GallardoSE_Grey_rims} 61276512
{Gallardo_Y_options} 62276512
{IS350_Rims} 63276512
{F308_Rims} 53386512
{Brera_Storico} 54386512
{360stradale_rims} 55386512
{612_polish} 56386512
{612_etoile} 57386512
{Charger_Rims} 58386512
{T440_rims} 59386512
{F40_rims} 60386512
{S6_Rims} 61386512
{Edonis_Rims} 62386512
{Cien_Rims} 53486512
{Curve_rims} 54486512
{Brera_sprint} 55486512
{mclarenGT_rims} 56486512
{sixteen_rims} 57486512
{Crossfire_rims} 58486512
{Solstice_rims} 59486512
{A4_TC_rims} 60486512
{63_rims} 61486512
{LS460_rims} 62486512
{GS_Rims} 53586512
{LS600_Rims} 54586512
{LS460_rimsO} 55586512
{RK_spyder_rim} 56586512
{Dino246_Rims} 57586512
{512TR_rims} 58586512
{Cobalt_rims} 59586512
{Cobalt_optionA} 60586512
{Cobalt_optionB} 61586512
{Judge_rims} 62586512
{Efijy_Rims} 53686512
{None} 53690512
{Aston} 54690512
{Audi} 55690512
{Caterham} 56690512
{Citroen} 57690512
{Dodge} 58690512
{Ferrari} 59690512
{Ford} 60690512
{Lamborg} 61690512
{Lotus} 62690512
{McLaren} 53790512
{Mercedes} 54790512
{Nissan} 55790512
{Noble} 56790512
{Pagani} 57790512
{Koenigsegg} 58790512
{Saleen} 59790512
{Ducati} 60790512
{Pontiac} 61790512
{RUF} 62790512
{Shelby} 53890512
{Chevrolet} 54890512
{VAG} 55890512
{Alfa} 56890512
{Jaguar} 57890512
{Maserati} 58890512
{Saturn} 59890512
{Mazda} 60890512
{Chrysler} 61890512
{AC} 62890512
{Spyker} 53990512
{Cadillac} 54990512
{Ascari} 55990512
{Mv-Agusta} 56990512
{Triumph} 57990512
{Wiesmann} 58990512
{Kawa} 59990512
{TVR} 60990512
{Farboud} 61990512
{Default} 62990512
{Lexus} 54090512
{Edonis} 55090512
{Holden} 56090512
{None} 53358512
{DB9_Cpe_F_01} 54658512
{AMV8_Cpe_F_01} 55658512
{TT_F_01} 56658512
{Sev_CSR_F_01} 57658512
{2CV_F_01} 58658512
{Viper_SR_F_01} 59658512
{Enzo_F_01} 60658512
{Ford_GT_F_01} 61658512
{Must_GT_F_01} 62658512
{Gall_Cpe_F_01} 53758512
{Murc_Cpe_F_01} 54758512
{Murc_Cpe_R_01} 55758512
{Murc_Rst_F_01} 56758512
{Murc_Rst_R_01} 57758512
{Elis_Rst_F_01} 58758512
{SLR_F_01} 59758512
{300_SL_F_01} 60758512
{SLK_350_F_01} 61758512
{SLK_55_F_01} 62758512
{350ZCPE_F_01} 53858512
{SKYGTR_F_01} 54858512
{M12_GTO_F_01} 55858512
{Zonda_C_F_01} 56858512
{Zonda_RSt_F_01} 57858512
{CLK_55_F_01} 58858512
{CCR_F_01} 59858512
{Miu_F_01} 60858512
{S7T_F_01} 61858512
{Duca_S4R_F_01} 62858512
{Duca_S4R_R_01} 53958512
{SLK_55_F_02} 54958512
{SLK_55_F_03} 55958512
{DB4_Zag_F_01} 56958512
{TRANS_AM_F_01} 57958512
{RT12_F_01} 58958512
{Rt12_R_01} 59958512
{A3_V6_F_01} 60958512
{A6_V8_F_01} 61958512
{Shelb_Day_F_01} 62958512
{Ford_Cobra_F_01} 54058512
{Corv69_F_01} 55058512
{W12_Cpe_F_01} 56058512
{W12_Rst_F_01} 57058512
{Alfa_GT_F_01} 58058512
{Exige_240R_F_01} 59058512
{F575_M_F_01} 60058512
{XKR_Conv_F_01} 61058512
{F250_GTO_F_01} 62058512
{Cam_Z28_F_01} 63058512
{Alfa_8C_F_01} 54158512
{TYPE_Cpe_F_01} 55158512
{Viper_Cpe_F_01} 56158512
{Shelb_GT_F_01} 57158512
{DB9_Vol_F_01} 58158512
{GTO_Cpe_F_01} 59158512
{Mas_Rst_F_01} 60158512
{SKY_Rst_F_01} 61158512
{CLS_55_F_01} 62158512
{W12_Cpe_R_01} 63158512
{W12_Rst_R_01} 54258512
{MCL_F1_F_01} 55258512
{Noble_M14_F_01} 56258512
{M400_F_01} 57258512
{CC8_F_01} 58258512
{XJ_220_F_01} 59258512
{XJ_220_R_01} 60258512
{MER01_F_01} 61258512
{MER02_F_01} 62258512
{MER03_F_01} 63258512
{MER04_F_01} 54358512
{AMG3_F_01} 55358512
{AMG4_F_01} 56358512
{AMG5_F_01} 57358512
{AMG6_F_01} 58358512
{AMG7_F_01} 59358512
{AMG8_F_01} 60358512
{RX8_Cpe_F_01} 61358512
{300_C_F_01} 62358512
{Vanquish_Cpe_F_01} 63358512
{AC_427_F_01} 54458512
{ME_FT_F_01} 55458512
{350ZNISMO_F_01} 56458512
{Esprit_F_01} 57458512
{TT_Cpe_QS_F_01} 58458512
{SPYK_RST_F_01} 59458512
{Esprit_R_01} 60458512
{CLK_DTM_F_01} 61458512
{SSR_F_01} 62458512
{AC_289_F_01} 63458512
{XLR_V_F_01} 54558512
{MCL_F1_LM_F_01} 55558512
{Corv_57_F_01} 56558512
{KZ1_F_01} 57558512
{F288_GTO_F_01} 58558512
{FirePW_F_01} 59558512
{F430_Cpe_F_01} 60558512
{Mas_Cpe_GS_F_01} 61558512
{Brutal_F_01} 62558512
{Brutal_R_01} 63558512
{DB9_Vol_F_02} 533758512
{NISSAN2_F_01} 543758512
{NISSAN3_F_01} 553758512
{RX8_1_F_01} 563758512
{SLR_F_02} 573758512
{Viper_Cpe_1_F_01} 583758512
{Lotus_1_F_01} 593758512
{Lotus_2_F_01} 603758512
{Lotus_3_F_01} 613758512
{Lotus_4_F_01} 623758512
{Lotus_5_F_01} 534758512
{AMV8_Cpe_F_02} 544758512
{MX5_F_01} 554758512
{MX5_1_F_01} 564758512
{Vanquish_Cpe_F_03} 574758512
{AMG10_F_01} 584758512
{BRAB5_F_01} 594758512
{AMG9_F_01} 604758512
{AMG11_F_01} 614758512
{ARGT01_F_01} 624758512
{ARGT02_F_01} 535758512
{Shelby_GR-1_F_01} 545758512
{Gall_Cpe_F_02} 555758512
{Gall_Rst_F_01} 565758512
{Duca_999R_F_01} 575758512
{Duca_999R_R_01} 585758512
{Duca_DS_F_01} 595758512
{Duca_DS_R_01} 605758512
{RUF_R TBR_F_01} 615758512
{RUF_RGT_F_01} 625758512
{Must_GTR_F_01} 536758512
{Mas_Cpe_GS_F_02} 546758512
{Mas_Cpe_GS_F_03} 556758512
{Corv_71_F_01} 566758512
{LT1_1_F_01} 576758512
{MV_F4S_F_01} 586758512
{MV_F4S_R_01} 596758512
{TR_SP_F_01} 606758512
{TR_SP_R_01} 616758512
{Alfa_Brera_1_F_01} 626758512
{Alfa_Brera_2_F_01} 537758512
{Alfa_Brera_3_F_01} 547758512
{Dodge_Challenger_F_01} 557758512
{SSR_F_02} 567758512
{Mas_MC12_F_01} 577758512
{MUST2_F_01} 587758512
{MUST1_F_01} 597758512
{C6_Conv_F_01} 607758512
{C6_Conv_F_02} 617758512
{C6_Conv_F_03} 627758512
{C6_Z06_F_01} 538758512
{C6_Z06_F_02} 548758512
{Gall_Rst_F_02} 558758512
{Wies_GT_F_01} 568758512
{CLK_GTR_F_01} 578758512
{MCL_F1_GTR_F_01} 588758512
{RS4_1_F_02} 598758512
{RS4_1_F_01} 608758512
{XK_Cpe_F_01} 618758512
{Alfa_Brera_2_F_01} 628758512
{Alfa_Brera_1_F_01} 539758512
{Countach_25_F_01} 549758512
{Miu_F_02} 559758512
{ZX10R_F_01} 569758512
{ZX10R_R_01} 579758512
{Z1000_F_01} 589758512
{Z1000_R_01} 599758512
{Ford_GT_F_03} 609758512
{Diablo_GT_F_01} 619758512
{S281_F_01} 629758512
{C6_1_F_01} 540758512
{F430_02_F_01} 550758512
{Must_GT_F_02} 560758512
{X150_4_F_01} 570758512
{X150_3_F_01} 580758512
{X150_2_F_01} 590758512
{DB7_Zag_F_01} 600758512
{A4_S4_F_01} 610758512
{RGT_F_01} 620758512
{RGT_R_01} 630758512
{SPYK_F_01} 541758512
{JAGUARxkr_2_F_01} 551758512
{JAGUARxkr_1_F_01} 561758512
{JAGUARxkr_3_F_01} 571758512
{Tuscan_F_01} 581758512
{Mas_GT_F_01} 591758512
{Sagaris_F_01} 601758512
{Golf_R32_F_01} 611758512
{DB7_Zag_F_02} 621758512
{F612_F_01} 631758512
{Elis_Rst_F_02} 542758512
{Faroub_F_01} 552758512
{Default_F_01} 562758512
{Faroub_F_02} 572758512
{Wies_Rst_F_02} 582758512
{Wies_Rst_F_01} 592758512
{Sagaris_F_02} 602758512
{CTS_V_F_01} 612758512
{Wies_GT_F_02} 622758512
{IS350_F_01} 632758512
{F308_F_01} 533858512
{AR_Brera_2F_01} 543858512
{F360_F_01} 553858512
{F612_1_F_01} 563858512
{F612_2_F_01} 573858512
{Charger_F_01} 583858512
{T440R_F_01} 593858512
{F40_F_01} 603858512
{A6_S6_F_01} 613858512
{Edonis_F_01} 623858512
{Cien_F_01} 534858512
{Curve_F_01} 544858512
{Countach_25_R_01} 554858512
{Sprint_F_01} 564858512
{Eleganza_F_01} 574858512
{MCL_F1_GT_F_01} 584858512
{Sixteen_V_F_01} 594858512
{SRT6_Cpe_F_01} 604858512
{Tuscan_R_F_01} 614858512
{SOLSTICE_F_01} 624858512
{R_TBR_F_01} 535858512
{A4_DTM_F_01} 545858512
{C63_2_F_01} 555858512
{LS460_F_01} 565858512
{GS450H_F_01} 575858512
{LS600HL_F_01} 585858512
{LS460_F_02} 595858512
{Ruf_Spyder_F_01} 605858512
{246_GT_F_01} 615858512
{512_TR_F_01} 625858512
{Cobalt_SS_F_01} 536858512
{Cobalt_1_F_01} 546858512
{Cobalt_2_F_01} 556858512
{GTO_JUDGE_F_01} 566858512
{Efijy_F_01} 576858512

```
## Post #3
- Username: RacersHardware
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Dec 17, 2007 6:36 pm
- Post datetime: 2007-12-19T09:32:44+00:00
- Post Title: Test Drive Unlimited (PC) support for .db .map .3dg

thx Mr.Mouse.   

the numbers behind each name are id´s wich use the game to find his data. these id must be shown in the rims.db file too. the game use the *.db - entries to communicate between the server and other clients.
## Post #4
- Username: RacersHardware
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Dec 17, 2007 6:36 pm
- Post datetime: 2008-01-08T16:20:21+00:00
- Post Title: Test Drive Unlimited (PC) support for .db .map .3dg

someone know hwo to read this xmb-file?
[CarVSTConfig.rar](https://xentaxbackup.github.io/file/1422_CarVSTConfig.rar)
## Post #5
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-01-14T17:22:19+00:00
- Post Title: Test Drive Unlimited (PC) support for .db .map .3dg

```
   string name; 
}; 

char magic[4]; // XMBF
uint uk1; // = 257
uint uk2; // = 28
uint Part2Offset; // Offset of data following the names at the start (with padding)
uint uk4;
uint uk5;
uint uk6;
//Name names[100]; // some strings, couldn't find any value holding the number of strings
FSeek(Part2Offset);
uint uk[100]; // couldn't find any number here as well

// this is just a rough draft, probably incorrect,
// describes the data around strings like Transmission_OnLoad
struct EmbedFileEntry {
	string name;
	uint uk1;
	uint uk2;
	uint uk3;
	uint size; // found this out via the common.xmb from the sounds folder, there you can measure the size because it contains RIFFs
	uint uk4;
	uint uk5;
	uint uk6;
	uint uk7;
	uint decompsize; // ?
	uint uk8;
};
```
## Post #6
- Username: RoadTrain
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Dec 13, 2007 12:57 am
- Post datetime: 2008-01-17T03:43:24+00:00
- Post Title: Test Drive Unlimited (PC) support for .db .map .3dg

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: RacersHardware
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Dec 17, 2007 6:36 pm
- Post datetime: 2008-01-18T15:50:00+00:00
- Post Title: Test Drive Unlimited (PC) support for .db .map .3dg

cool rheini!

but, what can i do with this information? is this any enlargement for a existing software application?
## Post #8
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-01-18T15:56:47+00:00
- Post Title: Test Drive Unlimited (PC) support for .db .map .3dg

This is a 010 Editor (this is a hex editor) binary template. Just wanted to publish the information I got so far for other people who want to dig into the format.
## Post #9
- Username: RacersHardware
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Dec 17, 2007 6:36 pm
- Post datetime: 2008-02-17T08:43:17+00:00
- Post Title: Test Drive Unlimited (PC) support for .db .map .3dg

i get some XBOX data for test drive. someone know what i can do with *.big files?
i think its a compressed archiv....
## Post #10
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-17T09:54:37+00:00
- Post Title: Test Drive Unlimited (PC) support for .db .map .3dg

Well if it's a different format, open another thread and upload some sample files, e.g. to xirror.com or xlice.net
## Post #11
- Username: RacersHardware
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Dec 17, 2007 6:36 pm
- Post datetime: 2008-02-28T17:19:55+00:00
- Post Title: Test Drive Unlimited (PC) support for .db .map .3dg

ok, thx rheini. i upload them and open a new thread.

some new news about the other formats here?
