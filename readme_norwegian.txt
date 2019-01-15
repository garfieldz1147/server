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

Instruksjoner:

    1. Start "pk_dedicated_server.exe" - en loggfil, en konfigurasjonsfil og en lagringsdata-mappe vil bli opprettet.
    2. Lukk "pk_dedicated_server.exe" slik at du kan redigere konfigurasjonsfilen.
    3. Åpne filen "server_config.json" med et skriveprogram for å sette opp serveren.
       ALLE OPPFØRINGER MÅ VÆRE I ASCII ELLER UTF-8!
    4. Følgende innstillinger kan sees eller endres:
        a. basicServerData
            i. name: Navnet som din dedikerte server vil vise.
            ii. ipv4: Den lokale IP-adressen til din dedikerte server. Adressen 0.0.0.0 tillater verts-PC-en å lytte til all lokal nettverkstrafikk. Du vil sannsynligvis ikke trenge å endre dette med mindre du setter opp din server til å fungere med et spesifikt nettverkskort eller grensesnitt.
            iii. port: Porten til den dedikerte serveren. Vi anbefaler ikke å endre dette med mindre dine brannmur/ruter-innstillinger krever det, eller du ønsker å kjøre flere servere på den samme PC-en (i så fall vil hver av dem trenge en separat port).
            iv. saveFolderPath: Dette er mappeplasseringen hvor lagringsdata vil bli skrevet. Dette trenger å bli endret, om du ønsker å kjøre flere serverinstanser på samme PC.
        b. universeSize: (Small/Normal/Large) Størrelsen på universet til den dedikerte serveren.
        c. hideConsoleWindow: (true/false) Dette vil skjule konsoll-vinduet. Hvis dette alternativet er aktivert, kan serveren kun avsluttes ved å terminere den i oppgavebehandleren.
        d. admins/users/guests
            i. Credentials
                • password: Velg passordene som brukes for tilgang til din dedikerte server av forskjellige brukergrupper. Det er tre brukergrupper (admin, brukere og gjester) som kan settes opp med forskjellige passord og rettigheter. Gi spillere kun passordet for brukergruppe-rettighetene som du ønsker at de skal ha og hold admin-passordet ditt privat!
            ii. canLogin: (true/false) Definerer om en bestemt brukergruppe kan logge inn.
            iii. canKickPlayers: (true/false) Definerer om en bestemt brukergruppe kan kaste ut andre spillere fra serveren.
            iv. canModifyWorld: (true/false) Definerer om en bestemt brukergruppe kan utvinne/bygge blokker/gjenstander.
            v. canInteractWithLockables: (true/false) Definerer hvorvidt en bestemt brukergruppe kan kommunisere med kister. Bør i tillegg brukes sammen med canModifyWorld for å hindre utvinning av kister.

    5. Start "pk_dedicated_server.exe" igjen for å starte den dedikerte serveren med de nye innstillingene.
    6. Hvis din dedikerte server er koblet til internett via en ruter (noe som vanligvis er tilfelle), vil du trenge å redigere ruterens innstillinger for portviderekobling (port forwarding) for å sikre at spilldata blir sendt til din verts-PC. Du kan gjøre dette ved å lokalisere din ruters administrasjonsside og videre finne innstillingene for portviderekobling der. Her kan du forsøke å legge til en ny tjeneste (eller kundespesifisert tjeneste) hvis det er mulig. Når du blir spurt om å sette opp en ny regel (rule), vil du bli bedt om å gi den et navn. Du kan velge hvilket navn du måtte ønske, men vi anbefaler "portalknights" for enkelthetens skyld. Porttype skal være "UDP". For alle porter (interne eller eksterne) bruk "16365", med mindre du har endret porten i konfigurasjonsfilen (sjekk i så fall at portene stemmer overens med det du har oppført der). For "output IP" eller "server IP", skriv din lokale nettverksadresse som du kan finne ved å kjøre ipconfig via kommandolinjen. Hvis du blir bedt om noen annen informasjon, la det stå som det er og fortsett. Hvis du har vanskeligheter med denne prosessen, vennligst gå til https://portforward.com/ for hjelp. Vær klar over at med mindre du setter en statisk IP for PC-en som skal være vert for spillet, kan den lokale IP-adressen endre seg (noe som kan ugyldiggjøre reglene for portviderekobling). Referer til din spesifikke ruters dokumentasjon for å fastslå hvordan du skal sette opp en statisk IP-adresse for din PC.

    7. Send din eksterne IP-adresse sammen med et brukergruppe-passord til personene som du ønsker skal få tilgang til serveren. Legg merke til at IP-adressen du brukte til portviderekobling IKKE er din eksterne IP-adresse, det vil da være den lokale IP-adressen. For å finne den eksterne IP-adressen som brukerne trenger for å koble seg til, kan du gå til et nettsted slik som http://whatismyip.host/. Pass på at du sender din IP v4-adresse til brukerne, ikke IP v6 (IP-adressen skal se ut som xxx.xxx.xxx.xxx -- ikke xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx).

    For å sette opp flere servere på den samme PC-en, bruk kommandolinjeargumentene som er beskrevet under for å forberede forskjellige konfigurasjoner for hver av dem og tilpasse konfigurasjonsfilene til hver deretter.
        
    Argumenter:
        a. -config myConfig.json: Konfigurasjonsfilen myConfig.json vil bli brukt for å sette opp serveren.

                      i. Hvis en fil med dette navnet ikke eksisterer, vil en standard konfigurasjonsfil med dette navnet bli opprettet. Merk: Du står fritt til å bruke ditt eget filnavn på dine konfigurasjonsfiler, "myConfig.json" er kun et eksempel.

        b. -log mylogfile.log: Loggfilen vil bli skrevet til den spesifiserte filen.

            Eksempel:
        pk_dedicated_server -config myOwnConfig.json -log testServer.log
        Vil starte en dedikert server som leser sin konfigurasjon fra myOwnConfig.json og vil skrive sin loggdata til testServer.log


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
    
    
Lisens:
    BRUK AV PRIVATE ELLER UAVHENGIGE SERVERE

    Ved å kjøpe og bruke dette programvareproduktet, har du kun anskaffet tillatelseslisensen til å bruke programvareproduktet i samsvar med vilkårene i denne lisensavtalen, som inkluderer tillatelsen til å distribuere den kjørbare filen til produktet på private eller uavhengige servere (heretter "private servere"); imidlertid da gitt, at enhver tredjepart som ønsker tilgang til programvareproduktet på en privat server fremdeles vil måtte kjøpe den fulle versjonen av programvareproduktet, inkludert den kjørbare filen til den fulle versjonen av programvareproduktet som vil gi enhver slik tredjepart deres egen lisens.

    Du samtykker at lisensgiver ikke på noe som helst vis er ansvarlig for hva tredjeparts-brukere gjør med ethvert innhold som befinner seg på enhver privat server som du tillater tilgang til.

    Enhver bruk av en privat server eller ethvert innhold skapt og spredd ved bruk av en slik privat server må holde seg til de følgende, ikke-eksklusive betingelsene:

      • Må være originalt og ikke krenke opphavsretten til noen tredjeparter
      • Kan ikke være lovstridig i noe geografisk myndighetsområde hvor det kan bli gitt tilgang til
      • Ingen bruk av krenkende, pornografisk, nedsettende, diskriminerende materiale
      • Ingen bruk av noe slags misvisende eller villedende materiale
      • Ingen bruk av forulempende eller mobbende materiale, eller som på annet vis kan skade omdømmet til en tredjepart eller det til lisensgiver
      • Kan ikke inkludere reklame eller kreve ekte penger i bytte mot spillpenger
      • Må ikke framstå som om det er en server fra, tilbyr noe materiale fra eller er godkjent av lisensgiver

    For klarhetens skyld, skal du være ansvarlig for alt innhold som du gjør tilgjengelig på den private serveren, uansett om det er skapt av deg og/eller du har tillatt å gjøre det tilgjengelig fra enhver tredjepart som bruker din private server. I så måte, står du ved og garanterer overfor lisensgiver at du er fullstendig berettiget til å kjøre programvareproduktet på din private server, gjør så i samsvar med vilkårene i denne avtalen og  har rettigheten til å innvilge tillatelsene og lisensene som du har samtykket å skaffe ved å bruke de private serverne, til lisensgiver og enhver tredjepart som her ovenfor framsatt.