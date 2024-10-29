# Nexus Proof

{% hint style="info" %}
Herhangi bir sunucuda yapabilirsiniz. **Sürekli çalışacak bir şey değil proof aldığınızda işlem bitecek.** Kullandığım sunucu: **Ubuntu 22.04**
{% endhint %}

{% stepper %}
{% step %}
Güncelleme

```bash
sudo apt update -y && sudo apt upgrade -y
sudo apt install cmake
sudo apt install build-essential
```
{% endstep %}

{% step %}
Rustup kurulumu

1 seçeneğini seçiyoruz

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
{% endstep %}

{% step %}
Rust kurulumu tamamlandıktan sonra

```bash
. "$HOME/.cargo/env"
rustup target add riscv32i-unknown-none-elf
```
{% endstep %}

{% step %}
Nexus tool kurulumu

Burası biraz uzun sürer - hatalar görürseniz sorun yok.

```bash
cargo install --git https://github.com/nexus-xyz/nexus-zkvm nexus-tools --tag 'v1.0.0'
```
{% endstep %}

{% step %}
Nexus oluşturuyoruz

```bash
cargo nexus new nexus-project
```
{% endstep %}

{% step %}
Main.rs değiştireceğiz

```bash
cd nexus-project
nano ./src/main.rs
```

İçersindeki kodları silip aşağıdaki bloğu girin

```bash
#![no_std]
#![no_main]

fn fib(n: u32) -> u32 {
    match n {
        0 => 0,
        1 => 1,
        _ => fib(n - 1) + fib(n - 2),
    }
}

#[nexus_rt::main]
fn main() {
    let n = 7;
    let result = fib(n);
    assert_eq!(result, 13);
}
```

**CTRL + X tıklayın. Y tıklayıp Entera tıklayın.**
{% endstep %}

{% step %}
Contratı run edelim

```bash
cargo nexus run
cargo nexus run -v
```
{% endstep %}

{% step %}
Prove etmesini bekleyelim işlemlerin

```bash
cargo nexus prove
```
{% endstep %}

{% step %}
Verify işlemini tamamlayalım

```
cargo nexus verify
```
{% endstep %}
{% endstepper %}

{% hint style="danger" %}
#### **nexus-project** dizinde ki **nexus-proof** dosyamızı kaydedip saklayalım.
{% endhint %}

