# Wybierz język
```mermaid
sequenceDiagram
    actor User as Użytkownik
    participant GUI as Interfejs użytkownika

    User->>+GUI: Wybranie opcji 'Język'
    GUI-->>-User: Wyświetlenie menu wyboru języków
    User->>+GUI: Wybranie języka
    GUI->>GUI: Zmiana języka wyświetlania
    GUI-->>-User: Wyświetlenie interfejsu w danym języku
```
# Pozyskaj raport
```mermaid
sequenceDiagram
    actor Admin as Administrator
    participant GUI as Interfejs użytkownika
    participant System as System monitorowania sprzedaży
    participant DB as Baza danych

    Admin->>+GUI: Wciśnięcie przycisku 'Raporty sprzedaży'
    GUI->>+System: Pobierz dane
    System->>+DB: Pobierz dane
    DB-->>-System: :(dane)
    System->>System: Przetwórz dane(dane)
    System-->>-GUI: :(dane)
    GUI-->>-Admin: Wyświetl raport sprzedaży
```
# Konfiguruj dostępne bilety, promocje, taryfy
```mermaid
sequenceDiagram
    actor Admin as Administrator
    participant GUI as Interfejs użytkownika
    participant System as System ofert
    participant DB as Baza danych

    Admin->>+GUI: Wciśnięcie przycisku 'Oferta'
    GUI->>+System: Pobranie aktualnych ofet
    System->>+DB: Pobranie aktualnych ofert
    DB-->>-System: :(aktualne oferty)
    System-->>-GUI: :(aktualne oferty)
    GUI-->>-Admin: Wyświetlenie aktualnych ofert(aktualne oferty)
    Admin->>+GUI: Wprowadzenie zmiany w ofercie
    GUI-->>-Admin: ''
    Admin->>+GUI: Wciśnięcie przycisku 'Zatwierdź'
    GUI->>+System: Zaktualizuj ofertę(oferta)
    System->>+DB: Zaktualizuj ofertę(oferta)
    DB-->>-System: ''
    System-->>-GUI: ''
    GUI-->>-Admin: Wyświetlenie potwierdzenia zmiany oferty
```
# Zdalne zaktualizowanie oprogramowania biletomatu
```mermaid
sequenceDiagram
    actor Admin as Administrator
    participant GUI as Interfejs użytkownika
    participant System as System ofert
    participant DB as Baza danych

    Admin->>+GUI: Wciśnięcie przycisku 'Oprogramowanie biletomatów'
    GUI-->>-Admin: Wyświetlenie widoku zmiany oprogramowania biletomatów

    alt Zmiana w GUI
    Admin->>+GUI: Wprowadzenie zmiany wartości w formularzu
    else Zmiana w pliku
    Admin->>+GUI: Wybór przycisku 'Wyślij plik konfiguracyjny'
    GUI-->>-Admin: Wyświetla okno wyboru pliku
    Admin->>+GUI: Wysyła plik konfugiracyjny
    end

    GUI->>+System: Prześlij konfigurację
    System->>+DB: Zapisz konfigurację
    DB-->>-System: ''
    System-->>-GUI: ''
    GUI-->>-Admin: Wyświetlenie potwierdzenia zmiany konfiguracji oraz widok aktualizacji

    Admin->>+GUI: Wciśnięcie przycisku 'Aktualizuj biletomaty'
    GUI->>+System: Zaktualizuj biletomaty
    System->>+DB: Pobierz najnowszą konfigurację
    DB-->>-System: ''
    System->>System: Zaktualizuj biletomaty
    System-->>-GUI: ''
    GUI-->>-Admin: Wyświetl potwierdzenie zaaktualizowania biletomatów
```
# Monitorowanie stanu biletomatów
```mermaid
sequenceDiagram
    participant support as System wsparcia technicznego
    participant system as System zgłoszeń
loop co 5 minut
    support->>+system: Wysłanie informacji o stanie biletomatu
end
```

# Wysłanie alertu o błędach i anomaliach
```mermaid
sequenceDiagram
    participant support as System wsparcia technicznego
    participant system as System zgłoszeń

    support->>+system: Wysłanie alertu o błędzie
```
