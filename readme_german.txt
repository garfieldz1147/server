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

Anleitung:    

    1. Starte pk_dedicated_server.exe – es werden dann eine Logdatei, eine Konfigurationsdatei und ein 
       Speicherordner erzeugt.
    2. Schließe pk_dedicated_server.exe, um die Konfigurationsdatei zu erstellen.
    3. Öffne die Dateiserver_config.json mit einem Texteditor, um den Server einzurichten.
       ALLE EINTRÄGE MÜSSEN IN ASCII ODER UTF-8 VORGENOMMEN WERDEN!
    4. Die folgende Einstellung kann angesehen oder geändert werden:
        a. basicServerData
            i.   name: Der Name, den dein dedizierter Server anzeigen wird.
            ii.  ipv4: Die IP-Adresse des lokalen Netzwerks deines dedizierten Servers. Die Adresse 0.0.0.0 
                 ermöglicht es dem Host-Computer, jeglichen lokalen Netzwerk-Traffic nachzuvollziehen. Du 
                 wirst dies wahrscheinlich nicht ändern müssen, bis du deinen Server so einstellst, dass er 
                 mit einer bestimmten Netzwerkkarte oder einem bestimmten Interface arbeitet.
            iii. port: Der Port des dedizierten Servers. Wir empfehlen nicht, dies zu ändern, außer wenn 
                 deine Firewall-/Routereinstellungen das erfordern oder du mehrere Server mit demselben PC 
                 betreiben willst (in diesem Fall braucht jeder seinen eigenen Port).
            iv.  saveFolderPath: Dies ist der Ort, an dem die Speicherdaten geschrieben werden. Er muss 
                 geändert werden, wenn du mehrere Serverinstanzen auf demselben PC laufen lassen willst.
        b. universeSize: (Small/Normal/Large) Die universale Größe für den dedizierten Server.
        c. hideConsoleWindow: (true/false) Dies wird das Konsolenfenster verbergen. Wenn diese Option 
           aktiviert ist, kann der Server nur im Task Manager geschlossen werden.
        d. admins/users/guests
            i.   Credentials
                 • password: Wähle ein Passwort, mit dem verschiedene Benutzergruppen auf deine dedizierten 
                   Server zugreifen können. Es gibt drei Benutzergruppen (Admin, Benutzer und Gäste), die du 
                   mit verschiedenen Passwörtern und Rechten ausstatten kannst. Gib nur denjenigen Spielern 
                   das Passwort für die Rechte der Benutzergruppe, die es auch bekommen sollen und behalte 
                   dein Admin-Passwort für dich!
            ii.  canLogin: (true/false) Bestimmt, ob sich eine bestimmte Benutzergruppe anmelden kann.
            iii. canKickPlayers: (true/false) Bestimmt, ob eine bestimmte Benutzergruppe andere Spieler vom 
                 Server entfernen kann.
            iv.  canModifyWorld: (true/false) Bestimmt, ob eine bestimmte Benutzergruppe Bergbau 
                 betreiben/Blöcke oder Requisiten bauen kann.
            v.   canInteractWithLockables: (true/false) Definiert, ob eine bestimmte Benutzergruppe mit Truhen
		 interagieren kann. Sollte zusammen mit canModifyWorld verwendet werden um auch den Abbau von 
		 Truhen zu verhindern.
        
    5. Starte pk_dedicated_server.exe erneut, um den dedizierten Server mit neuen Einstellungen zu starten.
    6. Wenn sich dein dedizierter Server hinter einem Router befindet (was normalerweise der Fall ist), 
       musst du die Portweiterleitung deines Servers ändern, um sicherzustellen, dass die Spieldaten auch 
       an deinen Hostcomputer gesendet werden. Du kannst dies erledigen, indem du die Adminseite deines 
       Routers und dort die Einstellungen für die Portweiterleitung suchst. Hier kannst du (falls möglich) 
       versuchen, einen neuen Dienst (oder Kundendienst) hinzuzufügen. Falls du darum gebeten wirst, eine 
       neue Regel zu erstellen, solltest du zu einer Namenseingabe aufgefordert werden. Du kannst dort wählen, 
       was immer du willst, aber aus Gründen der Einfachheit empfehlen wir portalknights. Der Typ muss UDP 
       sein. Verwende für alle Ports (interne und externe) 16365, solange du den Port nicht in der 
       Konfigurationsdatei geändert hast (und stelle in diesem Fall sicher, dass die Ports dazu passen, 
       was du dort eingestellt hast). Gib für die Ausgangs-IP oder Server-IP deine lokale Netzwerkadresse 
       ein, die du findest, indem du über die Eingabeaufforderung ipconfig laufen lässt. Solltest du zu 
       weiteren Informationen aufgefordert werden, dann ignoriere dies und fahre fort. Solltest du 
       Schwierigkeiten damit haben, dann besuche bitte https://portforward.com/. Man wird dir dort 
       weiterhelfen. Denk daran, dass sich die IP-Adresse vom lokalen Netzwerk ändern kann, solange du 
       keine feste IP-Adresse für den Computer eingerichtet hast, der das Spiel hostet. Schlage in den 
       Unterlagen für deinen jeweiligen Router nach, um zu erfahren, wie man eine feste IP-Adresse für 
       deinen Computer einrichtet.

    7. Sende deine externe IP-Adresse mit dem Passwort der Benutzergruppe an diejenigen, denen du den 
       Zugriff auf den Server ermöglichen willst. Denk bitte daran, dass die von dir für die Portweiterleitung 
       eingegeben IP-Adresse NICHT deine externe IP-Adresse sein wird, sondern die lokale Netzwerkadresse. 
       Um die externe IP-Adresse zu finden, die Benutzer zum Beitritt benötigen, musst du Seiten wie 
       http://whatismyip.host/ besuchen. Stelle sicher, dass du Benutzern deine Adresse mit IP v4 und nicht 
       mit IP v6 sendest 
       (die IP-Adresse sollte folgendermaßen aussehen xxx.xxx.xxx.xxx, und nicht so: xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx).

    Damit du mehrere Server auf demselben PC einrichten kannst, musst du die Befehle unten in der 
    Eingabeaufforderung eingeben, um verschiedene Konfigurationen für jeden vorzubereiten und die 
    Konfigurationsdateien für jeden entsprechend anpassen zu können.
        
    Argumente:
        a. -config myConfig.json: Die Konfigurationsdatei myConfig.json wird zum Einrichten des 
                                  Servers verwendet.
                      
                      i. Sollte keine Datei mit diesem Namen existieren, wird eine Standardkonfigurationsdatei 
                         mit diesem Namen erstellt. Hinweis: Du kannst deinen Konfigurationsdateien gerne einen 
                         eigenen Namen geben. myConfig.json ist einfach nur ein Beispiel.

        b. -log mylogfile.log: Die Logdatei wird in die jeweilige Datei geschrieben.
    
            Beispiel:
        pk_dedicated_server -config myOwnConfig.json -log testServer.log
        Sie wird einen dedizierten Server starten, der seine Konfiguration von myOwnConfig.json bezieht 
        und seine Protokollausgabe auf testServer.log schreiben wird.


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
    
    
Lizenz:
    VERWENDUNG FÜR PRIVATE ODER UNABHÄNGIGE SERVER
    
    Durch den Kauf und die Verwendung dieses Softwareprodukts erhältst du nur eine Lizenz mit der Erlaubnis 
    zur Verwendung des Softwareprodukts in Übereinstimmung mit den Bedingungen dieser Lizenzvereinbarung. Sie 
    enthält die Erlaubnis zur Verteilung der Anwendungsdatei des Produkts auf private oder unabhängige Server 
    (in Folge „Private Server“). Trotz dieser Voraussetzung muss jeder Dritte, der Zugriff auf das 
    Softwareprodukt auf dem Privatserver haben möchte, die Vollversion des Softwareprodukts kaufen, inklusive 
    der Programmdatei der Vollversion des Softwareprodukts, welche einen solchen Dritten mit seiner eigenen 
    Lizenz versorgt.

    Du bist einverstanden, dass der Lizenzgeber keinesfalls für das verantwortlich ist, was Dritte mit 
    beliebigen Inhalten auf jeglichen Privatservern unternehmen, zu denen du ihnen Zugriff erteilt hast.
    
    Jegliche Verwendung eines Privatservers oder beliebiger Inhalte, die in Verwendung solch eines Privatservers 
    erstellt oder verbreitet wurden, unterliegt den folgenden, nicht-exklusiven Anforderungen:

      • Sie muss original sein und darf nicht die Rechte am geistigen Eigentum Dritter verletzen.
      • Sie darf nicht die Gesetze einer Gerichtsbarkeit verletzen, von der auf sie zugegriffen werden kann.
      • Es dürfen keine beleidigenden, pornographischen, abwertenden oder diskriminierenden Materialien 
        verwendet werden.
      • Es dürfen keine missverständlichen oder irreführenden Materialien verwendet werden
      • Es dürfen keine missbräuchlichen oder mobbenden Materialien verwendet werden, die dem Ruf eines Dritten 
        oder des Lizenzgebers schaden.
      • Es darf keine Werbung betrieben oder echtes Geld für Spielwährungen verlangt werden.
      • Es darf nicht vorgegeben werden, ein Server oder Material zu sein, das vom Lizenzgeber angeboten oder 
        genehmigt ist.

    Der Übersicht halber: Du bist für jegliche Inhalte verantwortlich, die du auf dem Privatserver zur Verfügung 
    stellst, egal, ob sie von dir erstellt wurden und/oder du Dritten die Erlaubnis erteilt hast, zur 
    Veröffentlichung deinen Privatserver zu verwenden.  Zu diesem Zweck gewährleistest du dem Lizenzgeber, 
    dass du berechtigt bist, das Softwareprodukt auf deinem Privatserver zu hosten und dies in Übereinstimmung 
    mit den Bedingungen dieser Vereinbarung vornimmst. Du verpflichtest dich zur Einhaltung der Bestimmungen 
    dieser Vereinbarung und hast das Recht, auch künftig wie hier festgelegt Genehmigungen und Lizenzen (welche 
    du zu erteilen bei der Verwendung der Privatserver zugestimmt hattest) dem Lizenzgeber und beliebigen 
    Dritten zu erteilen.