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

Instructions:    

    1. Start the "pk_dedicated_server.exe" - a log file, a configuration file, and a save data 
       folder will be created. 
    2. Close the "pk_dedicated_server.exe" in order to set up the config file. 
    3. Open the "server_config.json" file with a text editor to set up the server.
       ALL ENTRIES MUST BE IN ASCII OR UTF-8!
    4. The following settings can be viewed or changed:
        a. basicServerData
            i.   name: The name that your dedicated server will display.
            ii.  ipv4: The local network IP address of your dedicated server. The address 0.0.0.0
                 allows the host computer to listen to all local network traffic. You probably won't
                 need to change this unless you're setting up your server to work on a specific
                 network card or interface.
            iii. port: The port for the dedicated server. We recommend against changing
                 this unless your firewall/router settings require it, or if you want to run several
                 servers on the same PC (in which case each will need a separate port).
            iv.  saveFolderPath: This is the location where save data will be written.
                 This needs to be changed, if you wish to run multiple server instances
                 on the same PC.
        b. gameplayMode: (Adventure/Creative) The game play mode for the dedicated server.
		c. universeSize: (Small/Normal/Large) The universe size for the dedicated server.
        d. hideConsoleWindow: (true/false) This will hide the console window. If this option
           is enabled, the server can only be closed by terminating it in the task manager.
        e. admins/users/guests
            i.   Credentials
                • password: Choose passwords used to access your dedicated server 
                  by different user groups. There are three user groups (admin, 
                  users, and guests) which can be set up with different passwords 
                  and rights. Only give players the password for the user group
                  rights you want them to have and keep your admin password private!
            ii.  canLogin: (true/false) Defines whether a particular user group can log in.
            iii. canKickPlayers: (true/false) Defines whether a particular user group 
                 can kick other players from the server.
            iv.  canModifyWorld: (true/false) Defines whether a particular user group
                 can mine/build blocks/props.
            v.   canInteractWithLockables: (true/false) Defines whether a particular user group can
		 interact with chests. Should be used together with canModifyWorld in order to also
		 prevent mining of chests.
        
    5. Start the "pk_dedicated_server.exe" again to start the dedicated server with the new settings.
    6. If your dedicated server is behind a router (which is usually the case), you'll need to
       edit your router's port forwarding settings to ensure game data is sent to your host 
       computer. You can do this by locating your router's admin page and finding the Port 
       Forwarding settings therein. Here you can try to add a new service (or customer service)
       if possible. When asked to set up the new rule, you should be prompted on what to call 
       it. You can choose whatever name you wish, but we recommend "portalknights" for
       simplicity. Type needs to be "UDP". For all ports (internal and external) use "16365", 
       unless you've changed the port in the config file (in which case make sure the ports match 
       what you've configured there). For the "output IP" or "server IP", enter your local network
       address which you can find by running ipconfig via the Command Prompt. If prompted for
       any other information, leave it alone and continue. If you're having difficulties with this
       process, please visit https://portforward.com/ for help. Note that unless you set a static IP
       for the computer that is hosting the game, the local network IP address can change (which
       can make port forwarding rules invalid). Refer to your specific router's documentation to
       determine how to set up a static IP address for your computer.

    7. Send your external IP address along with a user group password to people whom you'd like
       to have access to the server. Note that the IP address you entered for port forwarding
       will NOT be your external IP address, it will be the local network IP address. To find
       the external IP address needed for users to join, you'll need to visit a site such as
       http://whatismyip.host/. Be sure to send users your IP v4 address, not IP v6 
       (the IP address should look like xxx.xxx.xxx.xxx -- not xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx)

    In order to set up multiple servers on the same PC, use the Command Prompt arguments
    provided below to prepare different configurations for each one and adapt the config files 
    for each accordingly.
        
    Arguments:
        a. -config myConfig.json: The myConfig.json configuration file will be used to set
                      up the server. 
                      
                      i. If a file with this name does not exist a default configuration file with
             this name will be created. Note: You are free to create your own name for
             your configuration files, "myConfig.json" is just an example. 

        b. -log mylogfile.log    : The log file will be written to the specified file.
    
            Example:
        pk_dedicated_server -config myOwnConfig.json -log testServer.log
        Will start a dedicated server that reads its configuration from 
        myOwnConfig.json and will write its log output to testServer.log


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
    
    
License:
    USE OF PRIVATE OR INDEPENDENT SERVERS
    
    By purchasing and using the Software Product, you are only obtaining the license 
    permission to use Software Product in accordance with the terms of this License 
    Agreement, which includes the permission to distribute the executable file of 
    the product on private or independent servers (hereafter, "Private Servers"); 
    provided however, that any third party wishing to access the Software Product on 
    the Private Server shall still be required to purchase the full version of the 
    Software Product, including the executable of the full version of the Software 
    Product which will provide any such third party with their own license. 

    You agree that Licensor is in no way liable for what third party users do with 
    any content found on any Private Servers to which you permit access. 
    
    Any use of a Private Server or any content created or disseminated using such 
    Private Server must adhere to the following, non-exclusive requirements:

      • Must be original and not infringe upon the intellectual property rights
        of any third parties
      • May not violate the laws of any jurisdiction from which it may be accessed
      • No use of offensive, pornographic, derogatory, discriminating materials
      • No use of any misleading or deceptive materials
      • No use of abusive or bullying materials, or otherwise damage the reputation 
        of a third party or that of Licensor 
      • May not include advertising or charge actual cash for in-game currency
      • Must not hold itself out to be a server or any material offered or approved 
        by Licensor

    For clarity, you shall remain liable for all content that you make available on 
    the Private Server, whether created by you and/or which you permit to be made 
    available by any third party using your Private Server.  To that end, you represent 
    and warrant to Licensor you are fully entitled to host the Software Product on your 
    Private Server, do so in compliance with the terms of this Agreement and have the 
    right to grant the permissions and licenses you have agreed to provide in so using 
    the Private Servers to Licensor and any third parties as set forth herein above. 