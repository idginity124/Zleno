# Zleno · Geliştirme notları

[← Zleno](README.md) · [English ↓](#english) · [Yol haritası](ROADMAP.md)

## 25 Ekim 2026

### Linux · 0.1.9 hazırlığı

- Arch Linux / CachyOS için yerel `.pkg.tar.zst` paketi üretildi.
- DEB ve RPM paketleri üretildi; SHA-256 dosyaları hazırlandı.
- Wayland kısayolları, arka plan davranışı ve ekran paylaşımı kullanılabilirlik kontrolleri iyileştirildi.
- AppImage hazırlığı ve gerçek cihaz testleri sürüyor. [Linux test paketleri indirmeye açıldı.](https://github.com/idginity124/Zleno/releases/tag/desktop-v0.1.9-linux-test)

Kurulum ve dağıtım uyumluluğu: [Linux rehberi](docs/LINUX.md).

### Android · 1.0.5 hazırlığı

Yeni sürüm için çıkışta yerel mesaj önbelleğinin temizlenmesi iyileştirildi. Google Play yayın hazırlığı sürüyor; bu sürüm henüz yayımlanmadı. Mevcut test sürecine [README’deki adımlardan](README.md#telefonda-dene) katılabilirsin.

### Hizmet güncellemesi

Sunucu tarafında erişim kontrolleri ve istek sınırları güncellendi. Kullanıcı geri bildirimleriyle ses, medya ve bildirim akışları doğrulanmaya devam ediyor.

Bu notlar geliştirme durumunu gösterir. Burada hazırlanan bir sürümün belirtilmesi, mağazada veya Releases bölümünde yayımlandığı anlamına gelmez.

---

## English

### October 25, 2026

**Linux 0.1.9 preparation:** native Arch / CachyOS, DEB and RPM packages have been built with SHA-256 files. Wayland shortcuts, background behavior and screen-capture capability handling were improved. AppImage and device testing remain in progress; [Linux test downloads are available](https://github.com/idginity124/Zleno/releases/tag/desktop-v0.1.9-linux-test). See the [Linux guide](docs/LINUX.md#english).

**Android 1.0.5 preparation:** local message-cache cleanup on sign-out was improved. Google Play release preparation continues; this version has not been published. Join the existing test through the [README](README.en.md#try-it-on-your-phone).

**Service update:** server-side access controls and request limits were updated. Voice, media and notification flows remain subject to real-world testing and feedback.

Development notes do not imply that a prepared version is already available in a store or GitHub Releases.
