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
szkielet: wprowadzenie → co odszukać na osi → **obrazy kultury** → **tekst źródłowy**
→ dzieła i autorzy → pojęcia → ćwiczenie interaktywne → quiz → miejsce na własny wkład.

- **Wielka oś antyku** — grafika wektorowa: 68 wydarzeń w pięciu pasmach (Bliski Wschód,
  Grecja, Rzym, chrześcijaństwo, dzieła), 19 belek życiorysów i odczepiona wstęga czasu
  mitycznego, rysowana **bez skali**, bo mit jest porządkiem opowieści, nie kalendarzem.
  Skala osi jest odcinkowa — epoka klasyczna i augustowska są rozciągnięte, co strona
  wprost sygnalizuje. Osobno zaznaczony jest szew er: jedyne miejsce, w którym oś
  zmienia znak.
- **33 wycinki tekstów źródłowych** — po grecku, po łacinie, po hebrajsku i w transliteracji
  akadyjskiej, każdy z przekładem, notą o pochodzeniu przekładu i komentarzem filologicznym.
  Od tabliczki Siduri i §§ 196–199 Kodeksu Hammurabiego, przez inwokacje obu eposów Homera,
  Safonę, Antygonę i Protagorasa, po Tacyta, Senekę i Augustyna.
- **41 obrazów zabytków** — fotografie z Wikimedia Commons dobrane do kultur opisywanych
  w kolejnych modułach, z podpisem, muzeum, licencją i odnośnikiem do strony pliku.
- **Nakładka „paradoks"** — trzy pomiary rozbrajające najczęstsze pomyłki chronologiczne
  wokół *Eneidy*: Wergiliusz umiera piętnaście lat przed narodzinami Jezusa, od jego
  śmierci do prześladowań Nerona mijają 82 lata, a akcja eposu dzieje się jakieś
  1155 lat przed jego napisaniem.
- **Jedenaście różnych ćwiczeń** — sortery, paralela Gilgamesz ↔ Księga Rodzaju, dekoder
  przypowieści, budowanie heksametru, klikalny plan teatru greckiego, maszyna konfliktu
  tragicznego, schemat ustroju republiki, close reading proroctwa Jowisza z adnotacjami,
  układanki chronologiczne, kalkulator dystansu czasowego, konstruktor pałacu pamięci.
- **118 fiszek** w systemie Leitnera, 60 pytań quizowych, postęp i odpowiedzi zapisywane
  lokalnie w przeglądarce, eksport notatek do Markdown, wydruk całego kursu razem
  z wycinkami źródłowymi.

Sterowanie: **← →** moduły · **spacja** zalicz i dalej · **F** fiszki · **M** przełącz tryb ·
kółko myszy i szczypanie — zoom osi. W powiększeniu obrazu: **← →** następny, **Esc** zamknij.

### Obrazy a tryb offline

Fotografie zabytków wczytuje przeglądarka wprost z Wikimedia Commons przez
`Special:FilePath`, czyli po nazwie pliku, bez zaszywania adresów konkretnych serwerów.
Cała reszta strony działa bez sieci, więc **każdy kafelek ma pod spodem rysowaną wektorowo
planszę** — gdy obrazu nie da się pobrać, zostaje ona, a strona nigdy nie pokazuje pustej
ramki. Pobieranie fotografii można wyłączyć w **Warstwach → „Fotografie z Wikimediów"**;
wybór jest zapamiętywany.

### Uwagi merytoryczne

Odstępy między latami liczone są bez roku zerowego: między 19 p.n.e. a 64 n.e. mija
82 lata, nie 83. Daty wydarzeń mitycznych i legendarnych (1184, 753 p.n.e.) podane są
jako umowne, za tradycją antyczną.

Wycinki źródłowe podane są w oryginale — teksty greckie, łacińskie, hebrajskie i akadyjskie
są w domenie publicznej. Fragmenty biblijne po polsku cytowane są w przekładzie **Jakuba
Wujka** (1599, domena publiczna); pozostałe przekłady to **przekłady robocze sporządzone
na potrzeby kursu** i tak oznaczone przy każdym wycinku — nie są to żadne z przekładów
publikowanych. Klasyczne tłumaczenia (Dmochowskiego, Siemieńskiego, Karyłowskiego) są
wskazywane z nazwiska tam, gdzie warto je porównać z oryginałem. Autorzy XX-wieczni są
omawiani, a cytowani wyłącznie we fragmentach, z podaniem autora i tytułu.

## Atlas

- 34 etapy wyprawy: opis, datowanie, dzisiejsza lokalizacja, odniesienie do sceny z filmu
- animowany przemarsz armii po trasie z kamerą śledzącą i osią czasu
- przełączane warstwy: imperium perskie ok. 334 p.n.e., krainy starożytne,
  dzisiejsze państwa, rzeki i jeziora, siatka geograficzna, miejsca z kursu
- pan / zoom (mysz i dotyk), tryb pełnoekranowy, wersja mobilna

## Jak to jest zrobione

Pojedynczy plik HTML (~1,4 MB) bez żadnych zależności sieciowych — działa też offline
(z rysowanymi planszami zamiast fotografii). W środku osadzone są inline:

| element | źródło |
|---|---|
| cieniowana rzeźba terenu (WebP) | dane wysokościowe SRTM/ETOPO (Mapzen Terrain Tiles), przeliczone na hillshade + tinting hipsometryczny |
| linie brzegowe, rzeki, jeziora, granice | Natural Earth 1:10 m |
| kroje pisma (woff2) | Cinzel + EB Garamond, SIL Open Font License 1.1 |

Jedyne zasoby pobierane z sieci to fotografie zabytków z Wikimedia Commons — opcjonalne
i wyłączalne, opisane wyżej.

Odwzorowanie: Albers, równopolowe stożkowe (południk środkowy 49°E,
równoleżniki standardowe 25°N i 43°N). Kadr obejmuje cały wschodni i środkowy basen
Morza Śródziemnego — od Kartaginy i Rzymu po Taksilę — więc ta sama mapa obsługuje
geografię niemal całego kursu.

Trasa, daty i zasięg imperium są przybliżone; datowanie za Arrianem, Plutarchem
i Kurcjuszem Rufusem.
