# Automatyczny-grafik-pracy

To narzędzie automatycznie generuje miesięczny grafik pracy dla zespołu 11 pracowników.
Zostało zbudowane w Excelu z wykorzystaniem OpenSolver (CBC) oraz modelu optymalizacyjnego opartego na zmiennych binarnych.

Projekt pokazuje umiejętność:

modelowania procesów i ograniczeń,

budowania narzędzi automatyzujących pracę operacyjną,

pracy z Solverem i logiką optymalizacyjną,

projektowania czytelnych, dynamicznych arkuszy.

# Funkcjonalności
Automatyczne generowanie kalendarza na podstawie miesiąca i roku

Uwzględnianie weekendów i świąt państwowych

Obsługa preferencji pracowników (zmiany, wolne, urlopy)

Ograniczenia minimalnej liczby osób na zmianie

Równoważenie liczby zmian między pracownikami

Uwzględnienie pracy maksimum 5 dni w tygodniu

Podsumowanie obciążenia pracą dla każdego pracownika

# Model optymalizacyjny
Model wykorzystuje zmienne binarne (0/1), gdzie każda komórka oznacza decyzję:

„Czy pracownik X pracuje w dniu Y na zmianie Z”.

# Ograniczenia uwzględnione w modelu:
minimalna liczba pracowników na zmianie

maksymalna liczba zmian w miesiącu

równomierne rozłożenie pracy

limity pracy w weekendy

preferencje pracowników (twarde i miękkie)

dni ustawowo wolne od pracy

wykluczenia (urlopy, odbiory, wolne)

# Cel optymalizacji:
zminimalizować różnice w liczbie zmian między pracownikami,

spełnić wszystkie ograniczenia operacyjne.

# Struktura narzędzia
1. Panel sterowania
Zawiera:

wybór miesiąca i roku,

parametry grafiku,


2. Model zmiennych (macierz 0/1)
Macierz zawiera:

11 pracowników (P1–P11),

dwie zmiany: 6–14 i 12–20,

wartości 0/1 generowane przez Solver.


3. Ograniczenia
Sekcja zawiera:

sumy zmian,

pracę w weekendy,

różnice między zmianami,

urlopy i wykluczenia.


4. Preferencje pracowników
Pracownicy mogą zgłaszać:

preferowane zmiany (6, 8, 14),

wolne (W),

urlop (U),

dyspozycyjność.


5. Wynik działania Solver
Gotowy grafik zawiera:

przypisane zmiany,

dyżury,

wsparcie,

podsumowanie obciążenia.


6. Święta i dni specjalne
Arkusz automatycznie wykrywa święta i uwzględnia je w modelu.


7. Podsumowanie pracy pracowników
Zawiera:

liczbę zmian,

liczbę weekendów,

różnice między zmianami,

wykryte konflikty.


# Jak korzystać
Wybierz miesiąc i rok.

Uzupełnij preferencje pracowników (opcjonalnie).

Kliknij Uruchom Solver.

Odbierz gotowy grafik.

# Technologie
Excel

OpenSolver (CBC)

Model optymalizacyjny liniowy

Formuły dynamiczne

Formatowanie warunkowe

