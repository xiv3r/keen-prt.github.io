# Обновление прошивки Keenetic

## Для NAND памяти (от 128MB)

### Способ #1 <Badge type="keenetic" text="Автоматический, рекомендуемый" />

• Используйте [KeenKit](/wiki/helpful/keenkit.md) с функцией `Обновить прошивку из файла` или `OTA Update`

![альтернативный текст](/assets/images/wiki/helpful/keenkit/update-firmware.png){width=500px height=100px}

### Способ #2 <Badge type="keenetic" text="Через KeenBOOT" />

1. Выполнить [вход в загрузчик](/wiki/helpful/keenboot#%D0%B2%D1%85%D0%BE%D0%B4-%D0%B2-%D0%B7%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D1%87%D0%B8%D0%BA)
2. Загрузить обновление поверх через веб-интерфейс

![альтернативный текст](/assets/images/wiki/helpful/keenboot/main.png)

### Способ #3 <Badge type="keenetic" text="Ручной" />

1. Поместите файл обновления на встроенный/внешний накопитель с установленной [Entware](/wiki/helpful/entware)
2. Через `Telnet/SSH` попасть в Entware
3. Введите команду для получения информации о разделах `Firmware_1` и `Firmware_2`

```shell
cat /proc/mtd
```

4. Перезаписываем разделы и перезагружаемся

```shell
dd if=/opt/firmware.bin of=/dev/mtdblock5
```

```shell
dd if=/opt/firmware.bin of=/dev/mtdblock12
```

```shell
reboot
```

::: info Где 5/12 разделы `Firmware_1` и `Firmware_2` полученные в 3 шаге, а `/opt/firmware.sh` путь до файла помещённого в 1 шаге
:::
![альтернативный текст](/assets/images/wiki/helpful/updateFirmware/manualUpdate.png)

### Способ #4 <Badge type="keenetic" text="Через Breed" />

::: danger ВНИМАНИЕ
Данный способ при невнимательности может окирпичить роутер, внимательно следуйте командам
:::

1. Загрузиться в Breed
2. Запустить Putty, заходим по TelNet `192.168.1.1 port 23` и дальнейшие команды вставляем(ПКМ) поочередно, ожидая
   выполнения предыдущей команды.
3. Размещаем прошивку в `HFS.exe`, например `firmware.bin`

::: details Команды для устройств с Flash накопителем 256MB (SmartBox Pro, Xiaomi R3P)
Вводить поочередно
```shell
flash erase 0x180000 0x1AB3F00
```
```shell
flash erase 0x8140000 0x1AB3F00
```
```shell
wget http://192.168.1.2/firmware.bin
```
```shell
flash write 0x180000 0x80001000 0x1AB3F00
```
```shell
flash write 0x8140000 0x80001000 0x1AB3F00
```
```shell
reset
```
:::
::: details Команды для остальных устройств
Вводить поочередно
```shell
flash erase 0x180000 0x1AB3F00
```
```shell
flash erase 0x4140000 0x1AB3F00
```
```shell
wget http://192.168.1.2/firmware.bin
```
```shell
flash write 0x180000 0x80001000 0x1AB3F00
```
```shell
flash write 0x4140000 0x80001000 0x1AB3F00
```
```shell
reset
```
:::

![альтернативный текст](/assets/images/wiki/helpful/updateFirmware/breedInstall.png){width=500px height=100px}

## Для SPI памяти (до 32MB)

### Способ #1 <Badge type="keenetic" text="Автоматический, рекомендуемый" />

1. Загрузиться в Breed
2. В Upgrade -> Generic -> Firmware выбираем нашу прошивку. Перевод разделов может отличаться от версии Breed

![альтернативный текст](/assets/images/wiki/helpful/updateFirmware/breedSPI.png)

::: tip ОБРАТИТЕ ВНИМАНИЕ
Этот пункт используется только для файла прошивки. Не используйте полный дамп флешки
:::

3. После успешной загрузки роутер перезагрузится в систему