# Настройка Mesh системы

<br/>

## Захват

<br/>

1. В меню `"Параметры системы" (Общие настройки)` нажмите `"Изменить режим работы"` и установите режим дополнительного интернет-центра `"Усилитель/Ретранслятор"`.
   ![альтернативный текст](/assets/images/wiki/helpful/mesh/repeater01.png){width=500px height=100px}

   ![альтернативный текст](/assets/images/wiki/helpful/mesh/repeater03.png){width=500px height=100px}
2. Подключите роутер проводом к контроллеру
3. Выполните захват  
   ![альтернативный текст](/assets/images/wiki/helpful/mesh/mesh05.png){width=800px height=100px}
   ::: tip При успешном захвате роутер отобразится в списке, в названии будет его серийный номер, например `Keenetic Giga 123***456`
   :::
   ![альтернативный текст](/assets/images/wiki/helpful/mesh/mesh06.png){width=800px height=100px}

## Решение проблем

### 1. Не захватывается

Убедитесь что у захватываемых устройств разный серийный номер, он отображается на главной странице в блоке `О системе`
![альтернативный текст](/assets/images/wiki/helpful/mesh/servicenumber.png){width=800px height=100px}

Если он одинаковый, используйте [**`ServiceDataGenerator`**](https://github.com/spatiumstas/ServiceDataGenerator/archive/refs/heads/main.zip) или [KeenKit](/wiki/helpful/keenkit.md) с использованием функционала `Заменить сервисные данные`
::: tip Использование ServiceDataGenerator:

1. Положить в корень папки со скриптом `U-Config` из архива прошивки которую прошиваете
2. Наведите `U-Config.bin` на `generate.bat`
3. Получим новый файл, его шьем или заменяем через [KeenKit](/wiki/helpful/keenkit.md)

На SPI памяти можно загрузить в скрипт весь FULL снятый из Breed и восстановиться
:::
<br/>

### 2. После захвата по проводу не подключается по воздуху
Включите `Беспроводную транспортную сеть` у контроллера
<br/>

![альтернативный текст](/assets/images/wiki/helpful/mesh/wireless.png){width=800px height=100px}
<br/>

### 3. Ошибка Mws::Controller::Candidate: "xx:xx:xx:xx:xx:xx": invalid CSR response
Появляется после захвата устройства с одинаковым сервисным номером и/или мак-адресом устройства. Для решения воспользуйтесь 1 пунктом


