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

Instrucciones:

    1. Abre "pk_dedicated_server.exe".  Se crearán un archivo de registro, un archivo de configuración y una carpeta para los datos guardados.
    2. Cierra "pk_dedicated_server.exe" para configurar el archivo de configuración.
    3. Abre el archivo "server_config.json" con un editor de texto para configurar el servidor.
       ¡TODAS LAS ENTRADAS DEBEN HACERSE EN ASCII O UTF-8!
    4. Podrás ver y cambiar la siguiente configuración:
        a. basicServerData
            i. name: el nombre de tu servidor dedicado.
            ii. ipv4: la dirección IP de la red local de tu servidor dedicado. La dirección 0.0.0.0 permite al ordenador anfitrión escuchar todo el tráfico de la red local. Seguramente no necesites modificar esto a no ser que configures tu servidor para una tarjeta de red o interfaz específicas.
            iii. port: el puerto de tu servidor dedicado. No recomendamos cambiarlo a menos que lo requiera la configuración de tu cortafuegos o router, o si quieres usar varios servidores en el mismo PC (en cuyo caso, cada uno necesitará un puerto separado).
            iv. saveFolderPath: ubicación donde se escribirán los datos guardados. Tendrás que cambiarla si quieres usar varios servidores en el mismo PC.
        b. universeSize: (Small/Normal/Large) Tamaño del servidor dedicado.
        c. hideConsoleWindow: (true/false) Esta función ocultará la ventana de la consola. Con esta opción activada, el servidor solo se podrá cerrar desde el administrador de tareas.
        d. admins/users/guests
            i. Credentials
                • password: elige las contraseñas con las que los distintos grupos de usuarios accederán a tu servidor dedicado. Hay tres grupos de usuarios (administradores, usuarios e invitados), que se pueden configurar con diferentes contraseñas y derechos. Comparte con los jugadores la contraseña que les otorgue los derechos que quieras asignarles y no compartas tu contraseña de administrador.
            ii. canLogin: (true/false) Define si un grupo de usuarios concreto puede iniciar sesión.
            iii. canKickPlayers: (true/false) Determina si un grupo de usuarios concreto puede echar a otros jugadores del servidor.
            iv. canModifyWorld: (true/false) Determina si un grupo de usuarios concreto puede excavar, construir bloques y atrezo.
            v. canInteractWithLockables: (true/false) Define si un grupo de usuarios en particular puede interactuar con cofres. Se debe usar junto con canModifyWorld para prevenir también la explotación de cofres.
        
    5. Abre de nuevo "pk_dedicated_server.exe" para iniciar el servidor dedicado con la nueva configuración.
    6. Si tu servidor dedicado depende de un router (lo cual es lo más habitual), tendrás que modificar la
configuración de la redirección de puertos de tu router para asegurarte de que los datos del juego se envían a tu ordenador anfitrión. Podrás hacerlo si localizas la página de administración del router y encuentras allí la configuración de la redirección de puertos. Aquí podrás intentar añadir un nuevo servicio (o servicio al cliente) si fuera posible. Cuando te pida que configures la nueva norma, te preguntará cómo llamarla. Puedes elegir el nombre que quieras, pero te recomendamos ""portalknights"". Tendrás que usar ""UDP"". Para todos los puertos (internos y externos), usa ""16365"" a no ser que hayas cambiado el puerto en el archivo de configuración (en este caso, asegúrate de que los puertos coinciden con dicha configuración). Para la ""IP de salida"" o la ""IP del servidor"", escribe tu dirección de red local, que encontrarás ejecutando ipconfig a través del símbolo del sistema. Si aparece más información, ignórala y continúa. Si tienes problemas con el proceso, encontrarás ayuda en https://portforward.com/. Ten en cuenta que si no configuras una IP estática para el ordenador anfitrión del juego, la dirección IP de la red local puede cambiar (lo que puede invalidar las normas de redirección de puertos). Revisa la documentación específica de tu router para saber cómo configurar una dirección IP estática para tu ordenador."

    7. Envía tu dirección IP externa junto a una contraseña de grupo de usuarios a las personas a las que quieras dar acceso al servidor. Ten en cuenta que la dirección IP introducida para la redirección de puertos NO será la dirección IP externa, sino la dirección IP de la red local. Para ver la dirección IP externa que necesitarán los usuarios para unirse, tendrás que entrar en una página como http://whatismyip.host/. Envía a tus usuarios tu dirección IP v4 y no tu IP v6 (la dirección IP debe tener este formato xxx.xxx.xxx.xxx y no este xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx).

    Para configurar varios servidores en el mismo PC, usa los argumentos del símbolo del sistema que encontrarás más abajo para preparar distintas configuraciones para cada uno y adaptar los archivos de configuración de forma correcta.
        
    Argumentos:
        a. -config myConfig.json: el archivo de configuración myConfig.json se usará para configurar el servidor.
                      
                      i. Si no existe un archivo con este nombre, se creará un archivo de configuración por defecto con este nombre. Nota: puedes nombrar como quieras a tus archivos de configuración, "myConfig.json" es solo un ejemplo.

        b. -log mylogfile.log: el archivo de registro se escribirá en el archivo especificado.

            Ejemplo:
        pk_dedicated_server -config myOwnConfig.json -log testServer.log
        Iniciará un servidor dedicado que leerá su configuración de myOwnConfig.json y escribirá sus salidas del registro en testServer.log


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
    
    
Licencia:
    USO DE SERVIDORES PRIVADOS O INDEPENDIENTES
    
    Al comprar y utilizar el Producto de software, no solo obtienes el permiso de licencia para usar el Producto de software de acuerdo con los términos de este acuerdo de licencia, que incluye el permiso para distribuir el archivo ejecutable del producto en servidores privados o independientes (en adelante, "servidores privados"); siempre que todo tercero que desee acceder al Producto de software en el servidor privado compre la versión completa del Producto de software, incluido el ejecutable de la versión completa del Producto de software, que proporcionará su propia licencia a dicho tercero.

    Aceptas que el cedente no es, en ningún caso, responsable de lo que hagan los terceros con cualquier contenido encontrado en cualquier servidor privado al que permitas el acceso.
    
    Cualquier uso de un servidor privado o de cualquier contenido creado o distribuido a través de dicho servidor privado deberá cumplir los siguientes requisitos no exclusivos:

      • Ser original y no infringir los derechos de propiedad intelectual de ningún tercero
      • No infringir las leyes de ninguna jurisdicción desde la que se acceda a él
      • No hacer uso de materiales ofensivos, pornográficos, despectivos y discriminatorios
      • No usar materiales erróneos o engañosos
      • No usar materiales abusivos ni amenazantes, ni dañar la reputación de ningún tercero ni del cedente
      • No incluir publicidad ni cobrar dinero real a cambio del dinero del juego
      • No se usará como servidor de ningún material ofrecido o aprobado por el cedente

    Para clarificar, serás responsable de todo el contenido que hagas accesible en el servidor privado, tanto si fue creado por ti como si lo has hecho accesible a cualquier tercero que use tu servidor privado. A dicho fin, representas y garantizas al cedente que tienes pleno derecho a contener el Producto de software en tu servidor privado, que lo haces en cumplimiento de los términos de este acuerdo y que tienes derecho a conceder los permisos y licencias que has concedido al cedente y a terceros para usar los servidores privados de acuerdo con lo establecido anteriormente.