# ExtensionAndClosureKonuAnlatimi
Swift dilinde "extension" (uzantı), mevcut bir sınıf, yapı veya enum türünü genişletmek veya yeni özellikler eklemek 
için kullanılan güçlü bir özelliktir. Extension'lar, Swift'te kodunuzu daha modüler hale getirir ve mevcut türleri daha
işlevsel hale getirmenizi sağlar. İşte Swift extension'larının temel özellikleri:

Mevcut Türleri Genişletme: Bir extension ile varolan bir türü genişletebilirsiniz. Bu, mevcut bir türün yeni metodlar,
hesaplamalı özellikler veya alttaki veriye erişim sağlayan özellikler eklemenizi sağlar.
Örnek:
extension Int {
    func squared() -> Int {
        return self * self
    }
}

let sayi = 5
let kare = sayi.squared() // 25

Yukarıdaki örnekte, Int türünü genişleten bir extension tanımlandı ve squared() adlı bir metod ekledi. Bu, herhangi bir
Int değeri üzerinden kullanılabilir.

Yeni İnitlalizer'lar Ekleme: Extension'lar, mevcut bir türe yeni başlatıcılar (initializers) eklemenizi sağlar. Bu, türün 
farklı şekillerde başlatılmasını destekler.
Örnek:
struct Konum {
    var x: Double
    var y: Double
}

extension Konum {
    init(koordinat: (Double, Double)) {
        self.x = koordinat.0
        self.y = koordinat.1
    }
}

let koordinat = (3.0, 4.0)
let konum = Konum(koordinat: koordinat)

Yukarıdaki örnekte, Konum yapısına bir extension eklenerek, init(koordinat:) adlı yeni bir başlatıcı eklendi.

Protocols Implementasyonu: Extension'lar, mevcut bir türe bir protocol'ü uygulamanıza izin verir. Bu, özellikle bir 
türün çok sayıda protocol'ü uygulaması gerektiğinde kullanışlıdır.
Örnek:
protocol Describable {
    func describe() -> String
}

extension Int: Describable {
    func describe() -> String {
        return "Bu sayı \(self) değerindedir."
    }
}

let sayi = 42
let aciklama = sayi.describe() // "Bu sayı 42 değerindedir."

Yukarıdaki örnekte, Int türüne Describable protocol'ünü uygulayan bir extension tanımlandı ve describe() metodunu ekledi.

Computed Properties: Extension'larla mevcut türlere hesaplanmış (computed) özellikler ekleyebilirsiniz.
Örnek:
extension Double {
    var kareKoku: Double {
        return sqrt(self)
    }
}

let sayi = 25.0
let kareKok = sayi.kareKoku // 5.0

Bu örnek, Double türüne kareKoku adında bir hesaplanmış özellik ekler ve bu özelliği kullanarak bir sayının karekökünü hesaplar.

Swift extension'larını kullanmak, kodunuzu daha düzenli ve okunaklı hale getirirken mevcut türleri genişletmenizi sağlar.
Ancak, extension'lar türlere yeni depolama özellikleri (stored properties) ekleyemezler ve mevcut türlerin içindeki 
özellikleri değiştiremezler. Bu nedenle, extension'ları kullanırken bazı kısıtlamalara dikkat etmek önemlidir.
