<details>

 ```plantuml
@startuml
actor Recenzent

usecase ShowGameList as "Wyświetlenie listy gier przez recenzenta"
usecase SendMessage as "Przesłanie komunikatu do twórcy"
usecase Review as "Recenzja gry"

Recenzent --> ShowGameList
ShowGameList --> SendMessage : <<invoke>>
ShowGameList --> Review  : <<invoke>>
@enduml

```
</details>

![diagram](https://www.plantuml.com/plantuml/png/POuzJWCn44PxdsAKFXT0qIeT3KWe5DGZvzDYrZ_8CuwrMt8DZi4HKEw52GehAwtzlZTlByfPI_26hQPC1rZ41L6DAGBB0df-JVMU0nwSAB7GvcK-VrO7zOWEvDlpJAD3flUyOA5yLV1cTI0U7o728owAfqRA-OD_1LCA9Rg9jT0naTRlhspdTNh0oQ5ULdznRqnZRe3vRwNjTkWoJTVSVhk0EzhjN3ob2SDmGrxlzTI-pKlmFm00)
