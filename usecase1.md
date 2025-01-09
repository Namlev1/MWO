![RP6_JiCm4CPtFyKfUmUQJgYA2aniI925xPgOOFoliYz4wOXKyH0y1YiRoNkHf6wJL5YovBllT-VpvuqdT5HgnHH_8I0BJXIl1BbmF2DX3MEOaNMGjZyrILiP8G4zfFjJ5FJeiVR4DP13ur5czPkfevuyvf_wz0Mw5OgJhQROhL0dw2RNmWZVzUl20Pbb62izpz1pY9vHbhjZjt80qxkh](https://github.com/user-attachments/assets/c1664cc7-fa67-4ee5-a3dc-9780c5410b85)

```PlantUML
@startuml
left to right direction

actor Użytkownik as Uzytkownik
actor "System transakcyjny" as SystemTrans
actor "System biletowy" as SystemBil
actor "Administrator" as Administrator

usecase "Zakup biletu" as UC1
usecase "Płatność gotówką" as UC2
usecase "Płatność kartą lub telefonem" as UC3
usecase "Zaktualizowanie oprogramowania biletomatu" as UC4


Uzytkownik --> UC1
UC1 --> UC2 : <<Invoke>>
UC1 --> UC3 : <<Invoke>>
UC3 --> SystemTrans
Administrator --> UC4
UC1 --> SystemBil

@enduml
```
