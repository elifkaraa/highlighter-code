# Basit JavaScript Tokenizer ve Parser
Bu proje, JavaScript benzeri bir dil için temel düzeyde bir **tokenizer** ve **parser** içermektedir.
Kod, kaynak kodu alır, onu tokenlara ayırır ve belirli dil yapıları için sözdizimsel analiz yapar.
Not: Projede harici kütüphane kullanımı yasak olduğundan, tüm analizler kendi yazdığımız kodlarla gerçekleştirilmiştir.
🎥 Demo & Kaynaklar
📹 Demo Videosu: [YouTube'da İzle](https://youtu.be/diOKEUCPZmA)
🛠️ Teknik Altyapı
Bu projede JavaScript programlama dili tercih edilmiştir. JavaScript'in web ortamında doğal olarak çalışabilmesi sayesinde, kolayca interaktif ve dinamik kullanıcı arayüzleri geliştirilmiştir.

Projenin diğer temel bileşenleri şunlardır:

- HTML kullanılarak yapısal ve semantik olarak anlamlı kullanıcı arayüzü tasarlanmıştır.

- CSS ile arayüzün görsel düzenlemeleri ve stil iyileştirmeleri sağlanmıştır.

- Düzenli ifadeler (RegEx), kaynak kodun sözcüksel analizini (tokenize) yapmak için kullanılmıştır. Bu sayede, girdideki farklı türdeki öğeler (anahtar kelimeler, operatörler, sayılar, tanımlayıcılar vb.) ayrıştırılmıştır.

- Recursive descent parser yaklaşımı benimsenerek, sözdizimsel analiz (parsing) gerçekleştirilmiştir. Bu yöntemle, token dizileri programın dil kurallarına uygun olarak hiyerarşik yapılar şeklinde kontrol edilip, anlamlı ifadeler oluşturulmuştur.

- Bu teknik altyapı sayesinde, kullanıcıların yazdığı kod gerçek zamanlı olarak analiz edilmekte ve sözdizimi hataları hızlıca tespit edilebilmektedir
- 🧩 Proje Tasarımı
  -  Sözcüksel Analiz
Kod, anahtar kelimeler, sayılar, operatörler ve yorumlar gibi parçalara ayrılır.

-  Sözdizimsel Analiz
Tokenlar, kurallara uygun olup olmadığına recursive descent yöntemiyle kontrol edilir.
Desteklenen yapılar: değişken atamaları, if-else blokları, switch-case yapısı.

-  Vurgulama
Her token türü için farklı renkler kullanılarak kod okunabilir hale getirilir.

-  Arayüz
Kullanıcı kodu yazarken, altında gerçek zamanlı olarak renkli ve hatalı kod bilgisi gösterilir.
📚 Sözdizimsel Analiz ve Hata Yönetimi
- Parser, recursive descent yöntemiyle yazılmıştır.
Desteklenen yapılar:

- Değişken atamaları (örneğin: let x = 5;)

- Koşullu ifadeler (if ve else blokları)

- switch-case yapısı

🎨 Kullanıcı Arayüzü Tasarımı
- Tema: Sade 

- Giriş: HTML textarea

- Stil: CSS ile renkler ve yazı tipleri

- İşlevsellik: JavaScript ile gerçek zamanlı tokenizasyon, parse ve sözdizimi vurgulama

⚙️ Karşılaşılan Zorluklar ve Çözümler
- Tokenizer ile parser uyumunun sağlanması

- Gerçek zamanlı analiz performansının korunması

- Kullanıcıdan gelen ham kodun güvenli işlenmesi (HTML escape ile)
Çözümler:

- Modüler ve okunabilir kod yapısı

- Düzenli ifadelerle (RegEx) sözcüksel analiz

- escapeHTML() fonksiyonu ile XSS risklerinin azaltılması

✅ Proje Sonuçları ve Gelecek Planlar
- Temel sözcüksel ve sözdizimsel analizler başarılı şekilde uygulanmıştır.(Sadece bazı hata mesajlarının çalışmasında sorunlar bulunur)

- Gerçek zamanlı renkli vurgulama ile kullanıcı deneyimi artırılmıştır

- Eğitim amaçlı kullanım için uygundur

🚀 Gelecek Çalışmalar
- Daha karmaşık dil yapılarının eklenmesi (döngüler, fonksiyonlar)

- Performans iyileştirmeleri

- Daha gelişmiş kullanıcı arayüzü ve hata bildirim mekanizmaları


