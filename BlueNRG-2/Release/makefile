################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include User/subdir.mk
-include Startup/subdir.mk
-include Stack/subdir.mk
-include Platform_Layers/subdir.mk
-include Library/subdir.mk
-include HAL/subdir.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(ASM_DEPS)),)
-include $(ASM_DEPS)
endif
ifneq ($(strip $(S_DEPS)),)
-include $(S_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
endif

-include ../makefile.defs

# Add inputs and outputs from these tool invocations to the build variables 
POST_BUILD_OBJCOPY += \
BLE_SerialPort_Master_Slave_Release.hex \

POST_BUILD_PRINT_SIZE += \
elf-size \


# All Target
all: BLE_SerialPort_Master_Slave_Release.elf secondary-outputs

# Tool invocations
BLE_SerialPort_Master_Slave_Release.elf: $(OBJS) $(USER_OBJS)
	@echo 'Building target: $@'
	@echo 'Invoking: GCC Linker'
	arm-none-eabi-gcc -mcpu=cortex-m0 -mthumb -mfloat-abi=soft -nostartfiles -nodefaultlibs -Wl,--gc-sections -Wl,-Map="BLE_SerialPort_Master_Slave_Release.map" -T"../BlueNRG2.ld" -L../../../../../../Library/Bluetooth_LE/library -L../../../../../../Library/cryptolib -Wl,--cref --specs=nano.specs -o "BLE_SerialPort_Master_Slave_Release.elf"  -Wl,--start-group @"objects.list" $(USER_OBJS) $(LIBS) -lm -lc  -Wl,--end-group
	@echo 'Finished building target: $@'
	@echo ' '
	$(MAKE) --no-print-directory post-build

BLE_SerialPort_Master_Slave_Release.hex: BLE_SerialPort_Master_Slave_Release.elf
	@echo 'Invoking: Generate binary'
	arm-none-eabi-objcopy -O ihex "BLE_SerialPort_Master_Slave_Release.elf"  "BLE_SerialPort_Master_Slave_Release.hex"
	@echo 'Finished building: $@'
	@echo ' '

elf-size: BLE_SerialPort_Master_Slave_Release.elf
	@echo 'Invoking: Print Size'
	arm-none-eabi-size -B "BLE_SerialPort_Master_Slave_Release.elf"
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) $(POST_BUILD_OBJCOPY)$(OBJS)$(ASM_DEPS)$(S_DEPS)$(S_UPPER_DEPS)$(POST_BUILD_PRINT_SIZE)$(C_DEPS) BLE_SerialPort_Master_Slave_Release.elf BLE_SerialPort_Master_Slave_Release.bin *.map
	-@echo ' '

post-build:
	arm-none-eabi-objcopy -O binary BLE_SerialPort_Master_Slave_Release.elf BLE_SerialPort_Master_Slave_Release.bin
	-@echo ' '

secondary-outputs: $(POST_BUILD_OBJCOPY) $(POST_BUILD_PRINT_SIZE)

.PHONY: all clean dependents
.SECONDARY: post-build

-include ../makefile.targets
