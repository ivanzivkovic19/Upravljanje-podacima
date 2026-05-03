Zadatak 1.

Green = Sve radi
Yellow = Klaster nema nedodijeljenih primarnih fragmenta, ali ima neke nedodijeljene replike fragmenta. To povećava rizik od gubitka podataka i može smanjiti performanse klastera.
Red = Klaster ima neke nedodijeljene primarne fragmente, što znači da neke operacije poput pretraživanja i indeksiranja mogu zakazati

Zadatak 2.
5. Naslov je tipa text jer se koristi za full-text pretragu po riječima. Elasticsearch ga analizira i razbija na tokene kako bi mogao pronaći slične ili djelomične podudarnosti.
6. Polje naslov.keyword omogućuje točno pretraživanje cijelog naslova bez analize. Također se koristi za sortiranje i agregacije gdje je potrebna originalna vrijednost.
7. Autor i žanr su tipa keyword jer se koriste za točno podudaranje i filtriranje. Nema potrebe za analizom teksta jer se vrijednosti ne dijele na riječi.
8. Opis je duži tekst i treba se pretraživati po riječima, pa mora biti tipa text. Ako bi bio keyword, pretraga bi radila samo za potpuno iste rečenice, što nije praktično.

Zadatak 3.
11. Zbog analyzera koji pretvara tekst u mala slova i uklanja dijakritike. Riječ "ćuprija" se u indeksu sprema kao "cuprija", pa se podudara s upitom.
12. _score označava koliko dokument odgovara upitu (relevantnost). Razlikuje se jer neki dokumenti sadrže više traženih riječi ili ih sadrže na važnijim mjestima.

Zadatak 5.
18. Tokeni za tekst "Na Drini ćuprija" su: na, drini, cuprija. Tekst se razbija na riječi i obrađuje analyzerom.
19. Lowercase pretvara sva slova u mala. Asciifolding uklanja dijakritike (npr. ć → c). Razlika je što jedan mijenja veličinu slova, a drugi znakove.
20. Analyzer omogućuje da se tekst pravilno pretražuje po riječima i sličnim oblicima. Bez njega bi pretraga bila stroga i radila bi samo za potpuno iste riječi.

Zadatak Završni
30. Elasticsearch je brži od SQL LIKE jer koristi indeks. SQL mora pregledati sve podatke a Elasticsearch odmah nalazi rezultate. Može ignorirati velika slova i dijalekte. Može pronaći slične riječi ne samo tekst. Rezultati su sortitani po relevantnosti (score). Može raditi sa velikim količinama podataka i lako se skalira