# Swift Temelleri: Değişkenler, Sabitler ve Veri Türleri

Bu dokümanda Swift dilinin temel özelliklerini, değişkenleri, sabitleri ve farklı veri türlerini başlıklar altında inceleyeceğiz.

---

## Giriş
Swift, **type-safe** bir dildir, yani her değişkenin belirli bir türü olmalıdır. Bu yapı, kodun güvenliğini ve okunabilirliğini artırır.

---

## Değişkenler (Variables)
Swift'te değişkenler `var` anahtar kelimesiyle tanımlanır ve türleri belirlenir.

```swift
var greeting = "Hello, playground"
var age = 45
var population = 8_000_000 // Alt çizgilerle okunabilir hale getirildi.

Çok Satırlı Stringler (Multiline Strings)

Birden fazla satır içeren stringler oluşturmak için üç tırnak işareti (""") kullanılır.

var multilinestr = """
this is
multiline
string
"""

Tek Satır Haline Getirme:

Satır kırılmalarını önlemek için \ kullanılabilir.

var singleLineMulti = """
this is \
actually \
one line
"""

Double ve Boolean Türleri

Swift, ondalıklı sayılar için Double, mantıksal değerler için Boolean türlerini sağlar.

var thisISDouble = 3.1415
var isTrue = true

Önemli Not:

Farklı türleri (örneğin Double ve Integer) doğrudan toplamak mümkün değildir.

var myDouble = 3.4
var myInt = 3
// Hata: Binary operator + cannot be applied
// var sum = myDouble + myInt

String İçerisinde Değişken Kullanımı (String Interpolation)

String’lere değişkenleri veya ifadeleri yerleştirmek için \(değişken) kullanılır.

var score = 88
var str = "My score is \(score)"
var result = "The test results are: \(str)"

Sabitler (Constants)

Sabitler let anahtar kelimesi ile tanımlanır ve bir kez tanımlandıktan sonra değiştirilemez.

let pi = 3.14

Tip Açıklamaları (Type Annotations)

Swift, tip çıkarımı yapabilir, ancak türü açıkça belirtmek de mümkündür.

Temel Türler:

var thisInt: Int = 3
var thisDouble: Double = 3.14
var myString: String = "Hello"
var myBool: Bool = true

Diziler:

var myArray: [Int] = [1, 2, 3, 4, 5]
var mySingleArray: [Int] = [1]

Genel Bakış

	•	Değişkenler: var ile tanımlanır.
	•	Çok Satırlı Stringler: Üç tırnak işareti (""") ile oluşturulur.
	•	Double ve Boolean: Ondalıklı sayılar ve mantıksal ifadeler için kullanılır.
	•	String Interpolation: String’lerde değişkenleri veya ifadeleri göstermek için kullanılır.
	•	Sabitler: let ile tanımlanır ve değiştirilemez.
	•	Tip Açıklamaları: Türü açıkça belirtmek mümkündür.

Bu yazıda Swift’in temel yapı taşlarını öğrendik. Daha fazla konu için takipte kalın!

