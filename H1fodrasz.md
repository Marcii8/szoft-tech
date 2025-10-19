# ✂️ IdőMester – Fodrász Szalon Időpontfoglaló  
🎓 **H1 – Projektterv**  
👤 **Készítette:** Kóró Marcell József  
📚 **Tantárgy:** Szoftver Technológia  
🗓 **Dátum:** 2025. október  
🏷 **Csapatnév:** SoloDev  
---

## 🎯 0. Projektleírás

Az **IdőMester** egy **webes időpontfoglaló rendszer** fodrászszalonok számára.  
A felhasználók (vendégek) online választhatnak **szolgáltatást** (pl. hajvágás, festés, melír), **stylistot**, valamint **foglalható időpontot** az üzlet nyitvatartása és a szakemberek beosztása alapján.

A rendszer céljai:

- ✅ **Ütközésmentes időpontfoglalás**
- ✅ **Gyors, modern foglalási felület**
- ✅ **Naptárnézet adminisztrátornak**
- ✅ **Automatikus visszaigazolás**

💡 *A megoldás célja a manuális (telefonos/chat) egyeztetés kiváltása, ezáltal digitális, átlátható rendszer bevezetése a szalonba.*

---

## 👥 1. Csapattagok és szerepek

| Név | Szerepkör | Felelősségek |
|------|---------|-------------|
| **Kóró Marcell József** | Fejlesztő, Tesztelő, Dokumentáció | Backend fejlesztés Pythonban, admin és vendég UI, tesztelés, dokumentáció |

📌 **Kommunikáció és nyomon követés**
- GitHub Issues & Projects → feladatkezelés
- Saját státuszriportok → heti dokumentált előrehaladás
- Verziózás → Git alapján (branch: `feature/…`, `main`, `release`)

---

## 🗂 2. Fejlesztési terv – Mérföldkövek

| Mérföldkő | Leszállítandó | Határidő |
|-----------|--------------|---------|
| **H1** | Projektterv (ez a dokumentum) | 6. hét |
| **H2** | Vízió + szalon folyamatleírás | 6. hét |
| **H3** | SRS + folyamatok + kézikönyv (1. verzió) | 6. hét |
| **H4** | Analízis modell + adatmodell + architektúra | 9. hét |
| **H5** | MVP prototípus + tesztterv | 12. hét |

> 💬 **Megjegyzés:** A szolgáltatáslista és foglalható időtartomány konfigurálható lesz (JSON / admin UI).

---

## 💻 3. Technológiai stack

### 🔤 Programozási nyelv
- **Python** – backend REST API-hoz

### 🛠 Fejlesztői eszközök
- **Visual Studio Code / PyCharm**
- **GitHub** – verziókezelés + dokumentáció tárolás
- **GitHub Actions (opció)** – automatizált ellenőrzés

### 🍃 Framework és adatbázis
- **FastAPI vagy Flask** (Python)
- **SQLite** – egyszerű fejlesztői DB (később PostgreSQL is lehet)
- **pytest + coverage** – teszteléshez

---

## 🔄 4. Módszertan

### ⚙ Fejlesztési folyamat
- **Iteratív fejlesztés**, MVP fókusz
- Minden modul külön commit / branch
- Verziók: `v0.1`, `v0.2`, stb.

### ✅ Tesztelési technikák
- **Egységtesztek:** időütközés, nyitvatartási szabály, időtartamkezelés
- **Integrációs tesztek:** foglalási API
- **Kézi UAT:** vendég/admin folyamatok kipróbálása

### 📦 Telepítési mód
- **Docker konténer** (fejlesztői környezet + bemutatás)
- `docker run idomester-backend`

---

## 📑 5. Dokumentumok

| Dokumentum | Felelős | Határidő |
|------------|--------|---------|
| Vízió dokumentum (fodrász domain) | Kóró Marcell József | 6. hét |
| SRS (részletes rendszerleírás) | Kóró Marcell József | 6. hét |
| Szótár (fogalmak tisztázása) | Kóró Marcell József | 6. hét |
| Analízis modell | Kóró Marcell József | 9. hét |
| Rendszertervezési dokumentum | Kóró Marcell József | 9. hét |
| Felhasználói kézikönyv | Kóró Marcell József | 12. hét |
| Tesztterv | Kóró Marcell József | 12. hét |
| Prototípus kód | Kóró Marcell József | 12. hét |

---

## 🧪 6. Tesztelés

**Teszttípusok:**
- ✅ Egységteszt (min. 70%)
- ✅ Integrációs API teszt
- ✅ Rendszer / Elfogadási teszt
- ✅ Kézi bemutató → **élő demo**

**Eszközök:**
- pytest
- HTTPie / Postman → API tesztekhez

---

## 🚚 7. Bemutatás és leszállítás

🎬 **Bemutatás menete (élő demo):**
1. Vendég kiválaszt egy szolgáltatást
2. Stylist + szabad időpont kiválasztása
3. Foglalás létrehozása → visszaigazolás
4. Admin felület → foglalások megtekintése / lemondása
5. Ütközéskezelés demonstrálása

📦 **Leszállítás módja:**
- GitHub repó → forráskód + dokumentáció
- Release tag → `v1.0-Handover`
- Opcionálisan: Docker image (`ghcr.io/…/idomester`)

---

## 📚 8. Információs források

- Python hivatalos dokumentáció – <https://docs.python.org>
- FastAPI / Flask dokumentáció
- Git / GitHub workflow dokumentáció
- Clean Code (Robert C. Martin)
