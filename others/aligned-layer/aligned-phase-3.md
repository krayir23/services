# Aligned Phase 3

{% hint style="info" %}
* Bir **Ethereum cüzdanı oluşturun.**
* İçine **0.01** gibi bir miktar **Holesky ağında ETH** gönderin.
* Oluşturduğunuz cüzdanın **Private key** çıkarın ve hazırda bekletin.
{% endhint %}



Rust kurulumu

```bash
wget https://raw.githubusercontent.com/Hitasyurekk/aligned-layer-phase3/main/rust.sh && chmod +x rust.sh && ./rust.sh
```

Foundry kurulumu

```bash
curl -L -o foundry.sh https://raw.githubusercontent.com/Hitasyurekk/aligned-layer-phase3/main/foundry.sh && chmod +x foundry.sh && ./foundry.sh
```

Config kurulumu

```bash
sudo apt update && sudo apt install pkg-config libssl-dev
```

Komutu yazın ve private key girin

```bash
npm install -g cast-cli

source ~/.bashrc

[ -d ~/.aligned_keystore ] && rm -rf ~/.aligned_keystore && echo "Deleted existing directory ~/.aligned_keystore." ; mkdir -p ~/.aligned_keystore && cast wallet import ~/.aligned_keystore/keystore0 --interactive
```

Aligned dosyalarını indirme

```bash
[ -d aligned_layer ] && rm -rf aligned_layer && echo "Deleted existing aligned_layer directory." ; git clone https://github.com/yetanotherco/aligned_layer.git && cd aligned_layer/examples/zkquiz

make answer_quiz KEYSTORE_PATH=~/.aligned_keystore/keystore0
```

Quiz cevapları

{% hint style="info" %}
y , c , c , a , y
{% endhint %}

