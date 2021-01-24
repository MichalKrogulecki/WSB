# Laboratorium 5

Pomoc do zadań znajdą Państwo w sekcji [POMOC](https://github.com/MichalKrogulecki/WSB/tree/master/Programowanie%20komputer%C3%B3w/Pomoc)

## Zadania (6 pkt):

1. (4 pkt) Mając zdefiniowaną listę *todoList*, napisz program, który pozwoli użytkownikowi dodać albo usunąć jakieś zadanie do swojego planu dnia. Możesz np. w programie w pętli pytać użytkownika o podanie cyfry 1, jak chce dodać zadanie, a 0, jak usunąć (podając również numer zadania).  *Podpowiedź:* Skorzystaj z [przykładów z dokumentacji Microsoftu](https://docs.microsoft.com/pl-pl/dotnet/api/system.collections.generic.list-1?view=net-5.0)

   ```c#
   List<string> todoList = new List<string>();
   
   todoList.Add("zjesc sniadanie");
   todoList.Add("zjesc obiad");
   todoList.Add("zjesc kolacje");
   
   do
   {
       // podaj cyfre 1 albo 0
       
       // jak 1 - spytaj o zadanie i miejsce gdzie je dodac (zadbaj o sprawdzenie dlugosci listy!)
       
       // jak 0 - spytaj o zadanie - usun to zadanie (nie pytaj jesli nie ma co usuwac!)
       
       // wyświetl zadania
       foreach (string zad in todoList)
       {
           Console.WriteLine(zad);
       }
   } while (true);
   ```

   

2. (2 pkt) Utwórz podstawowy projekt typu [Windows Forms Application](https://docs.microsoft.com/pl-pl/visualstudio/ide/step-1-create-a-windows-forms-application-project?view=vs-2019) i:

* Dodaj przycisk z tekstem koloru czerwonego "Wczytaj plik tekstowy" - *Podpowiedź:* Zapoznaj się z [Dodawaniem kontrolek do formularza](https://docs.microsoft.com/pl-pl/visualstudio/ide/step-5-add-controls-to-your-form?view=vs-2019)
* Po kliknięciu przycisku "Wczytaj plik tekstowy", zamień tekst na kolor zielony, wczytaj plik tekstowy używając okna dialogowego i wyświetl zawartość pliku tekstowego w MessageBoxie - *Podpowiedź:* Zapoznaj się z [Pisaniem kodu dla programu obsługi zdarzeń przycisku](https://docs.microsoft.com/pl-pl/visualstudio/ide/step-8-write-code-for-the-show-a-picture-button-event-handler?view=vs-2019) i [Otwieranie pliku i MessageBox](https://docs.microsoft.com/pl-pl/dotnet/api/system.windows.forms.openfiledialog.openfile?view=net-5.0)
