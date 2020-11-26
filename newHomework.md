# DEVELOPER SUMMIT 2020'deki yazılım konferanslarından ilginizi çekenlerin özetlerini çıkarmaya çalışınız. 
*Vize haftasında olduğum için haftasonu vakit ayıramadım ama sanırım kayıtlar paylaşılacakmış, paylaşılınca izleyip eklemeyi düşünüyorum :)*

# SQLite ve LocalDB kavramlarını karşılaştırınız. 
### LocalDB

LocalDB , kullanıcı modunda isteğe bağlı ve çalışır durumda başlayan SQL Server Express veritabanı altyapısının hafif bir sürümüdür. LocalDB, veritabanlarıyla .mdf dosyaları olarak çalışmanıza olanak sağlayan SQL Server Express özel bir yürütme modunda çalışır. 

SQL Server Express üretim Web uygulamalarında kullanılması önerilmez. LocalDB, IIS ile çalışmak üzere tasarlanmadığı için bir Web uygulamasıyla üretim için kullanılmamalıdır. Ancak, bir LocalDB veritabanı SQL Server veya SQL Azure kolayca geçirilebilir. 

LocalDB kurulumu, SQL Server Veritabanı Motorunu başlatmak için gereken minimum dosya kümesini kopyalar. LocalDB kurulduktan sonra, özel bir bağlantı dizesi kullanarak bir bağlantı başlatabilirsiniz. Bağlanırken, gerekli SQL Server altyapısı otomatik olarak oluşturulur ve başlatılır, bu da uygulamanın veritabanını karmaşık yapılandırma görevleri olmadan kullanmasını sağlar. 

SQL Express LocalDB , tam SQL Server Express motorunu kullanır, ancak bir SQL Server hizmetinin çalıştırılmasını veya kurulmasını gerektirmez. 

LocalDB ikili dosyaları ayrı bir yükleyici ile veya SQL Server Express'in bir parçası olarak kurulabilir. 

LocalDB örnekleri kullanıcıya göre yalıtılmıştır. 

LocalDB sistem veritabanları, kullanıcı profilindeki AppData'nın derinlerine gömülüdür. Kullanıcı veritabanları için varsayılan konum, kullanıcı profilinin köküdür. 

Bir SQL Server LocalDB yüklemesi de yaklaşık 140 MB alır ve uygulamanız web üzerinde dağıtılırsa indirme boyutunu artırır. 

 ### SQLite

Sqlite, bir veritabanı kütüphanesidir. Kullanımı ve kurulumu oldukça kolaydır. Kullanmak için kurulum yapmanızı gerektirmez. Herhangi bir kurulum prosedürü yoktur. 

Sqlite kullanımı için bir yöneticinin yeni bir veritabanı örneği oluşturmasına veya kullanıcılara erişim izni vermesine gerek yoktur. 

Sqlite herhangi bir ana sunucu işlemi gerektirmez. Veritabanına erişmek için sunucuya istek göndermek ve sonuç almak için ara işlem iletişimi kurmak gerekmez. Bu program doğrudan diskteki veritabanı dosyalarını okur ve yazar. 

Sqlite disk dosyasını okuyabiliyorsa, veritabanında bulunan herhangi bir şeyi de okuyabilir. Disk dosyası ve dizini yazılabilir durumda ise, bu programı kullanarak veritabanındaki her şeyi değiştirebilirsiniz. Veritabanı dosyalarını bir USB’ye kopyalayabilir ya da e-posta ile paylaşabilirsiniz. Dosyalara erişmek son derece kolaydır. Elbette tüm bu işlemleri kolay ve hızlı bir şekilde yaparken verilerin güvenliğini sağlamak da son derece önemlidir. 

Boyut düşünüldüğünde, bir Sqlite kütüphanesi 500 KiB’den küçüktür. Daha fazla yer saklamak için gereksiz özellikler devre dışı bırakılabilir. Kütüphanenin boyutu 300 KiB’ye kadar düşürülebilir. Diğer veritabanlarının büyük bir çoğunluğunun boyutu bundan büyüktür. 

Sqlite kaynak kodları okunabilir durumdadır. Standart programlar tarafından erişilebilir ve okunabilir olacak şekilde tasarlanmıştır. Ayrıca Sqlite için kaynak kodları kamu malıdır. Herkes erişebilir ve okuyabilir. 

 

# Lazy Loading kavramı hakkında temel bir araştırma yapınız. 

