# Customer Feedback Analyzer — Power BI Dashboard
Ten projekt przedstawia kompletny dashboard analityczny do monitorowania opinii klientów, jakości obsługi oraz problemów produktowych.
Dashboard został zbudowany w Power BI na podstawie tabeli Feedback zawierającej:

ocenę (Rating)

sentyment (Sentiment)

kategorię problemu (IssueCategory)

komentarz klienta

kanał kontaktu

produkt

datę

Celem projektu jest szybka identyfikacja problemów, analiza jakości obsługi oraz monitorowanie trendów w czasie.

## Najważniejsze funkcje dashboardu
### 1. Pasek KPI (główne wskaźniki jakości)
Total Feedback

Positive %

Negative %

Issue Rate %

Missing Comment %

Avg Rating

Dzięki temu od razu widać ogólną jakość obsługi i stan danych.

### 2. Analiza sentymentu i problemów (lewa strona)
Sentiment by Product – porównanie pozytywnych, neutralnych i negatywnych opinii

Issue Category by Product – najczęstsze problemy dla każdego produktu

Trend Sentiment Over Time – zmiany jakości obsługi w czasie

### 3. Analiza kanałów i produktów (prawa strona)
Channel by Sentiment – jakość obsługi w kanałach (Email, Chat, Phone)

Avg Rating by Product – średnia ocena produktów

Issue Rate % by Product – procent opinii zawierających problem

### 4. Tabela szczegółowa (dół)
Zawiera pełne dane z opinii klientów:

miesiąc

klient

ocena

sentyment

kategoria problemu

komentarz

kanał

Tabela ma formatowanie warunkowe (kolory sentymentu, gradient ocen).

## Najważniejsze miary DAX

Issue Count =
CALCULATE(
    COUNTROWS(Feedback),
    KEEPFILTERS(Feedback[IssueCategory] <> "Other")
)

Issue Rate % =
DIVIDE([Issue Count], [Total Feedback])

Pozostałe miary: Positive %, Negative %, Missing Comment %, Avg Rating itd.
