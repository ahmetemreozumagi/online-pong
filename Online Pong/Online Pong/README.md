🏓 Online Pong P2P
Python ve Pygame kullanılarak geliştirilmiş, yerel ağ (LAN) üzerinden oynanabilen Peer-to-Peer (P2P) bir çok oyunculu Pong oyunudur. Proje, gerçek zamanlı veri iletimi için UDP, güvenli sinyalleşme ve sohbet için TCP protokollerini bir arada kullanır.

🚀 Öne Çıkan Özellikler
P2P Mimari: Sunucuya ihtiyaç duymadan iki oyuncu arasında doğrudan bağlantı.

Hibrit Ağ Yapısı: * UDP: Top konumu, skor ve raket hareketleri gibi hız kritik veriler için.

TCP: Sohbet mesajları, oyuncu isimleri ve oyun durumu (rematch/quit) sinyalleri için.

Fizik Yetkisi (Host Authority): Çarpışma hesaplamaları ve skor takibi sadece Host tarafından yapılarak senkronizasyon hataları önlenir.

Gelişmiş Durum Makinesi (FSM): Giriş ekranından oyun sonuna kadar akıcı geçişler.

Dahili Sohbet: Oyun sırasında gerçek zamanlı mesajlaşma.

🛠️ Teknik Detaylar
Ağ Protokolleri ve Port Yönetimi
Windows işletim sistemindeki soket sınırlamalarını aşmak ve paketlerin doğru hedefe ulaştığından emin olmak için çift portlu UDP yapısı kullanılmıştır:

Host: 5001 portunu dinler, paketleri Joiner'ın 5002 portuna gönderir.

Joiner: 5002 portunu dinler, paketleri Host'un 5001 portuna gönderir.

Fizik ve Senkronizasyon
Swept-AABB: Top ve raket çarpışmalarında kare atlamalarını önlemek için hassas fizik hesaplaması.

Goal Pause: Gol atıldığında her iki tarafta senkronize 2 saniyelik duraklama ve görsel bildirim.

📦 Kurulum ve Çalıştırma
Gereksinimler:
Sisteminizde Python 3.x ve Pygame kütüphanesinin kurulu olması gerekir.

Bash
pip install pygame
Oyunu Başlatma:
Aynı yerel ağdaki iki bilgisayarda da projeyi çalıştırın:

Bash
python client.py
Bağlantı Kurma:

Birinci oyuncu "Host Ol" butonuna basarak IP adresini arkadaşıyla paylaşır.

İkinci oyuncu "Katıl" diyerek bu IP adresini girer.

🎮 Kontroller
Hareket: YUKARI / AŞAĞI ok tuşları.

Sohbet: ENTER tuşuna basarak mesaj yazabilir, tekrar ENTER ile gönderebilirsiniz.

Yeniden Oyna: Oyun bittiğinde R tuşuna basarak rakibe istek gönderebilirsiniz.

Çıkış: ESC tuşu ile lobiye dönebilir veya oyundan çıkabilirsiniz.

📂 Proje Yapısı
client.py: Ana uygulama döngüsü ve durum yönetimi.

network_handler_p2p.py: TCP/UDP soket yönetimi.

physics.py: Çarpışma ve hareket mantığı.

game_screen.py: UI bileşenleri ve render işlemleri.

chat_handler.py: Sohbet mesajlaşma mantığı.

Geliştiren: Ahmet Emre Özümağı

Ekran Görüntüleri:
<img width="1502" height="1098" alt="Ekran görüntüsü 2026-05-03 190011" src="https://github.com/user-attachments/assets/334d8995-120b-4099-8a90-68ed8359c8c0" />
<img width="751" height="549" alt="Ekran görüntüsü 2026-05-03 185948" src="https://github.com/user-attachments/assets/98bea6f1-5fdf-4e9d-95f9-1f495a7c192f" />
<img width="1502" height="1098" alt="Ekran görüntüsü 2026-05-03 185945" src="https://github.com/user-attachments/assets/b66b4ae8-d074-4cac-9852-c81791e0068b" />
<img width="960" height="600" alt="Ekran görüntüsü 2026-05-03 191232" src="https://github.com/user-attachments/assets/0d895795-258a-4af4-9a79-9ef36255be66" />
<img width="1502" height="1098" alt="Ekran görüntüsü 2026-05-03 190531" src="https://github.com/user-attachments/assets/ab5f35fe-dbd4-443f-a6ad-d84db221d99e" />
<img width="1502" height="1098" alt="Ekran görüntüsü 2026-05-03 190238" src="https://github.com/user-attachments/assets/4a9a5cf4-db46-4b58-aa3f-89f1e4e603c5" />
<img width="1502" height="1098" alt="Ekran görüntüsü 2026-05-03 190200" src="https://github.com/user-attachments/assets/514efd90-e99f-46db-99d6-5c540ba5ef83" />
<img width="1502" height="1098" alt="Ekran görüntüsü 2026-05-03 190154" src="https://github.com/user-attachments/assets/112a9aff-8331-4ad7-a560-a4495f10cbfa" />
<img width="1502" height="1098" alt="Ekran görüntüsü 2026-05-03 190139" src="https://github.com/user-attachments/assets/0164e9e0-4fe3-4087-be03-bc10974f1137" />
<img width="1502" height="1098" alt="Ekran görüntüsü 2026-05-03 190132" src="https://github.com/user-attachments/assets/02d95f50-0e4c-478a-b917-49a645e492cb" />
<img width="1502" height="1098" alt="Ekran görüntüsü 2026-05-03 190119" src="https://github.com/user-attachments/assets/52f79f36-39ed-4608-bf1f-ea55ba274207" />
<img width="751" height="549" alt="Ekran görüntüsü 2026-05-03 190058" src="https://github.com/user-attachments/assets/b2628dab-f419-4eae-9e7b-8de5f1572f52" />
<img width="1502" height="1098" alt="Ekran görüntüsü 2026-05-03 190054" src="https://github.com/user-attachments/assets/6207a711-bd75-446a-be38-3171c28faed1" />
<img width="751" height="549" alt="Ekran görüntüsü 2026-05-03 190014" src="https://github.com/user-attachments/assets/fb86e35f-c12d-4b36-9d49-579d45bc900b" />
