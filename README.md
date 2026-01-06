# SQL-injection

**Zadanie 1**
Wyświetlić dane wszystkich użytkowników, omijając warunek WHERE id = ?.

**Kroki**

1.Kliknij DVWA Security → ustaw Low → Submit.

2.Kliknij SQL Injection w menu.

3.W polu User ID wpisz payload SQL.

4.Kliknij Submit.

**Co powinno się stać** 
Zamiast jednego użytkownika zobaczysz listę wielu użytkowników (więcej niż jeden rekord).

Podpowiedź
<details>
1' OR '1'='1
</details>

**Zadanie 2**
Użyć UNION SELECT, aby pobrać dane z innej tabeli (users).

**Co powinno się stać** 
W wynikach pojawią się loginy i hasła użytkowników DVWA.

Podpowiedź
<details>
1' UNION SELECT user, password FROM users -- -
</details>
