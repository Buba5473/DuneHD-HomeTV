# DuneHD-HomeTV
Резервная копия настроек плагина плеера DuneHD "Домашнее-ТВ" для города Новосибирска. У установленного плагина в локации должны быть: Сибирь/Новосибирская область/Новосибирск/7 часов/Автообновление

Установите на компьютер tftp сервер (например, tftp32), и установите в нем корневую директорию. В нее закиньте извлеченный из 7z архив home_tv_nsk_backup_3.2.4.tar.gz.
Далее, подключитесь к приставке с помощью telnet и выполните: 
```
mount -o remount,rw /
cd /
tftp -r home_tv_nsk_backup_3.2.4.tar.gz -g ip_сервера [порт]
tar xvzf home_tv_nsk_backup_3.2.4.tar.gz
chown root:root /config/home_tv_plugin_cookies.properties
chown root:root -R /flashdata/plugins_data/home_tv
chmod 777 /config/home_tv_plugin_cookies.properties
chmod 777 -R /config/home_tv_plugin_cookies.properties
```
Если сбилась телепрограмма, сделайте групповое редактирование сдвига на +1 час. Групповым редактированием же сдвиг программы эфирных (новосибирских) телеканалов верните на 0
Перезагрузите приставку.
