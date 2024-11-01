---
description: Semaphore V4 Ceremony
---

# Risc Zero

> Herhangi bir sunucuda yapabilirsiniz. **Sürekli çalışacak bir şey değil katkıda bulunduktan sonra işlem bitecek.** Kullandığım sunucu: **Ubuntu 22.04**

#### Sunucu güncelleme

```bash
sudo apt update
sudo apt upgrade -y
```

#### Nvmi yükleyelim

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.0/install.sh | bash
source ~/.bashrc
```

#### Geçici dizin oluşturup içine giriyoruz

```bash
mkdir ~/p0tion-tmp
cd ~/p0tion-tmp
```

#### Nvm v16.20 kuralım

```bash
nvm install 16.20
nvm use 16.20
```

#### phase2cli yüklüyoruz

```bash
npm i @p0tion/phase2cli
```

GitHub ile kimlik doğrulaması yapmak gerekiyor. Aşağıdaki linki açın

[https://github.com/login/device\
](https://github.com/login/device)

#### Aşağıdaki kodu sunucuda içinde çalıştırın

```bash
npx phase2cli auth
```

> 8 dijit şifreyi verecek verdiği şifreyi açılan linke giriniz - Github'ınızı bağlayınız. "Congratulations, you're all set!" olarak şifreyi doğru girerseniz Github sayfanızda mesaj göreceksiniz

### Katkıda bulunma kısmı

<pre class="language-bash"><code class="lang-bash"><strong>//Screen oluşturalım
</strong>screen -S risczero

//Dizine geçelim
cd ~/p0tion-tmp
</code></pre>

Alttaki komut çalıştığında **Semaphore V4 Ceremony** gelecek **Enter** tıklayın **Randomly/Manually** gelecek tekrar **Enter**.

```bash
npx phase2cli contribute
```

**32 Circuit** tamamlaması gerek **yaklaşık 30 dk** sürecektir. İşlem tamamlanınca Githubunuzda bir **Gist** oluşturacak ve linkini göreceksiniz onu kopyalayın ve **bir yere kayıt edin.** Altında da bir **Tweet linki olacak onu da kopyalayıp paylaşın.**

Hata alırsanız daha sonra tekrar deneyin.

#### Kodları silme ve kaldırma

```bash
npx phase2cli clean
npx phase2cli logout
rm -rf ~/p0tion-tmp
```

