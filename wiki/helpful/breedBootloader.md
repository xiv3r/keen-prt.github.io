# Breed Bootloader

Это альтернативный загрузчик для маршрутизаторов на базе процессоров, таких как Broadcom и MediaTek. Его основная функция — управление загрузкой операционной системы маршрутизатора, а также предоставление дополнительных возможностей для управления устройством на низком уровне.

Все версии загрузчика доступны на ресурсе его автора, [HackPascal](https://breed.hackpascal.net/)

## Какую версию выбрать?

Для устройств с флэш-накопителем NAND и CPU MTK7621 `breed-mt7621-xiaomi-r3g.bin`<br/>
Для SPI/MTK7621 `breed-mt7621-jd-cloud-1.bin`<br/>
Для SPI/MTK7628 `breed-mt7628-hiwifi-hc5661a.bin`

Так же есть модифицированные версии загрузчика, предназначенные для конкретных устройств:

| Роутер                          | Ссылка на загрузчик             |
|---------------------------------|---------------------------------|
| **SmartBox Giga**               | [Скачать](https://vk.cc/czhVZL) |
| **SmartBox Flash/MTS WG430223** | [Скачать](https://vk.cc/czhVXy) |
| **SmartBox Pro/WiFire S1500**   | [Скачать](https://vk.cc/czhW31) |
| **SmartBox Turbo+**             | [Скачать](https://vk.cc/czhW5P) |
| **Xiaomi Mi Router 4**          | [Скачать](https://vk.cc/czhW8Z) |
| **TP-Link EC330-G5u**           | [Скачать](https://vk.cc/czhVz4) |

В наших модифицированных загрузчиках, выполненных в содружестве со [zbancam](https://4pda.to/forum/index.php?showuser=9098171) сделаны следующие правки:<br/>
• Reset настроен на вход в загрузчик удержанием при включении<br/>
• Смещения корректно настроены для бэкапа EEPROM из веб-интерфейса загрузчика<br/>
• Прописаны необходимые autoboot команды для каждой модели<br/>

::: tip Обратите внимание
Модифицированные загрузчики уже содержаться в архивах с портированными прошивками
:::