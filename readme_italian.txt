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

Istruzioni:    

    1. Avvia "pk_dedicated_server.exe" - verranno creati un file di registro, un file di configurazione e una cartella dei dati di salvataggio.
    2. Scegli "pk_dedicated_server.exe" per impostare il file di configurazione.
    3. Apri il file "server_config.json" con un editor di testo per impostare il server.
       TUTTE LE INFORMAZIONI DEVONO ESSERE CODIFICATE IN CARATTERI ASCII O UTF-8!
    4. Puoi visualizzare o cambiare le seguenti impostazioni:
        a. basicServerData
            i. name: il nome che apparirà sul server dedicato.
            ii. ipv4: l'indirizzo IP della rete locale del server dedicato. L'indirizzo 0.0.0.0 consente al computer host di monitorare tutto il traffico di rete locale. Molto probabilmente non avrai bisogno di cambiarlo a meno che non stai impostando il server su una specifica interfaccia o scheda di rete.
            iii. port: la porta per il server dedicato. Sconsigliamo di cambiarla a meno che non venga richiesto nelle impostazioni del firewall/router o se desideri avviare più server sullo stesso PC (in tal caso sarà necessaria una porta per ogni server).
            iv. saveFolderPath: in questa posizione verranno scritti i dati di salvataggio. Deve essere cambiata se desideri lanciare istanze multiple del server sullo stesso PC.
        b. universeSize: (Small/Normal/Large) La dimensione dell'universo sul server dedicato.
        c. hideConsoleWindow: (true/false) Nasconderà la finestra Console. Attivando quest'opzione, il server può essere spento solo attraverso Gestione operazioni.
        d. admins/users/guests
            i. Credentials
                • password: Scegli le password necessarie ai vari gruppi di utenti per accedere al server dedicato. I gruppi di utenti sono tre (admin, users e guests) e possono essere impostati con password e diritti diversi. Fornisci ai giocatori solo le password corrispondenti ai diritti del gruppo di utenti in cui vuoi farli rientrare e mantieni privata la tua password admin!
            ii. canLogin: (true/false) Definisce se un particolare gruppo di utenti può effettuare il login.
            iii. canKickPlayers: (true/false) Definisce se un particolare gruppo di utenti può cacciare altri giocatori dal server.
            iv. canModifyWorld: (true/false) Definisce se un particolare gruppo di utenti può estrarre/costruire blocchi/oggetti.
            v. canInteractWithLockables: (true/false) Stabilisce se un particolare gruppo di utenti può interagire con gli scrigni. Dovrebbe essere usato insieme a canModifyWorld per evitare che gli scrigni vengano estratti.

    5. Riavvia "pk_dedicated_server.exe" per avviare il server dedicato con le nuove impostazioni.
    6. Se il server dedicato è collocato a un router (come nella maggior parte dei casi), dovrai modificare le impostazioni di reindirizzamento delle porte del router per garantire che i dati di gioco vengano inviati al computer host. Puoi farlo localizzando la pagina di amministrazione del router e trovando le impostazioni di reindirizzamento delle porte ivi contenute. Qui puoi provare ad aggiungere un nuovo servizio (o servizio clienti) se possibile. Quando ti viene chiesto di impostare una nuova regola, ti dovrebbe venire richiesto di darle un nome. Puoi scegliere il nome che preferisci, ma ti raccomandiamo di usare "portalknights" per semplicità. Il tipo deve essere "UDP". Per tutte le porte (interne ed esterne) usa "16365", a meno che tu non abbia cambiato la porta nel file di configurazione (in tal caso assicurati che le porte corrispondano a ciò che vi hai configurato). Per l'"IP di uscita" o l'"IP del server", inserisci l'indirizzo di rete locale che troverai eseguendo l'ipconfig nel prompt dei comandi. Se ti vengono richieste altre informazioni, non tenerne conto e continua. Se tali operazioni ti causano delle difficoltà, visita https://portforward.com/ per ricevere assistenza. Tieni presente che, a meno che non imposti un IP statico per il computer che ospita il gioco, l'indirizzo IP della rete locale può cambiare (il che può rendere non valide le regole di reindirizzamento delle porte). Consulta la documentazione specifica del router per determinare come configurare un indirizzo IP statico per il tuo computer.

    7. Invia il tuo indirizzo IP esterno insieme a una password del gruppo di utenti alle persone cui desideri fornire l'accesso al server. Tieni presente che l'indirizzo IP inserito per il reindirizzamento delle porte NON sarà il tuo indirizzo IP esterno bensì quello della rete locale. Per trovare l'indirizzo IP esterno necessario agli utenti per partecipare, è necessario visitare un sito tipo http://whatismyip.host/. Assicurati di inviare agli utenti il tuo indirizzo IP v4, non l'IP v6 (l'indirizzo IP dovrebbe apparire come xxx.xxx.xxx.xxx e non come xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx)

    Per configurare più server sullo stesso PC, utilizza gli argomenti del prompt dei comandi forniti di seguito per impostare diverse configurazioni e per adattare i file di configurazione per ciascuno di essi.
        
    Argomenti:
        a. -config myConfig.json: Per impostare il server verrà usato il file di configurazione myConfig.json.

                      i. Se non esiste un file con questo nome, verrà creato un file di configurazione predefinito con questo nome. Nota: sei libero di denominare come vuoi i tuoi file di configurazione, "myConfig.json" è solo un esempio.

        b. -log mylogfile.log: Il file di registro verrà scritto nel file specificato.

            Esempio:
        pk_dedicated_server -config myOwnConfig.json -log testServer.log
        Avvierà un server dedicato che legge la propria configurazione da myOwnConfig.json e scrive la propria uscita registro su testServer.log


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
    
    
Licenza:
    UTILIZZO DI SERVER PRIVATI O INDIPENDENTI

    Acquistando e utilizzando il Prodotto software, si ottiene solo la licenza per l'utilizzo del Prodotto software in conformità con i termini del presente Contratto di licenza, che include il permesso di distribuire il file eseguibile del prodotto su server privati o indipendenti (d'ora in poi " Server privati "), purché i terzi interessati ad accedere al Prodotto software sul Server Privato acquistino la versione completa del Prodotto Software, incluso l'eseguibile della versione completa del Prodotto Software che fornirà ai suddetti terzi la loro licenza.

    L'utente accetta che il Licenziante non è in alcun modo responsabile dell'uso che persone terze fanno di qualsiasi contenuto che venga reperito su un server privato a cui è stato consentito l'accesso.

    L'uso di un server privato o dei contenuti creati o diffusi servendosi di tale server deve rispettare i seguenti requisiti non esclusivi:

      • Deve essere originale e non violare i diritti di proprietà intellettuale di terzi.
      • Non può violare le leggi di qualsiasi giurisdizione da cui possa essere consultato
      • Non può servirsi di materiale offensivo, pornografico, dispregiativo, discriminante
      • Non può servirsi di materiali fuorvianti o ingannevoli
      • Non può servirsi di materiali abusivi o relativi a bullismo e che comunque danneggino la reputazione di terzi o quella del Licenziante
      • Non può contenere pubblicità o addebitare denaro reale in sostituzione della valuta del gioco
      • Non deve presentarsi come materiale del server o offerto o approvato dal Licenziante

    Per maggior chiarezza, l'utente rimarrà responsabile di tutti i contenuti resi disponibili sul server privato, sia che vengano creati dall'utente sia che l'utente consenta di renderli disponibili a terzi tramite il proprio server privato. A tal fine, l'utente dichiara e garantisce al Licenziante il pieno diritto di ospitare il Prodotto Software sul proprio server Privato, lo fa in conformità con i termini del presente Accordo e ha il diritto di concedere le autorizzazioni e le licenze, che ha accettato di fornire utilizzando i server privati al Licenziante e a terzi come indicato precedentemente.