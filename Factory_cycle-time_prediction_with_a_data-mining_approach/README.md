# article-research

##Factory_cycle-time_prediction_with_a_data-mining_approach
Yarı iletken endüstrisinde çevrim süresinin önemi, müşteriye verilecek teslim tarihinin belirlenmesi, kaynakların planlanması ve beklenen iş tamamlamaları için eylemlerin zamanlanması açısından vurgulanmış.

Tahmin Modeli Oluşturma

Tarihsel veriler, çevrim süresi için öngörücü bir model oluşturmak amacıyla kullanılabilir.
Bu modeller, iş devam eden ürün (WIP), belirli operasyonlardaki iş yükü, parti önceliği, ürün tipi gibi ölçülen ve hesaplanan süreç metriklerine dayanır.
Yöntemin geliştirilmesi ve sürdürülmesi nispeten kolaydır

Clustering, K-Nearest Neighbors, Regression Trees yöntemleri kullanılmıştır.

###Kümeleme (Clustering)
Tanım: Bu yöntem, benzer özelliklere sahip partileri gruplar halinde toplar ve ardından her kümedeki ortalama döngü süresini tahmin olarak kullanır. Benzerlik ölçüsü genellikle hedef partinin ve tarihsel partilerin tahmin edici değerleri arasındaki Öklid mesafesidir.
Avantajları: Fiziksel benzer partiler kavramıyla uyumludur. Küme ataması Öklid mesafesine dayandığında, çoklu adımların tahmini tek bir küme seti kullanılarak yapılabilir.
Dezavantajları: Optimal küme sayısını belirlemek için kullanıcı etkileşimi gereklidir. Ürün veya fabrika anahtar özellikleri değiştikçe kümelerin güncellenmesi gerekir.Kategorik ve sürekli verilerin birlikte kullanılması zordur. Kümeler, partilerin nihai döngü süresi dikkate alınmadan oluşturulur.

####Kümelemenin Tanımı ve Kullanımı
Tanım: Kümeleme, benzer özelliklere sahip partileri gruplar halinde bir araya getirme işlemidir. Bu gruplar oluşturulduktan sonra, her kümedeki ortalama döngü süresi, ilgili partiler için tahmin olarak kullanılır.
Benzerlik Ölçütü: Partiler arasındaki benzerlik genellikle Öklid mesafesi kullanılarak ölçülür. Bu mesafe, hedef partinin ve tarihsel partilerin tahmin edici değerleri arasındaki farkı ifade eder.
Çoklu Adım Tahmini: Öklid mesafesine dayalı küme ataması yapıldığında, birden fazla üretim adımının tahmini tek bir küme seti kullanılarak gerçekleştirilebilir.



####Kümelemenin Avantajları ve Dezavantajları
• Avantajları:
Fiziksel Benzerlik: Kümeleme, fiziksel olarak benzer partilerin gruplandırılması kavramıyla uyumludur.
Esneklik: Bir partinin süreç içindeki ilerlemesiyle tahmin edicilerin sayısındaki değişimi kolayca yönetir.
• Dezavantajları:
Kullanıcı Etkileşimi: Optimal küme sayısını belirlemek için kullanıcı müdahalesi gereklidir.
Güncelleme İhtiyacı: Ürün veya fabrika anahtar özellikleri değiştikçe kümelerin güncellenmesi gerekir.
o Veri Tipi Zorluğu: Hem kategorik hem de sürekli verilerin birlikte kullanılması zordur.
o Döngü Süresi Göz Ardı Edilmesi: Kümeler, partilerin nihai döngü süresi dikkate alınmadan oluşturulur.

Özetle, kümeleme, benzer üretim partilerini gruplandırarak döngü süresi tahmini yapmada değerli bir araçtır. Ancak, optimal küme sayısının belirlenmesi ve farklı veri tiplerinin entegrasyonu gibi zorlukları bulunmaktadır. Makalede, CART(Classification and Regression Trees) algoritması ile birleştirildiğinde daha iyi performans gösterdiği belirtilmiştir.

###K-En Yakın Komşular (K-Nearest Neighbors - KNN)
Tanım: KNN, hedef partiye en benzer K sayıdaki tarihsel partiyi bulur ve bu K partinin ortalama döngü süresini tahmin olarak kullanır. Benzerlik, genellikle tahmin edici değerler arasındaki Öklid mesafesi ile ölçülür. Makalede K=10 değeri en iyi tahminleri sağlamıştır.
Avantajları: Tahmin edici değişken uzayındaki aykırı değerlere karşı dayanıklıdır. Genellikle orta sayıda tahmin edici için yüksek tahmin gücüne sahiptir. Eksik değerleri iyi yönetir. Çoklu adımların tahmini, aynı en yakın komşular kullanılarak herhangi bir mevcut adımdan yapılabilir. Modelin güncellenmesine gerek yoktur, çünkü en güncel veriler mevcut komşulara dahil edilir.
Dezavantajları: Kategorik ve sürekli verilerin birlikte kullanılması zordur. Yüksek boyutlu veriler için genellikle iyi performans göstermez. Optimal komşu sayısını belirlemek için kullanıcı etkileşimi gereklidir .



