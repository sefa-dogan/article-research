# Adaptive continual learning for cycle time prediction in wafer fabrication with time-varying product types

## Wafer Üretiminde Çevrim Süresi Tahmini için Adaptif Sürekli Öğrenme
### Temel Araştırma Sorunu
Wafer üretim sistemlerinde ürün tiplerinin zamanla değişmesi nedeniyle ortaya çıkan 'kavram kayması' (concept drift) problemi, çevrim süresi (CT) tahmin modellerinin performansını düşürmekte veya tamamen başarısız olmasına neden olmaktadır.
Mevcut modeller, veri akışındaki dinamik değişikliklere uyum sağlayamadığı için doğru tahminler yapamamaktadır. Bu durum, wafer ürünlerinin zamanında teslimatını ve üretim süreçlerinin verimliliğini olumsuz etkilemektedir.

### Ana Hipotez veya Tez
Makalenin temel iddiası, sürekli öğrenmeye dayalı bir derin öğrenme tahmin yöntemi olan FD-MIR'ın (Feature Distillation with Maximally Interfered Retrieval) wafer üretimindeki zamanla değişen ürün tipleri senaryolarında çevrim süresini doğru bir şekilde tahmin ederek, kavram kayması sorununu etkin bir şekilde ele almasıdır. Bu yöntem, yeni wafer ürün tipleriyle ilgili bilgileri sürekli olarak öğrenir ve mevcut veri akışını günceller.

### Çalışmanın Önemi
Bu çalışma, yarı iletken endüstrisindeki wafer üretim sistemlerinde çevrim süresi tahmininin kritik önemini vurgulamaktadır. Doğru çevrim süresi tahmini, wafer ürünlerinin zamanında teslimatını sağlamak, müşteri memnuniyetini sürdürmek, üretim yöneticilerine beklenmedik olaylara hızlı yanıt verme esnekliği sunmak ve operasyonel verimliliği artırmak için hayati öneme sahiptir. Gecikmeler, üreticinin itibarını zedeleyebilir ve sonraki üretim süreçlerinin verimliliğini bozabilirken, erken teslimatlar envanter birikimine ve artan operasyonel maliyetlere yol açabilir.

### Kilit Bulgular
**Üstün Tahmin Performansı:** FD-MIR, değişen wafer ürün tipleri senaryolarında çevrim süresini doğru bir şekilde tahmin etmede üstün performans sergilemiştir.Geleneksel regresyon modellerine (GBR ve SVR) kıyasla %59'dan fazla, sürekli öğrenme yöntemlerine (SER ve CLS-ER) kıyasla ise %7-8 civarında hata oranını azaltmıştır.

**Katastrofik Unutmayı Azaltma:** FD-MIR, eski ürün tiplerine ait bilgilerin katastrofik unutulmasını etkin bir şekilde azaltırken, yeni bilgilere adaptasyonu sağlamıştır. Özellikle, Product A için negatif AF değeri (-0.0021) ve pozitif BWT değeri (+0.0021) elde etmesi, modelin önceki görevlerden edindiği bilgiyi kullanarak tahmin yeteneğini geliştirdiğini göstermektedir.

**Dinamik Adaptasyon ve Kararlılık:** Yöntem, kavram kayması dönemlerinde daha küçük MSE dalgalanmaları ve daha hızlı yakınsama sergileyerek dinamik adaptasyon yeteneğini ve kararlılığını kanıtlamıştır.

### Verilerin Ana Tezi Desteklemesi
Evet, sunulan grafikler, tablolar ve istatistikler ana tezi güçlü bir şekilde desteklemektedir. Tablo 5, 6, 7, 8 ve Şekil 10, 11, 12, 13, 14, 15, 17, 18, 19, 20, 21, 22, 23 gibi veriler, FD-MIR'ın diğer algoritmalarla karşılaştırıldığında daha düşük hata oranları ve daha yüksek doğruluk gösterdiğini açıkça ortaya koymaktadır. Özellikle, kavram kayması senaryolarında (yeni ürün tiplerinin eklenmesiyle), FD-MIR'ın geleneksel modellerin aksine performansını sürdürdüğü ve hatta geliştirdiği görülmektedir.

