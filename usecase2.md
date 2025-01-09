![image](https://github.com/user-attachments/assets/130b395a-2e55-42ba-a335-6a817e56c3eb)
```plantUML
@startuml
left to right direction
actor Użytkownik as u
actor "Administrator systemu" as a

usecase "Kup bilet" as UC1
usecase "Wyświetl ofertę" as UC2
usecase "Wybierz język" as UC3
usecase "Pozyskaj raport" as UC4
usecase "Konfiguruj dostępne bilety, promocje, taryfy" as UC5

u --> UC2
UC2 --> UC1 : <<invoke>>
u --> UC3
a --> UC4
a --> UC5

@enduml
```
