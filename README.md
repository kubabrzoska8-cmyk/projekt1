# Antyk — interaktywny kurs i atlas wyprawy Aleksandra

Strona `index.html` ma dwa tryby, przełączane przyciskiem w nagłówku:

- **KURS** — jednodniowy kurs antyku w zakresie rozszerzonym: szesnaście modułów
  ułożonych na wielkiej osi czasu, od pisma klinowego po rok 476.
- **ATLAS** — interaktywna mapa wyprawy Aleksandra Wielkiego (336–323 p.n.e.),
  pomyślana jako towarzystwo do filmu „Aleksander" Olivera Stone'a (2004).

**To jest jedyna strona w tym repo — cała aplikacja mieści się w `index.html`.**

## Kurs

Trzynaście rozdziałów programu potraktowanych równomiernie, poprzedzonych diagnozą
i domkniętych osią czasu oraz modułem o metodzie nauki. Każdy moduł ma ten sam
szkielet: wprowadzenie → co odszukać na osi → dzieła i autorzy → pojęcia → ćwiczenie
interaktywne → quiz → miejsce na własny wkład.

- **Wielka oś antyku** — grafika wektorowa: 68 wydarzeń w pięciu pasmach (Bliski Wschód,
  Grecja, Rzym, chrześcijaństwo, dzieła), 19 belek życiorysów i odczepiona wstęga czasu
  mitycznego, rysowana **bez skali**, bo mit jest porządkiem opowieści, nie kalendarzem.
  Skala osi jest odcinkowa — epoka klasyczna i augustowska są rozciągnięte, co strona
  wprost sygnalizuje.
- **Nakładka „paradoks"** — trzy pomiary rozbrajające najczęstsze pomyłki chronologiczne
  wokół *Eneidy*: Wergiliusz umiera piętnaście lat przed narodzinami Jezusa, od jego
  śmierci do prześladowań Nerona mijają 82 lata, a akcja eposu dzieje się jakieś
  1155 lat przed jego napisaniem.
- **Jedenaście różnych ćwiczeń** — sortery, paralela Gilgamesz ↔ Księga Rodzaju, dekoder
  przypowieści, budowanie heksametru, klikalny plan teatru greckiego, maszyna konfliktu
  tragicznego, schemat ustroju republiki, close reading proroctwa Jowisza z adnotacjami,
  układanki chronologiczne, kalkulator dystansu czasowego, konstruktor pałacu pamięci.
- **118 fiszek** w systemie Leitnera, 60 pytań quizowych, postęp i odpowiedzi zapisywane
  lokalnie w przeglądarce, eksport notatek do Markdown, wydruk całego kursu.

Sterowanie: **← →** moduły · **spacja** zalicz i dalej · **F** fiszki · **M** przełącz tryb ·
kółko myszy i szczypanie — zoom osi.

### Uwagi merytoryczne

Odstępy między latami liczone są bez roku zerowego: między 19 p.n.e. a 64 n.e. mija
82 lata, nie 83. Daty wydarzeń mitycznych i legendarnych (1184, 753 p.n.e.) podane są
jako umowne, za tradycją antyczną. Cytaty pochodzą z przekładów w domenie publicznej —
*Iliada* w tłumaczeniu Franciszka Ksawerego Dmochowskiego, Biblia w tłumaczeniu Jakuba
Wujka; fragmenty *Eneidy* podane są po łacinie wraz z przekładem roboczym sporządzonym
na potrzeby kursu i oznaczonym jako taki. Autorzy XX-wieczni są omawiani, a cytowani
wyłącznie we fragmentach, z podaniem autora i tytułu.

## Atlas

- 34 etapy wyprawy: opis, datowanie, dzisiejsza lokalizacja, odniesienie do sceny z filmu
- animowany przemarsz armii po trasie z kamerą śledzącą i osią czasu
- przełączane warstwy: imperium perskie ok. 334 p.n.e., krainy starożytne,
  dzisiejsze państwa, rzeki i jeziora, siatka geograficzna, miejsca z kursu
- pan / zoom (mysz i dotyk), tryb pełnoekranowy, wersja mobilna

## Jak to jest zrobione

Pojedynczy plik HTML (~1,3 MB) bez żadnych zależności sieciowych — działa też offline.
W środku osadzone są inline:

| element | źródło |
|---|---|
| cieniowana rzeźba terenu (WebP) | dane wysokościowe SRTM/ETOPO (Mapzen Terrain Tiles), przeliczone na hillshade + tinting hipsometryczny |
| linie brzegowe, rzeki, jeziora, granice | Natural Earth 1:10 m |
| kroje pisma (woff2) | Cinzel + EB Garamond, SIL Open Font License 1.1 |

Odwzorowanie: Albers, równopolowe stożkowe (południk środkowy 49°E,
równoleżniki standardowe 25°N i 43°N). Kadr obejmuje cały wschodni i środkowy basen
Morza Śródziemnego — od Kartaginy i Rzymu po Taksilę — więc ta sama mapa obsługuje
geografię niemal całego kursu.

Trasa, daty i zasięg imperium są przybliżone; datowanie za Arrianem, Plutarchem
i Kurcjuszem Rufusem.
