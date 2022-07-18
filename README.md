# Kamp2
Değişkenler, veri tutuculardır. Verileri değişkenler ile yönetiriz.

C#'ta type safety vardır. Yani değişkenin ne tip olduğu yazılmalıdır.

Basit bir metni bile eğer birden fazla yerde yazıyorsan yine de değişken kullanmalısın.

Tek bir veriyi değil birden fazla veriyi tutmak istersem dizileri kullanırım.

Küçük s'li olan string değişken tipidir. Büyük olan S'li string ise classtır c#'ta.

Classları birden fazla veriyi tutmak için kullanırız temel amaç budur.

.Net : Microsoft tarafından geliştirilmiştir. Programlama dilinden ve işletim sisteminden bağımsız uygulama geliştirmek için bir platformdur veya ortamdır.

.Net CLI, .Net komut aracıdır. .Net, SDK ile gelir.

.cs uzantılı dosyalar c#'a karşılık gelir.

Main fonksiyonu, ayağa kalkan ilk fonksiyondur. İşletim sistemiyle iletişime geçen fonksiyondur. Sadece bir tane vardır. Program.cs dosyası içindedir.

<h2> Kamp3 </h2>

Eğer ki bir bir kod bloğunu tekrar tekrar kullanıcaksam fonksiyon şeklinde yazmalıyım. Clean Code'da fonksiyon da satır sayısı en fazla  15 olmalı.

Manager,Controller, Service gibi isimlendirmeler operasyon sınıflarının olduğunu belirtir.

Naming Convantion, yazım kuralıdır. Class isimleri, proje isimleri, metot isimleri pascal case yani harfler buyuk yazılır. Camel case'te ise ilk harf kuçüktür. Bu da public olmayanlar için kullanılır.

Değişkenler 2'ye ayrılır. Değer tipleri ve referans tileri olmak üzere. Int, float, decimal, double değer tiplere örnektir. Array, class, List, string referans tipe örnketir. Stack'te değer tipler ve değerleri tutulur. Ayrıca stack'te referans tiplerin referans noktaları tutulur. Bu referans noktalar ise heap'te nesnelerin adresini tutar. Yani orayı işaret eder.

New sözcüğü bellekte yeni bir adres oluştur demek.

<h2> Kamp4 </h2>

Foreign Key, Primary keyden sonra gelen anahtardır. Örneğin categoryId verilebilir. Başka tablodan veri tutar çünkü. Primary keyden sonra gelir.

Entity, bizim nesne modellerimizdir. Bu classlarda sadece özellik yani prop property olur.

CRUD ----> EKLE, SİL, GÜNCELLE, LİSTELE

C# küçük - büyük harf duyarlıdır. Yani case sensetivedir.

 public void Add(Product product)
        {
            Console.WriteLine(product.ProductName);
        }

Product p1 = new Product();
            p1.Id = 1;
            p1.ProductName = "Koltuk";
            p1.UnitPrice = 500;
            p1.UnitsInStock = 3;
            p1.Aciklama = "Tekli Koltuk"


ProductManager manager = new ProductManager();
            manager.Add(p1);
            
 şimdi ben burda p1 Productını gönderirken p1'in referansını gönderiyorum aslında. Ama değer tiplerde sadece değeri gönderiyorum. Diyelim ki p1'in heapte adresi 101. Ben fonskiyona 101i gönderiyprum aslında. Fonskiyondaki prodıcta diyorum ki p1'in işaret ettiği adresi sen de göster artık. O yüzden parametreeki productta değişiklik yapsa p1'de işaret ettikleri yerdeki nesne değerleri değişir.
 
 Birde bunu unutma fonskiyonlardaki değişken veya parametreler farklıdır.
 
 Fonksiyon sonucundaki değeri başka yerde kullanmak istersem geri dönüş tipi void olmamalıdır.
 
 #Koleksiyonlar
 
 Dizilere sonradan eleman ekleyemiyoruz. Yani genişletemiyoruz. C#'ta gerçek hayatta çok diziler kullanılmaz. Bu yüzden koleksiyonlar vardır.
 control+k+c seçtiğin satıları yorum satırına alır. control+k+u seçili satırları yorum satırından çıkarır. 
 
 Koeksiyonlar generik ve generik olmayan olarak 2'ye ayrılır. Generic yapılar her tipe uyum sağlaması için bir şablon oluşturmak için kullanılır. Örneğin List<int> =new List<int>() bu generic yapıalra bir örnektir. Sınıflar, diziler, metotlar, interfaceler generic olabilir. New'lediğimiz an da çalışan bloğa constructor denir.
 
 #Kamp5
 
 Özellik tuttuğumuz yerde yani prop tuttuğumuz yerde operasyon tutulmaz. Operasyon tutulan yerde özellik tutulmaz.
 
 *** Bir veri üzerinde eğer matematiksel işlem yapılmıyorsa o veri string tutulmalıdır. Örneğin TcNo, müşteri no, vergi no gibi veriler
 
 *** Eğer ki bir nesne de bir değeri kullanmak zorunda gibi görünmüyorsam o nesneye ayit gibi durmuyorsa orda soyutlama hatası vardır deriz. Örneğin bir bankacılık uygulamasında 2 ti müşterin var. Tüzel ve gerçek müşteri. Eğer ki sen bir müşteri nesnesi olşturursan ve bu iki müşteri tipini aynı nesneye koyarsan yanlış olur. Bu teknik SOLID tekniğinde ki L'dir.
 
 		L — Liskov substitution principle
ÖZET: Kodlarımızda herhangi bir değişiklik yapmaya gerek duymadan alt sınıfları, türedikleri(üst) sınıfların yerine kullanabilmeliyiz. “Yerine Geçme” olarak Türkçeye çevirdiğimiz prensibe göre; miras alarak türemiş olan class’ların önce miras aldıkları nesnenin tüm özelliklerini kullanması, daha sonra da kendi özelliklerini barındırması gerekir. Eğer oluşturduğumuz class, miras aldığı nesnenin ‘tüm’ özelliklerini kullanmayacaksa ortaya gereksiz kod blokları çıkar ve bu da bir geliştiricinin isteyeceği en son şeydir. Çünkü bir geliştirici her daim ‘Clean Code’ yazmaya çalışır.
 
 Entity sınıfında operasyon yazılmaz.
 
 *** Kalıtımda aslıda olay referans tiptir. Şöyle kalıtım veren sınıf kalıtım alan sınıfın referansını tutabilir. Örneğin her gerçek müşteri bir müşteridir. Müşteri sınıfı burda gerçek müşterinin referansını tutar.
 
 Örneğin Musteri musteri = new Gercekmusteri();
 
 İmza aynı ancak fonksiyon içi yani gövdesi farklıysa interface kullanırız. İnterfacelerde refrans tutuculardır unutma!!!!!
 
C# params nedir?
Metotların değişken sayıda parametre almasına imkan veren bir anahtar kelimedir. Değişken türü belli olmayan durumlarda C# içerisindeki her şeyin object türünden türediği özelliği kullanılabilir. Bu özellik kullanıldığında metodun aşırı yüklenmiş olduğu varsayılır. C# aşırı yüklenmiş metotları seçerken önceliği normal metotlara verir.
 
 Örneğin int Topla(params int[] sayilar);
 
