Bu eğitime ilk olarak Web uygulama güvenliği ve Web sızma ile başlayacağım. Uygulama güvenliği üzerindeki zafiyetleri tespit etmek ve bu zafiyetlerin kapatılmasına yönelik önlem almaktır.

Buradaki konularımız:
-Web uygulama güvenliğine giriş.
-Lab ortamının kurulumu & FoxyProxyEklenti kurulumu
-SQL injection
-Cross Site Scripting(XSS)
-Insecure Direct Object References 
-Command Injection 
-File Inclusion 
-Brute Force testi



-Web uygulama güvenliği: Web siteleri, web uygulamaları, web servislerinin(rest api ve soap api gibi) güvenliğini kapsar.

Neden Web uygulamalarına yönelik saldırı yapılıyor?: kurumsal birçok şirketin dışarıya bakan web uygulamaları var ve kullanıcıyla etkileşimli bir yapıya sahiptirler.Bu kurumsal firmaları korumak için siber güvenlik ürünlerine bir sürü yatırım yapılıyor.

Web uygulamaları: e-devlet, yemek sipariş, mobilya- kıyafet e-ticaret siteleri üzerinden işlemlerimzi yapabiliyoruz.
Web uygulamaları: SQL injection ve XSS gibi zafiyetler bulundurabilirler.

Web uygulamalarının güvenliği neden önemli çünkü:
-Sunucudan içeri olan ilk giriş kapısıdır.

Sunucu(Server): Sürekli ulaşılabilir olmaları için kesintisiz çalışacak şekilde tasarlanan, geniş güvenlik, jenaratör ve soğutma önlemleriyle veri merkezlerinde korunan, 7/24 internet bağlantısı olan gelişmiş ve dayanıklı bilgisayarlara sunucu denir.

Farklı türleri olsada en tanınmış sunucular, web sitelerinin içeriğini depolayan ve internet kullanıcılarına bu içeriği sunarak sitelerin yayınlanmasını 
sağlayan web sunuculardır.

Bir web sitelerinin görüntülenebilmesi için bir web sunucusunda depolanması gerekir.

-Sql İnjection nedir: Uygulamadan alınan parametrelerin (girdi) doğrudan veritabanı sunucusuna gönderilmesi sonucu veritabanı üzerinde izinsiz 
sorgular çalıştırılabilir.
İkinci olarak, uygulama seviyesinde yeterli girdi denetimi yapılmadığında veya Veritabanı sunucusunda gelen sorguların denetimi yapılmadığında 
SQL i gerçekleştirebilir.

* Sql injectionın sebepleri: Backend veri deposunu hedef alır, düzgün filtrelenmeyen girdilerden faydalanarak veritabanını manipüle etmeyi sağlayan 
kod enjeksiyon atağıdır.
İzinsiz olarak SQL sorgularını çalıştırır.
Yeterli derecede filtre yapılmayan SQL sorgularına ekleme yapabilir.
Saldırgan veri tabanından veri silebilir, veri tabanına veri ekleyebilir veya veri tabanındaki veriyi değiştirebilir.

* Sql injection tespiti: Web uygulamasındaki cookie, http başlıkları(http header dahil) da dahil olmak üzere bütün girdi noktaları bulunur.
Veri tabanından veri aldığı düşünülen bütün girdi noktaları bulunur.(Arama sözcükleri ve login formları)
Manuel olarakta saldırabilir, otomatik tool araçlarla da saldırabilir.

bu kısımda Sql İnjection saldırıları nasıl yapılıyor ve çeşitleri nelerdir bunu öğreneceğiz.

SQLUNIONMETHOD:burada bir web uygulamasında film aratma sekmesinde film aramamız beklenirken, biz kendi sorgularımızı bu arama butonuna yazdığımız zaman 
sisteme kayıt olan kullanıcıların hash li şekilde tutulan password bilgilerine ulaştık.Bunu da yine dictionary attack kullanarak çözebiliriz.
aşağıdaki sorgulardan yararlandık:
SELECT * FROM movies WHERE title LIKE '%man' ORDER BY 7#%'
man' ORDER BY 7#
man' UNION SELECT 1,2,3,4,5,6,7 FROM information_schema.tables WHERE table_schema=database()#
man' UNION SELECT 1,2,3,4,5,6,7 FROM information_schema.tables WHERE table_name='users'#
man' UNION SELECT 1,login, password, 4,5,6,7 FROM users#

SQL INJECTION (GET/SEARCH).

SQLBLINDMETHOD:

SQLMAPKULLANIMI:


*****************************SQL İNJECTİON İS OVER******************

CROSS SİTE SCRİPTİNG (XSS)








