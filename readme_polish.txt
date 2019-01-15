,-.----.                                                              ,--.                                                                
\    /  \                         ___                 ,--,        ,--/  /|                                 ,---,       ___                
|   :    \                      ,--.'|_             ,--.'|     ,---,': / '              ,--,             ,--.' |     ,--.'|_              
|   |  .\ :   ,---.    __  ,-.  |  | :,'            |  | :     :   : '/ /       ,---, ,--.'|             |  |  :     |  | :,'             
.   :  |: |  '   ,'\ ,' ,'/ /|  :  : ' :            :  : '     |   '   ,    ,-+-. /  ||  |,     ,----._,.:  :  :     :  : ' :  .--.--.    
|   |   \ : /   /   |'  | |' |.;__,'  /    ,--.--.  |  ' |     '   |  /    ,--.'|'   |`--'_    /   /  ' /:  |  |,--.;__,'  /  /  /    '   
|   : .   /.   ; ,. :|  |   ,'|  |   |    /       \ '  | |     |   ;  ;   |   |  ,"' |,' ,'|  |   :     ||  :  '   |  |   |  |  :  /`./   
;   | |`-' '   | |: :'  :  /  :__,'| :   .--.  .-. ||  | :     :   '   \  |   | /  | |'  | |  |   | .\  .|  |   /' :__,'| :  |  :  ;_     
|   | ;    '   | .; :|  | '     '  : |__  \__\/: . .'  : |__   |   |    ' |   | |  | ||  | :  .   ; ';  |'  :  | | | '  : |__ \  \    `.  
:   ' |    |   :    |;  : |     |  | '.'| ," .--.; ||  | '.'|  '   : |.  \|   | |  |/ '  : |__'   .   . ||  |  ' | : |  | '.'| `----.   \ 
:   : :     \   \  / |  , ;     ;  :    ;/  /  ,.  |;  :    ;  |   | '_\.'|   | |--'  |  | '.'|`---`-'| ||  :  :_:,' ;  :    ;/  /`--'  / 
|   | :      `----'   ---'      |  ,   /;  :   .'   \  ,   /   '   : |    |   |/      ;  :    ;.'__/\_: ||  | ,'     |  ,   /'--'.     /  
`---'.|                          ---`-' |  ,     .-./---`-'    ;   |,'    '---'       |  ,   / |   :    :`--''        ---`-'   `--'---'   
  `---`                                  `--`---'              '---'                   ---`-'   \   \  /                                  
                                                                                                 `--`-'                                   
----------------------------------------------------------------------------------------------------------------------------------------


pk_dedicated_server
-----------------------

