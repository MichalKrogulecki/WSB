# POMOC

Polecam zapoznanie się z książką: http://c-sharp.ue.katowice.pl/ksiazka/c_sharp_wer2_0.pdf 

1. **Instalacja programu Visual Studio Community i tworzenie aplikacji "Hello World"**

   1. Wejdź na stronę https://visualstudio.microsoft.com/pl/vs/community/ i pobierz Visual Studio Community
   2. Podczas instalacji, upewnij się że wybrałeś pakiet "Programowanie aplikacji klasycznych dla platformy .NET" (ang. ".NET desktop development")
   3. Otwórz aplikację Visual Studio i kliknij "Utwórz nowy projekt" (ang. "Create a new project"). Wybierz język "C#" i "Aplikacja konsoli (.NET Core)" (ang. "Console App (.NET Core)"). Nazwij swój projekt i zlokalizuj jego pliki gdziekolwiek zechcesz.
   4. Po chwili utworzy się domyślny, startowy program "Hello World" który wyświetla na konsoli napis "Hello World". Żeby go uruchomić z debuggerem należy użyć klawisza *F5*, natomiast bez debuggera klawiszy *Ctrl+F5*. Można również kliknąć strzałkę z napisem *Start*. 

2. **Struktura programu w C#**

   W poprzednim punkcie utworzyliśmy domyślny projekt Aplikacji konsoli w .NET Core. Powinien on wyglądać mniej więcej tak:

   ```c#
   using System;
   
   namespace Example
   {
       class Program
       {
           static void Main(string[] args)
           {
               Console.WriteLine("Hello World!");
           }
       }
   }
   ```

   Proszę zwrócić uwagę na strukturę programu. W języku C# spacje, tabulatory i nowe linie są ignorowane (w przeciwieństwie do języka*Python*).  Z drugiej strony, wszystkie linie poza blokami *{ }* muszą kończyć się średnikiem ';'.

   Przestrzeń nazw (ang. namespace), w tym wypadku *Example* jest kontekstem, w ramach którego wszystkie nazwy powinny być unikatowe (niepowtarzalne).

   Na początku programu dodajemy wszystkie przestrzenie nazw, które chcemy by były widoczne w danym pliku. W tym wypadku dodaliśmy przestrzeń nazw o nazwie *System*. Dzięki temu wypisując na ekran konsoli jakiś tekst możemy pominąć słowo *System* w linii *System.Console.WriteLine("Hello World!")*.

   Funkcja *Main()* może również być pozbawiona parametrów jak i może zwracać jakąś wartość. Wówczas mogłaby wyglądać na przykład tak:

   ```c#
   static int Main()
   {
       //...
       return 0;
   }
   ```

   

3. **Komentarze**

   Komenarze można zamieszczać w jednej linii albo w blokach wyznaczonych poprzez znaki " /* " i " */ "

   ```c#
   // komentarz jednolinijkowy
   
   /* komentarz
   ...
   wielolinijkowy */
   ```

   

4. **Deklarowanie i definiowanie zmiennych**

   Konwencją jest żeby zmienna zaczynała się od małej litery albo od podkreślnika '_' i żeby była pisana zgodnie z tzw. "camelCase" (kolejne wyrazy w nazwie zmiennej pisanej łącznie rozpoczynają się z wielkiej litery, np. "mojaZmienna1") . Nie może zaczynać się od cyfry. Może zawierać litery, cyfry i podkreślniki. Można w jednej lini zarówno deklarować zmienną (nadawać jej typ i nazwę), jak również definiować (przypisywać wartość). Można nawet w jednej lini deklarować kilka zmiennych. Poniżej kika przykładów:

   ```c#
   int wiek = 18;
   char plec = 'M';
   string mojaZmienna1 = "mama";
   string _zmienna1, _zmienna2;
   ```

