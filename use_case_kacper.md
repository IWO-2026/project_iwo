```mermaid
flowchart LR
    %% Aktorzy
    gracz["Gracz"]
    org["Organizator wydarzeń"]
    admin["Administrator systemu"]

    %% Pakiet / System
    subgraph Zarzadzanie_wydarzeniami ["Zarządzanie wydarzeniami LARP"]
        direction TB
        UC1(["Wyszukiwanie wydarzeń"])
        UC2(["Zapisanie się na wydarzenie"])
        UC3(["Opłacenie udziału"])
        UC4(["Tworzenie wydarzenia LARP"])
        UC5(["Wstępna wycena wydarzenia"])
        UC6(["Uruchomienie wydarzenia"])
        UC7(["Odwołanie wydarzenia"])
        UC8(["Zatwierdzenie ostatecznej wyceny"])
    end

    %% Zależności i powiązania wewnątrz systemu
    UC2 -. "<<extend>>" .-> UC3
    UC4 -. "<<include>>" .-> UC5

    %% Powiązania Aktorów z przypadkami użycia
    gracz --> UC1
    gracz --> UC2

    org --> UC4
    org --> UC6
    org --> UC7

    admin --> UC8
