# Zleno · Linux

[← Zleno](../README.md) · [English ↓](#english) · [Geliştirme notları](../CHANGELOG.md)

## Yayın durumu

**0.1.9 için Arch / CachyOS, DEB ve RPM paketleri üretildi.** Kurulum ve gerçek kullanım testleri sürüyor. AppImage henüz tamamlanmadı.

Linux paketleri şu anda herkese açık indirmeye sunulmuyor. Doğrulanan paketler yayımlandığında [Releases](https://github.com/idginity124/Zleno/releases) bölümüne eklenecek. Aşağıdaki adımlar, ilgili paket yayımlandıktan sonra kullanmak içindir.

## Hangi paket bana uygun?

| Sistem | Paket | Durum |
| :--- | :--- | :--- |
| Arch Linux / CachyOS · x86_64 | `.pkg.tar.zst` | Paket üretildi; kurulum ve kullanım testleri bekliyor |
| Debian / Ubuntu ailesi · x86_64 | `.deb` | Paket üretildi; hedef dağıtımda yeniden derleme ve test gerekiyor |
| RPM tabanlı dağıtımlar · x86_64 | `.rpm` | Paket üretildi; hedef dağıtımda yeniden derleme ve test gerekiyor |
| Diğer dağıtımlar | `.AppImage` | Hazırlanıyor |

Mevcut paketler CachyOS üzerinde glibc 2.44 ile derlendi. Eski glibc kullanan dağıtımlarda çalışmaları garanti edilmez. DEB/RPM biçimi tek başına dağıtım uyumluluğu sağlamaz. ARM64 sürümü henüz yok.

## Arch / CachyOS kurulumu

Paket yayımlandığında `.pkg.tar.zst` ve yanındaki `.sha256` dosyasını aynı klasöre indir. Bu klasörde terminal aç:

```bash
sha256sum -c zleno-desktop-bin-0.1.9-1-x86_64.pkg.tar.zst.sha256
sudo pacman -U ./zleno-desktop-bin-0.1.9-1-x86_64.pkg.tar.zst
```

Doğrulama `OK` vermeden kuruluma devam etme. SHA-256 dosya bütünlüğünü kontrol eder; yayıncı imzası değildir. Mevcut test paketi GPG ile imzalanmadı.

Uygulamayı menüde **Zleno Desktop** adıyla bulabilir veya `zleno_desktop` komutuyla açabilirsin. Güncellemek için yeni sürüm paketinde aynı `pacman -U` adımını uygula.

Kaldırmak için:

```bash
sudo pacman -R zleno-desktop-bin
```

## Masaüstünde nasıl davranıyor?

- **Wayland:** mikrofon kısayolları uygulama içindeyken kullanılabilir. Masaüstü genelindeki kısayollar native X11 oturumu gerektirir.
- **Arka plan:** pencere küçültülür; sistem tepsisi desteği masaüstüne göre değişebilir.
- **Ekran paylaşımı:** WebKit ve masaüstü yakalama desteğine bağlıdır. Her oturumda ekran veya sistem sesi paylaşımı sunulacağı garanti edilmez.
- **Dil:** arayüz şu an Türkçe; İngilizce desteği planlanıyor.

## İlk denemede bize yardımcı ol

Giriş ve çıkışı, iki kişiyle sesli odayı, mikrofon/kamera değişimini ve bildirimleri dene. Bir sorunla karşılaşırsan [hata bildirimi aç](https://github.com/idginity124/Zleno/issues/new/choose).

Bildirime dağıtımını, masaüstünü, X11/Wayland bilgisini, uygulama sürümünü ve tekrar etme adımlarını ekle. Günlük paylaşmadan önce hesap bilgilerini, özel mesajları ve erişim belirteçlerini çıkar.

---

## English

**Arch / CachyOS, DEB and RPM packages for 0.1.9 have been built.** Installation and real-world testing remain in progress; AppImage is not complete. Downloads are not public yet. Validated packages will be added to [Releases](https://github.com/idginity124/Zleno/releases).

Current builds use CachyOS with glibc 2.44 and x86_64. They are not verified for older distributions. DEB/RPM packages need an appropriate target-distribution build and testing before broad release. ARM64 packages are not available.

### Arch / CachyOS, after publication

Download the package and its `.sha256` file into the same directory, then run:

```bash
sha256sum -c zleno-desktop-bin-0.1.9-1-x86_64.pkg.tar.zst.sha256
sudo pacman -U ./zleno-desktop-bin-0.1.9-1-x86_64.pkg.tar.zst
```

Proceed only if checksum verification succeeds. SHA-256 checks integrity, not publisher identity; the current test package is not GPG-signed. Launch **Zleno Desktop** from your application menu or run `zleno_desktop`. Install future updates with `pacman -U` using the new package. Remove it with `sudo pacman -R zleno-desktop-bin`.

Wayland supports in-app shortcuts; global shortcuts require native X11. Backgrounding minimizes the window. Screen and system-audio capture depend on WebKit and desktop support. The interface is currently Turkish.

Please test sign-in/out, two-person voice rooms, device changes and notifications. [Report an issue](https://github.com/idginity124/Zleno/issues/new/choose) with your distribution, desktop, X11/Wayland session, app version and reproduction steps. Remove credentials and private conversations from logs.