Instrukcje:    

    1. Uruchom "pk_dedicated_server.exe" - utworzony zostanie log, plik konfiguracyjny oraz folder z zapisanymi danymi.
    2. Zamknij "pk_dedicated_server.exe", aby skonfigurować plik konfiguracyjny.
    3. Otwórz plik "server_config.json" edytorem tekstu, aby skonfigurować serwer.
       NALEŻY UŻYWAĆ KODU ASCII LUB UTF-8!
    4. Można wyświetlić lub zmienić poniższe ustawienia:
        a. basicServerData
            i. name: Wyświetlana nazwa serwera dedykowanego.
            ii. ipv4: Lokalny adres IP serwera dedykowanego. Adres 0.0.0.0 pozwala komputerowi hostującemu monitorować lokalny przesył danych. Zmiana tego ustawienie prawdopodobnie nie będzie konieczna, chyba że konfigurowany jest serwer na konkretnej karcie sieciowej lub interfejsie.
            iii. port: Port serwera dedykowanego. Odradzamy zmianę tego ustawienia, chyba że wymagają tego ustawienia zapory sieciowej/routera lub chcesz uruchomić kilka serwerów na tym samym komputerze (w takim wypadku każdy będzie potrzebował osobnego portu).
            iv. saveFolderPath: To miejsce, w którym będą zapisywane dane. Należy je zmienić, jeśli chcesz obsługiwać kilka serwerów na jednym komputerze.
        b. universeSize: (Small/Normal/Large) Rozmiar światu na serwerze dedykowanym.
        c. hideConsoleWindow: (true/false) Ta opcja ukrywa okienko konsoli. Jeśli ta opcja jest włączona, serwer może zostać zamknięty tylko poprzez zakończenie procesu w menedżerze zadań.
        d. admins/users/guests
            i. Credentials
                • password: Wybierz hasła używane do uzyskania dostępu do serwerów dedykowanych przez różne grupy użytkowników. Istnieją trzy grupy użytkowników (administrator, użytkownicy i goście), którym można przypisać różne hasła i prawa. Dawaj graczom hasła jedynie do tych grup, do których powinni należeć, i zachowaj hasło administratora dla siebie!
            ii. canLogin: (true/false) Określa, czy konkretna grupa użytkowników może się zalogować.
            iii. canKickPlayers: (true/false) Określa, czy konkretna grupa użytkowników może wyrzucać innych graczy z serwera.
            iv. canModifyWorld: (true/false) Określa, czy konkretna grupa użytkowników może zbierać/budować bloki/narzędzia.
            v. canInteractWithLockables: (true/false) Określa, czy wybrana grupa użytkowników może wchodzić w interakcję ze skrzyniami. Należy używać razem z canModifyWorld w celu zapobieżenia wydobywania skrzyń.
        
    5. Uruchom "pk_dedicated_server.exe" ponownie, by uruchomić serwer dedykowany z nowymi ustawieniami.
    6. Jeśli serwer dedykowany wykorzystuje router (a zwykle tak jest), musisz edytować ustawienia przekierowania portów swojego routera, aby dane gry były przesyłane do twojego komputera hostującego. Możesz zrobić to, otwierając stronę administratora routera, a następnie ustawienia przekierowania portów. Z tego miejsca możesz spróbować dodać nową usługę (lub obsługę klienta), jeśli jest to możliwe. W trakcie tworzenia nowej zasady powinno ukazać się pytanie o to, jak ją nazwać. Możesz wybrać dowolną nazwę, ale polecamy "portalknights" dla jasności. Należy użyć typu "UDP". Wszystkie porty (wewnętrzne i zewnętrzne) ustaw jako "16365", chyba że zmieniono port w pliku konfiguracyjnym (w takim wypadku upewnij się, czy porty pasują do tych, które podano w pliku). Jako "IP wychodzące" lub "IP serwera" wprowadź adres lokalnej sieci, który możesz znaleźć, uruchamiając ipconfig poprzez wiersz poleceń. Jeśli pojawi się prośba o inne informacje, zignoruj ją i kontynuuj. W przypadku problemów z tym procesem odwiedźhttps://portforward.com/, aby uzyskać pomoc. Pamiętaj, że jeśli nie ustawisz statycznego IP dla komputera, który hostuje grę, adres IP sieci lokalnej może się zmienić (co może unieważnić zasady przekierowania portów). Zapoznaj się z dokumentacją swojego routera, aby określić, jak ustawić statyczne IP dla swojego komputera.

    7. Wyślij zewnętrzny adres IP wraz z hasłem grupy użytkowników osobom, które powinny uzyskać dostęp do serwera. Pamiętaj, że adres IP wprowadzony do przekierowania portów NIE będzie twoim zewnętrznym adresem IP, ale lokalnym adresem IP. Aby odnaleźć zewnętrzne adresy IP potrzebne użytkownikom w celu dołączenia, należy odwiedzić witrynę taką jak http://whatismyip.host/. Pamiętaj, by wysłać użytkownikom adres IP v4 , nie IP v6 (adres powinien mieć format: xxx.xxx.xxx.xxx -- nie: xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx)

    Aby uruchomić kilka serwerów na tym samym komputerze, użyj poniższych argumentów wiersza poleceń w celu przygotowania różnych konfiguracji i dostosowania plików konfiguracyjnych dla każdego z nich.
        
    Argumenty:
        a. -config myConfig.json: Plik konfiguracyjny myConfig.json zostanie użyty do ustawienia serwera.
                      
                      i. Jeśli plik o takiej nazwie nie istnieje, zostanie on utworzony automatycznie. Uwaga: Możesz tworzyć własne nazwy plików konfiguracyjnych. "myConfig.json" to jedynie przykład.

        b. -log mylogfile.log: Log zostanie zapisany w konkretnym pliku.
    
            Na przykład:
        pk_dedicated_server -config myOwnConfig.json -log testServer.log
        Uruchomi serwer dedykowany odczytujący konfigurację z pliku myOwnConfig.json i zapisze jego log w pliku testServer.log


