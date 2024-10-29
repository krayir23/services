# Nubit Light Node

{% hint style="info" %}
Herhangi bir sunucuya kurabilirsiniz. **Sürekli çalışacak.** \
Kullandığım sunucu: **Ubuntu 22.04**
{% endhint %}

{% stepper %}
{% step %}
Screen oluşturalım

```bash
screen -S nubit
```
{% endstep %}

{% step %}
Nubit çalıştıralım

{% hint style="danger" %}
Aşağıdaki komutu girince logların içinde **PUBKEY**, **ADDRESS**, **MNEMONIC** gibi loglar göreceksiniz hepsini seçin (CTRL + C falan yapmayın seçmeniz kopyalamak için yeterli) bir yere kayıt edin.
{% endhint %}

```bash
curl -sL1 https://nubit.sh | bash
```

Screenden çıkın **CTRL + A + D**

Eğer ekran çok hızlı geçtiyse pubkey'inizi görmek için (screen dışında deneyin) çıktıdaki **key** kısmının içindekini alın sadece

```bash
$HOME/nubit-node/bin/nkey list --p2p.network nubit-alphatestnet-1 --node.type light
```

Adresinizin kurtarma tümceciklerini (mnemonic) görmek için ise

```
nano $HOME/nubit-node/mnemonic.txt
```
{% endstep %}

{% step %}
Verify etme

Aşağıdaki siteye gidin. **Kelimeleri girdiğiniz Keplr Wallet** ile bağlayın ve loglardan aldığınız **Pubkeyi verify ediyoruz.**

[https://alpha.nubit.org/](https://alpha.nubit.org/)
{% endstep %}
{% endstepper %}

