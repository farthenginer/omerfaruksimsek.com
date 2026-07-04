---
title: Platonikten Ürüne; LOV - Tracker
description: "Ne kadar ararsanız arayın: Uygulama mağazalarında LOV'un yaptığı
  işlevin aynısını yapan bir mobile app bulamazsınız. Kulağa garip geldiğinin
  farkındayım. Hazırsanız LOV'un ortaya çıkma ve zorlu yayın süreçlerinden
  bahsedelim!"
pubDate: Jul 04 2026
---
![Herşey lisedeyken başladı.](../../assets/uploads/depositphotos_658822814-stock-photo-two-women-make-heart-shape.jpg "LOV'un başlangıcı: Platonik bir aşk...")

##### Giriş

Lise 3. sınıfa başladığım zamanlar bir kızdan fena hâlde hoşlanıyordum. Tabii o zamanlar reddedilme korkusundan dolayı kıza açılamadım, hiç konuşamadım da. Sürekli **Instagram profilini** stalklayıp takipçi sayısını, profil resmini vs. kontrol ediyordum. Bir yerden sonra bu durum zamanımı almaya başladı. Ben de bu problemimi nasıl çözebileceğimi düşündüm ve aklıma bir arka plan servisi yazmak geldi.

[Rapid API](https://rapidapi.com/auth/login) platformundan bulduğum ücretsiz bir Instagram profile scraper API’ını, [Firebase](https://firebase.google.com/) Cloud Functions’dan belirli aralıklarla çağırıp önceki snapshot’lar ile karşılaştıran bir sistem inşa ettim. Eğer değişiklik algılanırsa FCM ile mobil bildirim gönderiliyor, bu sayede stalk çok daha keyifli ve verimli oluyordu. Sistem aslında çok da karmaşık değildi. Temel mantık şunun üzerine kuruluydu:

```
if(oldSnapshot.value != newSnapshot.value)
{
    //Call FCM
}
```

Tabii o zamanlar bununla uğraşacak pek vaktim olmadığından, **Unity** ile basit bir Android app yapıp Firebase bağımlılıklarını ekleyerek bildirim atmasını sağlıyordum. Ani bir kararla 2024 yılının Mayıs ayında projenin tüm fonksiyonlarını durdurdum. Tüm kaynak kodları ve yapıları da çöpe attım. Ama fikir beni heyecanlandırmaktan hiç vazgeçmedi. Bu sebeple aklımın hep bir köşesindeydi...

Bazen bazı projeler, yazılımcıları ile arasında bağ kurar. Bu tıpkı bir civcivin büyüdüğünü gün gün takip etmek gibidir. LOV da benim mor civcivimdi aslında. 2026 yılının Ocak ayında feci şekilde terk edildim. Bilirsiniz; boşa verilmiş umutlar, bilerek kırılmış kalpler, tutulmamış sözler... Terk edildikten sonraki iki ay kendime gelemedim açıkçası. Ve artık benim için bir anlamı da kalmamıştı.

Sınavdan kötü bir puan aldıysanız sonraki sınavda düzeltebilirsiniz. Kötü bir gün geçiriyorsanız biraz dinlenmek iyi gelir. Kolunuz kırıldıysa biraz sabredin, kaynayacaktır. Bu problemleri çözmek için biraz sabır + efor yeterli olacaktır. Fakat öyle sorunlar vardır ki bunların hiçbir çözümü yok :) Örneğin biri tarafından terk edilmek veya boyunuzun kısa olması gibi. Bu durumda muhtemelen hayal kırıklığı veya sorunun yarattığı stres etkisini yakıt olarak kullanmak yapabileceğiniz en mantıklı şey olacaktır. Ben de böyle yaptım. Yaşadığım bu derin üzüntü sonrasında, eskiden yaptığım stalk uygulamasını bir ürüne dönüştürme fikri bana hem toparlanma sürecinde hem de kendimi yeniden moda sokma sürecinde oldukça yardımcı oldu. Ve 24 Şubat 2026 itibarıyla LOV projesi resmen başladı.

