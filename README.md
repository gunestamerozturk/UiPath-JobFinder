# 🤖 AI Destekli Kariyer Danışmanı – UiPath & OpenAI Entegrasyonu

Bu proje, **REFramework** yapısını kullanarak, **OpenAI (ChatGPT 5.4)** desteğiyle **Kariyer.net** üzerindeki yüzlerce iş ilanını kişisel bir özgeçmişle karşılaştıran ve en uygun ilanları raporlayan akıllı bir RPA projesidir.

Proje, manuel iş arama sürecindeki zaman kaybını ortadan kaldırmak ve aday-ilan uyumunu yapay zeka analiziyle standardize etmek amacıyla geliştirilmiştir.

## 🚀 Projenin Amacı ve Çalışma Mantığı
Bot, kullanıcının müdahalesine gerek kalmadan Kariyer.net üzerinde kapsamlı bir tarama yapar ve sadece gerçekten uygun olan ilanları seçip detaylı analiz eder.

**Süreç şu adımları kapsar:**
- ✔ **AI Özetleme:** Kullanıcının CV metnini okuyarak profesyonel bir aday özeti çıkarır.
- ✔ **Hızlı Tarama:** Kariyer.net'teki yüzlerce ilan başlığını (testte 500+) saniyeler içinde kazır.
- ✔ **Akıllı Filtreleme:** AI, ilan başlıklarını aday özetiyle kıyaslayıp potansiyel olanları seçer.
- ✔ **Orchestrator Entegrasyonu:** Seçilen ilanlar detaylı analiz için Kuyruğa (Queue) eklenir.
- ✔ **Detaylı Puanlama:** Her ilanın açıklaması AI tarafından 0-100 arası puanlanır ve nedenleri açıklanır.
- ✔ **Raporlama:** %75 ve üzeri uyum sağlayan ilanlar, tüm detaylarıyla e-posta olarak gönderilir.

## 🧠 Projede Kullanılan Teknolojiler ve Yapılar
* **REFramework (Robotic Enterprise Framework):** Projenin sağlam bir hata yönetimi ve işlem döngüsü üzerinde çalışması sağlandı.
* **Orchestrator Queue:** Dispatcher-Performer mantığıyla ilanlar kuyruk yapısında işlendi.
* **OpenAI API (ChatGPT 5.4):** HTTP Request ve JSON işlemleri ile özgeçmiş analizi ve ilan eşleştirme yapıldı.
* **Web Automation:** Kariyer.net üzerinde veri kazıma ve navigasyon işlemleri gerçekleştirildi.
* **JSON Parsing:** AI'dan gelen karmaşık yanıtlar `Newtonsoft.Json` ile işlendi.

## 📊 Performans Notları
* **Kapsam:** Bugün açılan ilk 10 sayfalık ilan listesi.
* **Hız:** 500'den fazla ilan başlığı sadece **1 dakika 58 saniyede** tarandı.
* **Verimlilik:** AI 500 ilan arasından 10 potansiyel ilan seçti ve detaylı analiz sonucunda en yüksek uyumlu olanları raporladı.
* **Zaman Kazancı:** Manuel olarak saatler sürecek "ilan detayı okuma" işlemi saniyeler seviyesine indirildi.

## ▶️ Kurulum ve Çalıştırma
1. Bu projeyi klonlayın:
   `git clone https://github.com/gunestamerozturk/JobFinder.git`
2. **UiPath Studio** ile projeyi açın.
3. **Orchestrator** üzerinde gerekli Assetleri (OpenAIApiKey, ToMail vb.) ve Kuyruğu (Queue) oluşturun.
4. **Önemli:** Kariyer.net'in robot korumasını aşmak için varsayılan tarayıcınızda oturumun açık olduğundan (Beni Hatırla) emin olun.
5. Botu çalıştırarak süreci başlatabilirsiniz.
