# react_odev_1
 Bu fonksiyon **"async"** olarak tanımlanmalı ve default olarak dışa aktarılmalıdır. Fonksiyonun içindeki asenkron fonksiyonlar **"await"** ile tanımlanmalıdır.
-  Fonksiyon **Number** tipinde tek parametre alır. Bu parametre **user id**'yi belirtir.
-  Fonksiyonun görevi aşağıdaki endpoint'e giderek parametrede verilen user id ile ilgili kullanıcının verilerini çekmek olmalı. İstekleri **"axios"** kütüphanesini kullanarak yapmanız gerekiyor. İsteği yaparken aşağıdaki endpointin sonundaki rakamı parametrede gelen user id'ile değiştirmeniz gerekiyor.

	 [https://jsonplaceholder.typicode.com/users/1](https://jsonplaceholder.typicode.com/users/1)

-  Yine aynı fonksiyonun içerisinde ve yine aynı user id için bir de "posts" isteği yapılmalıdır.İsteği yaparken aşağıdaki endpoint'in sonundaki rakamı parametrede gelen user id'ile değiştirmeniz gerekiyor.

	[https://jsonplaceholder.typicode.com/posts?userId=1](https://jsonplaceholder.typicode.com/posts?userId=1)

-  Artık elimizde kullanıcı bilgileri ve bu kullanıcının post'ları var. Bu iki veriyi birleştirip return edin. 
- # JS ASAMALARI__________________
1. İlk olarak terminalde npm init diyerek yeni bir package.json ve app.js oluşturduk.
2. import axios from "axios" ile axios kütüphanesini çağırdık.
3. userslar ve postlar için 2 tane değişken tanımladık. bunlar arrow fonksiyon şeklinde. parametresi userId.
4. Yeni bir promise tanımlayarak return ettik.Promise yapısı(resolve,reject) şeklinde. Try ile doğru çalışırsa resolve ve then işlemleri gerçekleşir. yok hata verirse reject ve catch ile e çalışır. Ayrıca await sadece async fonksiyonda çalıştığı için async tanımlarız. ..return new Promise (async(resolve,reject)=>...)
5. getData diyerek birden fazla kez data çağıracağımız için tanımladığımız her bir parametre için değerini yazarız. {data:user} ve {data:post} şeklinde
6. linkleri fakejson'dan çektikten sonra sondaki sayıyı silip her değer için dönebilsin diye +userId parametresini ekledik.
7. userId'leri async tanımlı getData fonksiyonu ile çağırdık.
8. her seferinde .then .catch yazmamak için const parametre=await fonksiyon(userId) yapısını kullandık.
9. user'ların içine post diye bir kısmı post ettik.yani içine yerleştirdik. Böylece sadece user'i return etmemiz yeterli oldu. Diğer türlü her biri asnc olduğu için kendi hzına göre değişik zamanlarda değişik sırada dönerdi. Böylece sıralamış olduk.
10. Tüm bunu try içine yerleştirerek .then olunca çalışan kısmı belirtmiş olduk. eğer hata verirse de catch ile "error" almış olacağız. 
11. export default getData diyerek de getData fonksiyonunu dışarı aktarmış olduk.
12. buradan sonra callback fonksiyonunu index.js ye yazdığımız için terminale "node index.js" yazarak istediğimiz verileri çağırmış olacağız.
index.js 'de import data from "./app.js"; app.js dosyasını içe aktarıyoruz. sonra .then ve .catch'i console'a yazdırıyoruz.
(export default,ES6'nın bir modülü (dosyayı) dışa aktarmak ve onu başka bir modülde (dosya) kullanmak için kullanılan özelliğidir.
default exportdosyadan (modül) yalnızca bir nesneyi (değişken, işlev, sınıf) dışa aktarmak istiyorsanız kuraldır.)
