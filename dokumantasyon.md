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
# Token Tanımı
## Tanımlanan Token Türleri
|     Türü  |    Açıklama              |
|--------------|-----------------------|
| keywords     | Anahtar kelimeler     |
| identifier   | Değişken adları       |
| number       | Sayısal sabitler      |
| string       | Karakter dizileri     |
| operators     | +, -, *, /, = vb.     |
| delimiters  | Noktalama karakterleri|
| comment      | Açıklama satırları    |



