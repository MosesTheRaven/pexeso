Dokumentacia k hre PEXESO




Uzivatelska cast:

Cela hra je obsiahnuta v programe pexeso. 
K spusteniu nie su potrebne ziadne config subory, vsetky nastavenia sa nastavuju v programe.


Programatorska cast:

Cely program je pisany v awk.


Cast BEGIN nacita vstup, vola generovanie pexesa, zamiesanie pexesa, vypise pexeso.
V tejto casti sa nastavia premenne tahy (pochopitelne na pocitanie tahov) a spravnych (na pocitanie skore).

	Pri nacitavani vstupu funkcia getInput() ocakava parne cislo v intervale od 2 do 8. Bude volat sama seba, kym sa nezada spravny vstup. V tejto funkcii sa 			nastavi aj premenna number. Tato premenna sa bude pouzivat vo vacsine funkcii.
	
	Po nacitani vstupu je volana funkcia generateArray(). Tato funkcia vyplni pole (alebo skor mapu) pexesa array[x,y]. Polozky tohto pola su cisla, pocnuc od 33 			(33 je prve cislo, ktore sa da efektne zobrazit[medzera = char(32) bude pouzita inak]). Premenna pexesoNumber znaci cisla, ktore sa doplnaju do pola 			pexesa. Pri generovani sa cisla ukladaju vedla seba: 33 33 34 34 35 35...

	Po vygenerovani array sa musi pexeso zamiesat, inak by hra nemala zmysel. Funkcia randomizeArray() zamiesa polozky pexesa nasledujucim sposobom: nahodne si 			vyberie dve polozky (mozu byt aj rovnake ale taka moznost je velmi malo pravdepodobna) a cisla v tychto polozkach vymeni. Taketo miesanie sa uskutocni 			times-krat. Premenna times sa da zmenit, podla toho ako velmi ma byt pexeso premiesane. 

Cast ktora, sa spusta na kazdy riadok, ktory uzivatel zada, vybera dve polozky z array, porovnava ich a podla vysledku porovnania vyhodnoti, ako nasledovat.
	Pri kazdom regulernom tahu sa inkrementuje premenna tahy. 
	Pri kazdom uspesnom tahu (hrac nasiel dva rovnake znaky) sa inkrementuje aj premenna spravnych a v dalsich tahoch sa na tychto miestach bude zobrazovat uz len 			prazdne miesto. 
	Ak hrac zada nespravne vstupne suradnice pexes, tak sa tah nepocita. 
	Ak hrac zada 2x rovnake suradnice, tak sa rozhodol pouzit hint - v poli sa na 3 sekundy ukaze hracom zvolena pozicia.
Ak hrac nahral maximalne skore, tak sa hra skoncila. 

Cast END nakoniec vypise pocet tahov a spyta sa, ci hrac chce hrat dalej.
[Tu treba doplnit ako znova spustit hru].

   
	
