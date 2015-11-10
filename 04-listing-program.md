# Listing Program #

Berikut adalah Listing program dari game Suit ( Spartan VS ODST )

```prolog

%IIIIIIIIIIIIIIIII  TRADISIONAL SUWIT IIIIIIIIIIIIIIIIIII%


%> > > > > > > > Create by @yudihindarko < < < < < < < < %

% This program is developed by Irman Juliansyah
% 3IA13 - Gunadarma University

%>>>>>>>>>>>>>   Pendeklarasian Variabel   <<<<<<<<<<<<<<&
  
  ?-
  G_aksi_musuh:=0,
  G_aksi:=0,
  G_nilai_musuh:=0,
  G_nilai:=0,
  G_Loading is bitmap_image("indonesia.bmp",_),
  G_wel is bitmap_image("halo3.bmp",_),
  G_bel is bitmap_image("halo.bmp",_),
  G_nilaiPlay is bitmap_image("spartan.bmp",_),
  G_nilaiMusuh is bitmap_image("odst.bmp",_),


  G_siapkiri is bitmap_image("b2.bmp",_),
  G_jemkiri is bitmap_image("b2.bmp",_),
  G_telkiri is bitmap_image("g2.bmp",_),
  G_kelkiri is bitmap_image("k2.bmp",_),
  G_siapkanan is bitmap_image("cb2.bmp",_),
  G_jemkanan is bitmap_image("cb2.bmp",_),
  G_telkanan is bitmap_image("cg2.bmp",_),
  G_kelkanan is bitmap_image("ck2.bmp",_),
  G_mulai is bitmap_image("Mulai.bmp",_),

  window(G_pertama,_,window_pertama(_),"Loading...",0,0,800,620). 
  window_pertama(paint):- 
  draw_bitmap(0,0,G_Loading,_,_). 
  
 
window_pertama(init):-
	G_batas := 0,
	G_X:=370,
	G_setTime is set_timer(_,0.02,fungsi_timer).

fungsi_timer(end):-
	brush(rgb(0,0,0)),
    	round_rect(2,450,770,480,20,20), 
    	pen(5,rgb(0,0,0)),
    	brush(rgb(255,0,0)),
    	round_rect(2,450,G_X,480,20,20),
    	G_batas := G_batas + 1,
    	G_X := G_X + 4,
	(G_batas >= 100 -> close_window(G_pertama),





  window( G_menu, _, win_funtc(_), "SPARTAN VS ODST",100,100,600,400)).

%~~~~~~~~~~~~~~~~~ From pertama ~~~~~~~~~~~~~~~~~~~~~~~~%
  
  win_funtc(paint):-
  draw_bitmap(0,0,G_wel,_,_).

  win_funtc(init):-
  button( _,_,start(_),"Start",250,50,90,25),
  button( _,_,about(_),"About",250,100,90,25),
  button( _,_,exit(_),"Exit",250,150,90,25).


  exit(press):-
  close_window(G_menu).
  win_funtc(close):-
  not(yes_no("Exit","Anda yakin?", ?)).

  about(press) :-
  message("About This Game","
  Irman Juliansyah
  54413499
  3IA13 ", i).

%~~~~~~~~~~~~~~~~~~~~~ From Utama ~~~~~~~~~~~~~~~~~~~~~~~%

  start(press):-
  window(G_utama,_,win_func(_),"SPARTAN VS ODST",100,100,713,465),
  
  draw_bitmap(0,0, G_bel,_,_),
  draw_bitmap( 50, 57, G_nilaiPlay, _, _),
  draw_bitmap( 550, 57, G_nilaiMusuh, _, _),

  G_aksi_musuh:=0,
  G_aksi:=0,
  G_tuwak:=64,
  G_time:=4,
  G_nilai:=0,
  G_nilai_musuh:=0,
  draw_bitmap( 0, 282, G_siapkiri, _, _),
  draw_bitmap( 559, 282, G_siapkanan, _, _).

  win_func(init):-
  G_waktu is set_timer(_,1,waktu),
  G_timer is set_timer(_,1,time_func),
  menu(right, _, _, menu_exit(_),"&Keluar").

  menu_exit(press):-
  close_window(_),
  stop.

%~~~~~~~~~~~~~~~~~~~~~~ waktu AI ~~~~~~~~~~~~~~~~~~~~~~~~~%
	waktu(end):-
	
	G_tuwak=0 ->
	G_tuwak:=0
	else
	
	G_tuwak:=G_tuwak-1,
	(G_tuwak=60 -> tahan(_)),
	(G_tuwak=59 -> tahan(_)),
	(G_tuwak=58 -> serang(_)), 
	(G_tuwak=57 -> tahan(_)),
	(G_tuwak=56 -> pasrah(_)),
	(G_tuwak=55 -> tahan(_)),
	(G_tuwak=54 -> serang(_)),
	(G_tuwak=53 -> pasrah(_)),
	(G_tuwak=52 -> pasrah(_)),
	(G_tuwak=51 -> tahan(_)),
	(G_tuwak=50 -> pasrah(_)),
	(G_tuwak=49 -> serang(_)),
	(G_tuwak=48 -> serang(_)), 
	(G_tuwak=47 -> tahan(_)),
	(G_tuwak=46 -> serang(_)),
	(G_tuwak=45 -> pasrah(_)),
	(G_tuwak=44 -> serang(_)),
	(G_tuwak=43 -> pasrah(_)),
	(G_tuwak=42 -> tahan(_)),
	(G_tuwak=41 -> tahan(_)),
	(G_tuwak=40 -> serang(_)),
	(G_tuwak=39 -> pasrah(_)),
	(G_tuwak=38 -> serang(_)), 
	(G_tuwak=37 -> tahan(_)),
	(G_tuwak=36 -> serang(_)),
	(G_tuwak=35 -> tahan(_)),
	(G_tuwak=34 -> serang(_)),
	(G_tuwak=33 -> pasrah(_)),
	(G_tuwak=32 -> pasrah(_)),
	(G_tuwak=31 -> tahan(_)),
	(G_tuwak=30 -> serang(_)),
	(G_tuwak=29 -> serang(_)),
	(G_tuwak=28 -> pasrah(_)), 
	(G_tuwak=27 -> tahan(_)),
	(G_tuwak=26 -> serang(_)),
	(G_tuwak=25 -> tahan(_)),
	(G_tuwak=24 -> serang(_)),
	(G_tuwak=23 -> pasrah(_)),
	(G_tuwak=22 -> pasrah(_)),
	(G_tuwak=21 -> tahan(_)),
	(G_tuwak=20 -> pasrah(_)),
	(G_tuwak=19 -> serang(_)),
	(G_tuwak=18 -> serang(_)), 
	(G_tuwak=17 -> tahan(_)),
	(G_tuwak=16 -> serang(_)),
	(G_tuwak=15 -> tahan(_)),
	(G_tuwak=14 -> serang(_)),
	(G_tuwak=13 -> pasrah(_)),
	(G_tuwak=12 -> pasrah(_)),
	(G_tuwak=11 -> tahan(_)),
	(G_tuwak=10 -> serang(_)),
	(G_tuwak=9 -> serang(_)),
	(G_tuwak=8 -> serang(_)), 
	(G_tuwak=7 -> pasrah(_)),
	(G_tuwak=6 -> serang(_)),
	(G_tuwak=5 -> tahan(_)),
	(G_tuwak=4 -> serang(_)),
	(G_tuwak=3 -> pasrah(_)),
	(G_tuwak=2 -> pasrah(_)),
	(G_tuwak=1 -> tahan(_)),


	(G_tuwak=0 ->
  	G_tuwak:=0 ->
 	message("Waktu Habis","Waktu habis, Anda terlalu Lama.!",!)).


%~~~~~~~~~~~~~~~~~~~~ waktu mulai ~~~~~~~~~~~~~~~~~~~~%
  time_func(end):-
  G_time=0->
  G_time:=0
  else
  G_time:=G_time-1,
  T:=printq(G_time),
  


  font(20,30,"Times New Roman"),
  color_text(_, rgb(255, 255, 255)),
  color_text_back(_,rgb(25,85,164)),
  text_out(435,20,T),
 

  (G_time=0 ->
  G_time:=0 ->
  draw_bitmap( 280, 20, G_mulai, _, _)).


%~~~~~~~~~~~~~~~~~~~~ respon komputer (AI) ~~~~~~~~~~~~~~~~~~~%

  telunjuk(_):-
  draw_bitmap( 559, 282, G_telkanan, _, _).

  jempol(_):-
  draw_bitmap( 559, 282, G_jemkanan, _, _).

  kelingking(_):-
  draw_bitmap( 559, 282, G_kelkanan, _, _).

  siap(_):-
  draw_bitmap(559, 282, G_siapkanan,_,_).

  pasrah(_):-
  (G_aksi=3 ->
  G_aksi_musuh:=2,
  kelingking(_),
  balik(_)),
  (G_aksi=4 ->
  G_aksi_musuh:=3,
  telunjuk(_),
  balik(_)),
  (G_aksi=5 ->
  G_aksi_musuh:=4,
  jempol(_),
  balik(_)).

  tahan(_):-
  (G_aksi=3 ->
  G_aksi_musuh:=3,
  telunjuk(_),
  balik(_)),
  (G_aksi=4 ->
  G_aksi_musuh:=4,
  jempol(_),
  balik(_)),
  (G_aksi=5 ->
  G_aksi_musuh:=5,
  kelingking(_),
  balik(_)).

  serang(_):-
  (G_aksi=3 ->
  G_aksi_musuh:=4,
  jempol(_),
  balik(_)),
  (G_aksi=4 ->
  G_aksi_musuh:=5,
  kelingking(_),
  balik(_)),
  (G_aksi=5 ->
  G_aksi_musuh:=6,
  telunjuk(_),
  balik(_)).

%~~~~~~~~~~~~~~~~~~~~~ Posisi Awal ~~~~~~~~~~~~~~~~~~~~~~~%
	balik(_):-
	wait(1.5),
	nilaimusuh(_),
	nilaiplay(_),
	draw_bitmap( 0, 282, G_siapkiri, _, _),
	siap(_),
	nilai(_),
	G_aksi:=0.

%~~~~~~~~~~~~~~~~~~~~~~~ Score ~~~~~~~~~~~~~~~~~~~~~~~~~~%
	nilaimusuh(_):-
	G_aksi<G_aksi_musuh -> 
	G_nilai_musuh:=G_nilai_musuh+1,
	G_aksi:=0,
	N:=printq(G_nilai_musuh),
  	font(15,35,"Goudy Stout"),
	color_text(_, rgb(30, 41, 145)),
	color_text_back(_,rgb(154,190,219)),
  	text_out(600,0,N).

	nilaiplay(_):-
	G_aksi>G_aksi_musuh ->
	G_nilai:=G_nilai+1,
	G_aksi:=0,
	N:=printq(G_nilai),
  	font(15,35,"Goudy Stout"),
	color_text(_, rgb(30, 41, 145)),
	color_text_back(_,rgb(154,190,219)),
  	text_out(150,0,N).

	nilai(_):-
	(G_nilai=3 -> 
	beep("win.wav"),
	message("WIN","    Score "+print(G_nilai)+" VS "+print(G_nilai_musuh)+" 
Selamat, Anda Menang ^.^",i),
	wait(0.5),
	stop,
	close_window(G_utama)),
	(G_nilai_musuh=3 -> 
	beep("lose.wav"),
	message("LOSE","     Score "+print(G_nilai)+" VS "+print(G_nilai_musuh)+" 
Maaf, Anda Kalah O_o   ",i),
	wait(0.5),
	stop,
	close_window(G_utama)).



%~~~~~~~~~~~~~~~~~~~~~~~~~ Curang ~~~~~~~~~~~~~~~~~~~~~~~~~%
	curang(_):-
	(G_time=0->
	G_time:=0
	else
	message("x_x_x","Anda Curang !!!",s),
	stop,
	close_window(G_utama)).

%~~~~~~~~~~~~~~~~~~~~~ Tindakan Pemain ~~~~~~~~~~~~~~~~~~~~~%

	win_func(key_down(37,_)):-
     curang(_),
	wait(1.0),

	(G_aksi:=3 ->
	draw_bitmap( 0, 282, G_telkiri, _, _)).

	win_func(key_down(38,_)):-
	curang(_),
	wait(1.0),
	
	(G_aksi:=4 ->
	draw_bitmap( 0, 282, G_jemkiri, _, _)).

	win_func(key_down(39,_)):-
	curang(_),
	wait(1.0),
	
	(G_aksi:=5 ->
	draw_bitmap( 0, 282, G_kelkiri, _, _)).



```

