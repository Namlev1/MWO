![image](https://github.com/user-attachments/assets/611771a9-dfb1-4941-808a-002f41b9cb0f)

```plantUml
@startuml
left to right direction
actor Użytkownik as u
actor "Administrator systemu" as a
actor "System transakcyjny" as SystemTrans
actor "System biletowy" as SystemBil

rectangle Biletomat{
usecase "Kup bilet" as UC1
usecase "Wyświetl ofertę" as UC2
usecase "Wybierz język" as UC3
usecase "Pozyskaj raport" as UC4
usecase "Konfiguruj dostępne bilety, promocje, taryfy" as UC5
usecase "Zaktualizowanie oprogramowania biletomatu" as aUC4
usecase "Płatność gotówką" as aUC2
usecase "Płatność kartą lub telefonem" as aUC3

}


u --> UC2
UC2 --> UC1 : <<invoke>>
u --> UC3
a --> UC4
a --> UC5
a --> aUC4

UC1 --> aUC2 : <<Invoke>>
UC1 --> aUC3 : <<Invoke>>
aUC3 --> SystemTrans
UC1 --> SystemBil
@enduml
```
