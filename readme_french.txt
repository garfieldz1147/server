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

Instructions :

    1. Lancez le fichier « pk_dedicated_server.exe ». Un fichier journal, un fichier de configuration et un dossier de données sauvegardées seront créés.
    2. Fermez le fichier « pk_dedicated_server.exe » afin de paramétrer le fichier de configuration.
    3. Ouvrez le fichier « server_config.json » à l'aide d'un éditeur de texte pour configurer le serveur.
       LE TEXTE SAISI DOIT ÊTRE ENCODÉ EN ASCII OU UTF-8 !
    4. Les paramètres suivants peuvent être visualisés ou modifiés :
        a. basicServerData
            i. Name : le nom de votre serveur dédié sera affiché.
            ii. ipv4 : l'adresse IP du réseau local de votre serveur dédié. L'adresse 0.0.0.0 permet à l'ordinateur hôte d'écouter tout le trafic du réseau local. Vous n'aurez probablement pas besoin de modifier ces paramètres à moins que vous ne vouliez faire fonctionner votre serveur sur une carte réseau ou interface spécifique.
            iii. Port : le port pour le serveur dédié. Nous vous déconseillons de modifier ce paramètre à moins que les paramètres de votre parefeu/routeur ne l'exigent, ou que vous ne vouliez exécuter plusieurs serveurs sur le même PC (auquel cas chacun aura besoin d'un port séparé).
            iv. saveFolderPath : c'est l'emplacement où les données de sauvegarde seront écrites. Doit être modifié si vous souhaitez exécuter plusieurs instances du serveur sur le même ordinateur.
        b. universeSize : (Small/Normal/Large) la taille de l'univers pour le serveur dédié.
        c. hideConsoleWindow : (true/false) masque la fenêtre de la console. Si cette option est activée, le serveur ne peut être fermé qu'en l'arrêtant via le gestionnaire des tâches.
        d. admins/users/guests
            i. Credentials
                • password : choisissez les mots de passe utilisés par chaque groupe d'utilisateurs pour accéder à votre serveur dédié. Il existe trois groupes d'utilisateurs (administrateurs, utilisateurs et invités) pour chacun desquels vous pouvez configurer un mot de passe et des droits spécifiques. Ne donnez aux joueurs que le mot de passe donnant accès aux droits du groupe d'utilisateurs que vous souhaitez leur donner, et ne révélez pas le mot de passe réservé aux administrateurs !
            ii. canLogin : (true/false) détermine si un groupe d'utilisateurs spécifique peut se connecter.
            iii. canKickPlayers : (true/false) détermine si un groupe d'utilisateurs particulier peut déconnecter les autres joueurs du serveur.
            iv. canModifyWorld : (true/false) détermine si un groupe d'utilisateurs peut extraire/construire des blocs/accessoires.
            v. canInteractWithLockables : (true/false) détermine si un groupe d'utilisateurs spécifique peut interagir avec les coffres. Doit être utilisé conjointement à canModifyWorld afin d'empêcher l'extraction du contenu des coffres.

    5. Relancez le fichier « pk_dedicated_server.exe » pour redémarrer le serveur dédié avec les nouveaux réglages.
    6. Si votre serveur dédié est derrière un routeur (ce qui est généralement le cas), il vous faudra modifier les paramètres de transfert de port de votre routeur pour vous assurer que les données du jeu soient envoyées vers votre ordinateur hôte. Pour ce faire, rendez-vous sur la page d'administration de votre routeur et localisez les paramètres Transfert de port qui s'y trouvent. Ici, vous pouvez ajouter un nouveau service (ou service client) si possible. Au moment de créer une nouvelle règle, on vous demandera de la nommer. Vous pouvez saisir le nom de votre choix, mais nous vous conseillons « portalknights », pour plus de simplicité. Le protocole doit être du type « UDP ». Pour tous les ports (internes et externes), utilisez « 16365 », sauf si vous avez modifié le port dans le fichier de configuration (auquel cas vous devrez vous assurer que les ports soient identiques à celui configuré). Pour « IP de sortie » ou « IP du serveur », saisissez votre adresse de réseau local, que vous pourrez trouver en exécutant ipconfig dans la fenêtre d'invite de commandes. Si d'autres informations vous sont demandées, ignorez et continuez. Si vous rencontrez des difficultés, veuillez visiter le site https://portforward.com/ pour trouver de l'aide. Veuillez noter qu'à moins de configurer une adresse IP statique pour l'ordinateur hôte du jeu, l'adresse IP du réseau local peut changer (ce qui peut rendre les règles de transfert de port invalides). Référez-vous à la documentation spécifique à votre routeur pour savoir comment configurer une adresse IP statique pour votre ordinateur.

    7. Envoyez votre adresse IP externe ainsi qu'un mot de passe de groupe d'utilisateurs aux personnes auxquelles vous souhaitez donner accès au serveur. Veuillez remarquer que l'adresse IP saisie pour le transfert de port NE sera PAS votre adresse IP externe, mais sera l'adresse IP de votre réseau local. Pour trouver l'adresse IP externe nécessaire pour que les utilisateurs puissent se connecter, vous devrez vous rendre sur un site du type http://whatismyip.host/. Assurez-vous d'envoyer aux utilisateurs votre adresse IP v4, et non pas votre adresse IP v6 (l'adresse IP doit être du type xxx.xxx.xxx.xxx, et non pas xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx)

    Afin de configurer plusieurs serveurs sur un même ordinateur, utilisez les arguments de ligne de commande fournis ci-dessous pour préparer des configurations différentes pour chacun et adapter les fichiers de configurations à chacun.
        
    Arguments :
        a. -config myConfig.json : le fichier de configuration myConfig.json qui sera utilisé pour configurer le serveur.

                      i. S'il n'existe pas de fichier de ce nom, un fichier de configuration ayant ce nom par défaut sera créé. Remarque : Vous pouvez donner le nom de votre choix à vos fichiers de configuration. « myConfig.json » n'est qu'un exemple.

        b. -log mylogfile.log : le fichier journal sera écrit dans le fichier spécifié.

            Exemple :
        pk_dedicated_server -config myOwnConfig.json -log testServer.log
        Démarrera un serveur dédié lisant ses règles de configuration à partir du fichier myOwnConfig.json et écrira le journal dans le fichier testServer.log


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
    
    
Licence :
    UTILISATION DE SERVEURS PRIVÉS OU INDÉPENDANTS

    En achetant et utilisant ce Logiciel, vous obtenez uniquement la permission d'utiliser le Logiciel conformément aux modalités de ce Contrat de licence, ce qui comprend la permission de distribuer le fichier exécutable du produit sur des serveurs privés ou indépendants (ci-après dénommés « Serveurs privés ») ; sous réserve que tout tiers souhaitant accéder au Logiciel sur le Serveur privé soit tenu d'acheter la version complète du Logiciel, y compris l'exécutable de la version complète du Logiciel qui fournira à ce tiers sa propre licence.

    Vous acceptez que le Concédant n'est en aucun cas responsable de la façon dont les utilisateurs tiers utilisent le contenu trouvé sur les Serveurs privées auxquels vous leur avez donné accès.

    Toute utilisation d'un Serveur privé ou de tout contenu créé ou disséminé à l'aide dudit Serveur privé doit respecter les conditions non-exclusives suivantes :

      • Doit être original et ne violer en rien les droits de propriété intellectuelle de tiers
      • Ne viole en rien les lois de la juridiction d'où il est accessible
      • Aucune utilisation de  matériel offensif, pornographique, offensant ou discriminant
      • Aucune utilisation de matériel mensonger ou trompeur
      • Aucune utilisation de matériel abusif ou intimidant, ou portant atteinte à la réputation d'un tiers ou du Concédant
      • Ne peut comprendre de publicités ni vendre de l'argent du jeu contre de l'argent réel
      • Ne doit en aucun cas se présenter comme un serveur ou tout autre matériel proposé ou approuvé par le Concédant

    En clair, vous serez tenu responsable de tout contenu que vous mettez à disposition sur le Serveur Privé, qu'il ait été créé ou non par vous, et/ou que vous autorisez tout tiers à rendre disponible sur votre Serveur Privé. Pour ce faire, vous déclarez et garantissez au Concédant que vous êtes pleinement autorisé à héberger le Logiciel sur votre Serveur privé, que vous adhérez aux termes de cet Accord et avez le droit d'octroyer les permissions et licences que vous avez accepté de fournir au Concédant ou à tout autre tiers pour l'utilisation des Serveurs Privés comme établi ci-dessus.