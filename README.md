# Ders Takip — İlk MVP

Bu klasör, iPhone ana ekranına eklenebilen ve çevrimdışı çalışabilen bir PWA prototipidir.

## İçindekiler
- `index.html`: uygulama arayüzü ve işlevleri
- `manifest.json`: ana ekrana kurulum tanımı
- `sw.js`: temel çevrimdışı önbellek
- `icon-192.png`, `icon-512.png`: uygulama simgeleri

## Önemli
Veriler yalnızca aynı cihazdaki tarayıcının `localStorage` alanında tutulur. Tarayıcı verilerini silmek verileri silebilir. Uygulamadaki **Yedeği indir** işlevini düzenli kullanın. Bu ilk sürümde bulut senkronizasyonu, şifreli kullanıcı girişi ve gerçek zamanlı uzaktan yedekleme yoktur.

## iPhone'a yükleme
PWA'nın iPhone ana ekranına eklenebilmesi için HTTPS üzerinden yayımlanması gerekir. Bu klasörü HTTPS destekleyen bir statik barındırma servisine yükleyin. Ardından iPhone'da Safari ile uygulamanın adresini açın:
1. Paylaş düğmesine dokunun.
2. **Ana Ekrana Ekle** seçeneğini seçin.
3. Eklemeyi onaylayın.

Dosyayı doğrudan `index.html` olarak açmak, PWA kurulumunu ve service worker'ı etkinleştirmez.

## Mevcut özellikler
- Öğrenci profilleri: ad, soyad, veli, telefon, sınıf, not
- Ders kaydı: tarih, konu, konu değerlendirmesi, ödev durumu, öğretmen notu
- Sınıf bazlı başlangıç konu listeleri (resmî/güncel müfredat yerine geçmez; kullanıcı tarafından gönderilecek müfredata göre güncellenmeli)
- 8. sınıf profillerinde LGS denemesi: 6 ders, doğru/yanlış/boş, net = doğru - yanlış/3 ve toplam net grafiği
- Haftalık ders planı ve tek seferlik/telafi planı
- Genel ödev ve ders değerlendirme özeti
- JSON yedek dışa/içe aktarma
- Basit çevrimdışı önbellek

## Bildirimler hakkında
Arayüz bildirim izni isteyebilir; ancak bu MVP, ders saatlerini arka planda kontrol eden ve iOS'ta güvenilir şekilde yerel bildirim planlayan tam bir bildirim sistemi içermez. Güvenilir hatırlatmalar için sonraki aşamada iOS yerel bildirim entegrasyonu veya desteklenen bir push/planlama altyapısı gerekir.

## Müfredat
4. sınıf için başlangıç konu listesi, MEB Türkiye Yüzyılı Maarif Modeli'nin resmî 4. sınıf sayfasındaki 7 tema ve MAT.4 öğrenme çıktıları esas alınarak güncellendi: https://tymm.meb.gov.tr/ogretim-programlari/ilkokul-matematik-dersi/5
4. sınıf listesi uygulamada tema adlarını ve öğrenme çıktısı kodlarını gösterir. 5–8. sınıf listeleri hâlâ geçici başlangıç listesidir; bunlar ilgili güncel resmî programlara göre ayrıca güncellenmelidir.


6. sınıf listesi MEB resmî sayfasına göre güncellendi: https://tymm.meb.gov.tr/ogretim-programlari/ortaokul-matematik-dersi/7

8. sınıf listesi, MEB'in resmî 8. sınıf programındaki yedi tema ve MAT.8 öğrenme çıktılarının kısa takip başlıklarıyla güncellenmiştir: https://tymm.meb.gov.tr/ogretim-programlari/ortaokul-matematik-dersi/9
Bu liste kısa takip başlıklarını içerir; tüm süreç bileşenleri henüz uygulamaya aktarılmamıştır.

Sürüm 7 düzeltmesi: JavaScript sözdizimi hatası giderildi ve iOS Safari uyumluluğu için form alanları açık DOM referanslarıyla bağlandı.
