# Explainability driven post-hoc correction enhancing deep neural network performance for job cycle time prediction

## Makalenin Temel Sorusu, Hipotezi, Önemi, Kilit Bulguları, Literatüre Katkısı, Uygulamaları ve Açık Sorular
### Temel Soru ve Çözülmeye Çalışılan Problem
Derin Öğrenme Modellerinin Genelleme Sorunu: Makale, imalat sektöründe iş döngüsü süresi tahmini için kullanılan derin öğrenme (DL) modellerinin, gerçek dünya fabrikalarında sıkça karşılaşılan sınırlı veri setleriyle çalışırken genelleme yeteneklerinin yetersiz kalması sorununu ele almaktadır. Bu durum, modellerin yeni veya farklı senaryolara uyum sağlamakta zorlanmasına ve dolayısıyla tahmin doğruluğunun düşmesine neden olmaktadır.

Veri Kıtlığına Bağlı Zayıf Genelleme ve Aşırı Uyum: Çalışma, derin öğrenme modellerinin karmaşık, veri sınırlı ortamlarda (örneğin, yarı iletken fabrikaları gibi) karşılaştığı zayıf genelleme ve aşırı uyum (overfitting) sorunlarını gidermeyi amaçlamaktadır.
### Ana Hipotez veya Tez
**SHAP Destekli Sonradan Düzeltme Çerçevesi:** Makalenin temel iddiası, SHAP açıklanabilirliğini kullanan bir sonradan düzeltme çerçevesinin, sınırlı veri setleriyle bile derin öğrenme modellerinin iş döngüsü süresi tahminlerindeki doğruluğunu önemli ölçüde artırabileceğidir. 
Bu çerçeve, yanlış tahmin yapma olasılığı yüksek olan yeni işleri hedefleyerek ve bu işlerin kritik giriş özelliklerini SHAP içgörüleriyle ayarlayarak çalışır
### Çalışmanın Önemi
**Operasyonel Mükemmellik İçin Kritik:** Modern imalatta, iş döngüsü süresini doğru bir şekilde tahmin etmek sadece faydalı değil, aynı zamanda operasyonel mükemmellik için de kritiktir. Bu tahminler, üretim planlaması, teslim tarihi ataması, dinamik çizelgeleme ve kaynak tahsisi gibi temel yönetim fonksiyonlarının omurgasını oluşturur. Sınırlı Veri Ortamlarında DL Performansını Artırma: Çalışma, veri kıtlığı durumlarında derin öğrenme modellerinden daha fazla verim almanın pratik bir yolunu sunmaktadır. Gerçek bir yarı iletken fabrikasından alınan 300 işlik bir veri seti üzerinde yapılan testlerde, önerilen çerçeve Kök Ortalama Kare Hatasını (RMSE) %22,5 oranında azaltmış ve DNN'in performansını Random Forests gibi standart karşılaştırma modellerinden daha iyi veya en az onlar kadar iyi bir seviyeye getirmiştir. Bu, karmaşık ve veri sınırlı ortamlarda DL modellerinin güvenilirliğini artırmanın bir yolunu göstermektedir.

**Açıklanabilir Yapay Zeka ile Şeffaflık:** Çalışma, SHAP açıklanabilirliğini kullanarak modelin 'kara kutu' doğasını anlamayı ve tahminlerin neden belirli bir şekilde yapıldığını açıklamayı mümkün kılar 
Bu, modelin kararlarının şeffaflığını artırarak, imalat gibi kritik sektörlerde güven oluşturmaya yardımcı olur.

### Kilit Bulgular
RMSE'de Önemli Azalma: Geliştirilen SHAP destekli sonradan düzeltme çerçevesi, gerçek bir yarı iletken fabrikasından alınan 300 işlik veri seti üzerinde test edildiğinde, Kök Ortalama Kare Hatasını (RMSE) %22,5 oranında düşürmüştür. Bu iyileşme istatistiksel olarak anlamlı bulunmuştur.

