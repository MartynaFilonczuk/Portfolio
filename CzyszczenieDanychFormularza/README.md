# Projekt: Automatyczne czyszczenie danych z formularza

### Cel
Stworzenie procesu, który automatycznie czyści i waliduje dane z formularza rejestracyjnego.

### Zakres
- Normalizacja pól (Trim, Proper, Lower)
- Walidacja emaili (kropki, domena, @, null)
- Walidacja wieku (18–120, obsługa błędów)
- Walidacja daty (nie w przyszłości, poprawny format)
- Generowanie alertów (lista błędów na wiersz)
- Podział na dane poprawne i błędne

### Technologie
- Power Query (M)
- Excel

### Przykładowy fragment logiki (walidacja wieku)

```m
let
    wiek = try Number.From([Wiek])
in
    if wiek[HasError] then false
    else wiek[Value] >= 18 and wiek[Value] <= 120
