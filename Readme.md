![photo](https://getcomposer.org/img/logo-composer-transparent3.png)
# Composer Nedir ?
Php için geliştirilmiş bir bağımlılık yönetim aracıdır.Projemizde kullanmak istediğimiz php kütüphanesinin ihtiyacı olan php dosyalarını projeye dahil edilmesini sağlayan,çeşitli güncellemeleri otomatik yapabilen bir araçtır.Php'de Composer'ın yaptığı işlemleri Ruby'de bundler,NodeJs'de Npm,Java'da Maven yapmaktadır.

# Neden İhtiyaç Duyulur ?
Geliştirdiğimiz projelerimizde birçok kütüphaneye ihtiyaç duyarız ve bu kütüphanaleri projemize ekleriz.Bu kütüphaneler sürekli geliştiriliyor,güvenlik açıkları gideriliyor performans artırıcı güncellemeler yapılıyor bir üst versiyonları çıkarılıyor bizimde bu güncellemeleri almamız gerekiyor aksi takdirde projemizde güvenlik açığı oluşabilir,performans açısından istediğimizi alamayabiliriz,eski versiyonu kullandığımız için bu teknolojide geride kalmış olabliriz.Birden fazla kütüphane kullandığımız için bu kütüphaneleri tek tek projemize eklemek veya projede bulunana kütüphaneleri güncellmek biraz zahmetli olucaktır işte tam burada devreye composer giriyor. Biz ihtiyacımız olan kütüphaneyi veya güncellemesini istediğimiz kütüphaneyi composer'a belirtiyoruz composer bizim yerimize istediğimiz kütüphaneyi projemize ekliyor veya güncelliyor.Bir örnek ile gözümüzde canlandıralım Bizim Php ile yazdığımız kod başka birinin Bilgisayarın'da çalışmayalbilir bu sorun Php versiyonundan kaynaklanıyor olabilir bizim kodumuz Php 5.3 üstünü destekliyordur ancak o kişi Php 5.2 kullanıyır olabilir eğer biz projeye Composer aracını yüklemişsek o kişi Composer'ı kullanarak versiyon sorununa takılmadan projeyi çalıştırabilir.

# Composer Kurulumu
### 1-Linux
- Bilgisayarınız da curl yüklü ise; 

    ```
    curl -sS https://getcomposer.org/installer | php
    ```
- Curl yüklü değil ise;
 
    ```
    php -r "readfile('https://getcomposer.org/installer');" | php
    ```
- composer.phar dosyasını indirdikten sonra sistem dizininin içine taşıyalım;

    ```
    mv composer.phar /usr/local/bin/composer
    ```
    
### 2-Windows
Windows'a Composer yüklemek için 
[Composer-Setup.exe](https://getcomposer.org/Composer-Setup.exe) tıklayarak indirip kurabilirisiniz.

# Güncelleme
İhtiyaç duyduğumuz kütüphaneleri güncellemek için yapmamız gereken aşağıdaki komutu çalıştırmak.

```
php composer.phar update
```

![Update](https://github.com/mehmetdik/Php-Composer/blob/master/photo/update.png)

# Nasıl Kullanılır ?
App adında bir projemiz olsun bu projede loglama aracına ihtiyacımız olsun bizde bu ihtiyacımızı karşılaması için monolog kütüphanesini kullanalım.Monolog kütüphanesinin nasıl yükleneceğini görelim.Öncelikle projemizin içine girip şu komutu çalıştıralım
```
composer require monolog/monolog
```
![Monolog](https://github.com/mehmetdik/Php-Composer/blob/master/photo/monolog.png)

Composer'a monolog kütüphanesine ihtiyacımız olduğunu söyledik composer'da projemize monolog kütüphanesini eklemiş oldu.Komut çalıştıktan sonra uygulamamızın içine bakıyoruz ve aşağıdaki dosyaların oluştuğunu görüyoruz.

![file](https://github.com/mehmetdik/Php-Composer/blob/master/photo/m.png)

composer.json dosyasını inceleyelim.

### composer.json dosyası;
```
}
    "require": {
        "monolog/monolog": "^1.16"
    }
}
```
Dosyanın içine baktığımızda **require** anahtar kelimesini görüyoruz bu anahtar kelimenin içinde ihtiyacımız olan kütüphane ve özellikleri bulunmakta.

### Vendor

![vendor](https://github.com/mehmetdik/Php-Composer/blob/master/photo/vendors.png)

Bu klasörde composer tarafından indirilen sınıflar ve composer'ın autoload dosyası bulunmaktadır.Composer çalıştırıldığında otomatik olarak oluşturulur.autoload.php isminde bir dosya olduğunu gördük bu dosya yardımıyla projelerimizde kütüphaneleri kullanabileceğiz.Şimdi bu yüklediğimiz dosyaları yani kütüphaneyi projemizin içinde nasıl kullanacağımızı görelim.
index.php adında bir dosya oluşturalım.index.php dosyasının içine aşağıdaki kodları yazalım.

![icerik](https://github.com/mehmetdik/Php-Composer/blob/master/photo/indexiçerik.png)

Şimdi index.php içine yazdığımız kodu çalıştıralım bakalım kütüphaneyi kullanabiliyor muyuz.Konsol'a aşağıdaki komutu yazalım.

```
php index.php
```

Projenin içerisine baktığımız da logs adında bir klasör daha oluştuğunu görüyoruz.Logs dosyasının içinde de logdosyam.log adında bir dosya oluştuğunu görüyoruz bu dosyayı açalım bakalım içinde ne var;

![log](https://github.com/mehmetdik/Php-Composer/blob/master/photo/logs.png)


Loglarımızın bizim istediğimiz gibi tutulup txt dosyasına yazıldığını, yüklediğimiz monolog kütüphanesinin sorunsuz çalıştığını ,composerın bize nasıl yardımcı olduğunu işimizi kolaylaştırdığını görmüş olduk.






