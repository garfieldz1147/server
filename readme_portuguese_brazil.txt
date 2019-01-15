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

Instruções:    

    1. Execute o "pk_dedicated_server.exe" - um arquivo de log, um arquivo de configuração e uma pasta de dados salvos serão criados.
    2. Feche o "pk_dedicated_server.exe" para preparar o arquivo de configuração.
    3. Abra o arquivo "server_config.json" com um editor de texto para configurar o servidor.
       TODAS AS ENTRADAS DEVEM SER EM ASCII OU UTF-8!
    4. As seguintes configurações podem ser vistas ou alteradas:
        a. basicServerData
            i. name: O nome que seu servidor dedicado irá exibir.
            ii. ipv4: O endereço de IP da rede local do seu servidor dedicado. O endereço 0.0.0.0 permite que o computador anfitrião vigie todo o tráfego da rede local. Você provavelmente não precisará mudar isso a não ser que esteja configurando seu servidor para funcionar em uma placa de rede ou interface específica.
            iii. port: A porta do servidor dedicado. Não recomendamos alterar essa opção, a não ser que sua firewall ou roteador exijam, ou que você queria executar múltiplos servidores no mesmo PC (nesse caso, cada um precisará de uma porta separada).
            iv. saveFolderPath: Este é o local onde os dados salvos serão armazenados. Isso precisa ser alterado caso você queira ter múltiplos servidores no mesmo PC.
        b. universeSize: (Small/Normal/Large) O tamanho do universo no servidor dedicado. As opções indicam, respectivamente, pequeno, normal e grande.
        c. hideConsoleWindow: (true/false) Isso ocultará a janela do console. Se a opção estiver habilitada (true), o servidor só poderá ser fechado encerrando-o no gerenciador de tarefas.
        d. admins/users/guests
            i. Credentials
                • password: Escolha senhas usadas para acessar seu servidor dedicado por diferentes grupos de usuários (administrador - admin, usuários - users e visitantes - guests) que podem ser definidos com diferentes senhas e permissões. Dê aos jogadores apenas a senha do grupo de usuário que você quer que eles tenham e mantenha sua senha de administrador privada!
            ii. canLogin: (true/false) Define seu um grupo de usuários específico pode fazer login.
            iii. canKickPlayers: (true/false) Define se um grupo de usuários específico pode expulsar outros jogadores do servidor.
            iv. canModifyWorld: (true/false) Define se um grupo específico de usuários pode minerar/construir blocos/itens.
            v. canInteractWithLockables: (true/false) Define se um grupo de usuários específico pode interagir com baús. Deve ser usado em conjunto com canModifyWorld para também impedir de minerar baús.

    5. Execute "pk_dedicated_server.exe" novamente para iniciar o servidor dedicado com as novas configurações.
    6. Se seu servidor dedicado estiver atrás de um roteador (o que costuma ser o caso), você precisará editar as configurações de redirecionamento de porta do seu roteador para garantir que os dados do jogo sejam enviados para o seu computador anfitrião. Você pode fazer isso localizando a página de administração do seu roteador e encontrando as configurações de redirecionamento de portas nela. Ali, você pode tentar adicionar um novo serviço (ou serviço de consumidor) se possível. Quando solicitado a configurar uma nova regra, você deve ter que nomeá-la. Você pode escolher o nome que quiser, mas nós recomendamos "portalknights" para deixar mais simples. O tipo precisa ser "UDP". Para todas as portas (interna e externa) use 16365, a não ser que tenha mudado a porta no arquivo de configuração (nesse caso você precisa usar a mesma porta definida lá). Em "IP de saída" ou "IP do servidor", insira seu endereço de rede local que você pode descobrir executando "ipconfig" pelo prompt de comando. Se qualquer outra informação for solicitada, deixe como está e continue. Se estiver com dificuldades no processo, visite https://portforward.com/ para ter ajuda. Note que, a não ser que você defina uma IP estático para o computador que está hospedando o jogo, o endereço de IP da rede local pode mudar (o que pode tornar as regras de redirecionamento de porta inválidas). Confira a documentação específica do seu roteador para determinar como configurar um endereço de IP estático para o seu computador.

    7. Envie seu endereço de IP externo junto com uma senha de grupo de usuários para as pessoas que você deseja que acessem o servidor. Note que o endereço de IP que você inseriu no redirecionamento de portas NÃO será seu endereço de IP externo, ele será o endereço de IP da rede local. Para encontrar seu endereço de IP externo para os usuários utilizarem, você precisará visitar um site como http://whatismyip.host/. Certifique-se de enviar aos usuários o seu endereço de IP v4, não o IP v6 (o endereço de IP deve ser parecer com xxx.xxx.xxx.xxx -- não xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx)

    Para configurar múltiplos servidores no mesmo PC, use os argumentos do prompt de comando abaixo para preparar diferentes configurações para cada um e adaptar os arquivos de configuração de acordo.
        
    Argumentos:
        a. -config myConfig.json: O arquivo de configuração myConfig.json será usado para configurar o servidor.

                      i. Se não existir um arquivo com este nome, um arquivo de configuração padrão com este nome será criado. Obs.: Sinta-se à vontade para criar seu próprio nome para seus arquivos de configuração, "myConfig.json" é apenas um exemplo.

        b. -log mylogfile.log: O arquivo de log a será escrito no arquivo especificado.

            Exemplo:
        pk_dedicated_server -config myOwnConfig.json -log testServer.log
        Executará um servidor dedicado que lê suas configurações de myOwnConfig.json e escreve o registro e log em testServer.log


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
    
    
Licença:
    USO DE SERVIDORES PRIVADOS OU INDEPENDENTES

    Ao comprar e utilizar o Produto do Software, você está obtendo apenas a permissão de licença para usar o Produto do Software de acordo com o termos deste contrato de licença, que inclui a permissão para distribuir o arquivo executável do produto em servidores privados ou independentes (aqui chamados, "Servidores Privados"); desde que quaisquer terceiros que desejarem acessar o Produto do Software no Servidor Privado ainda tenha que comprar a versão completa do Produto do Software, incluindo o executável da versão completa do Produto do Software que fornecerá a quaisquer terceiros sua própria licença.

    Você concorda que o Licenciante não é responsável pelo que usuários terceiros fazem com qualquer conteúdo encontrado nos Servidores Privados aos quais você permitir acesso.

    Qualquer uso de um Servidor Privado ou qualquer conteúdo criado ou disseminado usando tal Servidor Privado deve aderir aos seguintes requisitos não exclusivos:

      • Deve ser original e não infringir os direitos de propriedade intelectual de nenhum terceiro
      • Não deve violar as leis de qualquer jurisdição da qual ele possa ser acessado
      • Não deve utilizar materiais ofensivos, pornográficos, depreciativos ou discriminatórios
      • Não deve usar materiais enganosos
      • Não deve usar material abusivo ou característico de bullying, ou qualquer outra forma de dano à reputação de terceiros ou do Licenciante
      • Não deve incluir propagandas ou cobrar dinheiro real por moeda interna do jogo
      • Não deve ser dizer um servidor ou qualquer material oferecido ou aprovado pelo Licenciante

    Em suma, você permanecerá responsável por todo conteúdo que tornar disponível no Servidor Privado, seja criado por você e/ou que você permita que esteja disponível por quaisquer terceiros usando seu Servidor Privado. Para este fim, você representa e garante ao Licenciante que possui total direito de hospedar o Produto do Software no seu Servidor Privado, fazendo isso de acordo com o termos deste contrato, e possui o direito de conceder permissões e licenças que concorda em fornecer, deste modo utilizando o Servidor Privado, ao Licenciante e quaisquer outros terceiros conforme definido aqui, adiante e acima.