### Beklenmeyen Sonuç
Makalede açıkça belirtilen beklenmedik bir sonuç bulunmamaktadır. Bulgular, FD-MIR'ın kavram kayması ve katastrofik unutma gibi zorlukları ele almada başarılı olduğunu ve hipotezi doğruladığını göstermektedir. Ancak, FD-MIR'ın SER'ye kıyasla Faz 1'de marjinal olarak daha yüksek bir unutma oranına sahip olması, yine de genel olarak daha iyi bir denge sağladığı belirtilmektedir.

### Makalenin Literatüre Katkısı
Bu makale, literatüre şu önemli katkıları sağlamıştır:

**Sürekli Derin Öğrenme Yöntemi:** Wafer ürün tiplerinin değiştiği senaryolarda çevrim süresi tahmini için sürekli bir derin öğrenme yöntemi önermiştir.

**Özellik Damıtma Yaklaşımı:** Regresyon görevlerinde, geleneksel sürekli öğrenmedeki logit damıtmasının uygulanamazlığına çözüm olarak, katastrofik unutmayı azaltmak için özellik damıtma (feature distillation) yaklaşımını benimsemiştir. Bu, öğrenme aşamaları arasında özellik düzeyinde içgörüleri aktararak latent bilgiyi korur.

**Kümeleme Tabanlı Adaptif Tekrar Stratejisi:** Adaptif K seçimi ile kümeleme tabanlı, maksimum müdahaleye uğramış geri çağırma (Clustering-driven Adaptive Threshold Maximally Interfered Retrieval - CA-MIR) stratejisi sunulmuştur. Bu strateji, müdahale değerlerini kümeleyerek ve kümülatif müdahale oranı eşiği aracılığıyla K'yi belirleyerek kritik geçmiş örnekleri dinamik olarak geri çağırır. Bu, sabit K sınırlamalarını ortadan kaldırır ve regresyon odaklı sürekli öğrenmede bilgi tekrarının hassasiyetini ve verimliliğini artırır.


### Pratik veya Teorik Uygulama
Bu çalışma, yarı iletken endüstrisindeki wafer üretim sistemlerinde çevrim süresi tahmininin doğruluğunu ve verimliliğini artırmak için doğrudan pratik uygulamalara sahiptir. Önerilen FD-MIR yöntemi, dinamik veri akışlarına sürekli adaptasyon sağlayarak, üretim planlamacılarına ve yöneticilerine daha doğru ve gerçek zamanlı çevrim süresi tahminleri sunar. Bu, üretim süreçlerinin optimize edilmesine, maliyetlerin düşürülmesine ve müşteri memnuniyetinin artırılmasına yardımcı olabilir. Teorik olarak, bu yöntem, kavram kayması ve katastrofik unutma gibi sürekli öğrenme zorluklarını ele almak için yeni bir çerçeve sunmaktadır.

### Açıkta Kalan Sorular
Bu makale, bir sonraki çalışma için şu yeni soruları doğurmaktadır:

**Hesaplama Karmaşıklığı:** Öğretmen-öğrenci mimarisi ve müdahale hesaplaması, hafif modellere kıyasla hesaplama karmaşıklığını artırmaktadır. Gelecekte, bu karmaşıklığı azaltacak ve yöntemin daha geniş ölçekli uygulamalara uygunluğunu artıracak yollar araştırılabilir.

**Sistem Çapında Kesintiler:** Mevcut yöntem, öncelikli olarak ürün karışımı değişikliklerinden kaynaklanan kavram kaymasını ele almaktadır. Ancak, daha geniş sistem çapındaki kesintilere (örneğin, ekipman arızaları, tedarik zinciri aksaklıkları) karşı dayanıklılık konusunda daha fazla çalışma yapılabilir.

**Proaktif Dayanıklı Planlama:** Çalışma, tahmin modelinin proaktif dayanıklı planlamayı desteklemek ve algoritmaların dayanıklılığını ölçüm yöntemleri kullanarak değerlendirmek üzere genişletilebileceğini belirtmektedir.


Özetle, bu çalışma, wafer üretimindeki çevrim süresi tahmininde kavram kayması sorununu ele almak için FD-MIR adlı yenilikçi bir sürekli öğrenme yöntemi sunmaktadır. Yöntem, özellik damıtma ve kümeleme tabanlı adaptif örnek geri çağırma stratejilerini birleştirerek, hem eski bilgiyi korurken hem de yeni veri akışlarına etkin bir şekilde uyum sağlamaktadır. Elde edilen sonuçlar, FD-MIR'ın mevcut yöntemlere kıyasla önemli ölçüde daha yüksek doğruluk ve kararlılık gösterdiğini kanıtlamaktadır.