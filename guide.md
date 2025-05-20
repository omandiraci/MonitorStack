# Monitoring Stack Kullanım Kılavuzu

## 1. Giriş
Bu kılavuz, monitoring stack'in kurulumu, yapılandırması ve kullanımı hakkında detaylı bilgi sağlar. Stack aşağıdaki bileşenlerden oluşur:

- **Prometheus**: Metrik toplama ve uyarı yönetim sistemi
- **Grafana**: Veri görselleştirme ve dashboard arayüzü
- **cAdvisor**: Konteyner izleme aracı
- **Node Exporter**: Sistem metrikleri toplayıcısı

## 2. Kurulum Adımları

### 2.1. Ön Gereksinimler
- Docker 20.10.7 veya üzeri
- Docker Compose 1.29.2 veya üzeri
- Minimum 2GB RAM
- 1 CPU çekirdek

### 2.2. Kurulum
1. Projeyi klonlayın:
   ```bash
   git clone https://github.com/your-repo/monitoring-stack.git
   cd monitoring-stack
   ```

2. Docker konteynerlerini başlatın:
   ```bash
   docker-compose up -d
   ```

3. Servislerin başladığını kontrol edin:
   ```bash
   docker-compose ps
   ```

## 3. Yapılandırma

### 3.1. Prometheus Yapılandırması
Ana konfigürasyon dosyası: `prometheus_config/prometheus.yml`

Örnek yapılandırma:
```yaml
global:
  scrape_interval: 15s
  evaluation_interval: 15s

scrape_configs:
  - job_name: 'prometheus'
    static_configs:
      - targets: ['localhost:9090']
  - job_name: 'node'
    static_configs:
      - targets: ['node-exporter:9100']
```

### 3.2. Grafana Yapılandırması
Grafana varsayılan olarak 3000 portunda çalışır. İlk giriş bilgileri:
- Kullanıcı: admin
- Şifre: admin

## 4. Kullanım

### 4.1. Prometheus Kullanımı
1. Tarayıcıda http://localhost:9090 adresini açın
2. 'Graph' sekmesine tıklayın
3. Metrikleri sorgulamak için PromQL sorguları yazın

### 4.2. Grafana Kullanımı
1. http://localhost:3000 adresini açın
2. Yeni bir dashboard oluşturun
3. Veri kaynağı olarak Prometheus'u ekleyin
4. Görselleştirmeler oluşturun

## 5. Sorun Giderme

### 5.1. Servisler Başlamıyor
- Docker loglarını kontrol edin:
  ```bash
  docker-compose logs
  ```

### 5.2. Metrikler Görünmüyor
- Prometheus hedef durumunu kontrol edin:
  http://localhost:9090/targets

## 6. Lisans
Bu proje MIT lisansı ile lisanslanmıştır. Detaylar için LICENSE dosyasına bakın.
