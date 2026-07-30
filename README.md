# Podboje Aleksandra Wielkiego — interaktywny atlas

Strona `index.html` to interaktywna mapa wyprawy Aleksandra Wielkiego (336–323 p.n.e.),
pomyślana jako towarzystwo do filmu „Aleksander" Olivera Stone'a (2004).

**To jest jedyna strona w tym repo — cała aplikacja mieści się w `index.html`.**

## Co zawiera

- 34 etapy wyprawy: opis, datowanie, dzisiejsza lokalizacja, odniesienie do sceny z filmu
- animowany przemarsz armii po trasie z kamerą śledzącą i osią czasu
- przełączane warstwy: imperium perskie ok. 334 p.n.e., krainy starożytne,
  dzisiejsze państwa, rzeki i jeziora, siatka geograficzna
- pan / zoom (mysz i dotyk), tryb pełnoekranowy, wersja mobilna

## Jak to jest zrobione

Pojedynczy plik HTML (~1 MB) bez żadnych zależności sieciowych — działa też offline.
W środku osadzone są inline:

| element | źródło |
|---|---|
| cieniowana rzeźba terenu (WebP) | dane wysokościowe SRTM/ETOPO (Mapzen Terrain Tiles), przeliczone na hillshade + tinting hipsometryczny |
| linie brzegowe, rzeki, jeziora, granice | Natural Earth 1:10 m |
| kroje pisma (woff2) | Cinzel + EB Garamond, SIL Open Font License 1.1 |

Odwzorowanie: Albers, równopolowe stożkowe (południk środkowy 49°E,
równoleżniki standardowe 25°N i 43°N).

Trasa, daty i zasięg imperium są przybliżone; datowanie za Arrianem, Plutarchem
i Kurcjuszem Rufusem.
