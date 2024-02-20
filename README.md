# Beam_search
1. Introducere
Pentru rezolvarea jocului N-Puzzle am reușit să implementez toți algoritmii de căutare din cerința temei. Pentru partea de analiză am utilizat seturile de date easy și rezultatele obținute în urma rulării algoritmilor pot fi vizualizate aici: (Tabel_analiza_algoritmi)
Pentru toți cei patru algoritmi am utilizat euristicile de la cerința 1. Prima euristică este distanța Manhattan, care calculează suma distanțelor fiecărei piese de la poziția curentă, la poziția din starea finală. 
Cea de-a doua euristică returnează numărul de piese care se află pe poziții greșite.

2. Algoritmul A*
Pentru algoritmul A* am utilizat structura de la laborator. Pentru partea de analiză, am utilizat ambele euristici și am rulat algoritmul atât impunându-i limita din cerință pentru numărul de stări stocate în  memorie, cât și fără a-i impune o limită.
Pentru cazul în care am rulat algoritmul impunându-i o limită am obținut rezultatele:
Manhattan
distance	Nr jocuri finalizate	Medie lungime
cale	Varianța lungime cale	Medie nr stari	Varianța nr stari	Medie timp	Varianță timp
N=4	0	-	-	-	-	-	-
N=5	3	38.66	74.33	126874.6	9375958220	11.5	74.7
N=6	5	14.8	8.7	87	6333	0.02	0.0001

Wrong pos	Nr jocuri finalizate	Medie lungime
cale	Varianța lungime cale	Medie nr stari	Varianța nr stari	Medie timp	Varianță timp
N=4	0	-	-	-	-	-	-
N=5	1	-	-	-	-	-	-
N=6	5	14.8	8.7	603	1128028.5	0.019	0.0007

Putem observa că pentru ambele euristici se obțin rezultate asemănătoare, cu Manhattan distance am obținut un număr procent puțin mai mare de jocuri rezolvate.
Pentru cazul în care am rulat algoritmul fără să îi impun o limită de memorie, rezultatele sunt:
Manhattan
distance	Nr jocuri finalizate	Medie lungime
cale	Varianța lungime cale	Medie nr stari	Varianța nr stari	Medie timp	Varianță timp
N=4	3	38	25	1165313.66	8.37477E+11	201.51	58046.62
N=5	5	38.2	38.7	313139.4	51496283141	31147	551.22
N=6	5	14.8	8.7	87.8	6786.2	0.02	0.0003

Wrong pos	Nr jocuri finalizate	Medie lungime
cale	Varianța lungime cale	Medie nr stari	Varianța nr stari	Medie timp	Varianță timp
N=4	0	-	-	-	-	-	-
N=5	2	30	2	323546.5	1.23912E+11	18.286	439.798482
N=6	5	14.8	8.7	575	894367.5	0.054	0.006

Și în acest caz utilizând euristica Manhattan distance am obținut rezultate mai bune, și se poate observa, de asemenea, că fără a impune o limită a numărului de stări care pot fi stocate în memorie algoritmul reușește să rezolve problema N-Puzzle pentru mai multe seturi de date decât în primul caz.

3. Beam Search
La fel ca pentru algoritmul A* și în cazul algoritmului Beam-search am rulat utilizând ambele euristici, toate valorile date pentru B și utilizând valorile impuse de cerință pentru limita numărului de stări stocate în memorie. Toate rezultatele obținute pot fi văzute aici: (Tabel_analiza_algoritmi)
Comparativ cu A*, pentru Beam-search am obținut rezultate mai bune utilizând euristica wrong_pos, cele mai multe jocuri fiind finalizate pentru B=500 și B=1000.

4. GLDS
La algoritmul GLDS am întâmpinat mici dificultăți în momentul rulării și încă nu îmi dau seama dacă de vină sunt eu pentru că am implementat prost algoritmul(varianta cea mai posibilă), este laptopul pentru că are doar 4Gb de memorie sau pur și simplu nu este un algoritm la fel de bun ca celelalte. 
Aproape la fiecare rulare obțineam eroarea din imaginea atașată mai jos, însoțită uneori și de Black screen pentru câteva secunde. Am reușit totuși să fac o pseudo-testare pe probleme generate utilizând funcția genOne și algoritmul pare să găsească soluția doar pe probleme cu o complexitate foarte mică.
 
Figură 1-Problemă GLDS

 5. BLDS
La fel ca la ceilalți algoritmi, rezultatele obținute în urma rulării pot fi văzute aici: (Tabel_analiza_algoritmi)
Pentru euristica wrong_pos am obținut un număr mai mare de jocuri rezolvate decât pentru Manhattan distance. Trebuie menționat faptul că pentru Manhattan distance, pentru B=500 am rulat câte o singură problemă din seturile cu N=5 si N=6 pentru că dura foarte, foarte mult până găsea soluția. 
Comparativ cu Beam-search și A*, BLDS rezolvă un număr mai mare de probleme, însă timpul de rulare este mai mare, la fel și numărul de stări stocate în memorie.
Mai jos sunt graficele în care se poate observa diferența de medie și varianță pentru fiecare metrică, între BLDS și Beam-search, folosind euristica wrong_pos.


6. Concluzie

Algoritmul BLDS este cel care reușește să găsească soluția pentru cel mai mare set de date, cu observația că necesită un timp de rulare mult mai mare comparativ cu ceilalți algoritmi și, pentru dimensiuni mari ale problemei(în cazul nostru N=6), stochează și mai multe stări în memorie.
Nu am reușit să implementez mecanismul de joc pentru Turnurile din Hanoi.

7. Referințe
Tabel analiza algoritmi https://docs.google.com/spreadsheets/d/17QGLmoTlyk32CWjTCK7LteI1cbaY3_WaMmYzPp_zLOM/edit?usp=sharing

