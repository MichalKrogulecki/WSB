# Laboratorium 2

## Zadania (10 pkt):
1. (2 pkt) Napisz program, który zainicjalizuje 2-wymiarową tablicę *int[10,10]* w taki sposób, jakby była tabliczką mnożenia. Następnie, tak jak w Zadaniu 2 na Laboratorium 1, wypisz tabliczkę mnożenia na ekran.
2. (2 pkt) Napisz program, który pozwoli zapełnić n–elementową tablicę jednowymiarową liczb całkowitych wartościami podanymi przez użytkownika. Na początku działania programu użytkownik podaje liczbę elementów tablicy, a następnie poszczególne wartości jej elementów. Po wypełnieniu całej tablicy program powinien wypisać jej wartości w oknie konsoli.
3. (4 pkt) Napisz program, który w losowy sposób zapełni jednowymiarową tablicę 100-elementową liczbami całkowitymi z przedziału [-1000, 1000]. Do generowania liczb losowych użyj metody *[Random.Next(-1000,1001)](https://docs.microsoft.com/pl-pl/dotnet/api/system.random.next?view=netcore-3.1)*. Następnie wyświetl na ekranie:
   1. W jednej linii całą tablicę, której elementy oddzielisz spacją
   2. Wartość i numer pozycji najmniejszego elementu korzystając z metody *[Array.IndexOf](https://docs.microsoft.com/pl-pl/dotnet/api/system.array.indexof?view=netcore-3.1)* i [Min()](https://docs.microsoft.com/pl-pl/dotnet/api/system.linq.enumerable.min?view=netcore-3.1#System_Linq_Enumerable_Min_System_Collections_Generic_IEnumerable_System_Nullable_System_Int32___)
   3. Wartość i numer pozycji największego elementu korzystając z metody *[Array.IndexOf](https://docs.microsoft.com/pl-pl/dotnet/api/system.array.indexof?view=netcore-3.1)* i *[Max()](https://docs.microsoft.com/pl-pl/dotnet/api/system.linq.enumerable.max?view=netcore-3.1#System_Linq_Enumerable_Max_System_Collections_Generic_IEnumerable_System_Nullable_System_Double___)*
   4. Posortowaną w kolejności rosnącej całą tablicę korzystając z metody *[Array.Sort()](https://docs.microsoft.com/pl-pl/dotnet/api/system.array.sort?view=netcore-3.1)*
   5. Odwrócona tablicę z powyższego podpunktu korzystając z metody *[Array.Reverse()](https://docs.microsoft.com/pl-pl/dotnet/api/system.array.reverse?view=netcore-3.1#System_Array_Reverse_System_Array_)*