> Lazy Loading (aynı zamanda **asynchronous loading** olarak da bilinir ), bir nesnenin başlatılmasını ihtiyaç duyulduğu noktaya kadar ertelemek için bilgisayar programlamasında ve çoğunlukla web tasarımı ve geliştirmede yaygın olarak kullanılan bir tasarım modelidir . Düzgün ve uygun şekilde kullanılırsa, programın işleyişinde verimliliğe katkıda bulunabilir. Bu, ağ içeriğine erişildiği ve web sayfalarında olduğu gibi başlatma sürelerinin minimumda tutulduğu kullanım durumlarında idealdir. Lazy Loading tersi, **eager loading**’ dir. Tembel Yükleme, web sayfalarının daha hızlı yüklenmesini sağlamak için yalnızca ihtiyaç duyulduğunda görünmelerini sağlamak için web'deki görsellerde büyük ölçüde kullanılır. 

Lazy Load daha çok e-ticaret sitelerinde kullanılmaktadır. Görsel listelemenin yoğun olarak kullanıldığı e-ticaret sitelerinde; oluşan görsel fazlalığı site hızını olumsuz etkiler. Bunun ana nedeni sayfaya girildiğinde tüm görsellerin aynı anda sunucudan çağrılması ve yüklenmesidir. Ancak Lazy Load özelliği kullanıldığı zaman sayfada listelenen ürünlerin görselleri aşağı doğru inildikçe yani gerek duyuldukça açılır. Bu şekilde site hızında artış sağlanır. Lazy Load özelliği kullanılmadığında; ürün listeleme yapıldığı zaman; aşağı doğru gidildiğinde tüm fotoğraflar sayfa daha ilk açıldığında yüklenmeye çalışır ve o sayfada kaç ürün varsa tamamı aynı anda sunucudan çağırılır ve yüklenir. Bu durum site hızını düşürürken aynı zamanda sitenin açılmasını ve istediği ürüne ulaşmayı bekleyen ziyaretçilerin siteden çıkmasına neden olmaktadır. 

### Lazy Load özelliğinin faydaları nelerdir? 

- Site hızı ve performansı yükselir. 

- Sayfaların daha hızlı açılması hemen çıkma oranlarını düşürür. Bu şekilde SEO çalışmaları da olumlu yönde etkilenir. 

- Siteye giren kullanıcı tüm resimlerin açılmasını beklemez. Bu durumda hemen çıkma oranlarının yükselmesinin önüne geçilmiş olur. 

- Aşırı kaynak kullanımı yerine sadece internet kullanıcısının görüntülediği alanlar sunucudan yüklenir. Bu sayede ihtiyaç dışı kaynak kullanımının önüne geçilmiş olur. 

- İçerik hareketlerini geliştirmeye yardımcı olurken kullanıcı deneyimini iyileştirir ve geliştirir. 

- SQL sorgularının gereksiz şekilde çalıştırılması engellenir. 

- Dynamically Loading, kullanıcının farklı sayfalara geçmeden ya da tarayıcıların yenilenmesini beklemeden daha fazla içerik keşfetmesini sağlar. 

### Dikkat edilmesi gereken noktalar: 

- Lazy Load; sitenizde yoğun olarak görsel kullanılıyorsa yararlıdır. İçerik açısından daha yoğun olan sitelerde kullanılması önerilmez. 

- Bu özellik dahili bir tarayıcı özelliği değil bir JavaScript dosyasının kullanımını gerektirir. Bu da geliştirme süreci ve test açısından süreci uzatabilir. 

- Yanlış bir kurgu ziyaretçilerin görselleri hiç görüntüleyememesine neden olabilir. Bu nedenle hatasız bir yapı kurulmasına önem verilmelidir. 

- Görseller mümkün olduğunca ziyaretçilerin ekranına düşerken hızlıca yüklenmelidir. Sayfada aşağıya inilmesine rağmen yüklenmesi gereken görselin 3 saniye içerisinde yüklenmemesi durumunda kullanıcı deneyimi olumsuz etkilenecektir. 

- Arka plan renkleri, yükleme animasyonları ya da küçük resim ön izlemeleri ile kullanıcıya o alanlara görsel yükleneceğinin bildirilmesi gerekmektedir. 

 
 ### KAYNAKÇA

https://www.sempeak.com/blog/lazy-load-nedir-neden-kullanilmali  

https://www.itwriting.com/blog/5364-microsoft-localdb-another-option-for-local-databases.html  

https://docs.microsoft.com/tr-tr/aspnet/mvc/overview/getting-started/introduction/creating-a-connection-string  

https://www.isimtescil.net/bilgibankasi/sqlitein-tum-avantajlar-ve-dezavantajlar  

https://en.wikipedia.org/wiki/Lazy_loading  

 

 

 

 

 