5. **Konsola - podstawowe operacje**

   Wypisywanie wartości na ekran w sposób tradycyjny jak i używając *string interpolation* ("" poprzedzony znakiem '$').

   ```c#
   Console.WriteLine("Hello World!");	// Wypisze: Hello World!
   
   int wiek = 18;
   Console.WriteLine("Mój wiek to " + wiek + " lat");	// Wypisze: Mój wiek to 18 lat
   Console.WriteLine("Mój wiek to {0} lat", wiek);		// Wypisze: Mój wiek to 18 lat
   Console.WriteLine($"Mój wiek to {wiek} lat");		// Wypisze: Mój wiek to 18 lat
   
   Console.Write('A');              // Wypisze tylko 'a' i nie przejdzie do nowej lini
   Console.Write("la");             // 
   Console.WriteLine(" ma kota");   // te trzy linie wypiszą na ekranie jedną linię: Ala ma kota
   ```

   Wczytywanie z konsoli, do komentu wciśnięcia znaku końca linii (klawisza 'Enter').

   ```c#
   string imie = Console.ReadLine();
   Console.WriteLine("Nazywam sie " + imie);
   ```

   Wczytywanie z konsoli dowolnego, pierwszego naciśniętego klawisza. Często używane na samym końcu funkcji *Main()* nie w celu wczytywania konkretnego znaku, ale w celu uniknięcia zamknięcia okna konsoli po wykonaniu funkcji *Main()*.

   ```c#
   static void Main()
   {
       //...
       Console.ReadKey();
   }
   ```

   **Znaki specjalne**

   Istnieje kilka znaków specjalnych, które użyte jako *string* są inaczej interpretowane.

   | Znak specjalny | Nazwa             | Opis / przykład użycia                                       |
   | -------------- | ----------------- | ------------------------------------------------------------ |
   | \\'            | apostrof          | *Console.WriteLine(" \\' ");*   // Wyświetla: '              |
   | \\"            | cudzysłów         | *Console.WriteLine(" \\" ");*   // Wyświetla: "              |
   | \\\            | ukośnik lewy      | *Console.WriteLine(" \\\ ");*   // Wyświetla: \              |
   | \n             | nowa linia        | *Console.WriteLine("a\nb");*   // Wyświetla 2 linie. W pierwszej *a* w drugiej *b* |
   | \t             | tabulator poziomy | *Console.WriteLine("a\tb");*   // Wyświetla w jednym wierszu z odstępem (tabulacją) wartości a i *b* |

   

6. **Typy danych**

   | Typ    | Rozmiar | Zakres                |
   | ------ | ------- | --------------------- |
   | sbyte  | 8       | od  -128 do 127       |
   | byte   | 8       | od 0 do 255           |
   | short  | 16      | od -32768 do 32767    |
   | ushort | 16      | od 0 do 65535         |
   | int    | 32      | od -(2^16)  do 2^16-1 |
   | uint   | 32      | od 0 do 2^32-1        |
   | long   | 64      | od -(2^32)  do 2^32-1 |
   | ulong  | 64      | od 0 do 2^64-1        |

   Przykład użycia:

   ```c#
   int wiek = 24;
   ```

   | Typ     | Rozmiar / Precyzja | Zakres                               |
   | ------- | ------------------ | ------------------------------------ |
   | float   | 32 / 6-9 cyfr      | od +/- 1.5x10^-45 do +/- 3.4x10^38   |
   | double  | 64 / 15-17 cyfr    | od +/- 5.0x10^-324 do +/- 1.7x10^308 |
   | decimal | 128 / 28-29 cyfr   | od 1.0x10^-28 do 7.9x10^28           |

   Przykład użycia:

   ```c#
   decimal pi = 3.14159265359; 
   ```

   | Typ    | Rozmiar | Zakres                             |
   | ------ | ------- | ---------------------------------- |
   | char   | 16      | znak Unicode ujęty w apostrof      |
   | string | -       | łańcuch znaków ujęty w cudzysłowie |

   Przykład użycia:

   ```c#
   char a = 'a';
   char aDuze = 'A';
   ```

   | Typ  | Rozmiar | Zakres       |
   | ---- | ------- | ------------ |
   | bool | 8       | true / false |

   Przykład użycia:

   ```c#
   bool prawda = true;
   bool falsz = false;
   string imie = "Jan";
   string nazwisko = "Kowalski"
   string imieNazwisko = $"{imie} {nazwisko}"; // interpelacja łańcucha znaków
   ```

   

