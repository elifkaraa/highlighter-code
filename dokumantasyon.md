# 1. Kullanılan Teknolojiler ve Dil Yapısı
## 1.1 Programlama Dili
Projede JavaScript kullanılmıştır. JavaScript’in tarayıcıda doğrudan çalışabilmesi, kullanıcıların ek kurulum yapmadan sözdizimi vurgulayıcıyı kullanabilmesini sağlar.

## 1.2 Desteklenen Kod Yapıları
- Değişken tanımlamaları

- Kontrol yapıları: if, else
- Seçim yapıları: switch,case

- Sayılar,String ifadeler

- Operatörler: +, -, *, /, =, ==, !=, <, > vb.
- Noktalamalar: (,),{,} vb.

## 1.3 Gramer Yaklaşımı
Parser, top-down (recursive descent) yöntemi ile tasarlanmıştır. Bu yöntem, kodun yapısal olarak okunmasını ve doğrulanmasını kolaylaştırır.

# 2. Sözcüksel ve Sözdizimsel Analiz
## 2.1 Lexical Analyzer (Tokenizer)
Kullanıcıdan alınan kod aşağıdaki gruplara ayırılır:
Tanımlayıcılar: değişken isimleri
Operatörler: =, +, -, vb.
Sayısal değerler
Semboller: (, ), {, }, ;
Kod örneği:
![image](https://github.com/user-attachments/assets/5a072538-1e16-49aa-ab8f-4a9b7870e116)

## 2.2 Parser
Top-down yaklaşımıyla çalışan parse, parse_expression, parse_if gibi fonksiyonlarla gramer kontrolü yapılır.
# 3 Token Tanımı
## 3.1 Tanımlanan Token Türleri
|     Türü  |    Açıklama              |
|--------------|-----------------------|
| keywords     | Anahtar kelimeler     |
| identifier   | Değişken adları       |
| number       | Sayısal sabitler      |
| string       | Karakter dizileri     |
| operators     | +, -, *, /, = vb.     |
| delimiters  | Noktalama karakterleri|
| comment      | Açıklama satırları    |
## 3.2 Tokenizer Kullanımı
Tokenizer, kullanıcıdan alınan kaynak kodu parçalara (token'lara) ayırır ve her token için aşağıdaki bilgileri içeren nesneler döner:

type: Token türü (örneğin KEYWORD, IDENTIFIER, NUMBER, STRING, OPERATOR, DELIMITER, COMMENT, INVALID)

lexeme: Kaynak koddan alınan orijinal kelime/parça (örneğin if, varName, 123, "hello", +, {, // yorum)
# 4. Parser Fonksiyonları
## 4.1 Top-Down Yöntemi
Parser, yukarıdan aşağıya doğru çalışır. Yani önce daha geniş yapılar (örneğin bir ifade, koşul veya blok) analiz edilir, sonra bunlar alt bileşenlerine ayrılır. Bu sayede kodun geçerli yapıda olup olmadığı kontrol edilir.

## 4.2 Fonksiyon Açıklamaları
- parse(input):
Girdi olarak aldığı kaynak kodunu tokenize eder, ardından token dizisi üzerinde sırayla parse_if(), parse_switch() ve parse_expression() fonksiyonlarını çağırarak kodun sözdizimini kontrol eder.

- parse_if():
if bloğunu işler. if anahtar kelimesini, ardından parantez içindeki koşul ifadesini ve süslü parantezler içindeki blok yapısını doğrular.

- parse_switch():
switch yapısını işler. switch anahtar kelimesi, parantez içindeki ifade ve süslü parantezler içindeki case/default bloklarını kontrol eder.

- parse_case():
switch içindeki case ve default bloklarını işler. Her case ifadesini, ardından gelen değeri, : sembolünü, kod bloğunu ve break; ifadesini kontrol eder.

- parse_expression():
Atama, karşılaştırma ve basit ifadeleri kontrol eder. Örneğin, değişken atamaları (x = 5), karşılaştırmalar (x == 10) veya tek başına değişken ve sayısal değerleri işler.

- parse_block():
{ ... } içindeki kod bloğunu işler. Blok içinde if, switch veya ifade satırlarını tekrarlar.

- match(type, lexeme = null):
Şu anki token’ın türünü ve isteğe bağlı olarak değerini kontrol eder, eşleşiyorsa ilerler, değilse hata fırlatır.

- check(type, lexeme = null):
Şu anki token’ın türünü ve isteğe bağlı olarak değerini kontrol eder ancak ilerleme yapmaz.
# 5. GUI ve Gerçek Zamanlı Vurgulama
## 5.1 Kullanıcı Arayüzü
Kullanıcı, metin kutusuna kod yazdıkça, tokenize(input) fonksiyonu çağrılarak kod tokenlara ayrılır. Tokenlar, türlerine göre farklı CSS sınıflarıyla işaretlenir ve sonuç olarak metin kutusu veya kod gösterim alanında renklendirilmiş olarak gösterilir.

## 5.2 CSS Stil Tanımları
Token dizisi üzerinde döngü kurularak, her token'ın tipi kontrol edilir ve uygun CSS sınıfı atanır. Bu sayede sözdizim vurgulaması yapılır. Örneğin:

- KEYWORD türündeki tokenlar .token-KEYWORD sınıfı ile,

- IDENTIFIER türündekiler  .token-IDENTIFIER ile,

- OPERATOR türündekiler   .token-OPERATOR ile,

- NUMBER türündekiler  .token-NUMBER ile,

- STRING türündekiler .token-STRING  ile,

- COMMENT türündekiler .token-COMMENT ile,

- DELIMITER türündekiler .token-DELIMITER ile,
- INVALID türündekiler .token-INVALID ile  renklendirilir.
# 6.  Proje Özeti ve Değerlendirme
Bu projede, JavaScript ile yazılmış, gerçek zamanlı çalışan bir sözdizimi analizi ve vurgulama sistemi geliştirilmiştir. Proje, tokenize etme (lexer) ve üstten aşağıya (top-down) parse işlemleri ile kaynak kodun yapısını kontrol eder. Kullanıcıdan alınan kod, anlık olarak tokenize edilip parçalara ayrılır; ardından parse fonksiyonlarıyla geçerlilik denetimi yapılır.

Kodun sözdizimi hataları ve yapısal eksiklikleri anında tespit edilerek kullanıcıya bildirilir. Ayrıca, token türlerine göre uygulanan CSS sınıfları sayesinde, kod editöründe farklı öğeler renklendirilerek okunabilirlik ve kullanım kolaylığı sağlanır.

Bu modüler ve genişletilebilir yapı, hem dil öğrenimi için interaktif bir araç olarak hem de basit programlama dillerinin analizinde temel bir altyapı olarak kullanılabilir.


