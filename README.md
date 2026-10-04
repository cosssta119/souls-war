# ⚔️ Souls Online War — Wyszukiwarka kontr-formacji

Narzędzie gildyjne dla graczy **Souls Online** (Habby) wspomagające planowanie walk w trybie Guild Battle. Pozwala szybko znaleźć kontr-formację na skład przeciwnika, zaplanować 3 walki naraz bez powtarzania bohaterów i sprawdzić umiejętności bohaterów, bonusy Księgi, artefakty oraz runy.

**[🔗 Otwórz aplikację](https://cosssta119.github.io/souls-war/)**

---

## 🎮 O grze — kontekst mechaniczny

Souls Online to turowy RPG z kolekcjonowaniem bohaterów od Habby. Gracze budują drużyny z 8 dostępnych slotów (wdrożenie: 5 bohaterów + 1 pet na walkę) w układzie **3-2-3**:

```
[ Poz6 ][ Poz7 ][ Poz8 ]   ← rząd tylny (DPS/Healerzy)
    [ Poz4 ][ Poz5 ]        ← rząd środkowy
[ Poz1 ][ Poz2 ][ Poz3 ]   ← rząd przedni (Tanki)
```

### System ras i kontr-zależności

Gra posiada 6 ras bohaterów tworzących system kamień-papier-nożyce:

```
Human → Horde/Fire → Elf → Undead → Human
```

| Rasa | Kolor | Kontruje | Jest kontrowana przez |
|------|-------|----------|-----------------------|
| Human | Niebieski | Fire/Horde | Undead |
| Fire (Horde) | Czerwony | Elf | Human |
| Elf | Zielony | Undead | Fire |
| Undead | Szary | Human | Elf |
| Light | Złoty | — (neutralna) | — |
| Dark | Fioletowy | — (neutralna) | — |

Bohaterowie rasy Light i Dark nie należą do cyklu kontr — są neutralni wobec wszystkich ras, ale statystycznie bardzo silni (meta end-game). W aplikacji rasa Fire jest wyświetlana jako **Horde**.

**Bonus synergii rasowej** (ATK + HP):
- 2+2 bohaterów tej samej rasy: +10%
- 3 tej samej rasy: +12%
- 4 tej samej rasy: +17%
- 5 tej samej rasy (pełna rasa): **+20%**

Trafienie w kontrę rasową dodatkowo daje **+20% obrażeń** przeciwko kontrowanej rasie.

---

## 🚀 Funkcje aplikacji

Aplikacja działa w przeglądarce (komputer i telefon), po polsku i angielsku (🇵🇱/🇬🇧), w motywie ciemnym lub jasnym. Dane odświeżają się na żywo — formacja dodana przez kogoś z gildii pojawia się u wszystkich bez przeładowania strony.

### 🔎 Szukaj wszędzie (Ctrl+K)
Przycisk 🔎 w górnej belce albo skrót **Ctrl+K** otwiera jedno pole przeszukujące naraz:
- formacje (bohaterowie, pety, nazwa, komentarz, numer `#id`),
- bohaterów i pety (także po treści umiejętności),
- bonusy Księgi i artefakty,
- składy Obrony i graczy (tylko admin) oraz screeny (gdy masz dostęp do Galerii).

Wyniki są pogrupowane po typie; strzałki ↑↓ + Enter przenoszą do właściwego miejsca, Esc zamyka.

### 🔍 Szukaj — wyszukiwarka kontr-formacji
Główna funkcja. Wpisujesz skład przeciwnika (do 8 pól + pet) albo klikasz tagi bohaterów pogrupowane po rasach, a aplikacja przeszukuje całą bazę.

**Jak liczone jest dopasowanie:** score = liczba trafionych bohaterów przeciwnika + 1 za trafionego peta. **Pozycja nie ma tu znaczenia** — liczy się sam skład, niezależnie od tego, w które pola wpiszesz bohaterów. Wielkość liter jest ignorowana, a nazwy można skracać (początek nazwy, min. 3 znaki).

Wyniki:
- sortowanie: 🎯 trafność albo 🕐 najnowsze,
- próg minimalnej trafności (np. „3+” — tylko formacje z co najmniej 3 trafieniami),
- trafieni bohaterowie podświetleni na zielono, widać kontrę, peta i komentarz, nowe formacje mają badge **NOWE**,
- **porównywarka** — zaznacz 2–3 wyniki i porównaj składy pozycja po pozycji.

Opcje:
- **Ctrl+klik na tag** = wyklucz bohatera (np. takiego, którego nie masz); formacje z wykluczonymi można ukryć — działa w Szukaj, Bazie i Podglądzie,
- historia ostatnich wyszukiwań,
- odwracanie kolejności rzędów i własna kolejność ras w tagach.

### 📚 Baza
Przeglądanie wszystkich zapisanych formacji:
- filtry: Wszystkie / Bazowe (oznaczone przez admina) / Dodane (przez graczy) / ⭐ Ulubione,
- szukanie tekstowe po nazwie, bohaterach, petach i komentarzu,
- sortowanie: ID, nazwa, data,
- **🧩 Pakiety bohaterów** — analiza, jakie zestawy 3–5 bohaterów najczęściej występują razem: u wrogów, w kontrach albo w obu; tryb „dokładnie N” lub „co najmniej N”, okno czasowe (cała baza / 30 / 90 dni) i minimalna liczba wystąpień.

### 👁️ Podgląd
Wizualizacja formacji w układzie 3-2-3 z kolorami ras:
- nawigacja strzałkami ◀ ▶ lub po numerze ID, lista ostatnio przeglądanych,
- inne kontry na tego samego przeciwnika,
- kliknięcie bohatera lub peta otwiera jego umiejętności; ikonki run i artefaktów przy bohaterach pokazują szczegóły,
- widżet **🎁 Bonusy Księgi** — które bonusy Księgi działają dla tego składu (wg ras i rzędów),
- kopiowanie składu jako tekst, link do formacji (🔗), dodawanie do ulubionych.

### ➕ Dodaj formację
Formularz z autouzupełnianiem i tagami do zapisania nowej kontry (skład przeciwnika + Twoja kontra + pety + komentarz):
- przy każdym bohaterze można przypiąć **runę** (12 typów, opcjonalnie wariant Divine) i **artefakt** (lista dopasowana do klasy bohatera),
- walidacja: maks. 5 bohaterów na stronę, tylko znani bohaterowie i pety (pisownia ujednolicana do tej z bazy),
- wykrywanie identycznej formacji przed zapisem (z podglądem istniejącej),
- pusta nazwa = nazwa z datą i godziną; układ sekcji obok siebie / góra-dół.

### ⚔️ Planer Wojny
Planowanie 3 walk jednocześnie. Wpisujesz składy 3 przeciwników, a system:
1. Dla każdego wroga szuka pasujących kontr i bierze **50 najlepszych** (score z bonusem za pozycję).
2. Tworzy wszystkie kombinacje 3 różnych kontr (do 125 000).
3. Ocenia każdą kombinację wg trafności i kary za **konflikty**, czyli bohatera lub peta potrzebnego w więcej niż jednej walce.
4. Pokazuje najlepsze kombinacje (domyślnie 20; admin ustawia 5–100) z zaznaczonymi konfliktami.

**Algorytm rankingu:**

```
score kontry  = trafieni bohaterowie + 1 (trafiony pet) + 0.3 × bohaterowie trafieni na tej samej pozycji
procent       = Σ trafień 3 kontr (bez bonusu pozycji) / Σ wpisanych postaci 3 wrogów × 100
ranking       = procent − konflikty^1.5 × 8
```

- Bonus za pozycję (+0.3) wpływa tylko na wybór i kolejność 50 kontr dla każdego wroga; sam ranking kombinacji liczy procent bez niego.
- Każde dodatkowe użycie tego samego bohatera lub peta to 1 konflikt (bohater w 3 walkach = 2 konflikty). Kara: 1 konflikt = −8 pkt, 2 = ok. −22.6, 3 = ok. −41.6.
- Przy prawie równym wyniku (różnica ≤ 0.1) wyżej jest kombinacja z mniejszą liczbą konfliktów.

Opcje:
- **🚫 Tylko grywalne** — odrzuca wszystkie kombinacje z konfliktem,
- **filtr podobnych składów** — ukrywa kombinacje, których łączna pula bohaterów jest zbyt podobna do lepszej (próg 40–90%, domyślnie 60%),
- osobna lista wykluczonych bohaterów, historia planera, automatyczne zapamiętywanie wpisanych składów.

**Podgląd kombinacji** porównuje szukanego wroga z wrogiem z bazy (trafieni / brakujący / inna pozycja), pokazuje konflikty, Twój skład z runami, artefaktami i bonusami Księgi. Stąd możesz: **📌 Przypnij** kombinację, **📝 Do Kreatora** albo **📋 Kopiuj skład tekstowo**.

### 🎯 Kreator
Ręczne układanie 1–3 składów z tagami bohaterów (tagi podświetlają już użytych), z własną listą wykluczonych. Składy można skopiować jako tekst (np. na Discorda) albo zapisać w pamięci przeglądarki i wczytać później.

### 🛡️ Obrona *(domyślnie admin)*
Ewidencja składów obronnych gildii:
- widoki **Gracze / Składy / Dodaj skład** oraz karta pojedynczego gracza,
- każdy gracz może mieć do **3 aktywnych składów**, bez powtarzania bohatera ani peta między nimi,
- per gracz: prędkości (speed) bohaterów i artefakty — ten sam skład u dwóch graczy może mieć inne wartości,
- edycja składu automatycznie przenosi przypisanych graczy (z ostrzeżeniem, gdy powstałby konflikt),
- informacja, ilu graczy używa tego samego zestawu bohaterów w innym ustawieniu,
- sortowanie i zaawansowana szukajka (spacja = ORAZ, `|` = ALBO, `-` = wyklucz, `"fraza"`); historia przypisań jest zachowywana.

### 📖 Kompendium
Cztery widoki do przełączania:
- **🦸 Bohaterowie** — umiejętności bohaterów (Active, pasywne, Przebudzenie, Grawerunek +10/+20/+30/+40, Exclusive Equipment poziomy 1–4) i petów (Active, pasywna, ładowanie energii). Filtry rasa / rola (Tank, Dealer, Support, Healer) / typ (STR, AGI, INT), szukajka po treści skilli ze składnią (`słowo słowo`, `"fraza"`, `a|b`, `-x`, `pole:x`), słownik synonimów (np. `acc` → accuracy, `cc` → stun/silence/freeze/shock), tryb tolerancji literówek, porównywarka 2–3 bohaterów, kafelki S/M/L. Niebieski ptaszek = dane sprawdzone ze screenami z gry.
- **📖 Księga** — bonusy pasywne z Book of Heroes / Light / Darkness z wyszukiwarką. Z widżetu „🎁 Bonusy Księgi” pod składem można przejść do dokładnie tych bonusów („🔎 Pokaż w Księdze”).
- **🗡️ Artefakty** — 36 artefaktów (31 Mythic + 5 Legendary) pogrupowanych po klasie, z bonusami, umiejętnością i licznikiem użyć w formacjach.
- **🪬 Runy** — 12 typów run i 6 wariantów Divine z kartą statystyk.

Kliknięcie bohatera lub peta w dowolnym składzie w aplikacji otwiera okno jego umiejętności. Gracze przeglądają Kompendium; edycja i import należą do admina.

### 🖼️ Galeria *(domyślnie admin)*
Screeny w drzewie folderów:
- wgrywanie przyciskiem, przeciąganiem lub Ctrl+V (na telefonie z galerii lub aparatu), opcjonalna kompresja, miniatury,
- podgląd z powiększaniem i przesuwaniem (także gestami), tagi z filtrem, opisy, ulubione, sortowanie, pobieranie,
- zaznaczanie wielu screenów (przenieś / otaguj / usuń),
- automatyczne foldery bohaterów (np. Mastery) i artefaktów — z okna umiejętności bohatera jest skrót do jego folderu.

Gdy admin udostępni Galerię graczom, mogą ją przeglądać, przeszukiwać i pobierać screeny.

### ⚙️ Import *(admin)*
Zakładka danych (zwijane sekcje):
- statystyki bazy (formacje, Obrona, bohaterowie, pety),
- eksport formacji do CSV (wszystkie / ulubione / dodane / bazowe) i import z CSV — z walidacją, pomijaniem duplikatów i potwierdzeniem,
- **kopia zapasowa JSON** (formacje + bohaterowie + pety + Obrona) i przywracanie z podglądem różnic (dodaje tylko nowe rekordy, nic nie kasuje),
- import/eksport umiejętności bohaterów i petów (JSON, z wyborem nadpisywanych różnic),
- import/eksport Księgi bonusów (JSON) oraz Obrony (CSV).

### 👑 Panel Admina *(admin)*
- skaner duplikatów formacji (podgląd + usuwanie),
- zarządzanie bohaterami i petami (dodawanie, edycja, usuwanie) — zmiana nazwy przepisuje się we wszystkich formacjach, Obronie i folderach Galerii,
- **globalna konfiguracja gildii** (działa od razu u wszystkich): próg badge „NOWE”, domyślny próg trafności i sortowanie wyników, liczba wyników Planera Wojny, domyślny filtr Bazy i ustawienia Pakietów, kompresja screenów,
- **widoczność zakładek**: dla każdej zakładki — kto ją widzi (wszyscy / admin), gdzie jest (pasek / menu „⋯ Więcej” / ukryta) i w jakiej kolejności (▲▼ lub przeciąganie),
- wylogowanie z trybu admina.

Tylko admin może edytować i usuwać formacje, oznaczać je jako bazowe oraz edytować dane Kompendium.

---

## 🔐 Dostęp i autoryzacja

### Hasło gildii
Aplikacja chroniona jest hasłem gildii (weryfikacja SHA-256). Hasło przekazuje admin gildii. Po zalogowaniu dostęp jest pamiętany w przeglądarce (`localStorage`).

### Tryb admina
Ukryty panel — kliknij nagłówek aplikacji **5 razy szybko pod rząd** (przerwy krótsze niż 2 sekundy). Hasło admina weryfikowane przez SHA-256. Admin widzi dodatkowe zakładki i przyciski edycji/usuwania.

### Widoczność zakładek
Admin decyduje, które zakładki widzą gracze. Domyślnie tylko dla admina są: **Obrona**, **Galeria**, **Import** i **Admin**. Pozostałe (Szukaj, Baza, Podgląd, Dodaj, Wojna, Kreator, Kompendium) są dostępne dla wszystkich.

---

## 🛠️ Technologie

| Komponent | Technologia |
|-----------|-------------|
| Frontend | Vanilla JS + HTML5 + CSS3 (bez frameworków) |
| Baza danych | Firebase Realtime Database (aktualizacje na żywo) |
| Pliki (Galeria) | Firebase Storage |
| Hosting | GitHub Pages |
| Fonty | Google Fonts (Cinzel, Nunito) |
| Auth | SHA-256 (Web Crypto API) |
| Persystencja lokalna | localStorage (klucze z prefiksem `souls_`) |
| Analityka | Google Analytics |
| Języki | polski / angielski |

Aplikacja to **4 pliki serwowane statycznie** przez GitHub Pages — bez procesu budowania i bez menedżera pakietów:

| Plik | Zawartość |
|------|-----------|
| `index.html` (w repo testowym: `souls-war.html`) | struktura strony, zakładki, okna |
| `souls-war.css` | style |
| `souls-war-i18n.js` | tłumaczenia PL/EN (ładowany **przed** `souls-war.js`) |
| `souls-war.js` | cała logika aplikacji |

Do tego folder `runes/` ze statycznymi ikonami run (nie są w bazie danych).

---

## 📦 Struktura danych (Firebase)

```
/formations/{id}                 — formacje (kontry)
  id, name                       — numer i nazwa
  enemy[8], enemyPet             — skład przeciwnika (sloty 1–8; max 5 bohaterów)
  my[8], myPet                   — Twoja kontra
  comment, isBase                — komentarz, formacja bazowa (admin)
  dateAdded, lastEdited          — daty (ISO)
  myArtifacts[8], enemyArtifacts[8]   — artefakt per slot (opcjonalnie)
  myRunes[8], enemyRunes[8]           — runa per slot: "typ" lub "typ|divine" (opcjonalnie)

/heroes/{nazwa}                  — { name, race }  race: Dark/Light/Human/Fire/Elf/Undead
/pets/{nazwa}                    — { name }

/heroSkills/{nazwa}              — role, stat, active, passives[], awaken, engraving{10..40}, exclusive{name, levels{1..4}}, verified
/petSkills/{nazwa}               — active, passive, energy, verified
/synonyms/{id}                   — { forms[], expand[] }  słownik synonimów szukajki
/bookBonuses/{id}                — { book, order, name, desc, calc }  bonusy Księgi
/bookMeta/{id}                   — { key, label, icon, color, order }  definicje ksiąg
/artifacts/{slug}                — { name, klass, rarity, bonuses[], skill, iconUrl }

/defenseFormations/{id}          — { my[8], myPet, name, comment, createdAt, fingerprint }
/defensePlayers/{id}             — { name, createdAt, deletedAt }
/defenseAssignments/{id}         — { playerId, formationId, assignedAt, unassignedAt, speeds[8], artifacts[8] }

/screenFolders/{id}              — { name, parentId, createdAt, managed, kind }  drzewo folderów Galerii
/screenshots/{id}                — { folderId, url, thumbUrl, title, comment, tags[], uploadedAt }

/config/settings                 — globalna konfiguracja gildii (progi, domyślne ustawienia, widoczność i kolejność zakładek)
```

Pliki screenów (pełny obraz + miniatura) leżą w Firebase Storage w `screenshots/`. Ikony run to statyczne pliki `runes/{typ}/…` w repozytorium.

---

## 🎯 Jak używać (szybki start)

### Szukanie kontry
1. Otwórz zakładkę **Szukaj**
2. Wpisz bohaterów przeciwnika w pola pozycji LUB klikaj tagi
3. Kliknij **SZUKAJ**
4. Przeglądaj wyniki — zielone nazwy = trafieni bohaterowie; w razie potrzeby ustaw próg trafności lub zmień sortowanie
5. Kliknij wynik, żeby zobaczyć pełny **Podgląd**

Szybki skrót: **Ctrl+K** i wpisz bohatera, skill albo `#id` formacji.

### Dodanie nowej formacji
1. Zakładka **Dodaj**
2. Wypełnij skład przeciwnika (sekcja „Skład przeciwnika”)
3. Wypełnij swoją kontrę (sekcja „Twoja kontra”)
4. Opcjonalnie przypnij runy/artefakty kwadracikami przy bohaterach i dodaj komentarz (np. kolejność speed)
5. Kliknij **ZAPISZ FORMACJĘ**

### Planowanie 3 walk
1. Zakładka **⚔️ Wojna**
2. Wpisz składy 3 różnych wrogów
3. Kliknij **🎯 ZNAJDŹ OPTYMALNE SKŁADY** (opcjonalnie zaznacz „Tylko grywalne”)
4. Wybierz kombinację bez konfliktów (lub z minimalną liczbą)
5. Otwórz **Podgląd** kombinacji → **📌 Przypnij**, **📝 Do Kreatora** albo **📋 Kopiuj skład tekstowo**

### Sprawdzenie bohatera
1. Kliknij bohatera w dowolnym składzie albo otwórz **📖 Kompendium**
2. Szukaj po treści skilli, np. `stun`, `"crit rate"`, `heal|shield`
3. Użyj **⚖️ Porównaj**, żeby zestawić 2–3 bohaterów obok siebie

---

## 🗺️ Roadmap (planowane funkcje)

- [ ] Filtrowanie wyników wyszukiwania po rasie
- [ ] Ocenianie formacji (skuteczność win/loss)
- [ ] Powiadomienia o nowych formacjach (dziś jest badge „NOWE”)
- [ ] Eksport podglądu formacji do PNG (dla Discorda)
- [ ] Tryb PWA (offline cache)
- [ ] Statystyki meta: najczęstsi bohaterowie, skuteczność kontr (częściowo: 🧩 Pakiety w Bazie)
- [ ] Historia walk z wynikami
- [ ] Discord webhook przy nowych formacjach
- [ ] Grupowanie bonusów Księgi „po efekcie” (rasa / rząd / statystyka)
- [ ] Bonusy Księgi w podsumowaniu wybranej trójki w Planerze Wojny

---

## 👥 Dla graczy gildii

Aplikacja jest wspólnym narzędziem gildii. Każdy zalogowany gracz może:
- przeglądać i wyszukiwać formacje (także przez Ctrl+K),
- dodawać własne kontry po wygranych walkach (z runami i artefaktami),
- planować walki w Planerze Wojny i Kreatorze (jeśli admin udostępnił zakładki),
- sprawdzać umiejętności bohaterów, bonusy Księgi, artefakty i runy w Kompendium,
- oznaczać ulubione formacje (zapisywane lokalnie w przeglądarce).

Tylko admin może edytować i usuwać formacje, oznaczać je jako bazowe, zarządzać bohaterami, Obroną, Galerią, importem danych i konfiguracją gildii.

---

## 🧪 Rozwój i wdrożenia

Informacje dla opiekunów aplikacji:

- Aplikacja ma **wersję testową** w repozytorium [`sw-test`](https://github.com/cosssta119/sw-test). Każda zmiana trafia najpierw tam i jest sprawdzana.
- Na produkcję (repozytorium `souls-war`, strona dla graczy) sprawdzone zmiany przenosi **skrypt**. Procedura krok po kroku: [WDROZENIE.md](https://github.com/cosssta119/sw-test/blob/main/WDROZENIE.md).
- Skrypt sam przenosi wszystkie pliki aplikacji (razem z folderem `runes/`), podmienia hasło gildii na produkcyjne i przed publikacją sprawdza, czy niczego nie brakuje.
- Wersja testowa korzysta z **tej samej bazy Firebase** co produkcja — usuwanie i operacje masowe w teście działają na prawdziwych danych gildii.
- Lokalnie aplikację uruchamia się przez serwer HTTP w folderze projektu (np. `python -m http.server 8000`); nie ma kroku budowania ani testów automatycznych.

---

*Souls Online © Habby / Concrit. Narzędzie nieoficjalne, stworzone przez graczy dla graczy.*
