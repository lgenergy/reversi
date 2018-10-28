# Útvonaltervezõ program elõzetes specifikációi:
---
1. **Bemenet**:
  * Térkép egy irányított gráf
  * Gráf csúcsai a keresztezõdések/városok, koordináták a síkon `(x,y)`
  * Gráf élei az utak, szomszédsági mátrixszal adjuk meg õket `A` 
  * Utakhoz egy bináris `m` vektor, ami megmondja, hogy megkülönböztetett-e (néha nem szeretnénk autópályán haladni)
  * Minden úthoz egy `c` költségvektor ami megadja, hogy mennyi idõ alatt lehet megtenni 1 egység távolságotaz adott úton (leggyorsabb út számítása)
  * Ezek a térkép szöveges reprezentációi, ezeket fájlból olvassuk be 

### **Algoritmus**:
* A gráfban kell 2 csúcs között irányított utakat megtalálni 
* Mélységi (DFS) vagy szélességi (BFS) bejárás megtalálja a legrövidebbet, erre tudunk C kódot írni
* Utak hossza a benne lévõ élek hosszainak az összege 
* Egy él hossza az útvonaltervezés szempontjaitól függ: (ezeket elõzetesen megadja a felhasználó)
*Legrövidebb út* : hossz =  csúcsok koordinátáinak távolsága
*Leggyorsabb út*: hossz =  fentit megszorozzuk a `c` vektor megfelelõ komponensével
*Autópálya nélkül*: Ez esetben bejön a képbe az `m` megkülönböztetõ vektor
* Esetleg lehet még olyan paraméter, hogy melyik keresztezõdést/várost érintsük az út során

3. **Kimenet**:
* SDL grafikus programcsomag segítségével látható lesz a teljes gráf
* A legrövidebb utak megkülönböztetett színûek lesznek
---
**Összegzés:**
A programban lehet választani, hogy a megadott térképen (gráf) melyik csúcsból melyik csúcsba szeretnénk menni, illetve ki lehet választani az útvonaltervezés szempontját is (legrövidebb/leggyorsabb, autópálya használatával/nem használatával, köztes csúcs érintésével...). Ezek után a térképen látható lesz a kívánt útvonal piros színnel és az út hossza és ideje. Ezt a program BFS vagy DFS és ügyes paraméterezés segítségével oldja meg.
