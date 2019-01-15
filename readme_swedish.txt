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

Anvisningar:    

    1. Starta "pk_dedicated_server.exe" - en loggfil, en konfigureringsfil och en katalog för sparade data kommer att skapas.
    2. Stäng "pk_dedicated_server.exe" för att ställa in konfigureringsfilen.
    3. Öppna "server_config.json"-filen med ett textredigeringsprogram för att konfigurera servern.
       ALL INMATAD TEXT MÅSTE VARA I FORMATET ASCII ELLER UTF-8!
    4. Följande inställningar kan visas eller ändras:
        a. basicServerData
            i. name: Namnet som din dedikerade server kommer att visa.
            ii. ipv4: Den lokala nätverks-IP-adressen för din dedikerade server. Adressen 0.0.0.0 gör det möjligt för värddatorn att lyssna på all lokal nätverkstrafik. Du kommer förmodligen inte att behöva ändra detta såvida du inte konfigurerar din server för att arbeta på ett specifikt nätverkskort eller gränssnitt.
            iii. port: Porten för den dedikerade servern. Vi rekommenderar att man inte ändrar detta såvida inte inställningarna för din brandvägg/router kräver detta, eller om du vill köra flera servrar på samma dator (i vilket fall vardera behöver en separat port).
            iv. saveFolderPath: Detta är platsen där informationen kommer att sparas. Detta måste ändras om du vill köra flera serverinstanser på samma dator.
        b. universeSize: (Small/Normal/Large) Den universella storleken för den dedikerade servern.
        c. hideConsoleWindow: (true/false) Detta kommer att dölja konsolfönstret. Om detta alternativ är aktiverat, kan servern endast stängas genom att avsluta den i aktivitetshanteraren.
        d. admins/users/guests
            i. Credentials
                • password: Välj lösenord för åtkomst till din dedikerade server för olika användargrupper. Det finns tre användargrupper (admin, användare och gäster) som kan konfigureras med olika lösenord och behörigheter. Ge endast spelarna lösenordet för användargruppbehörigheten du vill att de ska ha och håll ditt adminlösenord hemligt!
            ii. canLogin: (true/false) Definierar huruvida en bestämd användargrupp kan logga in.
            iii. canKickPlayers: (true/false) Definierar huruvida en bestämd användargrupp kan sparka ut andra spelare från servern.
            iv. canModifyWorld: (true/false) Definierar huruvida en bestämd användargrupp kan utvinna/bygga block/föremål.
            v. canInteractWithLockables: (true/false) Definierar huruvida en särskild användargrupp kan samverka med kistorna. Bör användas tillsammans med canModifyWorld för att även förhindra mining av kistor.
        
    5. Starta "pk_dedicated_server.exe" på nytt för att starta den dedikerade servern med de nya inställningarna.
    6. Om din dedikerade server är bakom en router (vilket normalt är fallet), måste du ändra din routers port forwarding-inställningar för att säkerställa att speldata skickas till din värddator. Du kan göra detta genom att leta upp din routers adminsida och hitta inställningarna för port forwarding där. Här kan du försöka att lägga till en ny tjänst (eller kundtjänst), om det är möjligt. När du uppmanas att konfigurera den nya regeln, bör du även uppmanas att döpa den. Du kan välja vilket namn du vill, men vi rekommenderar "portalknights" för enkelhetens skull. Typ måste vara "UDP". Använd "16365" för alla portar (interna och externa), såvida du inte har ändrat porten i konfigureringsfilen (i detta fall måste du kontrollera att portarna överensstämmer med vad du har konfigurerat där). För "output IP" eller "server IP" anger du din lokala nätverksadress som du hittar genom att köra ipconfig via kommandotolken. Om du ombeds att uppge annan information, låt det vara och fortsätt. Om du upplever svårigheter under denna process, var vänlig besök https://portforward.com/ för hjälp. Observera att om du har konfigurerat en statisk IP-adress för datorn som är värd för spelet, kan den lokala nätverks-IP-adressen ändras (vilket kan göra reglerna för port forwarding ogiltiga). Rådfråga dokumentationen för din specifika router för att fastställa hur du konfigurerar en statisk IP-adress för din dator.

    7. Skicka din externa IP-adress tillsammans med ett användargrupplösenord till de personer du vill ska ha åtkomst till servern. Observera att IP-adressen du angav för port forwarding INTE kommer att vara din externa IP-adress, det kommer att vara den lokala IP-adressen. För att hitta den externa IP-adressen som behövs för att användare ska kunna ansluta sig, måste du besöka en sida som exempelvis  http://whatismyip.host/. Se till att du skickar användarna din IP v4 -adress, inte IP v6 (IP-adressen bör se ut som xxx.xxx.xxx.xxx -- inte xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx)

    För att konfigurera flera servrar på samma dator, använd de kommandotolkargument som anges nedan för att förbereda olika konfigureringar för varje server och anpassa konfigureringsfilerna för respektive server på lämpligt sätt.
        
    Argument:
        a. -config myConfig.json: myConfig.json-konfigureringsfilen kommer att användas för att konfigurera servern.
                      
                      i. Om en fil med det namnet inte existerar, kommer en konfigureringsfil med det namnet att skapa automatiskt. Observera: Du kan själv välja namn för dina konfigureringsfiler, "myConfig.json" är bara ett exempel.

        b. -log mylogfile.log: Loggfilen kommer att sparas i den specificerade filen.
    
            Exempel:
        pk_dedicated_server -config myOwnConfig.json -log testServer.log
        Kommer att starta en dedikerad server som läser sin konfigurering från myOwnConfig.json och som kommer att skriva sina loggfiler till testServer.log


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
    
    
Licens:
    ANVÄNDNING AV PRIVATA ELLER OBEROENDE SERVRAR
    
    Genom att köpa och använda programvaruprodukten, har du endast licenstillstånd att använda programvaruprodukten i enlighet med villkoren i licensavtalet, som inkluderar tillstånd att vidarebefordra produktens körbara fil på privata eller oberoende servrar (hädanefter "Privata servrar"); dock under förutsättning att alla utomstående parter som önskar ha åtkomst till programvaruprodukten på den privata servern, ändå måste köpa den fullständiga versionen av programvaruprodukten, inklusive den körbara filen för den fullständiga versionen av programvaruprodukten som kommer att förse en sådan utomstående part med en egen licens.

    Du samtycker till att licensgivaren inte på något sätt är ansvarig för vad tredje part-användare gör med något innehåll som är tillgängligt på privata servrar till vilka du tillåter åtkomst.
    
    All användning av en privat server eller allt innehåll som skapas eller sprids med hjälp av en sådan privat server måste uppfylla följande krav, utan undantag:

      • Måste vara ursprungligt och inte kränka några immateriella rättigheter som tillhör någon utomstående part
      • Får inte bryta mot någon lagstiftning i något land från vilket den kan nås
      • Ingen användning av stötande, pornografiskt, nedsättande, diskriminerande material
      • Ingen användning av missledande eller bedrägligt material
      • Ingen användning av kränkande eller mobbande material, eller material som på annat sätt skadar ryktet för en tredje part eller licensgivaren
      • Får inte innehålla reklam eller ta betalt i riktiga pengar för spelvaluta
      • Får inte utge sig för att vara en server eller något material som erbjuds eller har godkänts av licensgivaren

    För att tydliggöra: du förblir ansvarig för allt innehåll som du tillgängliggör på den privata servern, oavsett om det har skapats av dig eller annat innehåll som du tillåter åtkomst till för någon tredje part som använder din privata server.  Du intygar och garanterar licensgivaren att du har fullständig tillåtelse att lagra programvaruprodukten på din privata server och att du gör detta i överensstämmelse med villkoren i detta avtal och att du har rätt att ge behörighet och licenser som du har samtyckt till att tillhandahålla genom användning av privata servrar till licensgivaren och någon tredje part, i enlighet med vad som anges ovan.