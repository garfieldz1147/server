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

使用方法：

    1.「pk_dedicated_server.exe」を立ち上げます。ログファイル、設定ファイル、サーバーデータ フォルダが生成されます。
    2.設定ファイルを設定するため、「pk_dedicated_server.exe」を閉じます。
    3.テキストエディタで「server_config.json」ファイルを開き、サーバーのセットアップを行います。
       文字コードは必ずASCIIかUTF-8にしてください！
    4.以下の設定の閲覧または変更を行えます。
        a.basicServerData
            i.name：専用サーバーの表示名です。
            ii.ipv4：あなたの専用サーバーのローカルネットワークIPアドレスです。0.0.0.0のアドレスにより、ホストコンピュータがすべてのローカルネットワークのトラフィックをリッスンできるようになります。特定のネットワークカードやインターフェイスでサーバーが動くようにする場合を除き、おそらく変更する必要はないでしょう。
            iii.port：専用サーバー用のポートです。ご利用のファイアウォールおよびルーター設定により必要な場合や、同じPCで複数のサーバーを走らせたい場合はを除き、この部分は変更しないことを推奨しております（その場合は、サーバーごとに別個のポートが必要になります）。
            iv.saveFolderPath：サーバーのデータが書き込まれる場所です。同じPCで複数のサーバーインスタンスを実行する場合には変更が必要です。
        b.universeSize：（Small/Normal/Large）専用サーバーのユニバースサイズです。
        c.hideConsoleWindow：（true/false）コンソールウィンドウを非表示にします。このオプションを有効にしていると、タスクマネージャーからしかサーバーを終了できません。
        d.admins/users/guests
            i.Credentials
                •password：各種ユーザーグループがあなたの専用サーバーにアクセスするためのパスワードを決めます。ユーザーグループは3種類（管理者、ユーザー、ゲスト）あり、それぞれにパスワードと権限を設定できます。プレイヤーにパスワードを与えるときには、想定したユーザーグループ権限のものを付与するように気をつけましょう。また、管理者パスワードは他人に教えないでください！
            ii.canLogin：（true/false）特定のユーザーグループがログインできるかどうかを決定します。
            iii.canKickPlayers:(true/false) 特定のユーザーグループが他のプレイヤーをサーバーから追い出せるかどうかを決定します。
            iv.canModifyWorld：（true/false）特定のユーザーグループがブロックや置物を掘れるか、および作れるかを決定します。
            v.canInteractWithLockables：(true/false) 特定のユーザーグループが宝箱とやりとりできるかどうかを定義します。宝箱のマイニングも防ぐには、canModifyWorldと一緒に使うべきです。

    5.「pk_dedicated_server.exe」をもう一度立ち上げ、新しい設定で専用サーバーを起動します。
    6.専用サーバーがルーターの奥にある場合には（多くの場合そうだと思いますが）、ルーターのポート転送設定を編集し、ゲームデータがホストコンピュータに送られるようにしなければなりません。その方法としては、ルーターの管理者ページを開いて、そちらでポート転送設定を探します。可能な場合にはここで新しいサービス（またはカスタマーサービス）を追加できます。新しいルールの設定を要求される際には、呼び方を尋ねられるはずです。好きな名前をつけられますが、わかりやすいので「portalknights」という名前を推奨しています。タイプは「UDP」にしてください。すべてのポート（内部と外部）に「16365」を使ってください。（ただし、設定ファイルでポートを変更している場合は、そちらで設定した内容と一致させます。）「出力IP」または「サーバーIP」については、ローカルネットワークアドレスを入力してください。コマンドプロンプトで「ipconfig」と打ち込むと出てきます。それ以外の情報を求められても、そのまま先に進んで構いません。このプロセスで手こずる場合は、https://portforward.com/の情報（英語）を参考にしてください。なお、ゲームをホストしているコンピュータに静的IPアドレスを設定している場合を除き、ローカルネットワークIPアドレスは変わることがあります（変わるとポート転送ルールが無効になります）。ご利用のコンピューターに静的IPアドレスを設定する方法については、お使いのルーターのマニュアル等でご確認ください。

    7.サーバーへのアクセス権を付与したい相手に、外部IPアドレスとユーザーグループのパスワードを送ります。なお、ポート転送用に入力したIPアドレスは外部IPアドレスではなく、ローカルネットワークIPアドレスになります。お間違えのないよう、お気をつけください。ユーザーの参加に必要な外部IPアドレスは、 http://whatismyip.host/のようなサイトで調べる必要があります。また、ユーザーに送るのはIP v6ではなく、IP v4アドレスですので、この点もご注意ください（xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx ではなく、xxx.xxx.xxx.xxx -- のような形のIPアドレスになるはずです）。

    同じPCで複数のサーバーを設定する場合は、以下で紹介するコマンドプロンプト実引数をお使いください。サーバーごとに異なる設定を行い、それに伴う異なる設定ファイルを用いてください。
        
    実引数：
        a.-config myConfig.json：サーバーの設定にmyConfig.json設定ファイルが使われます。

                      i.この名前のファイルが存在しない場合は、この名前のデフォルト設定ファイルが生成されます。なお、「myConfig.json」は単なる例であり、設定ファイルには好きな名前をつけられます。

        b.-log mylogfile.log：ログファイルが指定のファイルに書き込まれます。

            例：
        pk_dedicated_server -config myOwnConfig.json -log testServer.log
        myOwnConfig.jsonから設定を読み込む専用サーバーを起動し、そのログ出力をtestServer.logに書き込みます。


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
    
    
ライセンス：
    プライベートまたは独立サーバーの利用

    本ソフトウエア商品を購入し利用することで、本ライセンス契約の条件に基づき本ソフトウエア商品を使用する目的でのライセンス許可のみが得られます。かかる使用許可には、プライベートまたは独立サーバー（以下「本件プライベートサーバー」と言います）上で商品の実行ファイルを頒布する許可が含まれます。ただし、本件プライベートサーバー上で本ソフトウエア商品にアクセスすることを希望する第三者はなお、本ソフトウエア商品の完全版（本ソフトウエア商品の完全版の実行ファイルを含む）を購入しなければならず、これにより当該第三者には自身のライセンスを付与されます。

    あなたがアクセスを許可した本件プライベートサーバー上の一切のコンテンツにつき、第三者ユーザーがこれを用いていかなる行為を行おうとも、ライセンサーは一切の責任を負わなないということに、あなたは同意します。

    本件プライベートサーバーの使用、または当該本件プライベートサーバーを用いて作成あるいは頒布されたコンテンツの使用に際し、以下の非独占的条件を順守しなくてはなりません。

      •オリジナルなものでなければならず、いかなる第三者の知的財産権をも侵害しないこと
      •アクセス元の法域の法律に違反しないこと
      •不快、わいせつ、軽蔑的、差別的素材を使用しないこと
      •誤導的または欺罔的な素材を使用しないこと
      •虐待またはいじめを促すもの、あるいは第三者またはライセンサーの評判を損なう素材を使用しないこと
      •広告を含まず、またゲーム内通貨の購入に現実世界の金銭を請求しないこと
      •ライセンサーによって提示または認可されたサーバーならびに素材のように振る舞わないこと

    明確にする目的で記すと、あなたが本件プライベートサーバーで利用できるようにする全コンテンツについては、あなたが作ったものか否か、および／またはあなたが許可して本件プライベートサーバーを利用する第三者が利用できるようにしたものか否かを問わず、あなたが引き続き責任を負うものとします。この目的のため、あなたは本ソフトウエア商品を本件プライベートサーバー上でホストするための権利を全面的に有していること、本書の条件に従ってサーバーをホストすること、ならびにあなたが提供することに同意した本件プライベートサーバーを使用するための許可及びライセンスを、本書に定める条件に従いライセンサーおよび第三者に付与する権利を有していることを、あなたはライセンサーに対し表明および保証します。