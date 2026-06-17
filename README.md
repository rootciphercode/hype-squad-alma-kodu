# hype-squad-alma-kodu
# Discord HypeSquad House Changer

Discord istemcisi içindeki dahili Webpack modüllerini kullanarak HypeSquad evinizi tarayıcı veya uygulama konsolu üzerinden hızlıca değiştirmenizi sağlayan hafif ve işlevsel bir JavaScript scripti.

## 🚀 Nasıl Çalışır?

Bu script, Discord'un front-end mimarisinde kullandığı `webpackChunkdiscord_app` yapısına dinamik olarak sızar. Discord'un kendi dahili HTTP istek modülünü (`HTTPUtils`) tespit ederek, doğrudan Discord API'sinin `/hypesquad/online` uç noktasına (endpoint) güvenli bir POST isteği gönderir.

## 🛠️ Nasıl Kullanılır?

1. **Discord** masaüstü uygulamasını veya tarayıcı sekmesini açın.
2. Geliştirici araçlarını açmak için `Ctrl + Shift + I` (Mac kullanıyorsanız `Cmd + Option + I`) tuşlarına basın.
3. Üst menüden **Console** (Konsol) sekmesine geçiş yapın.
4. Aşağıdaki kod bloğunu kopyalayın, konsola yapıştırın ve `Enter` tuşuna basın:

```javascript
let wreq = webpackChunkdiscord_app.push([[Symbol()],{},r=>r]);
webpackChunkdiscord_app.pop();
const chunks = Object.entries(wreq.m)
const findChunkByCode = (...codes) => {
    for (let i = 0; i < chunks.length; i++) {
        const [id,func] = chunks[i]
        const chunkCode = func.toString()

        if (codes.every(code=>chunkCode.includes(code))) return wreq(id)
    }
}

const api = Object.values(findChunkByCode("HTTPUtils")).find(e=>e?.get)

// house_id değerini değiştirmek istediğiniz evin ID'si ile güncelleyebilirsiniz.
api.post({url: "/hypesquad/online", body: {house_id: 1}})

🏠 Ev Kimlikleri (House IDs)
Kodun en alt satırında yer alan house_id: 1 kısmındaki sayıyı değiştirerek geçmek istediğiniz evi seçebilirsiniz:
IDEv Adı (House Name)1House of Bravery (Cesaret)2House of Brilliance (Deha)3House of Balance (Denge)


⚠️ Sorumluluk Reddi (Disclaimer)
Bu proje tamamen eğitim, test ve Discord'un dahili Webpack mimarisini anlama amacıyla geliştirilmiştir. Hesap güvenliğiniz için kaynağını bilmediğiniz scriptleri konsolunuzda çalıştırmamanız önerilir. Bu scriptin kullanımından doğabilecek her türlü sorumluluk kullanıcının kendisine aittir.
