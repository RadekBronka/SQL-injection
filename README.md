# SQL-injection

Cel

Wyświetlić dane wszystkich użytkowników, omijając warunek WHERE id = ?.

Kroki

Kliknij DVWA Security → ustaw Low → Submit.

Kliknij SQL Injection w menu.

W polu User ID wpisz payload SQL.

Kliknij Submit.

Co powinno się stać (kryterium sukcesu)

Zamiast jednego użytkownika zobaczysz listę wielu użytkowników (więcej niż jeden rekord).

Podpowiedź
<details>
1' OR '1'='1
</details>
