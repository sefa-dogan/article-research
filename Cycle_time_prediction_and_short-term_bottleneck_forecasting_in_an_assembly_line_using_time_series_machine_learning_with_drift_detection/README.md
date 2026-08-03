# Cycle time prediction and short-term bottleneck forecasting in an assembly line using time series machine learning with drift detection
Bu tez, üretim hatlarında döngü süresi tahmini ve kısa vadeli darboğaz tahmini için kayma algılamalı zaman serisi makine öğrenimi modellerini geliştirmeyi ve değerlendirmeyi amaçlamaktadır. Yazar, geleneksel, statik tahmin yaklaşımlarının dinamik üretim ortamlarında, özellikle de değişen çalışma koşulları (örneğin, takım aşınması, ürün karışımı varyasyonu, vardiya değişiklikleri, makine arızaları) nedeniyle ortaya çıkan durağan olmayan koşullar ve kavram kayması altında yetersiz kaldığı bilgi boşluğunu ele almaktadır. 
Bu durum, yanlış tahminlere ve ortaya çıkan darboğazların gecikmeli tespitine yol açar.

## Ana Hipotez veya Tez
Tezin ana iddiası, kavram kaymasını algılayabilen ve buna adapte olabilen zaman serisi makine öğrenimi modellerinin, özellikle de ADWIN entegre edilmiş LSTM'lerin, dinamik üretim ortamlarında döngü süresi tahmini ve darboğaz öngörüsünde daha doğru ve sağlam performans sağlayabileceğidir. Bu, geleneksel statik modellere kıyasla daha erken uyarılar ve değişen koşullara daha iyi adaptasyon anlamına gelir. 

## Çalışmanın Önemi
Yazarlar, bu konunun araştırılmaya değer olduğunu, çünkü üretim hatlarının dinamik yapısının geleneksel statik tahmin yöntemlerinin güvenilirliğini azalttığını ve bunun da yanlış tahminlere ve darboğazların gecikmeli tespitine yol açtığını savunmaktadır. Çalışma, adaptif öğrenme mekanizmalarının entegrasyonunun, sürekli değişen üretim koşulları altında tahmin performansını sürdürme ve operasyonel müdahale için erken uyarı sağlama yeteneğini göstererek pratik bir değer sunmaktadır.

## Kilit Bulgular
**Döngü Süresi Tahmini:** ADWIN kayma algılamalı adaptif LSTM modeli, kararlı fazda bağımsız LSTM ile aynı performansı gösterirken, kurtarma fazında en güçlü genel performansı sergilemiştir. Kayma fazında sonuçlar karışıktı. Bu, adaptif mekanizmanın süreç değiştiğinde ve kısmen iyileşmiş bir duruma geçtiğinde daha faydalı hale geldiğini göstermektedir.  
**Darboğaz Tahmini:** Adaptif model, daha yüksek hassasiyet (precision) sağlayarak yanlış pozitif uyarıları azaltmış ve darboğaz olaylarından önce ortalama 7 ila 9 adımlık bir kurşun süresi (lead time) ile erken uyarılar sunmuştur. Ancak, statik model F1 skorunda daha iyi performans göstererek daha güçlü bir birleşik tespit performansı sergilemiştir.   
**Kayma Algılama:** ADWIN algılayıcısı, simüle edilmiş kaymanın başlangıcından yaklaşık 10 adım sonra kaymayı tespit etmiş ve kayma başlamadan önce hiçbir yanlış alarm üretmemiştir. Bu, algılayıcının kararlı fazda güvenilir ve dağılım değişikliklerinden sonra duyarlı olduğunu göstermektedir 

## Verilerin Ana Tezi Desteklemesi
Evet, sunulan veriler ve istatistikler ana tezi desteklemektedir. Özellikle kurtarma fazında adaptif LSTM'nin üstün performansı ve darboğaz tahmininde adaptif modelin yüksek hassasiyeti ve erken uyarı yeteneği, değişen koşullar altında adaptif modellerin faydasını doğrulamaktadır. ADWIN'in kaymayı gecikmeli ancak yanlış alarm olmadan tespit etmesi de adaptif mekanizmaların etkinliğini göstermektedir. 

