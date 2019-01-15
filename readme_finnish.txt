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

Ohjeet:

    1. Käynnistä ”pk_dedicated_server.exe”. Lokitiedosto, määritystiedosto ja tallennuskansio luodaan.
    2. Sulje ”pk_dedicated_server.exe”, jotta voit asettaa määritystiedoston.
    3. Avaa tiedosto ”server_config.json” tekstieditorilla palvelimen määrittämiseksi.
       KAIKKIEN MERKINTÖJEN ON OLTAVA ASCII- TAI UTF-8-MUODOSSA!
    4. Seuraavia asetuksia voi katsoa tai muuttaa:
        a. basicServerData
            i. name: Nimi, jonka dedikoitu palvelin näyttää.
            ii. ipv4: Dedikoidun palvelimen paikallisverkon IP-osoite. Osoitteella 0.0.0.0 isäntätietokone voi kuunnella kaikkea verkkoliikennettä. Tätä ei luultavasti tarvitse muuttaa, ellet ole asettamassa palvelinta toimimaan tietyn verkkokortin tai -rajapinnan kanssa.
            iii. port: Dedikoidun palvelimen portti. Suosittelemme, että tätä ei muuteta, ellei palomuurin/reitittimen asetukset vaadi sitä tai ellet halua pyörittää useita palvelimia samalla tietokoneella (jolloin jokainen vaatii erillisen portin).
            iv. saveFolderPath: Tallennustiedostot tallennetaan tähän sijaintiin. Tätä on muutettava, jos haluat käyttää useita palvelimia samalla tietokoneella.
        b. universeSize: (Small/Normal/Large) Dedikoidun palvelimen universumin koko.
        c. hideConsoleWindow: (true/false) Tämä piilottaa konsoli-ikkunan. Jos tämä asetus on käytössä, palvelin voidaan sulkea vain lopettamalla se Tehtävienhallinnasta.
        d. admins/users/guests
            i. Credentials
                • password: Valitse salasanat dedikoidun palvelimen käyttöön eri käyttäjäryhmissä. Käyttäjäryhmiä on kolme (valvojat, käyttäjät ja vieraat) ja niille voidaan asettaa eri salasanoja ja oikeuksia. Anna pelaajille salasana vain käyttäjäryhmiin, joiden oikeudet haluat heillä olevan, ja pidä valvojan salasana yksityisenä!
            ii. canLogin: (true/false) Määrittää voiko tietty käyttäjäryhmä voi kirjautua sisään.
            iii. canKickPlayers: (true/false) Määrittää voiko tietty käyttäjäryhmä poistaa toisia pelaajia palvelimelta.
            iv. canModifyWorld: (true/false) Määrittää käyttääkö tietty käyttäjäryhmä kaivaa/rakentaa palikoita/esineitä.
            v. canInteractWithLockables: (true/false) Määrittää, voiko tietty käyttäjäryhmä käyttää arkkuja. Tulisi käyttää yhdessä komennon canModifyWorld kanssa, jotta arkkuja ei voida myöskään kaivaa.
        
    5. Käynnistä ”pk_dedicated_server.exe” uudelleen, jotta dedikoitu palvelin käynnistyy uusilla asetuksilla.
    6. Jos dedikoitu palvelin on reitittimen takana (kuten yleensä), reitittimen porttivälityksen asetuksia on muutettava, jotta pelitiedot lähetetään isäntätietokoneeseen. Tämän voi tehdä reitittimen hallintasivun portin välitysasetuksista. Voit yrittää lisätä uuden palvelun (tai asiakaspalvelun), jos mahdollista. Kun uutta sääntöä asetetaan, sen nimeä pyydetään. Voit valita mitä haluat, mutta suosittelemme selkeyden vuoksi nimeä ”portalknights”. Tyypin on oltava ”UDP”. Käytä kaikille porteille (sisäiset ja ulkoiset) arvoa ”16365”, ellet ole muuttanut porttia määritystiedostossa (jolloin on muistettava käyttää siinä määritettyä porttia). Syötä lähtevään IP-osoitteeseen ja palvelimen IP-osoitteeseen paikallinen verkko-osoite, jonka voit selvittää suorittamalla sovelluksen ipconfig komentokehotteen kautta. Jos sinulta pyydetään muuta tietoa, jätä se täyttämättä ja jatka. Jos sinulla on ongelmia tässä toimenpiteessä, etsi apua osoitteesta https://portforward.com/. Huomaa, että jos peliä isännöivällä tietokoneella ei ole kiinteä IP-osoite, paikallinen verkko-osoite voi muuttua (jolloin portinvälityssäännöt eivät toimi). Katso reitittimesi asiakirjoista neuvoa siihen, miten tietokoneelle asetetaan staattinen IP-osoite.

    7. Lähetä ulkoinen IP-osoite ja käyttäjäryhmän salasana ihmisille, joiden haluat pääsevän palvelimelle. Huomaa, että portinvälitykseen asettamasi IP-osoite EI ole ulkoinen IP-osoitteesi vaan paikallinen IP-osoitteesi. Voit selvittää ulkoisen IP-osoitteen, jonka pelaajat tarvitsevat liittymiseen, esimerkiksi sivustolta http://whatismyip.host/. Lähetä käyttäjille IP v4 -osoitetta, älä IP v6 -osoitetta (IP-osoitteen tulisi olla xxx.xxx.xxx.xxx – ei xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx)

    Jos haluat asentaa useita palvelimia samalle tietokoneelle, käytä seuraavia komentokehotteen argumentteja valmistelemaan eri määritykset kullekin ja mukauta määritystiedosto sen mukaisesti.
        
    Argumentit:
        a. -config myConfig.json: Palvelimen määrittämiseen käytetään myConfig.json-määritystiedostoa.
                      
                      i. Jos tämännimistä tiedostoa ei ole olemassa, oletusmääritystiedosto luodaan kyseisellä nimellä. Huomautus: Voit vapaasti luoda oman nimen määritystiedostoille. Nimi ”myConfig.json” on vain esimerkki.

        b. -log mylogfile.log: Lokitiedosto kirjoitetaan määritettyyn tiedostoon.
    
            Esimerkki:
        pk_dedicated_server -config myOwnConfig.json -log testServer.log
        Käynnistää dedikoidun palvelimen, joka lukee määrityksensä tiedostosta myOwnConfig.json ja kirjoittaa lokinsa tiedostoon testServer.log


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
    
    
Lisenssi:
    YKSITYISTEN TAI ITSENÄISTEN PALVELINTEN KÄYTTÖ
    
    Ostamalla ja käyttämällä ohjelmistotuotetta saat vain lisenssiluvan ohjelmistotuotteen käyttämiseen tämän lisenssisopimuksen mukaan. Tähän sisältyy lupa levittää tuotteen suoritettavaa tiedostoa yksityisille tai itsenäisille palvelimille (tästä eteenpäin ”itsenäiset palvelimet”). Kuitenkin sellaisten kolmansien osapuolien, jotka haluavat käyttää yksityispalvelimella olevaa ohjelmistotuotetta, on ostettava ohjelmistotuotteen täysi versio, mukaan lukien ohjelmistotuotteen täyden version suoritettava tiedosto, joka antaa kolmannelle osapuolelle oman lisenssinsä.

    Hyväksyt, että lisensoija ei ole millään tavalla vastuussa siitä, mitä kolmas osapuoli voi tehdä sisällöllä, joka löytyy yksityispalvelimelta, jolle olet antanut pääsyn.
    
    Yksityispalvelimen käytön ja yksityispalvelinta käyttämällä luodun tai levitetyn sisällön on täytettävä seuraavat, ei-yksinomaiset vaatimukset:

      • On oltava alkuperäistä eikä saa rikkoa kolmansien osapuolien tekijänoikeuksia
      • Ei saa rikkoa minkään sellaisen alueen lakeja, jolta sitä voidaan käyttää
      • Ei saa käyttää loukkaavaa, pornografista, halventavaa tai syrjivää sisältöä
      • Ei saa sisältää harhaanjohtavaa tai pettävää sisältöä
      • Ei saa sisältää solvaavaa tai kiusaavaa sisältöä tai muuten vahingoittaa kolmannen osapuolen tai lisensoijan mainetta
      • Ei saa sisältää mainontaa tai veloittaa oikeaa rahaa pelin sisäisestä valuutasta
      • Ei saa esittää olevansa lisensoijan tarjoama tai hyväksymä palvelin tai muu sisältö

    Selkeyden vuoksi ilmoitamme, että olet vastuussa kaikesta sisällöstä, jonka teet saataville yksityispalvelimella, oli sisältö sitten itse tekemääsi tai sisältöä, jonka olet sallinut kolmannen osapuolen luoda yksityispalvelimellasi. Tässä tarkoituksessa esität ja takaat lisensoijalle, että sinulla on täysi oikeus isännöidä ohjelmistotuotetta yksityispalvelimellasi, että teet sen tämän sopimuksen mukaisesti ja että sinulla on oikeudet antaa lupia ja lisenssejä, jotka olet hyväksynyt antavasi, käyttämällä yksityispalvelimia lisensoijalle ja kolmansille osapuolille edellä määrätyllä tavalla.