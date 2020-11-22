# Laboratorium 1

Pomoc do zadań znajdą Państwo w sekcji [POMOC](https://github.com/MichalKrogulecki/WSB/tree/master/Programowanie%20komputer%C3%B3w/Pomoc)

Polecam zapoznanie się z książką: http://c-sharp.ue.katowice.pl/ksiazka/c_sharp_wer2_0.pdf 

## Zadania (10 pkt):

1. (2 pkt) Napisz program, w którym w zależności od wartości zmiennej *liczba* typu *int* wypisze:

   * "A" - jeśli *liczba* jest podzielna przez 3
   * "B" - jeśli *liczba* jest podzielna przez 5
   * "AB" - jeśli *liczba* jest podzielna przez 15

   **Uwaga**: Uniknij sprawdzenia w programie, czy liczba jest podzielna przez 15!

2. (2 pkt) Używająć pętlę *for* zagnieżdżoną w pętli *for*, wypisz tabliczkę mnożenia o wymiarach 10 x 10.

   Oczekiwany output konsoli:

   ```c#
   1       2       3       4       5       6       7       8       9       10
   2       4       6       8       10      12      14      16      18      20
   3       6       9       12      15      18      21      24      27      30
   4       8       12      16      20      24      28      32      36      40
   5       10      15      20      25      30      35      40      45      50
   6       12      18      24      30      36      42      48      54      60
   7       14      21      28      35      42      49      56      63      70
   8       16      24      32      40      48      56      64      72      80
   9       18      27      36      45      54      63      72      81      90
   10      20      30      40      50      60      70      80      90      100
   ```

   **Uwaga:** Zwróć uwagę, żeby tabliczka była prawidłowo wyświetlana (tak jak powyżej, bez efektu "rozjeżdżania").

3. (2 pkt) Napisz program, w którym w konsoli poprosisz użytkownika o podanie następujących danych: *imie*, *nazwisko*, wiek. Zadbaj o sprawdzenie poprawności wprowadzonego wieku korzystając z metody [*TryParse()*](https://docs.microsoft.com/pl-pl/dotnet/api/system.int32.tryparse?view=netcore-3.1) (proś użytkownika o podanie wieku tak długo, jak poda go w poprawnym formacie, zdolnym do zrzutowania na wartość liczbową) *Podpowiedź:* skorzystaj z pętli iteracyjnej *do...while*. 

   **Uwaga:** Wyświetl na ekranie konsoli podane informacje w jednej linii (nie wielu!).

4. (2 pkt) Korzystając z klasy [*Math*](https://docs.microsoft.com/pl-pl/dotnet/api/system.math?view=netcore-3.1) wylicz następujące wyrażenie w programie i wyświetl zarówno jego dokładny wynik jak i wynik w zaokrągleniu do 2 miejsc po przecinku: 

      <a href="https://www.codecogs.com/eqnedit.php?latex=\bg_white&space;|&space;-&space;\frac{(2&space;\cdot&space;2&space;&plus;&space;3)}{&space;(\sqrt{225}&space;-&space;3^2)}&space;|" target="_blank"> <img src="https://latex.codecogs.com/gif.latex?\bg_white&space;|&space;-&space;\frac{(2&space;\cdot&space;2&space;&plus;&space;3)}{&space;(\sqrt{225}&space;-&space;3^2)}&space;|" title="| - \frac{(2 \cdot 2 + 3)}{ (\sqrt{225} - 3^2)} |"/></a>

   **Uwaga:** Do potęgowania, pierwiastkowania, wartości bezwzględnej i zaokrąglania musisz użyć detykowanych funkcji z klasy [*Math*](https://docs.microsoft.com/pl-pl/dotnet/api/system.math?view=netcore-3.1).

5. (2 pkt) Używając **niekończącej pętli iteracyjnej *for***  i instrukcji skoku ***break*** i ***continue*** napisz program, który dla kolejnych liczb całkowitych od 1 do 50 wypisze tylko te, które są podzielne przez 6.

