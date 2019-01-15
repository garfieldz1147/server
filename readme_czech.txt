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

Pokyny:    

    1. Spustte „pk_dedicated_server.exe“ – vytvorí se záznamový soubor, konfiguracní soubor a složka pro uložená data.
    2. Zavrete „pk_dedicated_server.exe“, abyste mohli zacít pracovat s konfiguracním souborem.
    3. Otevrete v textovém editoru soubor „server_config.json“, ve kterém provedete nastavení serveru.
       VEŠKERÉ RETEZCE SE MUSÍ ZADÁVAT VÝHRADNE V KÓDOVÁNÍ ASCII NEBO UTF-8!
    4. Zobrazit a menit lze následující nastavení:
        a. basicServerData
            i. name: Zde se nastavuje jméno vašeho dedikovaného serveru.
            ii. ipv4: IP adresa lokální síte vašeho dedikovaného serveru. Adresa 0.0.0.0 umožní hostujícímu pocítaci prijímat veškerou komunikaci z lokální síte. Toto nastavení pravdepodobne není potreba menit, vyjma prípadu, kdy má server fungovat na konkrétní sítové karte nebo rozhraní.
            iii. port: Port dedikovaného serveru. Tento údaj doporucujeme nemenit, vyjma prípadu, kdy to vyžadují nastavení vašeho firewallu/routeru nebo kdy chcete z jednoho pocítace spravovat více serveru (v tomto prípade je treba pro každý z nich nastavit vlastní port).
            iv. saveFolderPath: Umístení pro ukládání dat. Tento údaj je treba upravit, pokud chcete z jednoho pocítace spravovat více serveru.
        b. universeSize: (Small/Normal/Large) Velikost vesmíru na dedikovaném serveru.
        c. hideConsoleWindow: (true/false) Tímto nastavením se skryje konzolové okno. Pokud je tato volba zapnutá, je server možné zavrít jen ze správce úloh.
        d. admins/users/guests
            i. Credentials
                • password: Nastavte si ochranu dedikovaného serveru heslem pro ruzné skupiny uživatelu. K dispozici jsou tri skupiny uživatelu (správce, uživatelé a hosté), pro které je možné nastavit ruzná oprávnení a ruzná hesla. Hrácum vydávejte zásadne pouze heslo, které odpovídá jejich uživatelské skupine, a správcovská hesla neširte!
            ii. canLogin: (true/false) Urcuje, zda se konkrétní uživatelská skupina muže prihlásit.
            iii. canKickPlayers: (true/false) Urcuje, zda konkrétní uživatelská skupina muže ze serveru vylucovat jiné hráce.
            iv. canModifyWorld: (true/false) Urcuje, zda konkrétní uživatelská skupina muže na serveru težit bloky/rekvizity.
            v. canInteractWithLockables: (true/false) Nastaví, zda určená skupina uživatelů může používat truhly. Současně s parametrem canModifyWorld se dá použít k zabránění hráčům ve vybírání truhel.
        
    5. Opetovným spuštením „pk_dedicated_server.exe“ spustíte dedikovaný server s novým nastavením.
    6. Jestliže je váš server za routerem (obvykle tomu tak je), je treba upravit nastavení presmerování portu (port forwarding) routeru tak, aby se data dostávala do vašeho hostitelského pocítace. Za tím úcelem otevrete stránku správy routeru a vyhledejte na ní nastavení presmerování portu (port forwarding). Zde mužete zkusit pridat novou službu (príp. vlastní službu). Systém se zeptá, jak chcete nové pravidlo/službu pojmenovat. Pro zjednodušení doporucujeme název „portalknights“, ale obecne muže být název libovolný. Typ musí být UDP. U všech portu (interních a externích) použijte „16365“, vyjma prípadu, kdy jste port zmenili v konfiguracním souboru (v takovém prípade se ujistete, že se císla portu shodují). U položek „output IP“ nebo „server IP“ zadejte svoji adresu lokální síte, kterou najdete spuštením príkazu ipconfig prostrednictvím príkazového rádku. Pokud budete vyzváni k zadání jiných údaju, ponechte je nevyplnené a pokracujte. V prípade potíží vyhledejte nápovedu na stránce https://portforward.com/. Nezapomente, že pokud pro hostující pocítac nenastavíte statickou IP adresu, bude se lokální IP adresa menit (a dojde ke zneplatnení údaju zadaných pri nastavení presmerování portu). Návod, jak pro svuj pocítac nastavit statickou IP adresu, najdete v dokumentaci ke svému routeru.

    7. Svoji externí IP adresu spolu s heslem dané uživatelské skupiny rozešlete hrácum, kterým chcete povolit prístup na server. Pozor: IP adresa, kterou jste nastavili v presmerování portu, NENÍ vaší externí IP adresou, ale vaší lokální IP adresou. Svoji externí IP adresu najdete napr. prostrednictvím stránky http://whatismyip.host/. Hrácum rozešlete adresu s protokolem IP v4, nikoliv s protokolem IP v6 (IP adresa by mela mít formát xxx.xxx.xxx.xxx – nikoliv xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx)

    Pri nastavování více serveru na jednom PC použijte v príkazovém rádku argumenty uvedené níže, prostrednictvím kterých mužete pro každý server nastavit jinou konfiguraci vcetne príslušné úpravy konfiguracních souboru.
        
    Argumenty:
        a. -config myConfig.json: Pro nastavení tohoto serveru bude použit konfiguracní soubor s názvem myConfig.json.
                      
                      i. Pokud soubor s tímto názvem neexistuje, bude vytvoren výchozí konfiguracní soubor s tímto názvem. Poznámka: Názvy konfiguracních souboru mohou být libovolné, „myConfig.json“ je jen príklad.

        b. -log mylogfile.log: Záznamový soubor (log) bude uložen do zadaného souboru.
    
            Príklad:
        pk_dedicated_server -config myOwnConfig.json -log testServer.log
        Spustí dedikovaný server, který svoji konfiguraci nacítá ze souboru myOwnConfig.json a záznamy ukládá do souboru testServer.log


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
    
    
Licence:
    POUŽÍVÁNÍ PRIVÁTNÍCH NEBO NEZÁVISLÝCH SERVERU
    
    Zakoupením a používáním softwarového produktu získáváte pouze licenci k jeho používání v souladu s podmínkami tohoto licencního ujednání, která zahrnuje povolení šírit spouštecí soubor produktu na privátních nebo nezávislých serverech (dále „privátních serverech“), ale pod podmínkou, že kterákoliv tretí strana, která bude chtít softwarový produkt na privátním serveru používat, si zakoupí plnou verzi softwarového produktu, vcetne spouštecího souboru této plné verze softwarového produktu, címž daná tretí strana získá vlastní licenci.

    Vyjadrujete souhlas s tím, že poskytovatel licence nenese žádnou odpovednost za to, jak tretí strana s obsahem na privátním serveru, ke kterému poskytujete prístup, naloží.
    
    Jakékoliv používání privátního serveru nebo jakýkoliv obsah vytvorený nebo šírený prostrednictvím privátního serveru musí splnovat následující, nevýlucné požadavky:

      • Musí se jednat o puvodní obsah, který nenarušuje práva na duševní vlastnictví žádné tretí strany
      • Nesmí být v rozporu s legislativou žádné jurisdikce, z jejíhož území se používá
      • Nesmí zahrnovat urážlivý, pornografický, hanlivý materiál nebo materiál diskriminacního charakteru
      • Nesmí zahrnovat zavádející nebo klamný materiál
      • Nesmí používat žádný materiál za úcelem šikany ci zastrašování ci jiného poškození reputace tretí strany nebo poskytovatele licence
      • Nesmí obsahovat reklamní materiál nebo prodávat herní menu za skutecné peníze
      • Nesmí se vydávat za server nebo materiál oficiálne nabízený nebo schválený poskytovatelem licencí

    Pro vysvetlení zduraznujeme, že ponesete odpovednost za veškerý obsah, který na privátním serveru zprístupníte, at už je vytvoren prímo vámi a/nebo jste jeho vytvorení umožnili tretí strane používající váš privátní server. Za tímto úcelem poskytovateli licence zarucujete, že máte plné oprávnení zprístupnovat softwarový produkt na svém privátním serveru, a to v souladu s podmínkami tohoto licencního ujednání, a máte právo udelovat svolení a licence, které jste se zavázali používáním privátních serveru poskytovat poskytovateli licencí nebo kterýmkoliv jiným tretím stranám v souladu s ustanoveními tohoto ujednání.