# Słownik

| Termin     | Definicja                                                                                |
| ---------- | ---------------------------------------------------------------------------------------- |
| Gra        | Definicja zasad interakcji między uczestnikami; ma mapę, postacie, akcie itd.            |
| Wydarzenie | Pojedyncza instancja gry.                                                                |
| Postać     | Spójna rola w grze, ma pewne akcje, atrybuty, przedmioty ...                             |
| Przedmiot  | Obiekt nieożywiony, który może posiadać gracz. Posiadanie przedmiotu rodzi różne skutki. |
| Mapa       | Ma pomieszczenia, przeszkody, przejścia.                                                 |
| Akcja      | Działanie systemu pod wpływem interakcji postaci albo czasu.                             |
# Diagram
```plantuml
@startuml Diagram przypadków użycia
left to right direction
actor gracz as "Gracz"
actor admin as "Administrator"
actor org as "Organizator"
actor tworca as "Twórca gier"
actor mistrz as "Mistrz wydarzenia"
actor recenzent as "Recenzent gier"
actor org_zew as "Organizator zewnętrzny"

usecase uc_dodaj_gre as "Zdefiniowanie gry"
usecase uc_zdefiniuj_postac as "Dodanie postaci/przedmiotu"
usecase uc_mapa as "Zdefiniowanie mapy gry"
usecase uc_akcja as "Zdefiniowanie akcji"
usecase uc_pomieszczenie as "Zdefiniowanie pomieszczenia"
usecase uc_lista_tworzonych_gier as "Wyswietlenie listy swoich gier"
usecase uc_przeslij_kom_rec as "Przesłanie komunikatu do recenzenta"
usecase uc_lista_gier as "Wyświetlenie listy gier"

tworca --> uc_dodaj_gre
uc_dodaj_gre ..> uc_zdefiniuj_postac : "<<invoke>>"
uc_dodaj_gre ..> uc_mapa : "<<invoke>>"
uc_dodaj_gre ..> uc_akcja : "<<invoke>>"
uc_mapa ..> uc_pomieszczenie : "<<invoke>>"
tworca --> uc_lista_tworzonych_gier
uc_lista_tworzonych_gier ..> uc_dodaj_gre : "<<invoke>>"
uc_dodaj_gre ..> uc_przeslij_kom_rec : "<<invoke>>"

usecase uc_lista_gier_rec as "Wyświetlenie listy gier recenzenta"
usecase uc_przeslij_komunikat_do_tw as "Przesłanie komunikatu do twórcy"
recenzent --> uc_lista_gier_rec
uc_lista_gier_rec ..> uc_przeslij_komunikat_do_tw : "<<invoke>>"
uc_lista_gier_rec --|> uc_lista_gier

usecase uc_kalendarz_wydarzen as "Wyświetlenie kalendarza wydarzeń"
usecase uc_lista_gier_org as "Wyświetlenie listy gier przez orgranizatora"
usecase uc_dodanie_wydarzenia_do_kal as "Dodanie wydarzenia do kalendarza"
usecase uc_zapros_graczy as "Zaproszenie graczy"
usecase uc_udostepnij as "Udostępnienie gry dla innych graczy"

uc_lista_gier_org --|> uc_lista_gier 

org --> uc_lista_gier_org
org --> uc_kalendarz_wydarzen
uc_lista_gier_org ..> uc_dodanie_wydarzenia_do_kal : "<<invoke>>"
uc_kalendarz_wydarzen ..> uc_dodanie_wydarzenia_do_kal : "<<invoke>>"
uc_dodanie_wydarzenia_do_kal ..> uc_zapros_graczy : "<<invoke>>"
uc_dodanie_wydarzenia_do_kal ..> uc_udostepnij : "<<invoke>>"

usecase uc_wys_kal_org_zew as "Wyświetlenie kalendarza przez orgranizatora zewnętrznego"

org_zew --> uc_wys_kal_org_zew

usecase uc_lista_Wydarzen_gracz as "Wyświetlanie kalendarza wydarzeń przez gracza"

gracz --> uc_lista_Wydarzen_gracz

usecase uc_uruchom_wyd as "Uruchomienie wydarzenia"
usecase uc_zak_wyd as "Zakończenie wydarzenia"


mistrz --> uc_uruchom_wyd
mistrz --> uc_zak_wyd
@enduml
```



