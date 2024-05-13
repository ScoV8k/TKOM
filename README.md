# TKOM
Programming language with object definition and type matching. Compilation Techniques - Politechnika Warszawska.

# Opis języka

Język programowania skupiający się na definiowaniu i manipulacji obiektami oraz wykorzystaniu mechanizmu dopasowywania typów. Pozwala na tworzenie własnych typów obiektów z ich atrybutami i metodami. Kluczową funkcją jest mechanizm dopasowywania typów, umożliwiający różne operacje w zależności od typu obiektu.

Interpreter tego języka jest tworzony w Pythonie.

## Funkcjonalności Standardowe

### Podstawowe Typy Danych i Operacje
Obsługuje typy liczbowe **int/float** z operacjami matematycznymi (np. `+`, `-`, `*`, `/`), typ **bool** oraz typy znakowe (**stringi**) z możliwością konkatenacji.

### Zmienne
Umożliwia tworzenie zmiennych, przypisywanie wartości i ich odczyt. Język oferuje **dynamiczne i silne typowanie**. Zmienne są **mutowalne**.

### Komentarze
Wsparcie dla komentarzy jednoliniowych, rozpoczynających się od `#`.

### Instrukcje Warunkowe i Pętle
Wspiera konstrukcje warunkowe i pętle.

### Funkcje
Pozwala na definiowanie własnych funkcji z dynamiczną semantyką przekazywania argumentów.

### Rekursja
Obsługuje rekursywne wywołania funkcji.

### Obsługa Błędów
Implementuje mechanizmy obsługi błędów.

## Funkcjonalności Dodatkowe

### Definiowanie Obiektów
Umożliwia definiowanie własnych obiektów z konstruktorami, atrybutami i metodami.

```python
obj Student {
    name: string,
    age: int,
    greet() => print("Hello, " + this.name)
}
```

### Dopasowywanie Typów
Mechanizm dopasowywania typów pozwala na wykonanie różnych operacji w zależności od typu obiektu.

```python
fun process_object(obj) {
    obj match {
        Student => print("Hello student ", obj.name),
        Teacher => print("Good morning sir"),
        _ => print("Unknown object type")
    }
}
```

## Wymagania Niefunkcjonalne
- Język programowania: Python
- Podział na moduły: lexer, parser, interpreter

## Gramatyka

```
program ::= { global_statement };

global_statement ::= declaration 
                   | assignment 
                   | if_statement 
                   | while_loop 
                   | function_def 
                   | type_match 
                   | expression_statement
                   | object_def ;

block_statement ::= declaration 
                  | assignment 
                  | if_statement 
                  | while_loop 
                  | type_match 
                  | expression_statement
                  | return_statement ;

object_def ::= "class", identifier, "{", { class_member }, "}" ;
class_member ::= declaration | function_def;

declaration ::= "var", identifier, [ "=", expression ], ";" ;
assignment ::= identifier, "=", expression, ";" ;

if_statement ::= "if", "(", expression, ")", block, [ "else", block ] ;
while_loop ::= "while", "(", expression, ")", block ;

return_statement ::= "return", [ expression ], ";" ;

function_def ::= "fun", identifier, "(", [ parameters ], ")", block ;
parameters ::= identifier, { ",", identifier } ;
identifier_or_function_call ::= identifier, [ "(", [ arguments ], ")" ]; 
arguments ::= expression, { ",", expression } ;


type_match ::= identifier, "match", "{", { match_case }, "}" ;
match_case ::= type, "=>", block
             | "_", "=>", block ;

block ::= "{", { statement }, "}" ;

expression_statement ::= expression, ";" ;

expression ::= logical_expression ;
logical_expression ::= equality_expression, { "&&" | "||", equality_expression } ;
equality_expression ::= relational_expression, { "==" | "!=", relational_expression } ;
relational_expression ::= add_expression, [ "<" | ">" | "<=" | ">=", add_expression ] ;
add_expression ::= mul_expression, { "+", | "-", mul_expression } ;
mul_expression ::= unary_expression, { "*", | "/", unary_expression } ;
unary_expression ::= [ "-", | "not", | "!", ], type_expression ;
type_expression ::= factor, [ "is", type ] ;

factor ::= literal | "(", expression, ")", | obj_access  ;

obj_access ::= item, { ".", item } ;
item ::= identifier_or_function_call ;


type ::= "int" | "float" | "bool" | "string" | custom_type;
custom_type ::= identifier;

literal ::= integer | float | bool | string ;
float ::= integer, ".", digit, { digit } ;
integer  ::= zero | (non_zero_digit, {digit}) ;
bool ::= "true" | "false" ;
string ::= '"', { any_character - '"' }, '"' ;

identifier ::= letter, { letter | digit | "_" } ;


digit ::= non_zero | zero ;
non_zero ::= "1" | "2" | "3" | "4" | "5" | "6" | "7" | "8" | "9" ;
zero ::= "0" ;
letter ::= "A" | "B" | "C" | ... | "Z" | "a" | "b" | "c" | ... | "z" ;
any_character ::= ? all visible characters ? ;

```