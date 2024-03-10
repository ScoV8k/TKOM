# TKOM
Programming language with object definition and type matching. Compilation Techniques - Politechnika Warszawska.

# Opis języka

Język programowania skoncentrowany na definiowaniu i manipulacji obiektami oraz zastosowaniu mechanizmu type matching. Jego główną cechą jest umożliwienie użytkownikom tworzenia własnych typów obiektów, wraz z ich atrybutami i metodami. Kluczową funkcjonalnością jest mechanizm type matching, który pozwala na wykonanie różnych operacji w zależności od typu przekazanego obiektu. 

Interpreter dla tego języka jest tworzony w Pythonie.



# Podstawowe Funkcjonalności Języka

- **Dynamiczne Typowanie**: Typ zmiennej określany jest w momencie przypisania wartości, nie wymaga deklaracji typu przed przypisaniem.

- **Definiowanie i Użycie Obiektów**: Umożliwienie definiowania własnych klas wraz z ich atrybutami i metodami. Możliwość tworzenia instancji tych klas i manipulowanie nimi.

- **Type Matching**: Mechanizm pozwalający na wykonanie różnych operacji w zależności od typu przekazanego obiektu, umożliwiający bardziej elastyczne podejście do programowania.

- **Podstawowe Typy Danych i Operacje**: Wsparcie dla typów danych takich jak `int`, `float`, `bool`, `string` oraz operacje arytmetyczne i logiczne z zachowaniem kolejności działań.

- **Kontrola Przepływu Programu**: Instrukcje warunkowe (`if`, `else`), pętle (`while`), oraz instrukcje sterujące (`return`, `break`, `continue`).

- **Funkcje**: Możliwość definiowania i wywoływania własnych funkcji, w tym rekursji. Przekazywanie argumentów do funkcji i zwracanie wartości.

- **Obsługa Wejścia/Wyjścia**: Funkcje do wypisywania danych na standardowe wyjście (`print()`) i wczytywania danych od użytkownika (`input()`).

- **Komentarze**: Wsparcie dla komentarzy w jednej linii, rozpoczynających się od znaku `#`.

- **Blok Kodu**: Użycie nawiasów klamrowych do ograniczenia bloków kodu i średników do zakończenia instrukcji.

# Dodatkowe Funkcjonalności

- **Mutowalność i Widoczność Zmiennych**: Zmienne są mutowalne, z zasięgiem widoczności ograniczonym do bloków, w których zostały zadeklarowane.

- **Rzutowanie Typów**: Możliwość rzutowania typów, szczególnie przydatne przy operacjach na typach liczbowych.

- **Obsługa Błędów**: Mechanizmy pozwalające na obsługę błędów, które mogą pojawić się podczas wykonania programu.
