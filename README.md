# Névtelen Kolléga — szerkesztői műhely

Mobilbarát, magyar nyelvű első prototípus a munkahelyi történetek szerkesztési és emberi jóváhagyási folyamatához.

## Mi működik ebben a verzióban?

- Áttekintő képernyő és munkafolyamat.
- Fiktív történetek listája, keresése és állapot szerinti szűrése.
- Szerkesztő címhez, posztszöveghez és belső jegyzethez.
- Helyi piszkozatmentés a böngésző `localStorage` tárhelyére.
- Demó státuszváltások: piszkozat, jóváhagyásra vár, jóváhagyva, elutasítva.
- Mobilra optimalizált felület.
- Demó visszaállítása.

## Fontos korlátok

**Ez jelenleg csak frontend demó. Ne tárolj benne valódi, bizalmas vagy beazonosítható történetet.** A mintatartalom kitalált. A mentés csak abban a böngészőben érhető el, amelyikben szerkesztették; böngészőadatok törlésével elveszhet.

- Nincs felhasználói hitelesítés és jogosultságkezelés.
- Nincs központi adatbázis vagy biztonságos beküldési űrlap.
- A „Szerkesztési ötlet” egy egyszerű helyi demófunkció; nincs AI-szolgáltatáshoz kötve.
- A jóváhagyás csak a demó állapotát módosítja. **Semmilyen tartalom nem kerül ki automatikusan LinkedInre.**
- Ne másolj be forrásként nyilvános posztokat automatikus újraközlésre; a felhasználási jogot/engedélyt külön rendezni kell.

## Fejlesztési sorrend

1. Külön, védett Supabase-projekt, belépés és szerepkörök.
2. Adatbázisséma és Row Level Security (RLS) szabályok a beküldések, piszkozatok, státuszok és auditnapló védelmére.
3. Biztonságos beküldési űrlap, amely elkülöníti a kapcsolattartási adatokat a publikálható szövegtől.
4. Szerveroldali AI-szerkesztés kockázati jelzésekkel, emberi jóváhagyás kötelezővé tételével.
5. LinkedIn OAuth és céges oldalhoz szükséges jogosultság ellenőrzése, külön tesztkörnyezettel.
6. Vercel-telepítés és végponttól végpontig teszt.

**Ne használjuk fel a CalicoChef adatbázisát.** Ehhez a projekthez önálló adatbázis és hozzáférési szabályok szükségesek.

## Futtatás

Ez a kezdeti változat statikus weboldal; a repository gyökérkönyvtárából szerver nélkül is megnyitható az `index.html`. Vercelen statikus oldalként szolgálható ki, buildlépés nélkül.
