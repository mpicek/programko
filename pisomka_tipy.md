Vo všetkých ako kategóriách bude ako príklad uvedený riešenie problému:
**Najít člověka/lidi, kteří se na náměstí vyskytují nejdelší dobu.**

#Tohle je typ na zkousku:
DOBRA RADA, KDYZ DOSTANEME PERGELA:
tohle napsala jedna holka na forum, co pergela mela:
Z ústní mi dal dynamické programování a ptal se jaký znám použití, 
    uzávorkování násobení matic je prý jeho nejoblíbenější.


# Postřehy

Táto kategória by mala byť vyriešená hneď na začiatku, respektíve ešte pred
predložením záverečného riešenia. Obsahuje veci, ktoré si na probléme všimneš.
Môžu to byť **problémy** ktoré sa môžu vyskytnúť, nepresnosti s ktorými sa
musí počítať, invarianty alebo iné konštanty, alebo jednoduché pozorovania o
probléme.

Pozorovania, konštanty (príklad):

    - Bez pohybu kamery

    - čím kvalitnější záznam, tím lepší výsledek

    - cokoliv použijeme k poznání lidí, bude nejspíš poměrně nepřesné


Problémy (príklad)

    - Některé skupinky nemožné rozlišit

    - problém s osvícením, budovy, pixel se bude muset  trochu hýbat,
      mnoho lidí mělo černou bundu

    - Tramvaje a auta působí problém.

    - potřeba poznat, že člověk nastoupil/vystoupil do/z vozidla

    - jak poznat, co se děje za tramvají (nastoupil/odešel v zákrytu)

    - dva lidi se překryjí -> započítávat oba, jak poznat, že jeden nastoupil
      do tramvaje

    - jak určit identitu (člověk odejde ze záběru a zase se vrátí),
      podle čeho poznat, že člověk je na dvou snímcích, když se otočí,...

    - Potřebujeme poznat stejného člověka na různých fotkách
        - můžeme předpokládat, že se nepřevlíká.
        - že se pohybuje přiměřenou rychlostí
        - ale pořád nám může zmizet ze záběru


Na toto všetko sa dá často naraziť pri tvorení algoritmu. Osobne by som strávil
len niaky čas v tejto sekcií, zamyslel sa nad problémom ale moc sa nezdržiaval
s nachádzaním všetkých problémov. Nechal by som si si volné miesto a body
postupne dopisoval ako budem riešiť algoritmy.


# Algoritmy

Táto sekcia by mala obsahovať postupy, algoritmy ako daný problém riešiť. Aj
triviálny a blbý algoritmus je algoritmu! Je tam možnosť ukázať, že rozumiem
prečo takým a takým spôsobom problém nie je vhodné riešiť a ukázať, čo viem
(alebo neviem). Blbé riešenie často vedie k celkom dobrému riešeniu po tom
ako rozoznáme prečo je blbé.


Algoritmy (príklad):
   
    - Podle barvy
        - rozoznávanie farieb?
        - priradzovanie farieb k osobám medzi snímkami?

    - Člověk má kolem sebe místo. Člověk je tam, kde je velký rozdíl barev
        - problém se skupinami, problém se sledováním
            - pomocí stejné barvy a počtu pixelů okolo člověka

    - Algoritmus na hledání lidí na fotce
        - **algoritmus nemusím nutne poznať**
        - Poznávání lidí pomocí matic

    - Algoritmus na určení identity lidí (jestli jsou dva výřezy fotky stejný
      člověk, výřezy by měli být nedaleko od sebe,...)


    - zapamatovat si pozadí - to co se nemění

    - rozpoznávat hýbající se objekty:
        - rozlišit lidi (podle počtu pohyblivých pixelů)
        - sledovat lidi v průběhu videa a pamatovat si je


    - saturace/desaturace videa
        - možná i upscaling

    - použití nějakého AI algoritmu
        - objekt detection

    - odstínit
        - části videa kde se nikdo nevyskytuje (větší části)
      	- relativně velké objekty (auta, tramvaje)
            - udělat si nějaké měřítko

    - najít pohybující se objekty

    - kouknout jak se objekt přestal pohybovat
        - odešel z obrazu
      	- začal stát na místě


    - trackování jednoho a samého objektu
        - pomocí sloučení barev
      	- nebo pomocí overlappingu boxů
        - pokud vyjde z objektu a vrátí se -> nějak identifikovat pomocí barev


# Representace dat

Táto časť by mala nasledovať po vybratí nášho algoritmického víťaza. Dáta sa
znova podobne ako algoritmi dajú reprezentovať viacerými spôsobmi. Znova je
možné ukázať čo neviem. 

Príklad

    -  Objekt člověk s atributy:
        - datová struktura člověk určená skupinou pixelů
        - Oblečení, neboli poměr barevných pixelů
          (chyba - změna světla, nebo pohyb (mají mezi nohama chodník)
        - Barevná stopa:
            - vypočítá se z barev všech pixelů, které danému člověku náleží,
              průběhu videa by se neměla moc měnit (bude se jednat o jakýsi 
              průměr)

    - Objekt  pozadí

    - Objekt tramvaj ručně nakreslit kde se bude pohybovat


# Dekomposice

Zahrňuje objektový návrh prípadne data flow diagram.

# Diskuse

V tomto bode budeš rád, že sem niečo napíšeš. V podstate zhrnieš všetko, na čo
si prišiel. Kde riešenie problému zlyháva, za akých podmienok by ho bolo možné
riešiť efektívnejšie. Ktoré aspekty sa dajú ďalej vylepšovať a za akú cenu.