**DNN Performansının Artırılması:** Çerçeve, derin sinir ağının (DNN) performansını Random Forests gibi standart kıyaslama modellerinden daha iyi veya en az onlar kadar iyi bir düzeye getirmiştir. Başlangıçta düşük bir R² değeri (0.24) ile zayıf performans gösteren DNN, uygulanan çerçeve ile önemli ölçüde iyileşmiştir.
Hedefe Yönelik Düzeltme Mekanizması: Önerilen çerçeve, tüm yeni işlere genel bir düzeltme uygulamak yerine, yanlış tahmin yapma olasılığı yüksek olan bireysel iş örneklerini seçici ve spesifik olarak hedeflemektedir. Bu, SHAP analizi kullanılarak kritik giriş özelliklerinin ayarlanmasıyla gerçekleştirilir. Bu yaklaşım, modelin tahminlerinin şeffaflığını artırırken, düzeltmenin etkinliğini maksimize eder. 

### Verilerin Ana Tezi Desteklemesi
**Veriler Tezi Destekliyor:** Sunulan grafikler, tablolar ve istatistikler, ana tezi güçlü bir şekilde desteklemektedir. Özellikle, Tablo 6'da farklı yöntemlerin tahmin performanslarının karşılaştırılması, önerilen "DNN + SHAP + global önleyici düzeltme" yönteminin en düşük RMSE (158.6 saat) ve en yüksek R² (0.49) değerine sahip olduğunu göstermektedir. Bu, çerçevenin DNN'in tahmin doğruluğunu önemli ölçüde artırdığını ve geleneksel ML modellerini geride bıraktığını kanıtlamaktadır.

**Deneysel Sonuçların Sağlamlığı:** Yarı iletken fabrikasından alınan gerçek dünya verileri üzerindeki deneysel sonuçlar, çerçevenin DNN modelinin tahmin doğruluğunu %22,5'e kadar başarılı bir şekilde iyileştirdiğini göstermektedir. Bu iyileşme istatistiksel olarak anlamlıdır ve Random Forests gibi klasik kıyaslama modellerine karşı yapılan karşılaştırmalı analizler çerçevenin etkinliğini doğrulamaktadır.
### Beklenmeyen Sonuçlar
**Yerel Düzeltmenin Daha Az Kararlı Performansı:** Çalışma, yerel sonradan düzeltme çerçevesinin performansının küresel düzeltmeye göre daha az kararlı olduğunu belirtmektedir. Bu, belirli imalat veri seti için tüm öznitelikler arasındaki karmaşık etkileşimin, SHAP tarafından belirlenen az sayıdaki en önemli özniteliğin izole edilmiş etkisinden daha kritik olabileceğini düşündürmektedir. Benzerlik eşikleri çok düşük ayarlandığında, mekanizma daha az ilgili örnekleri referans alabilir ve bu da kararsız performansa yol açabilir. Tersine, eşikler çok yüksek ayarlandığında, referans alınacak çok az örnek olur ve düzeltme mekanizması etkisiz hale gelir. 

### Bu Makale Literatüre Ne Kattı?
**SHAP Destekli Post-hoc Düzeltme Çerçevesi:** Bu makale, imalat sektöründe iş döngüsü süresi tahmini için SHAP açıklanabilirliğini kullanan, veri sınırlı ortamlarda derin öğrenme modellerinin genelleme yeteneğini artıran özgün bir "post-hoc" düzeltme çerçevesi sunmaktadır. Bu çerçeve, tüm verilere genel bir düzeltme uygulamak yerine, yanlış tahmin olasılığı yüksek olan bireysel iş örneklerini seçici ve spesifik olarak hedeflemesiyle mevcut yöntemlerden ayrılır. 