KNN'nin Tanımı ve Uygulaması
• Temel Prensip: KNN algoritması, hedef partiye en benzer K sayıdaki tarihsel partiyi (komşuyu) bulur ve bu K komşunun ortalama döngü süresini hedef partinin tahmini döngü süresi olarak kullanır.
• Benzerlik Ölçütü: Partiler arasındaki benzerlik, genellikle tahmin edici değerler arasındaki Öklid mesafesi kullanılarak ölçülür.
• Optimal K Değeri: Makalede, K=10 değerinin en iyi tahminleri sağladığı belirtilmiştir.
• Çoklu Adım Tahmini: Aynı en yakın komşular kullanılarak herhangi bir mevcut adımdan birden fazla adımın tahmini yapılabilir.
• Model Güncellemesi: Modelin güncellenmesine gerek yoktur, çünkü en güncel veriler mevcut komşulara dahil edilir.
KNN'nin Avantajları ve Dezavantajları
• Avantajları:
o Aykırı Değerlere Dayanıklılık: Tahmin edici değişken uzayındaki aykırı değerlere karşı dayanıklıdır.
o Yüksek Tahmin Gücü: Genellikle orta sayıda tahmin edici için yüksek tahmin gücüne sahiptir.
o Eksik Değer Yönetimi: Eksik değerleri iyi yönetir.
o Model Güncelleme Kolaylığı: En güncel veriler mevcut komşulara dahil edildiği için modelin sürekli güncellenmesine gerek kalmaz.
• Dezavantajları:
o Veri Tipi Zorluğu: Hem kategorik hem de sürekli verilerin birlikte kullanılması zordur.
o Yüksek Boyutlu Veri Performansı: Yüksek boyutlu veriler için genellikle iyi performans göstermez.
o Kullanıcı Etkileşimi: Optimal komşu sayısını (K) belirlemek için kullanıcı etkileşimi gereklidir
KNN, yarı iletken üretim ortamlarında döngü süresi tahminleri için sağlam bir yöntem sunar. Özellikle aykırı değerlere karşı dayanıklılığı ve model güncelleme kolaylığı önemli avantajlardır. Ancak, farklı veri tiplerini bir arada kullanma ve yüksek boyutlu verilerle başa çıkma konusunda zorlukları bulunmaktadır.

###Regresyon Ağaçları (Regression Trees)
Tanım: Regresyon ağaçları, özyinelemeli ikili kurallara dayalı tahminler oluşturur. Ağacın son düğümü (yaprak), oluşturulan kurallar serisine göre o düğüme ait tüm verilerin ortalamasıdır. Bölme kuralları, kareli kayıp fonksiyonunu minimize ederek oluşturulur. Makalede CART algoritması kullanılmıştır.
Avantajları: Hem kategorik hem de sürekli verileri iyi yönetir. Eksik değerleri iyi yönetir. Tahmin edici değişken uzayındaki aykırı değerlere karşı dayanıklıdır. Tahmin edici değişkenlerin önemine dair bilgi sağlar. Hızlı ve basittir. Optimal ağaç boyutunun otomatik olarak belirlenmesini sağlar. Modelin yeniden hesaplanması hızlı ve kolaydır.
Dezavantajları: Ağaç yapısının yüksek varyansı vardır .Tahmin edilecek her adım için ağacın oluşturulması gerekir. Fabrika ve ürün anahtar özellikleri değiştikçe ağaçların güncellenmesi gerekir.