“LOV” aslında oldukça havalı bir isim. Anlamı daha da havalı bence :) Son yıllardaki Türkiye - İspanya arasındaki dostluğun kardeşliğe dönüşmesi, İspanya kültürü ve İspanyollara duyduğum sempatiyi ikiye katladı diyebilirim. Stalk yaparken sürekli aklımızda dönen “son bir defa daha bakayım” düşüncesi kaçınılmazdır. LOV da oradan geliyor aslında. İspanyolca bir ifade olan “La Otra Vez”, yani “bir kez daha”. Tabii işin içerisinde market optimizasyonu gibi etkenler de girince LOV - Tracker kullanıcıları ile buluşuyor. İsterseniz biraz daha teknik tarafa kayıp geliştirme süreçlerinden bahsedelim.

**MVP Süreci**

Ürünün minimum sürümünü çıkarma konusunda iyi olduğumu düşünüyorum. Öyle ki LOV uygulaması kendi problemimden yola çıktığından ötürü ürün çıkarma konusunda da pek zorluk çekmedim. Öncelikle hangi ortamda geliştireceğime karar vermem gerekiyordu. Xcode ve Android Studio kullanarak native geliştirmek benim açımdan pek mantıklı değildi. Çünkü ben tek kişilik bir orduyum. Bu da UI’dan kodlamaya tüm işin bana kalacağı anlamına geliyordu. Tam da o sırada hızlı MVP çıkarmasıyla ün kazanan FlutterFlow’a bir şans vermek istedim. Hemen MacBook bilgisayarıma kurup gerekli kurulumları yaptım. Nihai hedefim, Mart’ın başında kodlamaya başladığım LOV’u 1 Nisan’da çıkarmaktı.



![](../../assets/uploads/chatgpt-image-5-mar-2026-22_50_21.png "Uygulamanın nasıl çalışacağını gösteren şema")

Oldukça hızlı bir başlangıç yaptım. Tabii ki daha önceden uğraştığım mobil uygulamalar olmuştu fakat bunlar daha çok öğrenme sürecimin bir parçasıydı. Apify, API konusunda oldukça iddialı durduğu için onu tercih ettim. Geliştirme süreci 1 Nisan’a kadar sürdü ve bu süreçte çok keyif aldım. Tahmin edeceğiniz üzere 1 Nisan’a yetiştiremedim ama 26 Şubat’ta 12’den fazla dili destekleyen LOV yayınlandı.

Tabii bu yayınlanma aşamasını bir cümle ile anlatmam haksızlık olur. Geliştirme sürecinden kat ve kat daha zor olan yayınlama sürecini ele alalım.

**App Store Kabusu**

Apple’ın ne kadar katı bir ekosistem olduğunu kavrayabilmek için deneyimli bir iOS developer veya Apple kullanıcısı olmaya gerek yok; kısa bir izlenim yeterli. LOV, yapısı gereği insanlar hakkında yapay profiller oluşturan bir uygulama. Bilin bakalım kim bu konseptten nefret ediyor; Apple.

Şanslıyım ki Play Store tarafı Apple gibi üç kez red verecek kadar katı değil. Play Console geliştirici hesabını 14 yaşındayken açmış olmamdan ötürü yaşadığım kolaylık, uygulamamın 48 saat içerisinde onaylanıp yayınlanmasında büyük rol oynadı. LOV uygulaması şu an herhangi bir başarıya ulaşmış olmasa da fiyat politikasında yapacağım değişikliklerden sonra ciddi bir indirme sayısı hedefliyorum.

**Sonuç**

Her ürün başarılı olacak diye bir kural yok. Muhtemelen de olmayacak. Bence önemli olan kısım, ürünü yaparken ne öğrendiğin. Ben LOV’u yaparken çok şey öğrendim. Daha hızlı MVP yapmam gerektiği, mobil uygulamada ürünü geliştirmenin işin en küçük kısmını kapsadığı vs.

LOV’un hikâyesine genel bir çerçeveden baktığımda acının bir yakıtı olduğunu görüyorum. Bazı insanlar sizi derinden etkiler. Önce hayatınıza girerler, sonra kalbinize, sonra da öyle bir çıkarlar ki siz ne olduğunu bile anlamazsınız. Sonrası belli zaten; bazen bir şiir, bazen bir şarkı, bazen de bir LOV çıkar ortaya. İyi mi oldu kötü mü oldu asla anlayamazsınız. Önemli olan da bunu asla anlayamamaktır zaten.

“Durgundu limanlar, sendin sebepleri.” deyip çekilirsiniz...
