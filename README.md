# AVR SPI Driver: 74HC595 Shift Register Control

## Описание проекта
Этот проект представляет собой низкоуровневый (Bare Metal) драйвер протокола **SPI** для микроконтроллера **ATmega328p** (Arduino Nano).
Цель проекта — продемонстрировать управление сдвиговым регистром **74HC595** через прямую запись в регистры процессора, минуя стандартные библиотеки Arduino (`SPI.h` и `digitalWrite`).

Программа реализует классический эффект "Бегущий огонь" (Chaser Light), управляя 8 светодиодами всего через 3 сигнальных провода.

## Ключевые особенности
* **Hardware SPI:** Использование аппаратного модуля SPI для максимальной эффективности.
* **Direct Register Access:** Прямое манипулирование регистрами `SPCR`, `SPSR`, `SPDR`, `DDRB`, `PORTB`.
* **Модульная архитектура:** Разделение логики драйвера (`spi.c`/`spi.h`) и логики приложения (`main.c`).
* **Стабильность:** Тактовая частота SPI снижена до 1 МГц (F_CPU/16) для надежной работы на макетных платах (breadboard).

## Инструменты
* **MCU:** ATmega328p (16 MHz)
* **Язык:** C (AVR-GCC)
* **Периферия:** 74HC595 (8-bit Shift Register)
* **Среда:** VS Code + PlatformIO

## Схема подключения

<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/9e2294d8-bd7a-4887-bd62-c45a1dff8420" />


> **Важно:** Светодиоды подключаются к выходам Q0-Q7 через резисторы (220 Ом).

### Распиновка Arduino Nano
<img width="2414" height="1374" alt="image" src="https://github.com/user-attachments/assets/5825a96c-f546-48f5-89f1-e04937e9626f" />


### Распиновка 74HC595
<img width="254" height="272" alt="image" src="https://github.com/user-attachments/assets/ade8f553-fb95-42e6-8569-6d0f15f54719" />
