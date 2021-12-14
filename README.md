#include <iostream>
#include <ncurses.h>
#include <windows.h>
using namespace std;

void loading(){
	initscr();
	
	WINDOW * win = newwin (21, 37, 5, 10);
	refresh();
	box(win, 0, 0);
	refresh();
	
	start_color();
	init_pair(1,COLOR_WHITE,COLOR_WHITE);
	
	mvwprintw(win, 9, 13, "Loading...");
	wrefresh(win);
	
	wattron(win,COLOR_PAIR(1));
	mvwprintw(win, 10, 10, ".");
	wrefresh(win);
	Sleep(100);
	mvwprintw(win, 10, 11, ".");
	wrefresh(win);
	Sleep(100);
	mvwprintw(win, 10, 12, ".");
	wrefresh(win);
	Sleep(100);
	mvwprintw(win, 10, 13, ".");
	wrefresh(win);
	Sleep(500);
	mvwprintw(win, 10, 14, "..");
	wrefresh(win);
	Sleep(100);
	mvwprintw(win, 10, 16, ".");
	wrefresh(win);
	Sleep(100);
	mvwprintw(win, 10, 17, ".");
	wrefresh(win);
	Sleep(100);
	mvwprintw(win, 10, 18, ".");
	wrefresh(win);
	Sleep(100);
	mvwprintw(win, 10, 19, ".");
	wrefresh(win);
	Sleep(100);
	mvwprintw(win, 10, 20, ".");
	wrefresh(win);
	Sleep(400);
	mvwprintw(win, 10, 21, "...");
	wrefresh(win);
	Sleep(100);
	mvwprintw(win, 10, 24, ".");
	wrefresh(win);
	Sleep(100);
	
	wattroff(win,COLOR_PAIR(1));
	
}

void proses(){
	initscr();
	
	WINDOW * win = newwin (21, 37, 5, 10);
	refresh();
	
	for(int i=0; i<3; i++){
		box(win, 0, 0);
		refresh();
		mvwprintw(win,9,8,"Sedang memproses");
		wrefresh(win);
		mvwprintw(win,9,24,".");
		Sleep(200);
		wrefresh(win);
		mvwprintw(win,9,25,".");
		Sleep(200);
		wrefresh(win);
		mvwprintw(win,9,26,".");
		Sleep(200);
		wrefresh(win);
		mvwprintw(win,9,26,".");
		Sleep(200);
		wrefresh(win);
		wclear(win);
	}
}

