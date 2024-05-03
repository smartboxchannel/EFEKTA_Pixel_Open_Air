# EFEKTA_Pixel_Open_Air

Поблагодарить автора: [https://yoomoney.ru/fundraise/P2XLTgJsB6k.231012](https://yoomoney.ru/fundraise/P2XLTgJsB6k.231012)

Thank the author: [https://yoomoney.ru/fundraise/P2XLTgJsB6k.231012](https://yoomoney.ru/fundraise/P2XLTgJsB6k.231012)

Телеграм чат DIY Devices - https://t.me/diy_devices

Продажа DIY Устройств - https://t.me/diydevmart

##### Только для не коммерческого использования. Запрещается использовать проект или его части в коммерческих целях без согласования с автором проекта.

##### For non-commercial use only. It is forbidden to use the project or its parts for commercial purposes without the consent of the author of the project.

##### hello@efektalab.com

![EFEKTA Pixel Open Air](https://raw.githubusercontent.com/smartboxchannel/EFEKTA_Pixel_Open_Air/main/Images/001.png) 

Проект zigbee датчика мониторинга углекислого газа, температуры и влажности воздуха c LCD дисплеем EFEKTA Pixel Open Air.

Датчик передает в сеть данные об уровне СO2, температуре и влажности воздуха. На дисплей помимо вывода уровня СO2, так же выводится график уровня углекослого газа за последние 24 часа. Датчик является роутером сети.

Датчик работает с временем через zigbee сеть. Настройка времени происходит автоматически. На дисплей выводится текущие дата и время.

В датчике реализована rgb подсветка дисплея в зависимости от уровня углекислого газа. В дополнение к rgb подсветке реализован функционал ночного режима по расписанию с полным отключением подстветки дисплея в заданным пользователем диапазоне времени.

Датчик оснащен функционалом газостата. Вы можете задать уровни СO2(верхний и нижний), привязать(биндинг) датчик к исполнительному устройству, реле или розетуке и датчик при переходе через пороги будет отправлять команды на включение или отключение на привязанное исполнителное устройство. Такая привязка будет работать даже если контроллер умного дома или координатор зигби сети будут недоступны.


Zigbee project of a carbon dioxide, temperature and humidity monitoring sensor with an EFEKTA Pixel Open Air LCD display.

The sensor transmits data on CO2 levels, air temperature and humidity to the network. In addition to displaying the CO2 level, the display also displays a graph of the carbon dioxide level for the last 24 hours. The sensor is a network router.

The sensor works with time via a zigbee network. The time is adjusted automatically. The display shows the current date and time.

The sensor implements RGB backlighting of the display depending on the level of carbon dioxide. In addition to RGB backlighting, the functionality of a night mode according to a schedule is implemented with complete shutdown of the display backlight in a user-specified time range.

The sensor is equipped with gasostat functionality. You can set CO2 levels (upper and lower), bind (binding) the sensor to an actuator, relay or socket, and the sensor, when crossing thresholds, will send commands to turn on or off to the bound actuator. This binding will work even if the smart home controller or Zigbee network coordinator are unavailable.


Для прошивки необходимо подключить базовую плату к SmartRF04EB и прошить через программу SmartRF Flash Programmer

For firmware, you need to connect the base board to SmartRF04EB and flash it through the SmartRF Flash Programmer program

![EFEKTA Pixel Open Air](https://raw.githubusercontent.com/smartboxchannel/EFEKTA_Pixel_Open_Air/main/Images/009.png)

Для работы устройства в сети zigbee через zigbee2mqtt необходимо установить внешний конвертер.

To operate the device on the zigbee network via zigbee2mqtt, an external converter must be installed.

![EFEKTA Pixel Open Air](https://raw.githubusercontent.com/smartboxchannel/EFEKTA_Pixel_Open_Air/main/Images/003.png)

### Основные данные:

#### CO2

Уровень углекислого газа

Carbon dioxide level

#### Temperature

Измеренное значение с встроенного сенсора температуры

Measured value from built-in temperature sensor

#### Humidity

Измеренное значение с встроенного сенсора влажности воздуха

Measured value from the built-in air humidity sensor

#### Linkquality

Качество связи (мощность сигнала) *1

Communication quality (signal strength) *1

*1 Качество связи, свойство которое не передается датчиком, а расчитывается координатором сети на основе оценки полученных данных.

*1 Communication quality, a property that is not transmitted by the sensor, but is calculated by the network coordinator based on an assessment of the received data.


### Конфигурационные данные:

#### Backlight

Включение rgb подсветки дисплея.

Turn on the RGB backlight of the display.

#### Night backlight

Полное отключение подсветки в ночном режиме, по умолчанию деактивировано

Complete disabling of the backlight in night mode, deactivated by default

#### Night backlight on

Время активации ночного режима

Night mode activation time

#### Night backlight off

Время отключения ночного режима

Night mode switch-off time

#### Contrast

Регулировка контрастности lcd дисплея

Adjusting the contrast of the LCD display

#### Temperature offset

Отрегулировать температуру внутреннего сенсора температуры, шаг 0.1 градус

Adjust the temperature of the internal temperature sensor, step 0.1 degrees

#### Humidity offset

Отрегулировать влажность воздуха внутреннего сенсора влажности, шаг 1 процент

Adjust the air humidity of the internal humidity sensor, step 1 percent

#### Forced_recalibration

Форсированная ручная калибровка. Калибровка осуществляется на свежем воздухе, необходимо оставить датчик на чистом воздухе на 60 минут, по истечении этого времени отправить команду. Время калибровки примерно 5 секунд, после завершения калибровки точке соответствующей чистому воздуху будет задано значение в 400ppm. Датчик отправит команду «выключено» по завершению калибровки

Forced manual calibration. Calibration is carried out in fresh air; you must leave the sensor in clean air for 60 minutes, after this time, send a command. Calibration time is approximately 5 seconds, after calibration is completed, the point corresponding to clean air will be set to 400ppm. The sensor will send a "off" command when calibration is complete

#### Automatic self calibration

Автоматическая самокалибровка реализованная производителем в серии датчиков MH-Z19.

Automatic self-calibration implemented by the manufacturer in the MH-Z19 series of sensors.

#### Co2 error read

Количество неудачных попыток чтения сенсора MH-Z19

Number of failed attempts to read the MH-Z19 sensor

#### Enable_gas

Включение функционала газостата. Управление реле к которому привязан датчик. Для работы данного функционала необходимо сделать привязку к исполнительному устройству(реле, розетки)

Enabling the gasostat functionality. Control of the relay to which the sensor is attached. For this functionality to work, it is necessary to bind to an actuator (relay, socket)

#### Invert_logic_gas

Инвертирует логику работы управления исполнительными устройствами. Пример. Если опция отключена, при превышение верхнего заданного порога углекислого газа датчик отправит команду «Включить» на привязанное реле. Если опция включена, при превышение верхнего заданного порога углекислого газа датчик отправит команду «Выключить» на привязанное реле.

Inverts the logic of the control of actuators. Example. If the option is disabled, when the upper specified carbon dioxide threshold is exceeded, the sensor will send the “Enable” command to the associated relay. If the option is enabled, when the upper specified carbon dioxide threshold is exceeded, the sensor will send the “Shutdown” command to the associated relay.

#### High_gas

Верхний порог углекислого газа

Upper limit of carbon dioxide

#### Low_gas

Нижний порог углекислого газа

Lower limit of carbon dioxide

![EFEKTA Pixel Open Air](https://raw.githubusercontent.com/smartboxchannel/EFEKTA_Pixel_Open_Air/main/Images/004.png)




### Ввод в сеть (JOIN)

Чтобы подключить датчик к сети, координатор должен быть включен для приема новых устройств. После этого нужно удерживать нажатой кнопку на датчике около 5 секунд, на дисплее появится сообщение о начале входа в сеть.

To join the sensor to the network, the coordinator must be turned on to receive new devices. After that, you need to hold down the button on the sensor for about 5 seconds, a message will appear on the display about the start of logging in to the network.


### Удаление из сети (LEAVE)

Чтобы отключить датчик от сети zigbee, удерживайте нажатой кнопку на датчике около 10 секунд, и на дисплее появится сообщение о выходе из сети zigbee.

To remove the sensor from the zigbee network, hold down the button on the sensor for about 10 seconds, and a message about disconnecting from the network will appear on the display.

### Конфигурация отчетов (Zigbee2mqtt)

Для конфигурации отчетов необходимо перейти на вкладку "Отчеты", и внести изменение в поля "Мин. интервал отчетов", "Макс. интервал отчетов", "Мин. интервал отчетов при изменении".

Мин. интервал отчетов - время, через которое будет отправлен новый отчет, при условии что новые значение изменилось в любую сторону, на величину указанную в поле "Мин. интервал отчетов при изменении", в сравнении с пердыдушими значениями. Указывется время в секундах.

Макс. интервал отчетов - время, через которое будет отправлен новый отчет, при условии что значения не менялись на величину больщую той которая уазана в поле "Мин. интервал отчетов при изменении". Указывется время в секундах.

Мин. интервал отчетов при изменении - Величина изменения данных. Для каждого типа данных указывается в своем формате, например для температуры 1 отзанчает 0.01°C, так как данные передаются типом интегер16, например температура 22.54°C, будет передана датчиком так 2254.

![EFEKTA Pixel Open Air](https://raw.githubusercontent.com/smartboxchannel/EFEKTA_Pixel_Open_Air/main/Images/006.png)

### Привязка датчика EFEKTA iAQ к исполнительному устройству(реле, розетки)

 Осуществляется на стороне датчика EFEKTA iAQ. Для привязки (биндинг) датчика EFEKTA iAQ к исполнительному устройству, для прямой передачи данных необходимо в веб интерфейсе zigbee2mqtt перейти на страницу датчика EFEKTA iAQ и далее на вкладку «Связь».

В первом поле слева выбрать «1», в следующем поле, в выпадающем списке выбрать исполнительное устройство к которому необходимо сделать привязку, в следующем поле ввести номер кластера на реле. Правее выбрать кластер OnOff. Еще правее нужно нажать на кнопку «Связать».

![EFEKTA Pixel Open Air](https://raw.githubusercontent.com/smartboxchannel/EFEKTA_Pixel_Open_Air/main/Images/005.png)

### Идентификация

Идентификация устройсва осуществляется отправкой команды identify time. Сразу после отправки команды датчик выведет на дисплей приветствие, по которому можно будет легко идентифицировать устройство.

![EFEKTA Pixel Open Air](https://raw.githubusercontent.com/smartboxchannel/EFEKTA_Pixel_Open_Air/main/Images/008.png)


