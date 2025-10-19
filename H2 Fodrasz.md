# 📌 H2 – Követelmény-analízis dokumentum
✂️ **Projekt:** IdőMester — Fodrász Szalon Időpontfoglaló  
👤 **Készítette:** Kóró Marcell József  
🏷 **Csapat:** SoloDev  
📚 **Tantárgy:** Szoftver Technologia  
🗓 **Dátum:** 2025. október  

---

## 1. 🎯 Leadandó összefoglaló

A H2 mérföldkő három fő dokumentumból áll:
1. **Vízió dokumentum** – a célok, probléma, felhasználói körök, kockázatok és szótár
2. **Projektterv** – mérföldkövek, erőforrások és ütemezés
3. **Munkanapló** – az egyéni hozzájárulások követése

---

## 2. 🎨 Vízió dokumentum

### 2.1 📎 Címlap
| Elem | Tartalom |
|---|---|
| **Projekt címe** | IdőMester — Fodrász Szalon Időpontfoglaló |
| **Verzió** | v0.9 (H2-tervezet) |
| **Dátum** | 2025.10. |

### 2.2 🧭 Bevezetés
Az IdőMester célja egy webes foglalási rendszer létrehozása fodrászszalonok számára, amelyben a vendégek önállóan választhatnak szolgáltatást, stylistot és időpontot. Az érintettek: *vendégek* (időpontfoglalás), *stylistok* (időbeosztás kezelése), *szalonadmin* (naptár és szolgáltatáskatalógus karbantartása), valamint a *fejlesztő* (üzemeltetés, hibajavítás). A rendszer célja a telefonos egyeztetések csökkentése, az ütközések megelőzése és a foglalási folyamat átláthatóvá tétele.

### 2.3 ⚠️ Probléma megfogalmazása
- **Jelenlegi helyzet:** Sok kis szalon telefonon vagy chatben egyezteti az időpontokat, ami pontatlanságokhoz és duplikált foglalásokhoz vezet.  
- **Fájdalompontok:** nincs valós idejű átlátható naptár; időigényes egyeztetés; gyakori ütközések; elfelejtett visszaigazolások.  
- **Miért fontos:** a hatékony időpontkezelés közvetlenül befolyásolja a bevételt, a vendégélményt és a stylistok terhelését.

### 2.4 🧭 A termék helye a piacon
A célcsoport a *kis és független fodrászszalonok*, amelyeknek túl bonyolult vagy drága a nagy rendszerek használata. A megoldás **könnyű, olcsón üzemeltethető**, és a lényegre (foglalás, ütközéskezelés, alap naptár) fókuszál. Megkülönböztető érték: egyszerű bevezetés, konfigurálható szolgáltatások és nyitvatartás, valamint *adatportabilitás* (export CSV/JSON).

### 2.5 💻 Felhasználói környezet
- **Felhasználói típusok:** Vendég (ügyfél), Stylist (szolgáltató), Admin (szalon tulaj/vezető).  
- **Eszközök/platformok:** mobil (iOS/Android böngésző), desktop böngésző; minimális követelmény: modern Chromium/Firefox/Safari.  
- **Hozzáférhetőség:** mobilbarát UI, alap ARIA címkék; magyar nyelv (később bővíthető).

### 2.6 ⭐ A termék előnyei
- **Vendégeknek:** 24/7 online foglalás, gyors visszaigazolás, átlátható szolgáltatás- és időpontválasztás.  
- **Szalonnak:** kevesebb telefon/üzenet, jobb kapacitáskihasználás, visszamondások kezelése.  
- **Stylistoknak:** rendezett beosztás, kevesebb ütközés, egyértelmű napi nézet.

### 2.7 🔗 Feltételezések és függőségek
- **Feltételezések:** stabil internetkapcsolat; valós nyitvatartás és szolgáltatáslista rendelkezésre áll; admin alap IT ismeretekkel bír.  
- **Függőségek:** e-mail szolgáltató (opcionális értesítés), külső naptár-export (ICS – későbbi fázis), böngésző API-k.

