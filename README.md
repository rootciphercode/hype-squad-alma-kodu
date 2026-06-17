# Discord HypeSquad House Changer

Discord istemcisi içindeki dahili Webpack modüllerini kullanarak HypeSquad evinizi tarayıcı veya uygulama konsolu üzerinden hızlıca değiştirmenizi sağlayan hafif ve işkelser bir JavaScript scripti.

## 🚀 Nasıl Çalışır?

Bu script, Discord'un front-end mimarisinde kullandığı `webpackChunkdiscord_app` yapısına dinamik olarak sızar. Discord'un kendi dahili HTTP istek modülünü (`HTTPUtils`) tespit ederek, doğrudan Discord API'sinin `/hypesquad/online` uç noktasına (endpoint) bir POST isteği gönderir.

## 🛠️ Nasıl Kullanılır?

1. **Discord** masaüstü uygulamasını veya tarayıcı sekmesini açın.
2. Geliştirici araçlarını açmak için `Ctrl + Shift + I` (Mac için `Cmd + Option + I`) tuşlarına basın.
3. Üst menüden **Console** (Konsol) sekmesine geçiş edin.
4. Projedeki `script.js` kodunu kopyalayın, konsola yapıştırın ve `Enter` tuşuna basın.

## 🏠 Ev Kimlikleri (House IDs)

Kodun en alt satırında yer alan `house_id: 1` kısmındaki sayıyı değiştirerek geçmek istediğiniz evi seçebilirsiniz:

| ID | Ev Adı (House Name) |
| :--- | :--- |
| `1` | **House of Bravery** (Cesaret) |
| `2` | **House of Brilliance** (Deha) |
| `3` | **House of Balance** (Denge) |

## ⚠️ Sorumluluk Reddi (Disclaimer)

Bu proje tamamen eğitim, test ve Discord'un dahili Webpack mimarisini anlama amacıyla geliştirilmiştir. Hesap güvenliğiniz için kaynağını bilmediğiniz scriptleri konsolunuzda çalıştırmamanız önerilir. Bu scriptin kullanımından doğabilecek her türlü sorumluluk kullanıcının kendisine aittir.
