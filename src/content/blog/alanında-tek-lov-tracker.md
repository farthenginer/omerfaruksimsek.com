---
title: Platonikten Ürüne; LOV - Tracker
description: "Ne kadar ararsanız arayın: Uygulama mağazalarında LOV'un yaptığı
  işlevin aynısını yapan bir mobile app bulamazsınız. Kulağa garip geldiğinin
  farkındayım. Hazırsanız LOV'un ortaya çıkma ve zorlu yayın süreçlerinden
  bahsedelim!"
pubDate: Jul 04 2026
---
![Herşey lisedeyken başladı.](../../assets/uploads/depositphotos_658822814-stock-photo-two-women-make-heart-shape.jpg "LOV'un başlangıcı: Platonik bir aşk...")

Lise 3. sınıfa başladığım zamanlar bir kızdan fena halde hoşlanıyordum. Tabii o zamanlar reddedilme korkusundan dolayı kıza açılamadım, hiç konuşamadım da. Sürekli instagram profilini stalklayıp takipçi sayısını, profil resmini vs. kontrol ediyordum. bi yerden sonra bu durum zamanımı almaya başladı. Bende bu problemimi nasıl çözebileceğimi düşündüm ve aklıma bi arka plan servisi yazmak geldi. 

[Rapid API](https://rapidapi.com/) platformundan bulduğum ücretsiz bir instagram profile scraper API'ını, firebase cloud functions'dan belirli aralıklarla çağırıp önceki snapshots'lar ile karşılaştıran bir sistem inşaa ettim. Eğer değişiklik algılanırsa **FCM** ile mobil bildirim gönderiliyor, bu sayede stalk çok daha keyifli ve verimli oluyordu. Sistem aslında çokta karmaşık değildi. Temel mantık şunun üzerinde kuruluydu: 

```
if(oldSnapshot.value != newSnapshot.value)
{
    //Call FCM
}
```

Tabii o zamanlar bununla uğraşacak pek vaktim olmadığından Unity ile basit bir Android app yapıp firebase bağımlılıklarını ekleyerek bildirim atmasını sağlıyordum. Ani bir karar ile 2024 yılının mayıs ayında projenin tüm fonksiyonlarını durdurdum. Tüm kaynak kodları ve yapıları da çöpe attım. Ama fikir beni heyecanlandırmaktan hiç vazgeçmedi. Bu sebeple aklımın hep bir köşesindeydi...

Bazen bazı projeler yazılımcıları ile arasında bağ kurar. Bu tıpkı bi civcivin büyüdüğünü gün gün takip etmek gibidir. LOV da benim mor civcivimdi aslında. 2026 yılının ocak ayında feci şekilde terk edildim. Bilirsiniz, boşa verilmiş umutlar, bilerek kırılmış kalpler, tutulmamış sözler... Terk edildikten sonraki 2 ay kendime gelemedim açıkçası. Ve artık benim için bi anlamı kalmamıştı da. 

Sınavdan kötü bir puan aldıysanız sonraki sınavda düzeltebilirsiniz. Kötü bir gün geçiriyorsanız biraz dinlemek iyi gelir. Kolunuz kırıldıysa biraz sabredin, kaynayacaktır. Bu problemleri çözmek için biraz sabır + efor yeterli olacaktır. Fakat öyle sorunlar vardır ki bunların hiçbir çözümü yok :) Örneğin biri tarafından terk edilmek veya boyunuzun kısa olması gibi. Bu durumda muhtemelen hayal kırıklığı veya sorunun yarattığı stres etkisini yakıt olarak kullanmak yapabileceğiniz en mantıklı şey olacaktır. Bende böyle yaptım. Yaşadığım bu derin üzüntü sonrasında eskiden yaptığım stalk uygulamasını bir ürüne dönüştürme fikri bana hem toparlama sürecinde hemde kendimi yeniden moda sokma sürecinde oldukça yardımcı oldu. Ve 24 şubat 2026 itibari ile LOV projesi resmen başladı.



"LOV" aslında oldukça havalı bir isim. Anlamı daha da havalı bence :) Son yıllardaki Türkiye - İspanya arasındaki dostluğun kardeşliğe dönüşmesi, İspanya kültürü ve İspanyollara duyduğum sempatiyi 2 ye katladı diyebilirim. Stalk yaparken sürekli aklımızda dönen "son bir defa daha bakayım" düşüncesi kaçınılmazdır. LOV da oradan geliyor aslında. İspanyolca bi ifade olan; "La Otra Vez" yani "bi kez daha". Tabii işin içerisinde market optimizasyonu gibi etkenler de girince LOV - Tracker kullanıcıları ile buluşuyor. İsterseniz biraz daha teknik tarafa kayıp geliştirme süreçlerinden bahsedelim.

### MVP Süreci

Ürünün minimum sürümünü çıkarma konusunda iyi olduğumu düşünüyorum. Öyle ki LOV uygulaması kendi problemimden yola çıktığından ötürü ürün çıkarma konusunda da pek zorluk çekmedim. Öncelikle hangi ortamda geliştireceğime karar vermem gerekiyordu. Xcode ve Android studio kullanarak native geliştirmek benim açımdan pek mantıklı değildi. Çünkü ben tek kişilik bir orduyum. Bu da UI dan kodlamaya tüm işin bana kalacağı anlamına geliyordu. Tam da o sırada hızlı MVP çıkarmasıyla ün kazanan FlutterFlow'a bi şans vermek istedim. Hemen Macbook bilgisayarıma kurup gerekli kurulumları yaptım. Nihai hedefim Mart'ın başında kodlamaya başladığım LOV'u 1 nisanda çıkarmaktı. 



![](../../assets/uploads/chatgpt-image-5-mar-2026-22_50_21.png "Uygulamanın nasıl çalışacağını gösteren şema")
