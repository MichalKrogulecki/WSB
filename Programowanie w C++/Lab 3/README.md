# Laboratorium 3

## Poruszane tematy z Sylabusa: 

* [Klasa i obiekt](https://pl.wikibooks.org/wiki/C%2B%2B/Czym_jest_obiekt)
* [Konstruktor i Destruktor](https://pl.wikibooks.org/wiki/C%2B%2B/Konstruktor_i_destruktor)
* [Mechanizm dziedziczenia](https://pl.wikibooks.org/wiki/C%2B%2B/Dziedziczenie)
* [Deklarowanie i używanie metod wirtualnych](http://cpp0x.pl/kursy/Programowanie-obiektowe-C++/Polimorfizm/Metody-wirtualne/495)

## Zadania (10 pkt):

1. (2 pkt) Utwórz klasę o nazwie *Prostokat*, która ma 2 publiczne pola *x* i *y* (typu *int)* i 1 publiczną metodę *pole(),* zwracającą pole powierzchni (również typu *int).* W funkcji głównej programu zadeklaruj obiekt *prostokat* typu *Prostokat* i poproś użytkownika o podanie obu wartości *x* i *y* dla pól obiektu. Następnie wywołaj metodę *pole()* na obiekcie *prostokat*. Wyświetl wynik rozwiązania na ekranie. **Uwaga**, możesz zignorować sprawdzanie parametrów wejściowych użytkownika. 

2. (2 pkt) Zmodyfikuj zadanie pierwsze w ten sposób, aby zmienne *x* i *y* były prywatne. Publiczną metodę *pole()* zamień na publiczną zmienną *int pole*. Następnie utwórz [konstruktor](https://pl.wikibooks.org/wiki/C%2B%2B/Konstruktor_i_destruktor) *Prostokat:Prostokat(int x, int y)* który będzie wyliczał pole powierzchni figury i przypisywał wynik do zmiennej *pole*. Ponownie pobierz od użytkownika oba wymiary, które to przekażesz do konstruktora i w efekcie na koniec wyświetlisz wynik odwołując się do publicznej zmiennej *pole*.

3. (2 pkt) Utwórz 3-poziomową hierarchię klas z konstruktorami domyślnymi i destruktorami, w których to używając funkcji *cout* wypiszesz na ekran skąd są wywołane. Następnie w funkcji głównej programu utwórz wskaźnik na klasę najbardziej pochodną, poinformuj użytkownika o utworzeniu klasy, a potem usuń ten wskaźnik i również poinformuj o tym użytkownika.

   Oczekiwany output konsoli:

   ```c++
   Konstruktor Klasa A
   Konstruktor Klasa B
   Konstruktor Klasa C
   Klasa utworzona
   Destruktor Klasa C
   Destruktor Klasa B
   Destruktor Klasa A
   Klasa usunieta
   ```

4. (4 pkt) Utwórz klasę bazową *Figura*, jak również klasy: *Prostokat*, *Kwadrat*, *Kolo* i *Trapez* [dziedziczące](https://pl.wikibooks.org/wiki/C%2B%2B/Dziedziczenie) po klasie bazowej *Figura*. Każda z klas musi mieć definicję metody *pole()*, wyliczającą pole danej figury. Następnie w funkcji *main()* utwórz 4-elementową tablicę wskaźników typu *Figura*, której każdy z elementów będzie inną figurą (zadbaj o określenie rozmiarów figur w konstruktorach). Następnie używając pętli *for* przejdź po wszystkich figurach z tablicy, wywołaj dla każdej metodę *pole()* i oblicz sumę pól wszystkich figur z tej tablicy. **Uwaga**, wielkości figur możesz zdefiniować w programie. **Uwaga**: Klasa bazowa *Figura* powinna mieć [metodę czysto wirtualną](http://cpp0x.pl/kursy/Programowanie-obiektowe-C++/Polimorfizm/Metody-wirtualne/495) *pole()*.

   <u>Przykład funkcji *main()*</u>

   ```c++
   double suma = 0;
   
   Figura *figura[4];
   figura[0] = new Prostokat(3, 4);
   figura[1] = new Kwadrat(5);
   figura[2] = new Kolo(2);
   figura[3] = new Trapez(2, 4, 3);
   
   for (int i = 0; i < 4; i++) {
   	suma += figura[i]->pole();
   }
   
   cout << "Suma pol: " << suma << endl;
   ```
