# Xiaomi Mi Router 4 <Badge type="keenetic" text="4.1.7" />

![альтернативный текст](/assets/images/wiki/guides/Xiaomi/xiaomi4.jpg)

## Особенности сборки

| Особенность              | Описание                                 |
|--------------------------|------------------------------------------|
| **Работоспособность**    | ✅ кроме Мобильного приложения, KeenDNS   |
| **Сброс настроек**       | ✅ через кнопку Reset                     |
| **Кнопка MiNet**         | ✅ Управляет светодиодом                  |
| **Светодиоды**           | ✅                                        |
| **Совместимость в Mesh** | ✅ С оригинальными устройствами и клонами |

## Установка

1. В архиве запускаем !Start.bat в папке `Установка Breed`
2. Поочерёдно выбираете пункты от 1 до 4. <br/>В папке data будет бекап в файле factory, его конвертируем в валидный eeprom для Keenetic через [онлайн-сервис](https://yeezyio.github.io/) выбрав `Вырезанный eeprom` с указанием вашего MAC с этикетки. Полученный файл поместите в папку с прошивкой
   ![альтернативный текст](/assets/images/wiki/guides/Xiaomi/install.png)
3. Перейдите в Breed по адресу 192.168.1.1. и сделайте Full бекап на случай отката на сток
   ![альтернативный текст](/assets/images/wiki/guides/Xiaomi/breed.jpg)
6. В папке с прошивкой перетягиваем все bin файлы на HFS.exe.
   ![альтернативный текст](/assets/images/wiki/guides/TP-Link-EC330/openhfs.png)
6. Запускаем Putty, заходим по TelNet (192.168.1.1 port 23) и дальнейшие команды вставляем(ПКМ) поочередно, ожидая
   выполнения предыдущей команды.
   ::: warning
   • Предварительно отключите Брандмауэр и Антивирус вашей ОС
   <br/>• Сообщения **skipped bad blocks** после ввода команд являются нормой
   :::
   ::: danger ВНИМАНИЕ
   •Каждая строка это **отдельная команда**. Если она не выполнилась, повторить снова.
   <br/>•Cравните IP в командах wget ниже с IP указанным в HFS, в загрузчике Breed он всегда начинается на
   192.168.1.xxx
   :::

```shell
flash erase 0x80000 0x7f00000

wget http://192.168.1.2/u-config.bin
flash write 0x80000 0x80001000 0x80000
flash write 0x4040000 0x80001000 0x80000

wget http://192.168.1.2/eeprom.bin
flash write 0x100000 0x80001000 0x40000
flash write 0x40c0000 0x80001000 0x40000

wget http://192.168.1.2/firmware.bin
flash write 0x180000 0x80001000 0x1A8003C
flash write 0x4140000 0x80001000 0x1A8003C

wget http://192.168.1.2/u-state.bin
flash write 0x3fc0000 0x80001000 0x80000

env set autoboot.command "boot flash 0x4140000"
env save
reset
```

::: details Примерный вывод консоли
![альтернативный текст](/assets/images/wiki/guides/TP-Link-EC330/breedlog.png)
:::
После перезагрузки устройство запустится в Keenetic
::: tip 192.168.1.1<br/>SSID: Keenetic<br/>Password: 12345678
:::
