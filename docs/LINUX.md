# Zleno · Linux

[← Zleno](../README.md) · [English ↓](#english) · [Geliştirme notları](../CHANGELOG.md)

## İndir

**[Linux 0.1.9 paketlerini indir →](https://github.com/idginity124/Zleno/releases/tag/desktop-v0.1.9-linux-test)**

| Sistem | Paket |
| --- | --- |
| Arch Linux / CachyOS · x86_64 | `.pkg.tar.zst` |
| Debian / Ubuntu ailesi · deneysel | `.deb` |
| RPM tabanlı dağıtımlar · deneysel | `.rpm` |

Paketler CachyOS x86_64 / glibc 2.44 üzerinde üretildi. Gerçek cihaz testleri henüz tamamlanmadı; DEB/RPM paketleri hedef dağıtımlarda doğrulanmadı. Eski glibc kullanan dağıtımlar için uygun tabanda yeniden derleme gerekiyor. AppImage ve ARM64 henüz yok.

<a name="imza-dogrulama"></a>
## İmzayı doğrulama

Paketler ayrı GPG imza dosyalarıyla (`.sig`) sunulur. İmza, paketin bu anahtarla imzalandığını ve değiştirilmediğini kontrol eder; dağıtım uyumluluğu veya hatasız çalışma garantisi değildir. DEB/RPM dosyalarında yerleşik paket yöneticisi imzası yerine bu ayrı imzalar kullanılır.

Beklenen anahtar parmak izi:

```text
D395 593F 3C7B 3844 3447 1081 E228 12B0 7036 A65E
```

Yayın sayfasından istediğin paketi, onun `.sig` dosyasını, `Zleno-Linux-signing-key.asc`, `SHA256SUMS` ve `SHA256SUMS.sig` dosyalarını aynı klasöre indir.

```bash
gpg --import Zleno-Linux-signing-key.asc
gpg --fingerprint D395593F3C7B384434471081E22812B07036A65E
gpg --verify SHA256SUMS.sig SHA256SUMS
sha256sum --ignore-missing -c SHA256SUMS
```

Gösterilen tam parmak izini yukarıdaki değerle karşılaştır. İmza doğrulaması ve indirdiğin dosyanın checksum kontrolü başarılı olmalı. GPG, imza doğru olsa da anahtarın kimliğine henüz güven atanmamış olduğunu söyleyebilir; bu, imza kontrolünden ayrı bir konudur.

## Arch / CachyOS kurulumu

Paketin kendi imzasını da doğrula:

```bash
gpg --verify zleno-desktop-bin-0.1.9-1-x86_64.pkg.tar.zst.sig zleno-desktop-bin-0.1.9-1-x86_64.pkg.tar.zst
```

Parmak izini doğruladıktan sonra pacman'ın da bu yayıncı anahtarını tanıması için:

```bash
sudo pacman-key --add ./Zleno-Linux-signing-key.asc
sudo pacman-key --finger D395593F3C7B384434471081E22812B07036A65E
sudo pacman-key --lsign-key D395593F3C7B384434471081E22812B07036A65E
sudo pacman -U ./zleno-desktop-bin-0.1.9-1-x86_64.pkg.tar.zst
```

`--lsign-key`, doğruladığın yayıncı anahtarına kendi sisteminde güven atar. Kimliğini doğrulamadığın başka anahtarlara bu adımı uygulama.

Menüden **Zleno Desktop**'ı açabilir veya `zleno_desktop` çalıştırabilirsin. Güncelleme yeni paketle aynı `pacman -U` adımıdır. Kaldırma: `sudo pacman -R zleno-desktop-bin`.

## Masaüstü desteği

- Wayland'da mikrofon kısayolları uygulama içindeyken kullanılabilir; global kısayollar native X11 gerektirir.
- Arka plana gönderme pencereyi küçültür. Sistem tepsisi davranışı masaüstüne göre değişebilir.
- Ekran ve sistem sesi paylaşımı WebKit/masaüstü yakalama desteğine bağlıdır.
- Arayüz şu an Türkçe; İngilizce desteği planlanıyor.

Sorunları [Issues](https://github.com/idginity124/Zleno/issues/new/choose) üzerinden dağıtımın, masaüstün, X11/Wayland bilgisi, uygulama sürümü ve tekrar etme adımlarıyla paylaş. Özel mesajları ve erişim bilgilerini günlüklerden çıkar.

---

## English

**[Download Linux 0.1.9](https://github.com/idginity124/Zleno/releases/tag/desktop-v0.1.9-linux-test)**

Built on CachyOS x86_64 with glibc 2.44. Real-device tests are not complete. DEB/RPM packages are experimental and have not been validated on their target distributions; older systems need an appropriate distribution build. AppImage and ARM64 are not available.

<a name="signature-verification"></a>
### Verify signatures

Expected signing fingerprint:

```text
D395 593F 3C7B 3844 3447 1081 E228 12B0 7036 A65E
```

Download a package, its `.sig`, the public key `Zleno-Linux-signing-key.asc`, `SHA256SUMS` and `SHA256SUMS.sig` into one directory. Run the import, fingerprint, manifest verification and checksum commands above. Compare the complete fingerprint before trusting the key. The signatures are detached; DEB/RPM native package-manager signing is not included.

For Arch, also verify the package signature, add the checked public key to pacman's keyring, compare its fingerprint, locally sign that publisher key with `pacman-key --lsign-key`, and install with `pacman -U` as shown above. This assigns local trust to that publisher key. Launch `zleno_desktop`; remove with `sudo pacman -R zleno-desktop-bin`.

A valid signature establishes authenticity relative to the verified key and file integrity, not compatibility or absence of bugs. GPG's trust warning is distinct from signature validity. Wayland supports in-app shortcuts; global shortcuts require native X11. Capture depends on WebKit and desktop support. The interface is currently Turkish.