**Açıklanabilir Yapay Zeka ile Şeffaflık ve Güven:** Çalışma, SHAP analizini kullanarak derin öğrenme modellerinin "kara kutu" doğasını anlamayı ve tahminlerin neden belirli bir şekilde yapıldığını açıklamayı mümkün kılarak, model kararlarının şeffaflığını artırmaktadır.
Bu, özellikle imalat gibi kritik sektörlerde yapay zeka modellerine olan güveni artırma potansiyeli taşır.

**Veri Kıtlığı Sorununa Pratik Çözüm:** Sınırlı veri setleriyle çalışan gerçek dünya fabrikalarındaki derin öğrenme modellerinin zayıf genelleme ve aşırı uyum sorunlarına pratik bir çözüm sunarak, bu modellerin uygulanabilirliğini artırmıştır.
Gerçek bir yarı iletken fabrikasından alınan verilerle elde edilen %22,5'lik RMSE düşüşü, bu yaklaşımın etkinliğini kanıtlamaktadır.
### Pratik veya Teorik Uygulaması Nedir?
**İmalat Sektöründe Operasyonel Verimlilik:** Bu çalışmanın bulguları, üretim planlaması, teslim tarihi ataması, dinamik çizelgeleme ve kaynak tahsisi gibi temel yönetim fonksiyonlarında iş döngüsü süresi tahminlerinin doğruluğunu artırarak imalat sektöründe operasyonel mükemmelliği doğrudan iyileştirebilir.

**Veri Sınırlı Ortamlarda Yapay Zeka Uygulamaları:** Önerilen çerçeve, sadece imalat değil, aynı zamanda veri toplamanın maliyetli veya zor olduğu diğer sektörlerde de derin öğrenme modellerinin performansını artırmak için kullanılabilir. Bu, sağlık, finans veya lojistik gibi alanlarda veri kıtlığı sorunuyla karşılaşan yapay zeka uygulamaları için değerli bir yaklaşımdır.

**Açıklanabilir Yapay Zeka Gelişimi:** Çalışma, açıklanabilir yapay zeka (XAI) alanındaki gelişmelere katkıda bulunarak, model tahminlerinin şeffaflığını ve anlaşılabilirliğini artırmanın yollarını göstermektedir. Bu, daha güvenilir ve denetlenebilir yapay zeka sistemleri geliştirmek için bir temel oluşturur.
### Açıkta Kalan Sorular Neler?
**Daha Büyük ve Çeşitli Veri Setleri Üzerindeki Ölçeklenebilirlik:** Bu çerçeve, yarı iletken fabrikasından alınan 300 işlik sınırlı bir veri seti üzerinde test edilmiştir. Daha büyük ve daha çeşitli veri setlerinde (farklı imalat türleri veya diğer sektörler) çerçevesinin ölçeklenebilirliği ve genel performansı henüz tam olarak doğrulanmamıştır.

**Farklı Benzerlik Değerlendirme Fonksiyonları:** Mevcut çalışmada kullanılan benzerlik değerlendirme fonksiyonlarının yerine, farklı türdeki benzerlik fonksiyonları veya metriklerinin performans üzerindeki etkisi araştırılabilir.

**Parametre Değerlerinin Sistematik Seçimi:** Çerçeve içindeki parametre değerlerinin (örneğin, benzerlik eşikleri) en uygun şekilde seçilmesi, modelin performansını daha da artırabilir. Bu parametrelerin otomatik ve sistematik olarak optimize edilmesi için daha fazla araştırma yapılması gerekmektedir.

Bu çalışma, derin öğrenme modellerinin imalat ortamlarındaki pratik uygulanabilirliğini artırmak için açıklanabilir yapay zeka tekniklerini kullanarak önemli bir boşluğu doldurmaktadır. Sınırlı veri sorununa hedefe yönelik bir çözüm sunarak, operasyonel verimliliği ve karar alma süreçlerini iyileştirme potansiyeli taşımaktadır. Elde edilen kilit bulgular, bu çerçevenin etkinliğini desteklerken, gelecekteki araştırmalar için de yeni yollar açmaktadır.