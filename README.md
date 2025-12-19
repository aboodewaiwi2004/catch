Bu proje, ROS2 (Robot Operating System 2) altyapısını kullanarak Turtlesim simülasyonu içerisinde dinamik bir "avcı-av" mekanizması sunar. Bir ana kaplumbağa (Avcı), sürekli olarak ortamda beliren rastgele hedefleri (Av) takip eder ve onlara ulaştığında onları yok eder.

Proje Özellikleri

    Dinamik Spawn: Belirli aralıklarla rastgele koordinatlarda yeni kaplumbağalar oluşturulur.

    P-Kontrolcü: Avcı kaplumbağa, hedefe en kısa yoldan gitmek için orantılı kontrol (Proportional Control) kullanarak hızını ayarlar.

    Servis Tabanlı Haberleşme: Kaplumbağaların "yakalanması" ve silinmesi özel tanımlanmış ROS2 servisleri ile yönetilir.

    Gerçek Zamanlı Takip: /new_turtles topic'i üzerinden aktif avların listesi anlık olarak güncellenir.

    Kurulum ve Çalıştırma
    
1. Workspace Derleme

Öncelikle terminalinizde çalışma alanına gidip derleme işlemini yapın:

cd ~/turtlesim_ws

colcon build --packages-select turtlesim_py_pkg turtlesim_interfaces

source install/setup.bash

2. Simülasyonu Başlatma
3. 
Üç farklı terminal açarak aşağıdaki komutları sırasıyla çalıştırın:

Terminal 1 (Turtlesim GUI):

ros2 run turtlesim turtlesim_node

Terminal 2 (Av Oluşturucu):

ros2 run turtlesim_py_pkg spawn_turtle

Terminal 3 (Avcı Kontrolcü):

ros2 run turtlesim_py_pkg go_to_loc

DEMO VIDEO
https://github.com/user-attachments/assets/4716fe20-aaa1-412b-adce-93601ac22ea5
