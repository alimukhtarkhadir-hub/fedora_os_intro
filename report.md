---
## Front matter
title: "Отчёт по лабораторной работе №1"
subtitle: "Установка и конфигурация операционной системы"
author: "Хадир"

## Generic options
lang: ru-RU
toc-title: "Содержание"

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: false # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
    - spelling=modern
    - indentation=first
polyglossia-otherlangs:
  name: english
## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
---

# Цель работы

Целью данной работы является приобретение практических навыков установки операционной системы на виртуальную машину, а также навыков работы с консолью и базовой настройки системы.

# Задание

1. Создать виртуальную машину в UTM на базе процессора M3.
2. Установить операционную систему Fedora Workstation.
3. Произвести базовую настройку: имя пользователя `khadir`.
4. Установи��ь дополнительные программные пакеты и собрать информацию о системе.

# Выполнение лабораторной работы

## Установка системы

Я созда�� виртуальную машину в программе UTM с названием `khadir_os_intro`. Я выделил 8 ГБ оперативной памяти и 64 ГБ дискового пространства (Рис. 1). 

![Настройка UTM](image/utm_setup.png){#fig:001 width=70%}

В процессе установки я выбрал виртуальный диск Virtio (Рис. 2) и создал пользователя с полным именем `Khadir` и логином `khadir` (Рис. 3).

![Выбор диска для установки](image/disk.png){#fig:002 width=70%}

![Создание пользователя khadir](image/user.png){#fig:003 width=70%}

## Настройка после установки

После установки я обновил систему и установил необходимые инструменты, такие как `tmux`, `mc`, `kitty`, `pandoc` и `texlive` (Рис. 4).

![Завершение установки программного обеспечения](image/terminal.png){#fig:004 width=70%}

## Сбор данных о системе

Я выполнил команды `dmesg` с использованием `sudo` для получения технической информации о системе (Рис. 5).

![Вывод системных данных в терминале](image/dmesg.png){#fig:005 width=70%}

Ниже приведены точные данные из моей системы:

1. **Версия ядра:**
```bash
sudo dmesg | grep "Linux version"
[ 0.000000] Linux version 6.17.1-300.fc43.aarch64 (mockbuild@2add97f4a38b42d1bd57a60109ad3038)
```

2. **Информация о процессоре:**
```bash
sudo dmesg | grep "CPU0"
[ 0.000000] Detected PIPT I-cache on CPU0
[ 0.009347] ACPI: CPU0 has been hot-added
```

3. **Доступная память:**
```bash
sudo dmesg | grep -i "Memory:"
[ 0.002543] Memory: 7976948K/8388608K available (22336K kernel code, 6030K rwdata, 19164K rodata, 14272K init, 10295K bss, 338908K reserved, 65536K cma-reserved) 
```

## Выводы
В ходе выполнения лабораторной работы я успешно установил Fedora 43 на архитектуре ARM64 с использованием UTM. Я закрепил навыки работы с правами sudo и научился извлекать информацию о конфигурации оборудования через системные логи.