## Beklenmeyen Sonuçlar
Beklenmeyen bir sonuç, kararlı fazda adaptif LSTM'nin bağımsız LSTM'ye kıyasla ek bir avantaj sağlamamasıdır. Ayrıca, kayma fazında adaptif LSTM'nin tüm hata ölçütlerinde en düşük değeri üretmemesi ve statik modelin F1 skorunda adaptif modelden daha iyi performans göstermesi de dikkat çekicidir. Bu durum, model performansının değerlendirme ölçütüne ve operasyonel faza bağlı olduğunu göstermektedir.

## Literatüre Katkı
Bu makale, zaman serisi makine öğrenimi modellerini, özellikle de LSTM'leri, kavram kayması algılama (ADWIN ile) ile entegre ederek üretim hatlarında döngü süresi tahmini ve darboğaz öngörüsü için adaptif bir çerçeve sunmaktadır. Literatüre, dinamik üretim ortamlarında adaptif modellerin performansını kararlı, kayma ve kurtarma fazlarında karşılaştırmalı olarak değerlendirerek katkıda bulunur. Ayrıca, adaptif modellerin pratik gereksinimlerini, zorluklarını ve faydalarını da tanımlar. 

## Pratik veya Teorik Uygulaması
**Pratik Uygulama:** Bu bilgi, gerçek dünya üretim hatlarında erken uyarı sistemleri geliştirmek için kullanılabilir. Operatörlere darboğaz olayları öncesinde müdahale etmeleri için zaman tanıyarak üretim kesintilerini azaltabilir. Ayrıca, ADWIN tabanlı kayma algılama, değişen üretim koşullarına otomatik olarak uyum sağlayan modellerin dağıtımını destekleyebilir.  
**Teorik Uygulama:** Çalışma, kavram kayması ve adaptif öğrenme alanındaki araştırmalara katkıda bulunarak, dinamik veri akışlarında makine öğrenimi modellerinin sağlamlığını artırma yolları hakkında daha fazla araştırma için temel oluşturur. Özellikle, ADWIN gibi kayma algılama yöntemlerinin LSTM gibi derin öğrenme modelleriyle entegrasyonu için bir çerçeve sunar.  

## Açıkta Kalan Sorular
**Gerçek Dünya Kayması:** Çalışma, kaymayı deneysel olarak simüle ettiği için, gerçek endüstriyel ortamlardaki daha kademeli, düzensiz veya karışık kayma modellerine adaptif davranışın nasıl genelleneceği belirsizdir.  
**Adaptif Güncelleme Mantığı Optimizasyonu:** Retraining (yeniden eğitim) aralığı, pencere boyutu ve tetikleyici hassasiyeti gibi adaptif güncelleme parametrelerinin sistematik olarak ayarlanması ve optimize edilmesi gerekmektedir.   
**Faz Bağımlı Eşik Yönetimi:** Gerçek bir dağıtım ortamında, mevcut işletim fazının önceden bilinmemesi nedeniyle, eşiklerin dinamik olarak ayarlanması veya fazın otomatik olarak tespit edilmesi için ek mantık gereklidir.  
**Ölçekleyici Geçerliliği:** Darboğaz tahmin hattında sabit bir ölçekleyici kullanılması, değişen veri dağılımları altında tahmin güvenilirliğini etkileyebilir; bu nedenle ölçekleyicinin adaptif olarak güncellenmesi gerekebilir.  
**Genellenebilirlik:** Bulguların farklı süreç dinamiklerine, veri kullanılabilirliğine veya darboğaz tanımlarına sahip diğer endüstriyel bağlamlara uygulanması için ek doğrulama gereklidir.