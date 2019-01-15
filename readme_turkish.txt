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

Talimatlar:

    1. "pk_dedicated_server.exe" dosyasını başlatın - bir günlük dosyası, bir yapılandırma dosyası ve bir kayıt verileri klasörü oluşturulur.
    2. Yapılandırma dosyasını kurmak için "pk_dedicated_server.exe" dosyasını kapatın.
    3. Sunucuyu kurmak için "server_config.json" dosyasını bir metin düzenleyicide açın.
       TÜM GİRİŞLER ASCII VEYA UTF-8 BİÇİMİNDE OLMALIDIR!
    4. Aşağıdaki ayarlar görüntülenebilir veya değiştirilebilir:
        a. basicServerData
            i. name: Özel sunucunuzun göstereceği ad.
            ii. ipv4: Özel sunucunuzun yerel ağ IP adresidir. 0.0.0.0 adresi, ana bilgisayarın tüm yerel ağ trafiğini dinlemesine olanak tanır. Sunucunuzu spesifik bir ağ kartında veya arayüzde çalışmak üzere ayarlamadığınız sürece bu adresi değiştirmeniz muhtemelen gerekli olmayacaktır.
            iii. port: Özel sunucunun bağlantı noktasıdır. Güvenlik duvarınız/yönlendiriciniz gerektirmediği sürece veya birkaç sunucuyu aynı bilgisayarda çalıştırmak istiyorsanız (bu durumda her bir sunucu için ayrı bir bağlantı noktası gerekir), bağlantı noktasını değiştirmemenizi öneririz.
            iv. saveFolderPath: Kayıt verilerinin yazılacağı konumdur. Birden fazla sunucu örneğini çalıştırmak istiyorsanız bu konumun değiştirilmesi gerekir.
        b. universeSize: (Small/Normal/Large) Özel sunucunun evren boyutudur.
        c. hideConsoleWindow: (true/false) Bu, konsol penceresini gizler. Bu seçenek etkinleştirildiğinde sunucu yalnızca görev yöneticisinden sonlandırılarak kapatılabilir.
        d. admins/users/guests
            i. Credentials
                • password: Özel sunucunuza erişmek için farklı kullanıcı gruplarının kullanacağı parolalar seçin. Farklı parolalar ve izinlerle ayarlanabilecek üç kullanıcı grubu (yönetici, kullanıcılar ve misafirler) bulunur. Oyunculara yalnızca sahip olmalarını istediğiniz kullanıcı grubu izinlerine ilişkin parolaları verin ve yönetici parolanızı gizli tutun!
            ii. canLogin: (true/false) Belirli bir kullanıcı grubunun oturum açıp açamayacağını belirtir.
            iii. canKickPlayers: (true/false) Belirli bir kullanıcı grubunun başka oyuncuları sunucudan atıp atamayacağını belirtir.
            iv. canModifyWorld: (true/false) Belirli bir kullanıcı grubunun blokları/özellikleri ekleme/çıkarma işlemi gerçekleştirip gerçekleştiremeyeceğini belirtir.
            v. canInteractWithLockables: (true/false) Belirli bir kullanıcı grubunun sandıklarla etkileşime geçip geçemeyeceğini belirtir. Ayrıca sandıkların çıkarılmasını önleyebilmek için canModifyWorld ile birlikte kullanılmalıdır.

    5. Özel sunucuyu yeni ayarlarıyla başlatmak için "pk_dedicated_server.exe" dosyasını yeniden başlatın.
    6. Özel sunucunuz bir yönlendiricinin arkasında bulunuyorsa (genellikle bu durum geçerlidir), oyun verilerinin ana bilgisayarınıza gönderildiğinden emin olmak için yönlendiricinizin bağlantı noktası yönlendirme ayarlarını düzenlemeniz gerekir. Yönlendiricinizin yönetici sayfasına gidip bu sayfada Bağlantı Noktası Yönlendirme ayarlarını bularak söz konusu işlemi gerçekleştirebilirsiniz. Burada, mümkünse yeni bir sunucu (veya müşteri hizmeti) eklemeyi deneyebilirsiniz. Yeni kuralı ayarlamak için kuralı adlandırmanız istenecektir. İstediğiniz adı seçebilirsiniz ancak kolaylık için "portalknights" adını öneririz. Tür "UDP" olmalıdır. Yapılandırma dosyasında bağlantı noktasını değiştirmediyseniz tüm bağlantı noktaları (dahili ve harici) için "16365" kullanın; değiştirdiyseniz bağlantı noktalarının o dosyada yapılandırdıklarınızla eşleştiğinden emin olun. "output IP" (çıkış IP'si) veya "server IP" (sunucu IP'si) için yerel ağ adresinizi girin. Komut İsteminden ipconfig komutunu çalıştırarak yerel ağ adresinizi bulabilirsiniz. Başka herhangi bir bilgi istenirse boş bırakıp devam edin. Bu işlemi gerçekleştirirken zorlanırsanız lütfen yardım için https://portforward.com/ adresini ziyaret edin. Oyunu barındıran bilgisayar için statik IP ayarlamadıysanız yerel ağ adresinin değişebileceğini (ve bağlantı noktası yönlendirme kurallarını geçersiz kılabileceğini) unutmayın. Bilgisayarınız için nasıl statik IP ayarlayabileceğinizi belirlemek üzere yönlendiricinize ait belgelere bakın.

    7. Sunucuya erişebilmesini istediğiniz kullanıcılara, bir kullanıcı grubu parolasıyla birlikte harici IP adresinizi gönderin. Bağlantı noktası yönlendirme için girdiğiniz IP adresinin, harici IP adresiniz olmayacağını unutmayın; bu adres yerel ağ IP adresiniz olacaktır. Kullanıcıların katılması için gereken harici IP adresini bulmak üzere http://whatismyip.host/ gibi bir adresi ziyaret etmeniz gerekir. Kullanıcılara, IP v6 (IP adresi, xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx biçiminde değil, xxx.xxx.xxx.xxx biçiminde görünmelidir) adresinizi değil, IP v4 adresinizi gönderdiğinizden emin olun.

    Aynı bilgisayara birden fazla sunucu kurarken her bir sunucuya farklı yapılandırmalar oluşturmak ve her birinin yapılandırma dosyasını buna göre uyarlamak için aşağıda sunulan Komut İstemi argümanlarını kullanın.
        
    Argümanlar:
        a. -config myConfig.json: Sunucuyu kurmak için myConfig.json yapılandırma dosyası kullanılır.

                      i. Bu adla bir dosya yoksa bu adı taşıyan bir varsayılan yapılandırma dosyası oluşturulur. Not: Yapılandırma dosyalarınız için istediğiniz adı verebilirsiniz; "myConfig.json" yalnızca örnektir.

        b. -log mylogfile.log: Günlük dosyası belirtilen dosyaya yazılır.

            Örnek:
        pk_dedicated_server -config myOwnConfig.json -log testServer.log
        yapılandırmasını myOwnConfig.json dosyasından okuyan bir özel sunucu başlatır ve günlük çıkışını testServer.log dosyasına yazar.


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
    
    
Lisans:
    ÖZEL VEYA BAĞIMSIZ SUNUCULARIN KULLANIMI

    Yazılım Ürününü satın alarak ve kullanarak, yalnızca Yazılım Ürününü, ürünün yürütülebilir dosyasını özel veya bağımsız sunucular (bundan sonra "Özel Sunucular" olarak anılacaktır) üzerinden dağıtma iznini içeren işbu Lisans Sözleşmesinin şartlarına uygun olarak kullanmak için lisans izni elde edersiniz. Ancak bu izin, Yazılım Ürününe Özel Sunucu üzerinden erişmek isteyen tüm üçüncü tarafların, üçüncü tarafa kendi lisans hakkını sağlayacak olan tam sürüm Yazılım Ürününün yürütülebilir dosyası dahil, Yazılım Ürününün tam sürümünü satın alması koşuluyla geçerlidir.

    Lisans Verenin, üçüncü taraf kullanıcıların erişim izni verdiğiniz herhangi bir Özel Sunucu üzerinde bulunan herhangi bir içerikle yaptıkları için hiçbir yükümlülüğü olmadığını kabul etmiş sayılırsınız.

    Bir Özel Sunucunun herhangi bir kullanımı ya da böyle bir Özel Sunucu kullanılarak oluşturulan veya yayılan herhangi bir içerik, aşağıdaki münhasır olmayan gerekliliklere bağlı kalmalıdır:

      • Orijinal olmalı ve herhangi bir üçüncü tarafın fikri mülkiyet haklarını ihlal etmemelidir
      • Erişilebileceği yetki bölgelerinin yasalarını ihlal edemez
      • Şiddet, pornografi, hakaret, ayrımcılık içeren materyaller kullanmamalı
      • Yanlış yönlendirici veya aldatıcı materyaller kullanmamalı
      • İstismar veya zorbalık içeren ya da bir üçüncü tarafın veya Lisans Verenin itibarını zedeleyecek materyaller kullanılmamalı
      • Reklam içermemeli veya oyun içi para birimi olarak gerçek nakit ücretlendirilmemeli
      • Lisans Veren tarafından sunulan veya onaylanan bir sunucu ya da materyal görevi göremez

    Sizin tarafınızdan oluşturulmuş olsun ya da olmasın, Özel Sunucu üzerinden kullanıma sunduğunuz ve/veya üçüncü taraflarca Özel Sunucunuzdan yararlanarak kullanıma sunulmasına izin verdiğiniz tüm içeriklerle ilgili yükümlülüğün size ait olacağını lütfen unutmayın. Bu amaçla, Lisans Verene Yazılım Ürününü Özel Sunucunuzda barındırmak için tam yetkili olduğunuzu, bunu işbu Sözleşmenin şartlarına uygun olarak yapacağınızı ve yukarıda belirtildiği gibi Özel Sunucuları kullanarak Lisans Verene ve tüm üçüncü taraflara sağlamayı kabul ettiğiniz izin ve lisansları verme hakkınız olduğunu beyan ve garanti edersiniz.