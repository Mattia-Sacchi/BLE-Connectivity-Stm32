# BLE-Connectivity-Stm32

## Board STM32L4 Discovery kit IoT B-L475E-IOT01A
STM32 is a family of 32-bit microcontroller integrated circuits by STMicroelectronics. Based on ARM® Cortex®-M, STM32 is suitable for low power, real time applications.

The [B-L475E-IOT01A](https://www.st.com/en/evaluation-tools/b-l475e-iot01a.html) (STM32L4 Discovery kit IoT node) allows users to develop applications with direct connection to cloud servers.
The Discovery kit enables a wide diversity of applications by exploiting low-power communication like BLE.
The support for Arduino Uno V3 and PMOD connectivity provides unlimited expansion capabilities with a large choice of specialized add-on boards.

This Repository contains the source code and the steps to follow to be able to make STM32 read sensor data and send it, in an organized way, to the Tangle (DLT) of the IOTA Network through the Streams layer.

## Sensors
We used the bsp library to read built-in sensors such as

* Accelerometer and gyroscope (LSM6DSL)
* Magnetometer (LIS3MDL)
* Altimeter / pressure sensor (LPS22HH)
* Humidity and temperature sensor (HTS221)

# Download the firmware on the board
## Install official IDE ST-Microelectronic
The source code can be built and flashed using the official IDE of St-microelectronics, supported IDEs are:

* [STM32CubeIDE](https://www.st.com/en/development-tools/stm32cubeide.html) available for Linux, Mac and Windows
* [SW4STM32](https://www.st.com/en/development-tools/sw4stm32.html) available for Linux, Mac and Windows

## Open the project

Clone the repository

```
git clone https://github.com/Mattia-Sacchi/BLE-Connectivity-Stm32.git

```

Once the installation of the IDE is complete click on *.cproject* file if you installed SW4STM32, the IDE will launch importing the project.

If you installed STM32CubeIDE click on the *.project* file and the IDE will import the project.

## Name of the device

The name of the device can be edited in the file *ble_project_interface.c* the address instead will be fixed.

## Flash the code

Connect the board to your pc using the (USB ST-link) connector, click on *run* on the IDE and the project will be compiled and flashed on the board. Press the reset button on the board and the device will start to work. The green led  (LD2) will fade according to the distance measured with the ToF sensor. The green power led instead will be always on.


## Read BLE Services and Characteristics
You may also want to read the data directly from the *BLE Server*. For this there are Free OpenSource software.

We recommend ***nRF Connect*** (free OpenSource software) of *NordicSemiconductor* available in [Desktop](https://www.nordicsemi.com/Software-and-tools/Development-Tools/nRF-Connect-for-desktop): on Windows, macOS and Linux. And in [Mobile](https://www.nordicsemi.com/Software-and-tools/Development-Tools/nRF-Connect-for-mobile): on Android and iOS (The mobile version is very simple and more comfortable to debug).

## Bluetooth Usage
You may look the ble_project_interface.h/c files, in particular the Services and Messages enums.
In the interface setup you can automatically setup service and charateristic through adding the enum and then call the respective setup function.
In the setup the IDs will be automatically assigned

## Twin android application

