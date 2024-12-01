

# Swift Temelleri: Değişkenler, Sabitler ve Veri Türleri

Swift, **type-safe** (tip güvenli) bir dil olduğu için her bir değişkenin belirli bir veri türüne sahip olması gerekir. Bu yazıda, değişkenler ve sabitlerle ilgili temel bilgileri paylaşacağım.

Swift’te değişkenler `var` anahtar kelimesiyle tanımlanır. Örneğin:

```swift
var greeting = "Hello, playground"

Örnekler:

	•	Tam Sayılar (Integer):

var age = 45

	•	Okunabilir Sayılar: (Alt çizgilerle daha okunabilir hâle gelir.)

var population = 8_000_000

Çok Satırlı Stringler (Multiline Strings)

Çok satırlı stringler üç tırnak işareti (""") ile tanımlanır. Ancak açılış ve kapanış tırnakları kendi satırlarında olmalıdır:

var multilinestr = """
this is
multiline
string
"""

Eğer satır kırılmalarını istemiyorsanız, \ karakterini kullanabilirsiniz:

var singleLineMulti = """
this is \
actually \
one line
"""

Double ve Boolean Türleri

Swift’te double ondalıklı sayılar, boolean ise doğru/yanlış değerler (true veya false) için kullanılır:

var thisISDouble = 3.1415
var isTrue = true

Not: Swift’te integer ve double türlerini doğrudan toplamak mümkün değildir:

var myDouble = 3.4
var myInt = 3
// Hata: Binary operator + cannot be applied
// var sum = myDouble + myInt

String İçerisinde Değişken Kullanımı (String Interpolation)

Bir string içinde değişkenlerin veya ifadelerin sonucunu yerleştirmek için \(değişken) kullanılır:

var score = 88
var str = "My score is \(score)"
var result = "The test results are: \(str)"

Sabitler (Constants)

Sabitler let anahtar kelimesi ile tanımlanır. Değeri sonradan değiştirilemez:

let pi = 3.14

Tip Açıklamaları (Type Annotations)

Swift genellikle tip çıkarımı (type inference) yaparak değişkenlerin türünü otomatik belirler. Ancak türü açıkça belirtmek de mümkündür:

var thisInt: Int = 3
var thisDouble: Double = 3.14
var myString: String = "Hello"
var myBool: Bool = true

Dizi türleri için de benzer bir şekilde tip açıklaması yapılabilir:

var myArray: [Int] = [1, 2, 3, 4, 5]
var mySingleArray: [Int] = [1]

Bu yazıda Swift’te değişkenler, sabitler ve veri türlerine giriş yaptık. Gelecekte daha derin konularla devam edeceğiz. Takipte kalın! 🚀

Bu dosya, tek parça bir markdown formatında düzenlenmiştir. Direkt kopyalayıp kullanabilirsin! 😊
