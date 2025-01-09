![Diagram](https://img.plantuml.biz/plantuml/png/PP4zRiCm38LtduBmqYL1aIPTEXGfEdOfK0IT5PjEvH_H42aOyas2NgLZSgzAjj84w220ullqI3njMPGLrxLPYvM045Xz-18ejSL2D9bC5K8MTkSVBmqDHZUW65nsTpyB-OTdmGx4AiEgANnjV1uHbd_CNhSeD2HzdwppbxBJHdDmY5UUM3SnAiiSOw4O8Nzp_MmmARlNrLNwzEVlGQEqG1LQEHqJyd2Bx3NQ4UhJSVHDqjTN_Pr6pusgmQgUx6N6vcOycKeVd7KrbCHXHczmtiSleBVKKL7Z0aAQllBf-MDO7vRBvscLS5AzWYVGfcXTYHmoYeqeXC0kz7fgptpCARKtVrLmtg8fux_z0W00)
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
UC2 --> UC1 : includes
u --> UC3
'/UC2 --> sb
a --> UC4
a --> UC5

@enduml
```
