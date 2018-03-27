Databáze.

Ukládání dat, adresace záznamů. Indexování a hašování pro více atributů, bitmapové indexy, dynamické hašování. Vyhodnocení dotazů, transformační pravidla, statistiky a odhady. Optimalizace dotazů a schématu. Transakční zpracování, výpadky a zotavení. Podobnostní vyhledávání. 
PA152, PA128

Databáze

Pouzivame pro efektivni ukladani, vyhledavani a zpracovani dat.

Storage Manager
	správa bloků na disku
	správa vyrovnávací paměti
Query Processor
	překlad dotazu, optimalizace
	vyhodnocení dotazu
Transaction Manager
	atomičnost, izolovanost a trvalost transakcí

DBMS - Database management system - sada nastroju pro ukladani dat

Relační model
  Struktura –data v relacích (tabulkách)
  Operace –dotazování, modifikace
  SQL, relační algebra

## Ukládání dat

### Hiearchie ukladani pameti
Rychle pameti stoji hodne penez, tak mame hiearchii a preklapime z pomalych do rychlych dle potreby

- primarni - cache, RAM
- sekundarni - Disk
- tercialni - zalozni - pasky, opticke disky

Rotacni disk
- pristupova doba(access time) - cas mezi pozadavkem a prenosem dat
  - vystaveni hlavicek
  - rotace disku  
- Atomicka jednotka cteni je sektor/diskovy blok
  - velky blok - amortizace I/O nakaldu, ale cteni vice nepotrebnych dat v okoli
- Sekvencni cteni mnohem rychlejsi nez random pristupy

### DBMS minimalizuje pocet nahodne ctenych bloku
- Defragmentace 
- Planovani pristupu
  - preusporadani pristupu na disk
  - pohyb hlavicky jednim smerem(Jako kdyz sbira lidi vytah, ale jsou i jine pristupy)
- Prefetching

### Diskova pole
- vice disku jako jeden logicky 
- paralelni cteni a zapis
- metody
  - Rozdeleni dat(data striping)
  - Zrcadleni dat (mirroring)


#### zrcadleni
- data ukladana na vic disku a ctena z jednoho z nich
- zvyseni spolehlivosti 
- Data dostupna pri vypadku disku
- Vypadky disku nemusi byt nezavisle(pozar, elektricky zkrat)

#### Rozdeleni dat
- (Jeden blok dat ulozen po castech na ruznych discich)
- Zvyseni prenosove rychlosti
- Paralelizace velkeho cteni
- Vyrovnani zateze - vetsi propustnost
- Vypadky disku nemusi byt nezavisle(pozar, elektricky zkrat)

#### RAID - Redundant Arrays of Independent Disks
Zpusoby rozdeleni dat na discich.
ruzne varianty pro ruzne pozadavky
NENHRAZUJE ZALOHOVANI
- vykonnost 
- spolehlivost
- Kombinace variant


RAID0 - block striping
blok ulozen po castech na vice disku
vysoky vykon, stejne kapacita, nezvysena spolehlivost

RAID1 - Zrcadleni
Kazda disk existuje celkem v n kopiich(Vetsinou n=2)
kapacita 1/n,rychle cteni, zapis jako 1 disk
vysoky vykon, stejne kapacita, nezvysena spolehlivost

RAID5 - data i kontrola parity rozdelena mezi n disku
![parita](./raid5.png) 
zapis bloku je paralelni, pokud jsou na ruznych discich

Jednotlive varianty lze kombinovat
Nejcasteji kombinace RAID1 nebo RAID5 s RADI0 (RAID1+0,RAID5+0)
![raid10](./raid10.png) 