7. **Operatory**

   1. **Arytmetyczne**

      | Operator | Nazwa                       | Przykład użycia                                              |
      | -------- | --------------------------- | ------------------------------------------------------------ |
      | +     -  | Dodawanie i odejmowanie     | *int zmienna* = 4 + 2 - 7;                                   |
      | *     /  | Mnożenie dzielenie          | *double* *zmienna* = 4.0 * 2.0 / 3.0;                        |
      | %        | Modulo (reszta z dzielenia) | *int* *reszta* = 6 % 5;   // *reszta* równa 1<br />*if* (*zmienna* % 3 == 0)   // sprawdzenie, czy *zmienna* jest podzielna przez 3 |
      | ++       | Inkrementacja               | *for* (*int i* = 0; *i* < 7; *i*++)   // zwiększanie *i* o 1 z każdym przejściem pętli *for* |
      | --       | Dekrementacja               | *int a* = 3;<br />*int b* = 2 * --*a*;<br />// *b* będzie równe 4, bo dekrementacja zapisana z lewej strony wykonuje się przed przypisaniem |

   

   2. **Przypisania**

      | Operator | Nazwa                                 | Przykład użycia                             |
      | -------- | ------------------------------------- | ------------------------------------------- |
      | =        | Przypisanie                           | *int a = 5;*<br />int b = a;   // b równe 5 |
      | +=   -=  | Przypisanie z dodawaniem/odejmowaniem | *b += 1*;   // tożsame z *b = b + 1*        |
      | *=   /=  | Przypisanie z mnożeniem/dzieleniem    | *b /= 2*;   // tożsame z *b = b / 1*        |
      | %=       | Przypisanie z modulo                  | *b %= 2;*   // tożsame z *b = b % 2*        |

      

   3. **Relacji**

      | Operator | Nazwa                        | Przykład użycia |
      | -------- | ---------------------------- | --------------- |
      | ==       | Równe                        | *a == b;*       |
      | !=       | Różne                        | *a != b;*       |
      | <   <=   | Mniejsze, mniejsze lub równe | *i < 10;*       |
      | \>   >=  | Większe, większe lub równe   | b >= 2;         |

      

   4. **Logiczne i bitowe**

      | Operator | Nazwa                 | Przykład użycia                                              |
      | -------- | --------------------- | ------------------------------------------------------------ |
      | !        | Negacja               | *bool a = true;*<br />*bool b = !a;*   // *b* równe *false*  |
      | &&       | Koniunkcja warunkowa  | *if (a > 5 && a < 10)*   // *true* dla a z przedziału od 6 do 9 |
      | &        | Koniunkcja bitowa     | *int x = 0b01 & 0b11;*   // *x* równe 0b01                   |
      | \|\|     | Alternatywa warunkowa | if (a < 5 \|\| a > 10)   // *true* dla a mniejszego od 5 LUB większego od 10 |
      | \|       | Alternatywa bitowa    | *int x = 0b01 \| 0b11;*   // *x* równe 0b11                  |

      

8. **Instrukcje warunkowe**

   1. **if**

      Jeśli *wyrażenie* ma wartość *true* to wykonywana jest *instrukcja*

      ```c#
      if(wyrazenie)
          instrukcja;
      ```

      Jeśli *wyrażenie* ma wartość *true* to wykonywana jest *instrukcja1*, w przyciwnym wypadku *instrukcja2*

      ```c#
      if(wyrazenie)
          instrukcja1;
      else
          instrukcja2;
      ```

      Zarówno w wyrażeniu *if* jak również w *if...else* zamiast pojedyńczych instrukcji mogą być wykonywane całe bloki instrukcji, które muszą być ujęte w klamry *{ }*

      Przykłady użycia:

      ```c#
      if (wiek > 18 && wiek < 99)
      {
          bool dostep = true;
      	Console.WriteLine("Dostęp przyznany!");
      }
      
      if (i > 0)
          i--;
      else
          i++;
      
      if (liczba < 0)
          Console.WriteLine("Liczba ujemna");
      else if (liczba > 0)
          Console.WriteLine("Liczba dodatnia");
      else
          Console.WriteLine("Liczba 0");
      
      ```

   2. **operator warunkowy ( ) ? :**

      Jeśli *wyrażenie* ma wartość *true* to operator warunkowy zwraca *instrukcjaTrue*, w przeciwnym wypadku *instrukcjaFalse*

      ```c#
      (wyrazenie) ? instrukcjaTrue : instrukcjaFalse;
      ```

      Przykład użycia:

      ```c#
      int liczba = 1;
      (liczba > 0) ? Console.WriteLine("Liczba dodatnia") : Console.WriteLine("Liczba ujemna");
      ```

      