Regresyon Ağaçlarının Tanımı ve Uygulaması
• Temel Prensip: Regresyon ağaçları, özyinelemeli ikili kurallara dayalı tahminler oluşturur. Ağacın son düğümü veya yaprağı, o düğüme ait tüm verilerin ortalamasıdır.
• Kural Oluşturma: Bölme kuralları, kareli hata fonksiyonunu minimize ederek oluşturulur. Makalede, CART algoritması varsayılan kriterlerle kullanılmıştır.
• Model Güncellemesi: Ürün veya fabrika anahtar özellikleri değiştikçe ağacın güncellenmesi gerekir.
• Çoklu Adım Tahmini: Her adım için ayrı bir ağaç oluşturulması gerektiğinden, birden fazla adımın tahmini için ayrı ayrı ağaçlar inşa edilmelidir.
Regresyon Ağaçlarının Avantajları ve Dezavantajları
• Avantajları:
o Veri Tipi Yönetimi: Hem kategorik hem de sürekli verileri iyi bir şekilde ele alır.
o Eksik Değer Yönetimi: Eksik değerleri iyi yönetir.
o Aykırı Değerlere Dayanıklılık: Tahmin edici değişken uzayındaki aykırı değerlere karşı dayanıklıdır.
o Yorumlanabilirlik: Ağaç yapısı, önemli tahmin edici değişkenler hakkında bilgi sağlar ve hızlı ve basittir.
o Otomatik Optimal Ağaç Boyutu: Optimal ağaç boyutunun otomatik olarak belirlenmesini sağlar.
o Modelin Hızlı Yeniden Hesaplanması: Modelin hızlı ve kolay bir şekilde yeniden hesaplanmasına olanak tanır.
• Dezavantajları:
o Yüksek Varyans: Ağaç yapısının yüksek varyansı vardır.
o Çoklu Adım Zorluğu: Tahmin edilecek her adım için bir ağaç oluşturulması gerekir.
o Güncelleme İhtiyacı: Fabrika ve ürün özelliklerindeki değişikliklerle ağaçların güncellenmesi gerekir.
Makalede, CART (Classification and Regression Trees) algoritmasının kullanıldığı belirtilmiştir. Regresyon ağaçları, yarı iletken üretiminde döngü süresi tahminleri için esnek ve yorumlanabilir bir yöntem sunar. Özellikle kategorik ve sürekli verileri birlikte ele alabilmesi önemli bir avantajdır. Ancak, her tahmin adımı için ayrı bir ağaç oluşturma ve modelin güncellenmesi gerekliliği gibi zorlukları vardır. Çalışmada, CART'ın en düşük medyan mutlak hatayı ve ortalama mutlak hatayı ürettiği ve kümeleme ile birleştirildiğinde daha da iyi performans gösterdiği sonucuna varılmıştır.

###Yarı İletken Üretiminde En İyi Performans Gösteren Yöntem ve Önerilen Çözüm###
Makalede, yarı iletken üretiminde döngü süresi tahmini için çeşitli veri madenciliği algoritmaları karşılaştırılmış ve "Regresyon Ağaçları" (Regression Trees) yönteminin, özellikle "Kümeleme" (Clustering) ile birleştirildiğinde en iyi performansı gösterdiği belirtilmiştir.
Yöntemlerin Karşılaştırılması ve Sonuçlar
• En Düşük Hata Oranı: Çalışmada, "Regresyon Ağaçları (CART)" algoritmasının en düşük medyan mutlak hatayı (0.042) ve ortalama mutlak hatayı (0.09) ürettiği tespit edilmiştir [1] [2].
• Kümeleme ile Kombinasyon: CART'ın "Kümeleme" ile birleştirildiğinde (CART in Cluster) performansının daha da iyileştiği, medyan mutlak hatanın 0.036'ya ve ortalama mutlak hatanın 0.06'ya düştüğü gözlemlenmiştir [1] [2]. Bu kombinasyon, diğer yöntemlere kıyasla en düşük hata oranlarını sağlamıştır [1].
• KNN ve Sinir Ağları Performansı: K-En Yakın Komşular (KNN) yönteminin, K=5 için 0.070 medyan mutlak hata ve K=10 için 0.078 medyan mutlak hata ile regresyon ağaçlarından daha yüksek hata oranlarına sahip olduğu belirtilmiştir. Sinir Ağları'nın medyan mutlak hatası ise 0.085 olarak kaydedilmiştir [1].
Önerilen Çözüm ve Robustluk
• Regresyon Ağaçlarının Avantajları: Regresyon ağaçları, hem kategorik hem de sürekli tahmin edici değişkenleri iyi bir şekilde ele alabilen esnek bir araç sunar [3]. Ayrıca, önemli değişkenleri tanımlama ve partiler arasındaki benzerliği belirleme yeteneği açısından avantajlıdır [3].
• Aykırı Değer Yönetimi: Üretim ortamlarında yaygın olan gürültülü veriler için, regresyon ağacı tahmincisinin robustluğu ele alınmıştır. Düğüm ortalaması yerine düğüm medyanının kullanılması, tahminleri iyileştirmiştir [4].
• Model Güncelleme Kolaylığı: Karar ağacı modelinin bir diğer avantajı, proses değişikliklerini yansıtmak üzere hızlı ve kolay bir şekilde yeniden oluşturulabilmesidir [5].
Sonuç olarak, yazarlar, yarı iletken üretiminde döngü süresi tahmini için Regresyon Ağaçları'nın (özellikle CART algoritmasının) en uygun çözüm olduğunu belirtmişlerdir. Bu yöntem, özellikle kümeleme ile birleştirildiğinde en iyi performansı sergilemiş, aykırı değerlere karşı robustluğu ve modelin kolayca güncellenebilir olması gibi pratik avantajlar sunmuştur.