### 2.8 ⚙️ A termék fő funkciói
| Kategória | Funkció | Leírás |
|---|---|---|
| Kötelező | Foglalás létrehozása | Vendég szolgáltatás + stylist + időpont választása; ütközésmentesítés. |
| Kötelező | Naptárnézet | Admin/stylist napi/heti nézet; lista vendégeknek. |
| Kötelező | Lemondás/átfoglalás | Vendég vagy admin kezdeményezheti szabályok szerint. |
| Ajánlott | E-mail visszaigazolás | Automatikus értesítés foglalásról és módosításról. |
| Ajánlott | Szolgáltatáskatalógus | Időtartam, ár, megjegyzés; admin által szerkeszthető. |
| Jó, ha van | Stylist elérhetőség | Szabadság/egyedi idősávok kezelése. |
| Jó, ha van | Export | Foglalások exportja CSV/ICS formátumban. |

### 2.9 🎛 Minőségi elvárások (NFR)
- **Teljesítmény:** ≤300 ms API válasz egyszerű lekérdezésre fejlesztői környezetben; 20 párhuzamos kérés kezelése.  
- **Biztonság:** jelszavak sózott-hash-elt tárolása; jogosultság-szintek (vendég, admin); bevitelvalidáció.  
- **Használhatóság:** mobil-first felület; konzisztens elnevezések és hibaüzenetek; ARIA.  
- **Karbantarthatóság:** tiszta rétegzett architektúra; tesztlefedettség cél: ≥70% a domain modulokra.

### 2.10 ⚡ Kockázati lista
| Kockázat | Valószínűség | Hatás | Csökkentés |
|---|---|---|---|
| Időütközés-kezelés hibái | Közepes | Magas | Unit tesztek edge case-ekre, integrációs tesztek; egyszerű BB szabályok. |
| Naptár időzónák | Alacsony | Közepes | UTC tárolás, lokális megjelenítés; könyvtár használat. |
| Adatvédelem | Közepes | Magas | Hash-elt jelszavak, min. adatkezelés, hozzáférés-naplózás. |
| Scope növekedés | Közepes | Közepes | MVP priorizálás, backlog fegyelem. |

### 2.11 📘 Szótár
| Fogalom | Definíció |
|---|---|
| Szolgáltatás | Konkrét fodrásztevékenység (pl. hajvágás), fix időtartammal és opcionális árral. |
| Stylist | A szolgáltatást végző szakember. |
| Időablak | Foglalható idősáv a nyitvatartáson belül. |
| Foglalás | Vendég által rögzített időpont és szolgáltatás a kiválasztott stylisttal. |
| Naptárnézet | Napi/heti áttekintés admin/stylist számára. |

---

## 3. 🧭 Projektterv (H2 kivonat)

### 3.1 👥 Csapattagok és szerepek
Egyéni projekt. Szerepek: Fejlesztő, Tesztelő, Dokumentáció felelős.

### 3.2 🧱 Mérföldkövek és várt eredmények
| Mérföldkő | Leszállítandó | Határidő |
|---|---|---|
| H1 | Projektterv | 6. hét |
| H2 | Vízió, frissített projektterv, munkanapló | 6. hét |
| H3 | SRS, Szótár, Felhasználói kézikönyv 1. verzió | 6. hét |
| H4 | Analízis modell, Rendszertervezés | 9. hét |
| H5 | Prototípus, Tesztelési terv | 12. hét |

### 3.3 🛠 Programozási nyelvek és eszközök
Python; FastAPI/Flask; SQLite; pytest; Git + GitHub; VS Code/PyCharm.

### 3.4 🔁 Tervezett módszerek és technikák
Iteratív fejlesztés 1–2 hetes ciklusokkal; MVP fókusz; CI (lint + test); Docker demóhoz.

### 3.5 🗓 Tervezett dokumentumok és idővonal
Lásd a fenti mérföldköveket; a dokumentumok az adott hetek végére esedékesek.

### 3.6 ✅ Tesztelési követelmények
Egységtesztek (≥70% domain), integrációs tesztek fő végpontokra, kézi UAT tipikus folyamatokra.

### 3.7 🎬 Bemutatás és leszállítás
Élő demó; GitHub repó és konténeres csomag.

### 3.8 📚 Információs források
- Python, FastAPI/Flask hivatalos dokumentációk  
- Git/GitHub workflow és Actions  
- Robert C. Martin: Clean Code (elvek)

---

## 4. 🗒️ Munkanapló (sablon)
| Dátum | Tag | Feladat leírása | Órák |
|---|---|---|---|
| 2025-10-16 | Kóró Marcell József | Vízió vázlat, funkciók priorizálása | 2 |
| 2025-10-17 | Kóró Marcell József | Probléma & piaci pozíció fejezetek | 1.5 |
| 2025-10-18 | Kóró Marcell József | Szótár & NFR kidolgozása | 1.5 |
