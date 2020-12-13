# Laboratorium 4

## Nowe poruszane tematy: 

* Obsługa plików
  * [źródło 1](https://cpp0x.pl/kursy/Kurs-C++/Poziom-4/Podstawy-obslugi-plikow/355)
  * [źródło 2](https://pl.wikibooks.org/wiki/C%2B%2B/Strumienie)

## Zadanie (10 pkt):

Napisz prostą konsolową grę typu Quiz, korzystając z zamieszczonej bazy pytań ["Questions.txt"](https://github.com/MichalKrogulecki/WSB/blob/master/Programowanie%20w%20C%2B%2B/Lab4/Questions.txt). 

Po uruchomieniu programu, poproś użytkownika o podanie swojej nazwy gracza i wyborze liczby pytań (3-10), które zostaną wylosowane z listy pytań i kolejno zadane użytkownikowi.

Baza pytań zawiera 10 pytań wraz z 4 wariantami odpowiedzi w formacie .csv, z elementami oddzielonymi w postaci ','. W danym wierszu pierwszym elementem jest pytanie, drugim jest poprawna odpowiedź, kolejnymi trzema są błędne warianty odpowiedzi. Podczas zadawania pytań zadbaj o to, żeby warianty odpowiedzi były prezentowane w losowej kolejności.

Na udzielenie odpowiedzi na każde z pytań użytkownik ma 10 sekund. W przypadku udzielenia błędnej odpowiedzi dostaje 0 punktów. W przypadku poprawnej otrzymuje punkty z przedziału (0-10) w zależności od ilości upłyniętego czasu (np. jak odpowiedź będzie po 3 sekundach to dostaje się 7 punktów; jak po 9,5 sekundach to dostaje 0,5 punktów; itp.).

Na koniec, wynik całkowity (w punktach) wraz z nazwą gracza i maksymalną dostępną liczbą punktów w danej grze należy wpisać w nowej lini na końcu pliku ["Results.txt"](https://github.com/MichalKrogulecki/WSB/blob/master/Programowanie%20w%20C%2B%2B/Lab4/Results.txt) dopisując nowy wynik gracza do pozostałych wyników dostępnych w pliku.

**Kryteria oceny:**

* (1 pkt) Sprawdzenie parametrów wejściowych do programu (nazwa gracza i wybór 3-10 pytań)
* (3 pkt) Załadowanie, obsługa pliku z bazą pytań "Questions.txt" (parsowanie pytań i wariantów odpowiedzi)
* (1 pkt) Wylosowanie wybranej liczby pytań z bazy pytań
* (1 pkt) Losowanie kolejności prezentowanych wariantów odpowiedzi dla każdego z pytań
* (2 pkt) Implementacja licznika 10 sekund dla każdego z pytań
* (1 pkt) Obsługa poprawnej i błędnej udzielonej odpowiedzi
* (1 pkt) Wpis wyniku gracza do pliku "Results.txt"
* *(1-3 pkt) [opcjonalne] Punkty dodatkowe za miłą dla oka oprawę graficzną i/lub dźwiękową
