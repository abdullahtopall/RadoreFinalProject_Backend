# Radore Final Project Backend

Bu proje, Radore için geliştirilmiş bir backend uygulamasıdır. Bu uygulama, çeşitli API uç noktaları sağlayarak veri yönetimi ve iş mantığı işlemlerini gerçekleştirmektedir.

## İçindekiler

- [Özellikler](#özellikler)
- [Kurulum](#kurulum)
- [Kullanım](#kullanım)
- [API Dökümantasyonu](#api-dökümantasyonu)
- [Katkıda Bulunma](#katkıda-bulunma)
- [Lisans](#lisans)

## Özellikler

- Kullanıcı yönetimi (kayıt, giriş, profil güncelleme)
- Veri yönetimi (CRUD işlemleri)
- JWT tabanlı kimlik doğrulama
- Hata yönetimi ve loglama

## Kurulum

Projeyi yerel ortamınıza kurmak için aşağıdaki adımları izleyin:

1. Bu repoyu klonlayın:
    ```bash
    git clone https://github.com/abdullahtopall/RadoreFinalProject_Backend.git
    ```

2. Proje dizinine gidin:
    ```bash
    cd RadoreFinalProject_Backend
    ```

3. Gerekli bağımlılıkları yükleyin:
    ```bash
    npm install
    ```

4. Ortam değişkenlerini yapılandırın. `.env` dosyasını oluşturun ve gerekli değişkenleri ekleyin:
    ```plaintext
    PORT=3000
    DATABASE_URL=your_database_url
    JWT_SECRET=your_jwt_secret
    ```

5. Veritabanını migrate edin:
    ```bash
    npx prisma migrate dev
    ```

6. Sunucuyu başlatın:
    ```bash
    npm start
    ```

## Kullanım

Sunucu başarıyla başlatıldıktan sonra, API uç noktalarına istek gönderebilirsiniz. Varsayılan olarak, sunucu `http://localhost:3000` adresinde çalışacaktır.

## API Dökümantasyonu

### Kullanıcı Kayıt

- **URL:** `/api/register`
- **Yöntem:** `POST`
- **İstek Gövdesi:**
    ```json
    {
        "username": "kullanici_adi",
        "password": "sifre"
    }
    ```
- **Başarılı Yanıt:**
    ```json
    {
        "message": "Kullanıcı başarıyla kaydedildi."
    }
    ```

### Kullanıcı Giriş

- **URL:** `/api/login`
- **Yöntem:** `POST`
- **İstek Gövdesi:**
    ```json
    {
        "username": "kullanici_adi",
        "password": "sifre"
    }
    ```
- **Başarılı Yanıt:**
    ```json
    {
        "token": "jwt_token"
    }
    ```

### Profil Güncelleme

- **URL:** `/api/profile`
- **Yöntem:** `PUT`
- **Başlıklar:**
    ```plaintext
    Authorization: Bearer jwt_token
    ```
- **İstek Gövdesi:**
    ```json
    {
        "email": "yeni_email@example.com"
    }
    ```
- **Başarılı Yanıt:**
    ```json
    {
        "message": "Profil başarıyla güncellendi."
    }
    ```

## Katkıda Bulunma

Katkıda bulunmak isterseniz, lütfen önce bir issue açın. Değişikliklerinizi tartıştıktan sonra, bir pull request oluşturabilirsiniz.

1. Fork yapın (https://github.com/abdullahtopall/RadoreFinalProject_Backend/fork)
2. Kendi branşınızı oluşturun (`git checkout -b feature/ozellik`)
3. Değişikliklerinizi commit edin (`git commit -am 'Yeni özellik ekle'`)
4. Branşınıza push edin (`git push origin feature/ozellik`)
5. Bir pull request oluşturun

## Lisans

Bu proje MIT Lisansı ile lisanslanmıştır. Daha fazla bilgi için `LICENSE` dosyasına bakabilirsiniz.
