# Basit JavaScript Tokenizer ve Parser
Bu proje, JavaScript benzeri bir dil için temel düzeyde bir **tokenizer** ve **parser** içermektedir.
Kod, kaynak kodu alır, onu tokenlara ayırır ve belirli dil yapıları için sözdizimsel analiz yapar.
Not: Projede harici kütüphane kullanımı yasak olduğundan, tüm analizler kendi yazdığımız kodlarla gerçekleştirilmiştir.
🛠️ Teknik Altyapı
Bu projede JavaScript programlama dili tercih edilmiştir. JavaScript'in web ortamında doğal olarak çalışabilmesi sayesinde, kolayca interaktif ve dinamik kullanıcı arayüzleri geliştirilmiştir.

Projenin diğer temel bileşenleri şunlardır:

- HTML kullanılarak yapısal ve semantik olarak anlamlı kullanıcı arayüzü tasarlanmıştır.

- CSS ile arayüzün görsel düzenlemeleri ve stil iyileştirmeleri sağlanmıştır.

- Düzenli ifadeler (RegEx), kaynak kodun sözcüksel analizini (tokenize) yapmak için kullanılmıştır. Bu sayede, girdideki farklı türdeki öğeler (anahtar kelimeler, operatörler, sayılar, tanımlayıcılar vb.) ayrıştırılmıştır.

- Recursive descent parser yaklaşımı benimsenerek, sözdizimsel analiz (parsing) gerçekleştirilmiştir. Bu yöntemle, token dizileri programın dil kurallarına uygun olarak hiyerarşik yapılar şeklinde kontrol edilip, anlamlı ifadeler oluşturulmuştur.

- Bu teknik altyapı sayesinde, kullanıcıların yazdığı kod gerçek zamanlı olarak analiz edilmekte ve sözdizimi hataları hızlıca tespit edilebilmektedir
