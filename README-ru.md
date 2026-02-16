# Установка CyberBackup на AltLinux
Здесь будет описана подробная установка CyberBackup на AltLinux Distro.

**Важно!** Здесь написана инструкция **только по установке** CyberBackup, без способов его активировать, с этим разберетесь сами.

## Подготовка
### Список библиотек
- gcc
- make
- kernel-headers-modules-`<core-version>`
- update-kernel
- perl
- dkms
- libelf-devel

### Ядро
Узнаем версию ядра следующей командой:
```bash 
[admin@srv ~]$ uname -r
6.12.65-6.12-alt1
[admin@srv ~]$ 
```
Отсюда берем только первые 2 числа, т.е. `6.12`, в моем случае.

### Установка пакетов
Пакеты можно установить следующей командой:
```bash
[admin@srv ~]$ su -
Password: 
[root@srv ~]# apt-get update && apt-get install gcc make update-kernel perl dkms libelf kernel-headers-modules-<core-version> -y
```
`<core-version>` меняем на свою версию ядра, как говорилось в пункте с разделе "Ядро"

После установки пакетов, прописываем следующую команду, чтобы сгенерировать исходники ядра:
```bash
[root@srv ~]# update-kernel
```

Затем перезапустите устройство.

### Установка CyberBackup
Переходим на сайт [CyberProtect](https://cyberprotect.ru/updates/updates-backup/)

И скачиваем установщик для Linux. **Не ISO** и **Не Astra Linux**.

После того, как скачали установщик, делаем его исполняемым:
```bash
[admin@srv ~]$ chmod +x CyberBackup_18_64-bit.x86_64 
```

И запускаем в режиме Sudo.

Далее выбираете, какие пакеты нужны и Profit, CyberBackup установлен.
