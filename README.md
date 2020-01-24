# FreeRTOS-STM32F4xx
This is a simple port of the FreeRTOS OS for the stm32f4xx microcontroller. 

### Build Instructions
As this sample-project is setup with **System Workbench for STM32** from [OpenSTM32](https://www.openstm32.org), so its recommended to use Eclipse with the SystemWorkbench Plugin, or the install the IDE/Toolchain with the full installer. Detailed install descriptions can be found on [Installing System Workbench for STM32](https://www.openstm32.org/Installing%2BSystem%2BWorkbench%2Bfor%2BSTM32) (Registration is necessary).

The project can now simply imported into your workspace with
(1) *File* -> *Import ...*
(2) Select *General/Existing Projects into Workspace*
(3) and choose the downloaded project as root directory
(4) now select the project and import it into the workspace

After this the project can be simply built with the STM32Workbench toolchain.

### Run Configruations and upload
To upload the binary onto the microcontroller a new run configration needs to be created:
(1) *Run* -> *Run Configurations...*
(2) In the left panel select **Ac6 STM32 Debugging** and click on *New Configuration* button
(3) Switch to the *Debugger* Tab and click on the button *Show generator options*
(4) Select now as Reset Mode: *Software system reset*
(5) Binary can now be uploaded with the run button


#### Current Clock Settings
HSE Value (external oscillator) is set to: 8MHz
System Clock oscillates with : 84MHz (due PLL configuration)

#### Folder Structure
<pre>
FreeRTOS/
  |-- FreeRTOSConfig.h      -> file for FreeRTOS settings and configuration
  |-- HookMemoryFunctions.h -> contains hook and memory allocation functions (definition)
  |-- HookMemoryFunctions.c -> implementation of the hook, memory functions
  |-- Source/               -> FreeRTOS Source files
  |-- License/              -> FreeRTOS Licens file
StdPeriph_Driver/
  |-- src/                  -> source files of the std peripheral library
  |-- inc/                  -> include files of the std peripheral library
CMSIS/                      -> cmsis device library
startup/                    -> startup files for the stm32f4xx
src/
  |-- main.c                -> entrypoint of the testapplication

</pre>