9. **Pętle interacyjne**

   1. **for**

      Blok jest wykonywany dopóki spełniony jest warunek. Pętla operuje na zmiennej nazywaną zmienną sterującą (zwyczajowo nazywaną '*i*')

      ```c#
      for (inicjalizacjaZmiennej; warunek; iterowanie)
      {
          //blok instrukcji
      }
      ```

      Przykłady użycia:

      ```c#
      for (int i = 0; i < 3; i++)
          Console.WriteLine(i);
      
      for (int i = 5; i > 0; i--)
          Console.WriteLine(i);
      
      for (int i = 0; i < 3; i++)
      {
          for (int j = 0; j < 3; j++)
          	Console.WriteLine($"{i} {j}");
      }
      
      for (int i = 0; ; i++)	// niekończąca pętla for, bez warunku zakończenia
          Console.WriteLine(i);
      ```

      

   2. **while**

      Blok instrukcji jest wykonywany dopóki wyrażenie ma wartość *true*.

      ```c#
      while (wyrazenie)
      {
          //blok instrukcji
      }
      ```

      Przykład użycia:

      ```c#
      int i = 0;
      while (i < 3)
      {
          Console.WriteLine(i);	// Wykona się 3 razy, wypisze: 0  1  2
          i++;
      }
      ```

      

   3. **do...while**

      Blok instrukcji jest wykonywany zawsze conajmniej raz, a potem, dopóki wyrażenie ma wartość *true*. 

      ```c#
      do
      {
          //blok instrukcji
      } while (wyrazenie);
      ```

      Przykład użycia:

      ```c#
      do
      {
          Console.WriteLine("Podaj slowo \"koniec\"");
          slowo = Console.ReadLine();
      } (slowo != "koniec");
      ```

      

   4. **foreach...in**

      Pętla *foreach* używana jest do automatycznej iteracji po całej kolekcji (np. liście albo tablicy). Blok instrukcji jest wykonywany dla każdego elementu o podanym typie danych znajdującego się w kolekcji. **Ważne**: używając tej pętli nie można przypisywać innych wartości elementom kolekcji (są one tylko do odczytu)

      ```c#
      foreach (typ zmienna in kolekcja)
      	Console.WriteLine(zmienna);
      ```

      Przykład użycia:

      ```c#
      string[] weekend = {"piatek", "sobota", "niedziela"};
      foreach (string dzien in weekend)
          Console.WriteLine(dzien);
      
      foreach(char c in "WSB")
          Console.WriteLine(c);
      
      foreach(int element in tablicaIntow)
          element += 100;  // Błąd kompilacji! Wartości kolekcji w pętli foreach są tylko do odczytu!
      ```

      

10. **Instrukcje sterujące**

    1. **switch...case**

       Wybiera pojedynczy *przełącznik* , który ma zostać wykonany z listy kandydatów na podstawie dopasowania.

       ```c#
       int x = 1;
       switch (x)
       {
            case 1:
            	Console.WriteLine("1");		// to zostanie wybrane, wyświetli: 1
            	break;
            case 2:
            	Console.WriteLine("2");
            	break;
            default:
            	Console.WriteLine("Nic");
            	break;
       } 
       ```

       

11. **Instrukcje skoku**

    1. **break**

       Instrukcja kończy <u>najbliższą</u> otaczającą pętlę lub instrukcję *switch*, w której występuje. 

       Przykład użycia:

       ```c#
       for (int i = 0; i < 100; i++)
       {
           if (i == 5)
           {
               break;
           }
           Console.WriteLine(i);	// wypisze: 0  1  2  3  4
       }
       ```

       

    2. **continue**

       Instrukcja pomija aktualnie wykonywaną iterację w danej pętli i wraca do jej początku.

       Przykład użycia:

       ```c#
       for (int i = 0; i < 10; i++)
       {
           if (i < 5)
           {
               continue;
           }
           Console.WriteLine(i);	// wypisze: 5  6  7  8  9
       }
       ```

       

    3. **return**

       Instrukcja kończy wykonywanie metody, w której występuje i zwraca kontrolę do metody wywołującej.

       

    4. **goto**

       Instrukcja przesyła bezpośrednio kontrolę programu do instrukcji oznaczonej etykietą.

       Przykład użycia:

       ```c#
       while(1)
       {
           Console.WriteLine("Podaj slowo \"koniec\"");
           slowo = Console.ReadLine();
           
           if (slowo == "koniec")
               goto Koniec;
       }
       
       Koniec:
       Console.WriteLine("KONIEC!");
       ```

       

