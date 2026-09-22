# CMSIS-CMake

This CMake-based example project runs on a
[B-U585I-IOT02A](https://www.keil.arm.com/boards/stmicroelectronics-b-u585i-iot02a-revc-c3bc599/projects/) development
board from STMicroelectronics. The example code was generated with STM32CubeMX.

## Quick start

1. Install [Keil Studio for VS Code](https://marketplace.visualstudio.com/items?itemName=Arm.keil-studio-pack) from the VS Code marketplace.
3. Clone this repository (for example using [Git in VS Code](https://code.visualstudio.com/docs/sourcecontrol/intro-to-git)) or download the ZIP file. Then open the repository folder in VS Code.
4. In VS Code, open the [CMSIS View](https://mdk-packs.github.io/vscode-cmsis-solution-docs/userinterface.html#2-main-area-of-the-cmsis-view) and then the [Manage Solution dialog](https://github.com/Open-CMSIS-Pack/vscode-cmsis-solution#manage-solution-view) to select the target board and one project.
5. In the CMSIS view, use the [Action buttons](https://github.com/Open-CMSIS-Pack/vscode-cmsis-solution#action-buttons) to build, load, and debug the example on your hardware.

## GPIO_IOToggle Example Description

How to configure and use GPIOs through the HAL API.

PH.07 and PH.06 IOs (configured in output pushpull mode) toggle in a forever loop.
On **B-U585I-IOT02A** board these IOs are connected to LED7 and LED6.

In this example, HCLK is configured at 160 MHz.

> [!NOTE]
> 1. Care must be taken when using HAL_Delay(), this function provides accurate delay (in milliseconds)
>    based on variable incremented in SysTick ISR. This implies that if HAL_Delay() is called from
>    a peripheral ISR process, then the SysTick interrupt must have higher priority (numerically lower)
>    than the peripheral interrupt. Otherwise the caller ISR process will be blocked.
>    To change the SysTick interrupt priority you have to use HAL_NVIC_SetPriority() function.
> 2. The example needs to ensure that the SysTick time base is always set to 1 millisecond
>    to have correct HAL operation.

### Keywords

System, GPIO, Input, Output, Alternate function, Push-pull, Toggle.

### Directory contents

- GPIO/GPIO_IOToggle/Inc/b_u585i_iot02a_conf.h   BSP configuration file
- GPIO/GPIO_IOToggle/Inc/stm32u5xx_hal_conf.h    HAL configuration file
- GPIO/GPIO_IOToggle/Inc/stm32u5xx_it.h          Interrupt handlers header file
- GPIO/GPIO_IOToggle/Inc/main.h                  Header for main.c module
- GPIO/GPIO_IOToggle/Src/stm32u5xx_it.c          Interrupt handlers
- GPIO/GPIO_IOToggle/Src/stm32u5xx_hal_msp.c     HAL MSP file
- GPIO/GPIO_IOToggle/Src/main.c                  Main program
- GPIO/GPIO_IOToggle/Src/system_stm32u5xx.c      STM32U5xx system source file

### Hardware and Software environment

- This example runs on STM32U585xx devices.
- This example has been tested with B-U585I-IOT02A board and can be
  easily tailored to any other supported device and development board.

### How to use it ?

In order to make the program work, you must do the following :

- Open your preferred toolchain
- Rebuild all files and load your image into target memory
- Run the example