Config File Format:

    {
        "basicServerData": {
            "name": "Servername",
            "ipv4": "0.0.0.0",
            "port": 16365,
            "saveFolderPath": "./savedata"
        },
        "universeSize": "Normal",
        "hideConsoleWindow": false,
        "admins": {
            "credentials": {
                "password": "admin_password_please_change"
            },
            "canLogin": true,
            "canKickPlayers": true,
            "canModifyWorld": true,
            "canInteractWithLockables": true
        },
        "users": {
            "credentials": {
                "password": ""
            },
            "canLogin": true,
            "canKickPlayers": false,
            "canModifyWorld": true,
            "canInteractWithLockables": true
        },
        "guests": {
            "credentials": {
                "password": ""
            },
            "canLogin": false,
            "canKickPlayers": false,
            "canModifyWorld": false,
            "canInteractWithLockables": false
        }
    }
    
    
Licencja:
    UŻYWANIE PRYWATNYCH LUB NIEZALEŻNYCH SERWERÓW
    
    Kupując i używając Oprogramowanie, otrzymujesz licencję na używanie go jedynie zgodnie z zasadami niniejszej Umowy Licencyjnej, która zawiera pozwolenie na dystrybucję pliku wykonywalnego oprogramowania poprzez prywatne lub niezależne serwery (dalej "Serwery Prywatne"). Jednak jakakolwiek strona trzecia pragnąca uzyskać dostęp do Oprogramowania na Serwerze Prywatnym musi zakupić pełną wersję Oprogramowania, w tym plik wykonywalny pełnej wersji Oprogramowania, z którym owa strona trzecia uzyska własną licencję.

    Akceptujesz postanowienie, że Licencjodawca nie jest w jakikolwiek sposób odpowiedzialny za to, w jaki sposób strony trzecie wykorzystują materiały znalezione na Serwerach Prywatnych, do których przyznano dostęp.
    
    Wykorzystanie Serwera Prywatnego lub jakichkolwiek materiałów stworzonych lub udostępnionych przy użyciu Serwera Prywatnego musi być zgodne z poniższymi, nie wykluczającymi się nawzajem wymogami:

      • Materiały muszą być oryginalne i nie naruszać praw własności intelektualnej stron trzecich
      • Materiały nie mogą naruszać praw miejsc, w których można uzyskać do nich dostęp
      • Zakaz wykorzystywania obraźliwych, pornograficznych, dyskryminujących materiałów
      • Zakaz wykorzystywania fałszywych lub wprowadzających w błąd materiałów
      • Zakaz używania materiałów, które w jakikolwiek sposób szkodzą reputacji strony trzeciej lub Licencjodawcy
      • Zakaz publikowania reklam oraz pobierania opłat pieniężnych za walutę używaną w grze
      • Materiały i serwery nie mogą być przedstawiane jako materiały lub serwery oferowane lub zatwierdzone przez Licencjodawcę

    Dla jasności: ponosisz odpowiedzialność za wszelkie materiały, które udostępniasz na Serwerze Prywatnym - bez względu na to, czy jesteś ich twórcą, czy pozwalasz na ich udostępnienie stronie trzeciej.  W związku z tym dajesz Licencjodawcy zapewnienie, że posiadasz uprawnienia do hostowania Oprogramowania na swoim Serwerze Prywatnym, robisz to zgodnie z niniejszą Umową i posiadasz prawo do udzielania pozwoleń i licencji, które zgodziłeś się zapewnić przy wykorzystywaniu Serwera Prywatnego Licencjodawcy i wszelkim omawianym powyżej stronom trzecim.