12. **Parsowanie/Konwertowanie**

    ```c#  
    // Konwertowanie łancucha znaków na liczbę
    string liczbaString = "123";
    int liczba = Int32.Parse(liczbaString);
    int liczba2 = Convert.ToInt32(liczbaString);
    ```

    Gdy nie jesteśmy pewni czy parsowanie się uda możemy zastosować konstruckję *TryParse()*

    ```c#
    Console.WriteLine("Podaj swój wiek");
    String sWiek = Console.ReadLine();
    
    if (Int32.TryParse(sWiek, out wiek))
    {
        Console.WriteLine($"Twój wiek to {wiek}");
    }
    else
    {
        Console.WriteLine("Podałeś wiek w złym formacie!");
    }
    ```

    

13. **Słowa kluczowe** (zastrzeżone w języku, nie mogą być nazwami zmiennych, funkcji, klas, itp.)

    abstract as base bool break byte case catch char checked class const continue decimal default delegate do double else enum event explicit extern false finally fixed float for foreach goto if implicit in in (generic modifier) int interface internal is lock long namespace new null object operator out out (generic modifier) override params private protected public readonly ref return sbyte sealed short sizeof stackalloc static string struct switch this throw true try typeof uint ulong unchecked unsafe ushort using virtual void volatile while

    Uwaga! Dopuszcza się użycie słów kluczowych jako nazwa zmiennej. Wówczas nazwa musi być poprzedzona znakiem '@'.

    ```c#
    string @class = "student";	// bez znaku '@' przed słowem kluczowym 'class' byłby błąd kompilacji
    ```

14. **Tablice statyczne**

    Tablice statyczne to takie, które w chwili kompilacji mają określony swój rozmiar (wielkość).

    1. **Tablica jednowymiarowa**

       Deklaracja:

       ```c#
       typ[] nazwa = new typ[rozmiar];
       ```

       Definicja / Inicjalizacja:

       ```c#
       typ[] nazwa = {lista_inicjacyjna}
       ```

       Przykłady użycia:

       ```c#
       //Przykład 1a: Deklaracja i w kolejnych liniach definicja elementów
       int[] tablica = new int[4];	//Deklaracja tablicy 4-elementowej
       tablica[0] = 0;	//PAMIĘTAJ! Indeksowanie w tablicach rozpoczyna się od '0'
       tablica[1] = 5;
       tablica[2] = 10;
       tablica[3] = 15;
       //PAMIĘTAJ! Nie możesz odwołać się do elementu tablica[4], ponieważ zadeklarowaliśmy tablicę 4-elementową (od '0' do '3')
       
       //Przykład 1b: Deklaracja i inicjalizacja wartości elementów tablicy w jednej linii
       int[] tablica = {0, 5, 10, 15};
       
       //Przykład 2a: Odwoływanie się do elementów tablicy używając pętli for
       for (int i = 0; i < tablica.Length; i++)
           Console.WriteLine(tablica[i]);
       
       //Przykład 2b: Odwoływanie się do elementów tablicy używając pętli foreach...in
       foreach (int element in tablica)
           Console.WriteLine(element);
       ```

    2. **Tablica dwuwymiarowa**

       Przykład użycia:

       ```c#
       //Przykład 1a: Deklaracja i w kolejnych liniach definicja elementów
       string[,] imie = new string[2,2]; // Deklaracja tablicy rozmiarów 2 x 2
       imie[0,0] = "Adam";
       imie[0,1] = "Ewa";
       imie[1,0] = "Kain";
       imie[1,1] = "Abel";
       
       //Przykład 1b: Deklaracja i inicjalizacja wartości elementów tablicy w jednej linii
       int[,] tablica = { {1,2}, {3,4} };
       
       //Przykład 2: Odwoływanie się do elementów tablicy 2-wymiarowej używając pętli for
       for (int i = 0; i < tablica.GetLength(0); i++)
       {
           for (int j = 0; j < tablica.GetLength(1); j++)
           {
               Console.WriteLine(tablica[i, j]);
           }
       }
       ```

       

    3. **Tablica N-wymiarowa**

       Zasada analogiczna jak dla 2-wymiarowych.



