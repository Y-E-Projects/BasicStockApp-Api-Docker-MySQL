# BasicStockApp - Docker Kurulum ve Çalıştırma

Bu döküman, **BasicStockApp API** uygulamasının Docker ortamında çalıştırılması için adım adım rehber sunmaktadır. Aşağıdaki talimatları takip ederek uygulamayı hızlı ve güvenli bir şekilde kurabilirsiniz.

---

## Ön Koşullar

* **Docker** ve **Docker Compose** sisteminizde yüklü olmalıdır.

  * [Docker Desktop](https://www.docker.com/products/docker-desktop/) (Windows/macOS için) veya Linux dağıtımınıza uygun Docker kurulumu yapılmalıdır.
* İnternet bağlantısı gereklidir.
* Git komutu sisteminizde kullanılabilir olmalıdır.

---

## Adım 1: Docker ve Docker Compose Kurulumu

1. Docker Desktop’u [resmî siteden](https://www.docker.com/products/docker-desktop/) indirin ve kurun.
2. Kurulumdan sonra terminal veya PowerShell’i açın ve aşağıdaki komutlarla kurulum doğrulaması yapın:

```bash
docker --version
docker-compose --version
```

> Eğer versiyon bilgisi görünüyorsa Docker başarıyla kurulmuştur.

---

## Adım 2: BasicStockApp API Docker Image’ını Pull Etmek

1. Terminal veya PowerShell’i açın.
2. Aşağıdaki komut ile resmi Docker Hub repository’sinden API imajını çekin:

```bash
docker pull yeteam/basicstockapp-api
```

> Eğer SSL ile çalıştırmak isterseniz, aşağıdaki imajı çekin ve `docker-compose-ssl.yml` ile başlatın:

```bash
docker pull yeteam/basicstockapp-api-ssl
```

3. Pull işlemi tamamlandıktan sonra imajlarınızı kontrol edebilirsiniz:

```bash
docker images
```

---

## Adım 3: Projeyi Git Üzerinden Klonlamak

1. İstediğiniz bir dizine gidin. Örneğin:

```bash
cd C:\Users\<KullanıcıAdı>\Desktop
```

2. Repository’yi klonlayın:

```bash
git clone https://github.com/Y-E-Projects/BasicStockApp-Api-Docker-MySQL.git
```

3. Klonlanan dizine geçin:

```bash
cd BasicStockApp-Api-Docker-MySQL
```

---

## Adım 4: Docker Compose ile Uygulamayı Başlatmak

1. Docker Compose dosyasının bulunduğu dizinde aşağıdaki komutu çalıştırın:

```bash
docker-compose up -d
```

> SSL ile çalıştırmak isterseniz:

```bash
docker-compose -f docker-compose-ssl.yml up -d
```

2. Komut çalıştıktan sonra container’lar arka planda başlatılacaktır. Durumu kontrol etmek için:

```bash
docker ps
```

* `mymarket-mysql` ve `basicstockapp-api` container’larının çalıştığını göreceksiniz.

3. Uygulama artık şu adreste çalışmaktadır:

* Standard: [**http://localhost:8080**](http://localhost:8080)
* SSL: [**https://localhost:5001**](https://localhost:5001)

---

## Adım 5: Uygulamayı Tekrar Başlatmak veya Durdurmak

* **Durdurmak için:**

```bash
docker-compose down
```

* **Tekrar başlatmak için:**
  Docker Desktop üzerinden `Containers / Apps` sekmesine giderek ilgili container’ı seçip **Start** butonuna tıklayabilirsiniz veya terminalde:

```bash
docker-compose up -d
```

---

## Özet

Bu rehber ile:

* Docker kurulumu ve doğrulaması,
* API imajının pull edilmesi (standart veya SSL),
* Git repository’nin klonlanması,
* Docker Compose ile container’ların başlatılması ve durdurulması

adımlarını tamamlayarak **BasicStockApp API**’yi lokal ortamınızda çalıştırabilirsiniz.