int main(){
	initscr();
	
	ulang:
		
	char ulangi;
	
	WINDOW * win = newwin (21, 37, 5, 10);
	refresh();
	
	box(win, 0, 0);
	refresh();
	
	start_color();
	init_pair(1,COLOR_WHITE,COLOR_WHITE);
	
	wattron(win,COLOR_PAIR(1));
	
	
	//huruf Q
	mvwprintw(win, 2, 9, "....");
	wrefresh(win);
	
	mvwprintw(win, 3, 9, ".");
	wrefresh(win);
	
	mvwprintw(win, 4, 9, ".");
	wrefresh(win);
	
	mvwprintw(win, 5, 9, ".....");
	wrefresh(win);
	
	mvwprintw(win, 4, 12, ".");
	wrefresh(win);
	
	mvwprintw(win, 3, 12, ".");
	wrefresh(win);
	
	//huruf U
	mvwprintw(win, 2, 15, ".");
	wrefresh(win);
	
	mvwprintw(win, 3, 15, ".");
	wrefresh(win);
	
	mvwprintw(win, 4, 15, ".");
	wrefresh(win);
	
	mvwprintw(win, 5, 15, "....");
	wrefresh(win);
	
	mvwprintw(win, 4, 18, ".");
	wrefresh(win);
	
	mvwprintw(win, 3, 18, ".");
	wrefresh(win);
	
	mvwprintw(win, 2, 18, ".");
	wrefresh(win);
	
	//huruf I
	mvwprintw(win, 2, 20, "...");
	wrefresh(win); 
	
	mvwprintw(win, 3, 21, ".");
	wrefresh(win);
	
	mvwprintw(win, 4, 21, ".");
	wrefresh(win);
	
	mvwprintw(win, 5, 20, "...");
	wrefresh(win);
	
	//huruf Z
	mvwprintw(win, 2, 24, "....");
	wrefresh(win);
	
	mvwprintw(win, 3, 26, ".");
	wrefresh(win);
	
	mvwprintw(win, 4, 25, ".");
	wrefresh(win);
	
	mvwprintw(win, 5, 24, "....");
	wrefresh(win);
	
	//garis
	mvwprintw(win, 8, 1, "...................................");
	wrefresh(win);
	
	wattroff(win,COLOR_PAIR(1));
	
	//pilihan
	string pilih[2] = {"1.START", "2.EXIT"};
	
	mvwprintw(win, 11, 15, pilih[0].c_str());
	wrefresh(win);
	
	mvwprintw(win, 12, 15, pilih[1].c_str());
	wrefresh(win);
	
	mvwprintw(win, 18, 1, "type 1 for start, 2 exit,");
	wrefresh(win);
	
	wattron(win, A_REVERSE);
	mvwprintw(win, 19, 1, "type a code:");
	wrefresh(win);
	wattroff(win, A_REVERSE);
	char x = wgetch(win);
	wprintw(win, "%c",x);
	Sleep(500);
	wclear(win);
	
	char nama [256];
	char jawab;
	int hp = 3;
	int score = 0;
	int totscore = 0;
	
	box(win, 0, 0);
	refresh();
	
	if(x=='1'){
	//start
		loading();
		mvwprintw(win, 3, 1, "*can't use space");
		mvwprintw(win, 4, 1, "press ENTER if finish");
		mvwprintw(win, 1, 1, "masukkan username anda: ");
		wrefresh(win);
		wscanw(win, "%s",nama);
		wclear(win);
		loading();
		
		//soal nomor 1
		if(hp>0){
			box(win, 0, 0);
			refresh();
			
			wattron(win, A_REVERSE);
			mvwprintw(win, 0, 1, "%s",nama);
			wrefresh(win);
			mvwprintw(win, 0, 24, "HP");
			mvwprintw(win, 0, 26, "%d",hp);
			wrefresh(win);
			mvwprintw(win, 0, 29, "Score");
			mvwprintw(win, 0, 34, "%d",score);
			wrefresh(win);
			wattroff(win, A_REVERSE);
			
			//soal
			mvwprintw(win, 2, 1, "1. Ibukota dari negara Cina adalah?");
			wrefresh(win);
			mvwprintw(win, 4, 4, "a. Beijing");
			wrefresh(win);
			mvwprintw(win, 6, 4, "b. Seoul");
			wrefresh(win);
			mvwprintw(win, 8, 4, "c. Tokyo");
			wrefresh(win);
			mvwprintw(win, 10, 4, "d. Pyongyang");
			wrefresh(win);
			mvwprintw(win, 12, 1, "Jawab Pertanyaan Diatas: ");
			wrefresh(win);
			jawab = wgetch(win);
			mvwprintw(win, 13, 1, "Jawaban anda adalah %c",jawab);
			mvwprintw(win, 18, 1, "*press ENTER to go to the next");
			wrefresh(win);
			mvwprintw(win, 19, 1, "question");
			wrefresh(win);
			
			if(jawab=='a'||jawab=='A'){
				score+=10;
				wattron(win, A_REVERSE);
				mvwprintw(win, 0, 34, "%d",score);
				wrefresh(win);
				wattroff(win, A_REVERSE);
				mvwprintw(win, 15, 1, "Selamat Jawaban Anda Benar!!!");
				wrefresh(win);
			}else{
				hp-=1;
				wattron(win, A_REVERSE);
				mvwprintw(win, 0, 26, "%d",hp);
				wrefresh(win);
				wattroff(win, A_REVERSE);
				mvwprintw(win, 15, 1, "Maaf Jawaban Anda Salah!!!");
				wrefresh(win);
			}
		}
		wgetch(win);
		wclear(win);
		//soal nomor 2
		if(hp>0){
			box(win, 0, 0);
			refresh();
			
			wattron(win, A_REVERSE);
			mvwprintw(win, 0, 1, "%s",nama);
			wrefresh(win);
			mvwprintw(win, 0, 24, "HP");
			mvwprintw(win, 0, 26, "%d",hp);
			wrefresh(win);
			mvwprintw(win, 0, 29, "Score");
			mvwprintw(win, 0, 34, "%d",score);
			wrefresh(win);
			wattroff(win, A_REVERSE);
			
			//soal
			mvwprintw(win, 2, 1, "2. Kota terpadat KEDUA di dunia ");
			wrefresh(win);
			mvwprintw(win, 3, 1, "Adalah ?");
			wrefresh(win);
			mvwprintw(win, 5, 4, "a. Delhi");
			wrefresh(win);
			mvwprintw(win, 7, 4, "b. Jakarta");
			wrefresh(win);
			mvwprintw(win, 9, 4, "c. Tokyo");
			wrefresh(win);
			mvwprintw(win, 11, 4, "d. New York");
			wrefresh(win);
			mvwprintw(win, 13, 1, "Jawab Pertanyaan Diatas: ");
			wrefresh(win);
			jawab = wgetch(win);
			mvwprintw(win, 14, 1, "Jawaban anda adalah %c",jawab);
			mvwprintw(win, 18, 1, "*press ENTER to go to the next");
			wrefresh(win);
			mvwprintw(win, 19, 1, "question");
			wrefresh(win);
			
			if(jawab=='a'||jawab=='A'){
				score+=10;
				wattron(win, A_REVERSE);
				mvwprintw(win, 0, 34, "%d",score);
				wrefresh(win);
				wattroff(win, A_REVERSE);
				mvwprintw(win, 15, 1, "Selamat Jawaban Anda Benar!!!");
				wrefresh(win);
			}else{
				hp-=1;
				wattron(win, A_REVERSE);
				mvwprintw(win, 0, 26, "%d",hp);
				wrefresh(win);
				wattroff(win, A_REVERSE);
				mvwprintw(win, 15, 1, "Maaf Jawaban Anda Salah!!!");
				wrefresh(win);
			}
		}
		wgetch(win);
		wclear(win);
		//soal nomor 3
		if(hp>0){
			box(win, 0, 0);
			refresh();
			
			wattron(win, A_REVERSE);
			mvwprintw(win, 0, 1, "%s",nama);
			wrefresh(win);
			mvwprintw(win, 0, 24, "HP");
			mvwprintw(win, 0, 26, "%d",hp);
			wrefresh(win);
			mvwprintw(win, 0, 29, "Score");
			mvwprintw(win, 0, 34, "%d",score);
			wrefresh(win);
			wattroff(win, A_REVERSE);
			
			//soal
			mvwprintw(win, 2, 1, "3. Siapakah dibawah ini yang ");
			wrefresh(win);
			mvwprintw(win, 3, 1, "mengetik naskah proklamasi ?");
			wrefresh(win);
			mvwprintw(win, 5, 4, "a. Ir. Soekarno");
			wrefresh(win);
			mvwprintw(win, 7, 4, "b. Moh. Hatta");
			wrefresh(win);
			mvwprintw(win, 9, 4, "c. Sayuti Melik");
			wrefresh(win);
			mvwprintw(win, 11, 4, "d. Fatmawati");
			wrefresh(win);
			mvwprintw(win, 13, 1, "Jawab Pertanyaan Diatas: ");
			wrefresh(win);
			jawab = wgetch(win);
			mvwprintw(win, 14, 1, "Jawaban anda adalah %c",jawab);
			mvwprintw(win, 18, 1, "*press ENTER to go to the next");
			wrefresh(win);
			mvwprintw(win, 19, 1, "question");
			wrefresh(win);
			
			if(jawab=='c'||jawab=='C'){
				score+=10;
				wattron(win, A_REVERSE);
				mvwprintw(win, 0, 34, "%d",score);
				wrefresh(win);
				wattroff(win, A_REVERSE);
				mvwprintw(win, 15, 1, "Selamat Jawaban Anda Benar!!!");
				wrefresh(win);
			}else{
				hp-=1;
				wattron(win, A_REVERSE);
				mvwprintw(win, 0, 26, "%d",hp);
				wrefresh(win);
				wattroff(win, A_REVERSE);
				mvwprintw(win, 15, 1, "Maaf Jawaban Anda Salah!!!");
				wrefresh(win);
			}
		}else{
			proses();
			box(win, 0, 0);
			refresh();
			mvwprintw(win, 7, 14, "GAME OVER");
			wrefresh(win);
			mvwprintw(win, 9, 5, "username: %s",nama);
			wrefresh(win);
			totscore+=score*hp;
			mvwprintw(win, 10, 5, "total score= score x hp = %d",totscore);
			wrefresh(win);
			mvwprintw(win, 12, 1, "Anda ingin kembali ke menu (y/n)?");
			wrefresh(win);
			wscanw(win, "%c",&ulangi);
			if(ulangi=='y'||ulangi=='Y'){
				wclear(win);
				goto ulang;
			}else{
				wclear(win);
				goto out;
			}
		}
		wgetch(win);
		wclear(win);
		//soal nomor 4
		if(hp>0){
			box(win, 0, 0);
			refresh();
			
			wattron(win, A_REVERSE);
			mvwprintw(win, 0, 1, "%s",nama);
			wrefresh(win);
			mvwprintw(win, 0, 24, "HP");
			mvwprintw(win, 0, 26, "%d",hp);
			wrefresh(win);
			mvwprintw(win, 0, 29, "Score");
			mvwprintw(win, 0, 34, "%d",score);
			wrefresh(win);
			wattroff(win, A_REVERSE);
			
			//soal
			mvwprintw(win, 2, 1, "4. Warna Bendera Amerika Serikat ?");
			wrefresh(win);
			mvwprintw(win, 4, 4, "a. merah, biru");
			wrefresh(win);
			mvwprintw(win, 6, 4, "b. merah, putih, hijau");
			wrefresh(win);
			mvwprintw(win, 8, 4, "c. merah, biru, hitam");
			wrefresh(win);
			mvwprintw(win, 10, 4, "d. merah, putih, biru");
			wrefresh(win);
			mvwprintw(win, 12, 1, "Jawab Pertanyaan Diatas: ");
			wrefresh(win);
			jawab = wgetch(win);
			mvwprintw(win, 13, 1, "Jawaban anda adalah %c",jawab);
			mvwprintw(win, 18, 1, "*press ENTER to go to the next");
			wrefresh(win);
			mvwprintw(win, 19, 1, "question");
			wrefresh(win);
			
			if(jawab=='d'||jawab=='D'){
				score+=10;
				wattron(win, A_REVERSE);
				mvwprintw(win, 0, 34, "%d",score);
				wrefresh(win);
				wattroff(win, A_REVERSE);
				mvwprintw(win, 15, 1, "Selamat Jawaban Anda Benar!!!");
				wrefresh(win);
			}else{
				hp-=1;
				wattron(win, A_REVERSE);
				mvwprintw(win, 0, 26, "%d",hp);
				wrefresh(win);
				wattroff(win, A_REVERSE);
				mvwprintw(win, 15, 1, "Maaf Jawaban Anda Salah!!!");
				wrefresh(win);
			}
		}else{
			proses();
			box(win, 0, 0);
			refresh();
			mvwprintw(win, 7, 14, "GAME OVER");
			wrefresh(win);
			mvwprintw(win, 9, 5, "username: %s",nama);
			wrefresh(win);
			totscore+=score*hp;
			mvwprintw(win, 10, 5, "total score= score x hp = %d",totscore);
			wrefresh(win);
			mvwprintw(win, 12, 1, "Anda ingin kembali ke menu (y/n)?");
			wrefresh(win);
			wscanw(win, "%c",&ulangi);
			if(ulangi=='y'||ulangi=='Y'){
				wclear(win);
				goto ulang;
			}else{
				wclear(win);
				goto out;
			}
		}
		wgetch(win);
		wclear(win);
		//soal nomor 5
		if(hp>0){
			box(win, 0, 0);
			refresh();
			
			wattron(win, A_REVERSE);
			mvwprintw(win, 0, 1, "%s",nama);
			wrefresh(win);
			mvwprintw(win, 0, 24, "HP");
			mvwprintw(win, 0, 26, "%d",hp);
			wrefresh(win);
			mvwprintw(win, 0, 29, "Score");
			mvwprintw(win, 0, 34, "%d",score);
			wrefresh(win);
			wattroff(win, A_REVERSE);
			
			//soal
			mvwprintw(win, 2, 1, "5. Planet Manakah Yang Paling Dekat");
			wrefresh(win);
			mvwprintw(win, 3, 1, "Dengan Matahari ?");
			wrefresh(win);
			mvwprintw(win, 5, 4, "a. Pluto");
			wrefresh(win);
			mvwprintw(win, 7, 4, "b. Merkurius");
			wrefresh(win);
			mvwprintw(win, 9, 4, "c. Venus");
			wrefresh(win);
			mvwprintw(win, 11, 4, "d. Saturnus");
			wrefresh(win);
			mvwprintw(win, 13, 1, "Jawab Pertanyaan Diatas: ");
			wrefresh(win);
			jawab = wgetch(win);
			mvwprintw(win, 14, 1, "Jawaban anda adalah %c",jawab);
			mvwprintw(win, 18, 1, "*press ENTER to go to the next");
			wrefresh(win);
			mvwprintw(win, 19, 1, "question");
			wrefresh(win);
			
			if(jawab=='b'||jawab=='B'){
				score+=10;
				wattron(win, A_REVERSE);
				mvwprintw(win, 0, 34, "%d",score);
				wrefresh(win);
				wattroff(win, A_REVERSE);
				mvwprintw(win, 15, 1, "Selamat Jawaban Anda Benar!!!");
				wrefresh(win);
			}else{
				hp-=1;
				wattron(win, A_REVERSE);
				mvwprintw(win, 0, 26, "%d",hp);
				wrefresh(win);
				wattroff(win, A_REVERSE);
				mvwprintw(win, 15, 1, "Maaf Jawaban Anda Salah!!!");
				wrefresh(win);
			}
		}else{
			proses();
			box(win, 0, 0);
			refresh();
			mvwprintw(win, 7, 14, "GAME OVER");
			wrefresh(win);
			mvwprintw(win, 9, 5, "username: %s",nama);
			wrefresh(win);
			totscore+=score*hp;
			mvwprintw(win, 10, 5, "total score= score x hp = %d",totscore);
			wrefresh(win);
			mvwprintw(win, 12, 1, "Anda ingin kembali ke menu (y/n)?");
			wrefresh(win);
			wscanw(win, "%c",&ulangi);
			if(ulangi=='y'||ulangi=='Y'){
				wclear(win);
				goto ulang;
			}else{
				wclear(win);
				goto out;
			}
		}
		wgetch(win);
		wclear(win);
		
		if(hp>0){
			proses();
			box(win, 0, 0);
			refresh();
			
			mvwprintw(win, 7, 5, "SELAMAT %s KAMU BERHASIL",nama);
			wrefresh(win);
			mvwprintw(win, 8, 5, "  MENAMATKAN GAME INI!!!");
			mvwprintw(win, 10, 5, "username: %s", nama);
			wrefresh(win);
			totscore+=score*hp;
			mvwprintw(win, 11, 5, "total score= score x hp = %d",totscore);
			wrefresh(win);
			mvwprintw(win, 13, 1, "Anda ingin kembali ke menu (y/n)?");
			wrefresh(win);
			wscanw(win, "%c",&ulangi);
			if(ulangi=='y'||ulangi=='Y'){
				wclear(win);
				goto ulang;
			}else{
				wclear(win);
				goto out;
			}
		}else{
			proses();
			box(win, 0, 0);
			refresh();
			mvwprintw(win, 7, 14, "GAME OVER");
			wrefresh(win);
			mvwprintw(win, 9, 5, "username: %s",nama);
			wrefresh(win);
			totscore+=score*hp;
			mvwprintw(win, 10, 5, "total score= score x hp = %d",totscore);
			wrefresh(win);
			mvwprintw(win, 12, 1, "Anda ingin kembali ke menu (y/n)?");
			wrefresh(win);
			wscanw(win, "%c",&ulangi);
			if(ulangi=='y'||ulangi=='Y'){
				wclear(win);
				goto ulang;
			}else{
				wclear(win);
				goto out;
			}
		}
	}
	if(x=='2'){
		//exit
		goto out;
	}
	out:
	mvwprintw(win, 9, 5, "Anda sudah keluar dari game");
	wrefresh(win);
	Sleep(2000);
	endwin();
}
